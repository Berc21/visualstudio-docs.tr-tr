---
title: "Nasıl yapılır: sınıflar için doğrulama ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 61107da9-7fa3-4dba-b101-ae46536f52c4
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 1ff8eb04ae9b5009aff13dc8588633b34d4d72dd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-validation-to-entity-classes"></a>Nasıl yapılır: sınıflar için doğrulama ekleme
*Doğrulama* varlık sınıfı olan bir nesnenin şeması ve ayrıca uygulama için oluşturulan kuralları kısıtlamaları veri nesneleri girdiğiniz değerleri uyması onaylama işlemi. Temel alınan veritabanı güncelleştirme göndermeden önce verileri doğrulama hataları azaltan iyi bir uygulamadır. Ayrıca, olası bir uygulama ve veritabanı arasındaki gidiş dönüş sayısını azaltır.  
  
 [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md) ekler, güncelleştirmeleri sırasında çalışan ve tüm varlıkların ve ayrıca sırasında ve sonrasında tek sütun siler Tasarımcısı ile oluşturulan kodun genişletmek kullanıcıların kısmi yöntemler sağlar değiştirir.  
  
> [!NOTE]
>  Bu konuda kullanarak sınıflar için doğrulama eklemek için temel adımlar sağlanmaktadır [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Belirli bir varlık sınıfı için başvuran olmadan aşağıdaki genel adımları izleyin zor olabilir çünkü gerçek veri kullanan bir kılavuz sağlanmıştır.  
  
## <a name="adding-validation-for-changes-to-the-value-in-a-specific-column"></a>Belirli bir sütunun değeri değişiklikleri için doğrulama ekleme  
 Bu yordamda, bir sütundaki değeri değiştiğinde veri doğrulama gösterilmiştir. Sınıf tanımı içinde doğrulamanın olduğundan (yerine kullanıcı arabiriminde) değeri doğrulama başarısız olmasına neden olursa özel durum oluşur. Hata sütun değerlerini değiştirmeye çalışırsa, uygulamanızdaki kod için işleme uygulayın.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-validate-data-during-a-columns-value-change"></a>Bir sütunun değeri değişikliği sırasında verileri doğrulamak için  
  
1.  Açın veya yeni bir LINQ to SQL sınıfları dosyası oluşturun (**.dbml** dosyası) içinde [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. (Çift **.dbml** dosyasını **Çözüm Gezgini**.)  
  
2.  O/R Tasarımcısı'nda doğrulama ekleyin ve ardından istediğiniz sınıfı sağ **görünümü kodu**.  
  
     Seçilen varlık sınıfı için bir parçalı sınıf ile Kod Düzenleyicisi açılır.  
  
3.  İmleci kısmi sınıfında yerleştirin.  
  
4.  Visual Basic projeleri için:  
  
    1.  Genişletme **yöntem adı** listesi.  
  
    2.  Bulun **OnCOLUMNNAMEChanging** doğrulama eklemek istediğiniz sütun için yöntem.  
  
    3.  Bir `OnCOLUMNNAMEChanging` yöntemi sınıfa eklenir.  
  
    4.  İlk girilen değer ve ardından sütunu için girilen değer emin olmak için uygulamanız için kabul edilebilir olduğunu doğrulamak için aşağıdaki kodu ekleyin. `value` Bağımsız değişkeni önerilen değer içeriyor, bu nedenle geçerli bir değer olduğunu onaylamak için mantık ekleyin:  
  
        ```vb  
        If value.HasValue Then  
            ' Add code to ensure that the value is acceptable.  
            ' If value < 1 Then  
            '    Throw New Exception("Invalid data!")  
            ' End If  
        End If  
        ```  
  
    C# projeleri için:  
  
    C# projeleri olay işleyicileri otomatik olarak oluşturmaz olduğundan, sütunu değiştirme kısmi yöntemler oluşturmak için IntelliSense kullanabilirsiniz. Tür `partial` ve ardından kullanılabilir kısmi yöntemlerin listesi erişim alanı. Doğrulama için eklemek istediğiniz sütun için sütun değiştirme yöntemi tıklatın. Aşağıdaki kod, sütunu değiştirme kısmi yöntemi seçtiğinizde, oluşturulan kod benzer:  
  
    ```csharp  
    partial void OnCOLUMNNAMEChanging(COLUMNDATATYPE value)  
        {  
           throw new System.NotImplementedException();  
        }  
    ```  
  
## <a name="adding-validation-for-updates-to-an-entity-class"></a>Bir varlık sınıfı için güncelleştirmeleri için doğrulama ekleme  
 Değerleri değişiklikleri sırasında denetlemin yanı sıra, tam varlık sınıfı güncelleştirmek için girişiminde bulunulduğunda veri da doğrulayabilirsiniz. Doğrulama güncelleştirme girişimi sırasında iş kurallarını bu gerekiyorsa birden çok sütun değerleri karşılaştırmanızı sağlar. Aşağıdaki yordamda, bir tam varlık sınıfı güncelleştirmek için bir girişimde zamanı doğrulamak gösterilmiştir.  
  
> [!NOTE]
>  Doğrulama kodu güncelleştirmelerin sınıflar tamamlamak kısmi yürütüldüğünde <xref:System.Data.Linq.DataContext> sınıfı (yerine belirli bir varlık sınıfı kısmi sınıfındaki).  
  
#### <a name="to-validate-data-during-an-update-to-an-entity-class"></a>Bir varlık sınıfı için bir güncelleştirme sırasında verileri doğrulamak için  
  
1.  Açın veya yeni bir LINQ to SQL sınıfları dosyası oluşturun (**.dbml** dosyası) içinde [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. (Çift **.dbml** dosyasını **Çözüm Gezgini**.)  
  
2.  O/R Tasarımcısı üzerinde boş bir alana sağ tıklatın ve **görünümü kodu**.  
  
     Kod Düzenleyicisi için bir parçalı sınıf açılır `DataContext`.  
  
3.  Kısmi sınıfı için imleci yerleştirin `DataContext`.  
  
4.  Visual Basic projeleri için:  
  
    1.  Genişletme **yöntem adı** listesi.  
  
    2.  Tıklatın **UpdateENTITYCLASSNAME**.  
  
    3.  Bir `UpdateENTITYCLASSNAME` yöntemi sınıfa eklenir.  
  
    4.  Tek tek sütun değerlerini kullanarak erişim `instance` aşağıdaki kodda gösterildiği gibi bir bağımsız değişken:  
  
        ```vb  
        If (instance.COLUMNNAME = x) And (instance.COLUMNNAME = y) Then  
            Dim ErrorMessage As String = "Invalid data!"  
            Throw New Exception(ErrorMessage)  
        End If  
        ```  
  
    C# projeleri için:  
  
    C# projeleri olay işleyicileri otomatik olarak oluşturmaz olduğundan, IntelliSense kısmi oluşturmak için kullanabileceğiniz `UpdateCLASSNAME` yöntemi. Tür `partial` ve ardından kullanılabilir kısmi yöntemlerin listesi erişim alanı. Doğrulama için eklemek istediğiniz sınıfı için güncelleştirme yöntemini tıklatın. Aşağıdaki kod seçtiğinizde oluşturulan kodu benzer bir `UpdateCLASSNAME` kısmi yöntemi:  
  
    ```csharp  
    partial void UpdateCLASSNAME(CLASSNAME instance)  
    {  
        if ((instance.COLUMNNAME == x) && (instance.COLUMNNAME = y))  
        {  
            string ErrorMessage = "Invalid data!";  
            throw new System.Exception(ErrorMessage);  
        }  
    }  
    ```  
  
## <a name="see-also"></a>Ayrıca bkz.
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[Verileri doğrulama](../data-tools/validate-data-in-datasets.md)  
[LINQ-SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)  