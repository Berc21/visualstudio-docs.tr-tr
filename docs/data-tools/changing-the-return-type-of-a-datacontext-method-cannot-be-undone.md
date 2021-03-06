---
title: "DataContext yöntemin dönüş türünü değiştirme alınamaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76b161fc-5075-4192-8d94-f15b02e199e9
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: e28cf13486e21564c4acdf62e3edc89321a4f1b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="changing-the-return-type-of-a-datacontext-method-cannot-be-undone"></a>DataContext yöntemin dönüş türünü değiştirme alınamaz
DataContext yöntemin dönüş türünü değiştirme işlemi geri alınamaz. Otomatik olarak oluşturulan türüne dönmek için öğe Gezgini'nden Sunucu Gezgini/veritabanı O/R Tasarımcısı üzerine yeniden sürükleyin gerekir. Dönüş türü değiştirmek istediğinizden emin misiniz?  
  
Dönüş türü bir <xref:System.Data.Linq.DataContext> yöntemi farklı öğe burada, bırak bağlı olarak [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Bir öğenin varolan bir varlık sınıfı doğrudan üzerine bırakın, bir <xref:System.Data.Linq.DataContext> varlık sınıfı dönüş türüne sahip yöntemi oluşturulur. Boş bir alanı bir öğe bırakma durumunda [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], <xref:System.Data.Linq.DataContext> otomatik olarak oluşturulan bir tür döndüren yöntem oluşturulur. Dönüş türünü değiştirebilirsiniz bir <xref:System.Data.Linq.DataContext> yöntemleri bölmesine ekledikten sonra yöntemi. İnceleme veya dönüş türünü değiştirmek için bir <xref:System.Data.Linq.DataContext> yöntemi seçin ve **dönüş türü** özelliğinde **özellikleri** penceresi.  
  
### <a name="to-change-the-return-type-of-a-datacontext"></a>Bir DataContext dönüş türünü değiştirmek için  
  
-   **Evet**'i tıklayın.  
  
### <a name="to-exit-the-message-box-and-leave-the-return-type-unchanged"></a>İleti kutusu çıkmak ve dönüş türü değiştirmeden bırakmak için  
  
-   **Hayır**'a tıklayın.  
  
### <a name="to-revert-to-the-original-return-type-after-changing-the-return-type"></a>Dönüş türü değiştirdikten sonra özgün dönüş türü döndürmek için  
  
1.  Seçin <xref:System.Data.Linq.DataContext> yöntemi [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] ve silin.  
  
2.  Öğesinde bulun **Sunucu Gezgini/veritabanı Gezgini** ve sürüklediğinizde [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
    A <xref:System.Data.Linq.DataContext> yöntemi, özgün varsayılan dönüş türüyle oluşturulur.  
  
## <a name="see-also"></a>Ayrıca bkz.
[O/R Tasarımcısı iletileri](../data-tools/o-r-designer-messages.md)  
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)