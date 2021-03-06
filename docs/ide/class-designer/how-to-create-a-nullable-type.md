---
title: "Nasıl yapılır: boş değer atanabilir bir tür (Sınıf Tasarımcısı) oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- nullable types, Class Designer
- Class Designer [Visual Studio], nullable types
ms.assetid: 84673a89-3f6d-4668-919e-1c0f56182fe5
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: fcef9fc80bbc55b07cd9dad68e217c9982a3b1f7
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-create-a-nullable-type-class-designer"></a>Nasıl Yapılır: Boş Değer Atanabilir Tür Oluşturma (Sınıf Tasarımcısı)
Belirli değer türleri her zaman sahip (gereksinim tanımlı bir değer veya). Bu ortak veritabanlarında olduğu bazı alanlar herhangi bir değer atanabilir olmayan uygulamadır. Örneğin, bir null değer, henüz bir değer atanmadı olduğunu belirtmek için bir veritabanı alanı atayabilirsiniz.  
  
A *boş değer atanabilir tür* genişletir ve böylece bu tür ve ayrıca bir null değer için değerleri tipik aralığı alır bir değer türü değil. Örneğin, bir boş değer atanabilir, `Int32`, boş değer atanabilir olarak da başlar\<Int32 > -2147483648 2147483647 için herhangi bir değer atanabilir veya bir null değer atanabilir. Bir null atanabilir\<bool > değerler atanabilir `True`, `False`, ya da null (hiçbir değer hiç).  
  
Boş değer atanabilir türler örnekleridir <xref:System.Nullable%601> yapısı. İki ortak salt okunur özellikler, her bir boş değer atanabilir tür örneğine sahip `HasValue` ve `Value`:  
  
-   `HasValue`tür `bool` ve değişken tanımlı bir değer içerip içermediğini belirtir. `True`değişkeni boş olmayan bir değer içeren anlamına gelir. Bir deyimi kullanarak için tanımlanmış bir değer sınayabilirsiniz `if (x.HasValue)` veya `if (y != null)`.  
  
-   `Value`temel alınan türü olarak aynı türde değil. Varsa `HasValue` olan `True`, `Value` anlamlı bir değer içeriyor. Varsa `HasValue` olan `False`, erişilirken `Value` geçersiz işlemi özel durum oluşturur.  
  
Bir değişken null olabilir bir tür olarak bildirirken varsayılan olarak, bu tanımlanmış değeri yok (`HasValue` olan `False`), temel alınan değer türü varsayılan değerini diğer.  
  
Sınıf Tasarımcısı, temel alınan türü görüntülediği null atanabilir bir tür görüntüler.  
  
C# boş değer atanabilir türler hakkında daha fazla bilgi için bkz: [boş değer atanabilir türler](/dotnet/csharp/programming-guide/nullable-types/index). Visual Basic'te boş değer atanabilir türler hakkında daha fazla bilgi için bkz: [boş değer atanabilir değer türlerinin](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types).  
  
[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-add-a-nullable-type-by-using-the-class-designer"></a>Sınıf Tasarımcısı kullanarak null atanabilir bir tür eklemek için  
  
1.  Sınıf diyagramında, varolan bir sınıfa genişletin veya yeni bir sınıf oluşturun.  
  
2.  Proje için bir sınıf eklemek için **sınıf diyagramı** menüsünde tıklatın **Ekle**ve ardından **sınıfı Ekle**.  
  
3.  Sınıf şekli üzerinde genişletmek için **sınıf diyagramı** menüsünde tıklatın **genişletme**.  
  
4.  Sınıf şekli seçin. Üzerinde **sınıf diyagramı** menüsünde tıklatın **Ekle**ve ardından **alan**. Varsayılan adına sahip yeni bir alan **alan** sınıfı şekli ve de görünür **sınıfı ayrıntıları** penceresi.  
  
5.  İçinde **adı** sütunu **sınıfı ayrıntıları** penceresi (veya sınıfında kendisini Şekil), geçerli ve anlamlı bir adla yeni alanın adını değiştirin.  
  
6.  İçinde **türü** sütunu **sınıfı ayrıntıları** penceresinde, aşağıdaki kodda gösterildiği gibi türü null olabilir bir tür bildirin:  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
### <a name="to-add-a-nullable-type-by-using-the-code-editor"></a>Kod Düzenleyicisi'ni kullanarak null atanabilir bir tür eklemek için  
  
1.  Bir sınıf projeye ekleyin. Proje düğümünde seçin **Çözüm Gezgini**ve **proje** menüsünde tıklatın **sınıfı Ekle**.  
  
2.  Yeni sınıf .cs veya .vb dosyasında bir veya daha fazla boş değer atanabilir türler Yeni sınıfta sınıf bildirimi ekleyin.  
  
3.  Sınıf görünümünden yeni sınıf simgesi Sınıf Tasarımcısı tasarım yüzeyine sürükleyin. Bir sınıf şekli sınıf diyagramında görünür.  
  
4.  Sınıf şekil ayrıntılarını genişletin ve fare işaretçisini sınıfı üyeleri taşınır. Araç İpucu her üye bildirimi görüntülenir.  
  
5.  Sınıf şekli sağ tıklatın ve **sınıfı ayrıntıları**. Görüntülemek veya yeni tür özelliklerini değiştirmek için **sınıfı ayrıntıları** penceresi.  
  
## <a name="see-alose"></a>Alose bakın
<xref:System.Nullable%601>   
[Boş değer atanabilir türler](/dotnet/csharp/programming-guide/nullable-types/index)   
[Boş değer atanabilir türleri kullanma](/dotnet/csharp/programming-guide/nullable-types/using-nullable-types)   
[Nasıl yapılır: boş değer atanabilir bir tür belirleme](/dotnet/csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type)   
[Boş Değer Atanabilen Değer Türleri](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)