---
title: "Nasıl yapılır: sınıf diyagramlarını (Sınıf Tasarımcısı) özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class diagrams, customizing
- shapes, removing type from class diagrams
- type shapes, removing from class diagrams
- class diagrams, removing type shapes
ms.assetid: e9030aea-c77d-4cc1-b8f6-b6ca469b692d
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3a8ba9df137eebc999d1875d75b38c79ffcbff32
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-customize-class-diagrams-class-designer"></a>Nasıl Yapılır: Sınıf Diyagramlarını Özelleştirme (Sınıf Tasarımcısı)
Sınıf diyagramlarının bilgileri görüntüleme biçimini değiştirebilirsiniz. Tüm diyagramı veya tasarım yüzeyinde tek tek türleri özelleştirebilirsiniz.  
  
 Örneğin, tüm bir sınıf diyagramının yakınlaştırma seviyesini ayarlayabilir, tek tek üyelerin gruplandırılma ve sıralanma şeklini değiştirebilir, ilişkileri gizleyebilir ya da gösterebilir ve tek tek türleri ya da tür kümelerini diyagram üzerinde istediğiniz yere taşıyabilirsiniz.  
  
> [!NOTE]
>  Şekillerin diyagram üzerinde görünme biçimi özelleştirildiğinde, diyagramda temsil edilen türlerin temelini oluşturan kod değişmez.  
  
 Tür üyelerini içeren bölümlere (bir sınıf içindeki Özellikler bölümü gibi) bölmeler adı verilir. Tek tek bölmeleri ve tür üyelerini gizleyebilir veya gösterebilirsiniz.  
  
 **Bu konudaki**  
  
-   [Sınıf diyagramında ve Yakınlaştır](../ide/how-to-customize-class-diagrams-class-designer.md#ZoomInOut)  
  
-   [Gruplandırma ve türü üyeleri sıralama özelleştirme](../ide/how-to-customize-class-diagrams-class-designer.md#CustomizeGroupingSorting)  
  
-   [Bir türdeki bölmeler Gizle](../ide/how-to-customize-class-diagrams-class-designer.md#HideCompartments)  
  
-   [Bir türdeki tek tek üyeleri Gizle](../ide/how-to-customize-class-diagrams-class-designer.md#HideMembers)  
  
-   [Bir türde gizli bölmeler ve üyeleri Göster](../ide/how-to-customize-class-diagrams-class-designer.md#DisplayHiddenCompartmentsAndMemberrs)  
  
-   [İlişkileri Gizle](../ide/how-to-customize-class-diagrams-class-designer.md#HideAssociationAndInheritance)  
  
-   [Gizli ilişkileri göster](../ide/how-to-customize-class-diagrams-class-designer.md#DisplayAssociationAndInheritance)  
  
-   [Bir şekli bir sınıf diyagramdan Kaldır](../ide/how-to-customize-class-diagrams-class-designer.md#RemoveCodeAndShape)  
  
-   [Türü şekli ve arka plandaki kod silme](../ide/how-to-customize-class-diagrams-class-designer.md#DeleteTypeShapeAndCode)  
  
##  <a name="ZoomInOut"></a>Sınıf diyagramında ve Yakınlaştır  
  
1.  Sınıf Tasarımcısı'nda bir sınıf diyagramı dosyasını açın ve seçin.  
  
2.  Sınıf Tasarımcısı araç çubuğunda tıklatın **Yakınlaştır** veya **Uzaklaştır** Tasarımcı yüzeyine yakınlaştırma düzeyini değiştirmek için düğmesi.  
  
     veya  
  
     Belirli bir yakınlaştırma değeri belirtin. Kullanabileceğiniz **yakınlaştırma** açılan liste veya geçerli yakınlaştırma düzeyini yazın (geçerli aralık: % %10 400 arasında).  
  
    > [!NOTE]
    >  Yakınlaştırma seviyesinin değiştirilmesi sınıf diyagramı çıktınızın ölçeğini etkilemez.  
  
##  <a name="CustomizeGroupingSorting"></a>Gruplandırma ve türü üyeleri sıralama özelleştirme  
  
1.  Sınıf Tasarımcısı'nda bir sınıf diyagramı dosyasını açın ve seçin.  
  
2.  Tasarım yüzeyine boş bir alana sağ tıklayın ve fareyle **Grup üyeleri**.  
  
3.  Kullanılabilir seçeneklerden birini belirtin:  
  
    1.  **Grup türü tarafından** tek tek tür üyeleri özellikleri, yöntemleri, olayları ve alanları gruplandırılmış liste halinde ayırır. Tek tek gruplar varlıklar tanımına göre değişir: Örneğin, bir sınıf için henüz hiç tanımlı olay yoksa, bu sınıf olaylar grubunu görüntülemez.  
  
    2.  **Erişim grupla** tek tek tür üyeleri gruplandırılmış listesine göre üyenin üzerinde ayırır erişim değiştiricileri. Örneğin, Genel ve Özel.  
  
    3.  **Alfabetik olarak sıralamak** öğeleri, bir varlığın tek alfabetik listesi olarak oluşturan gösterir. Liste artan düzende sıralanır.  
  
##  <a name="HideCompartments"></a>Bir türdeki bölmeler Gizle  
  
1.  Sınıf tasarımcısında bir sınıf diyagramı dosyasını açın ve seçin.  
  
2.  Özelleştirmek istediğiniz türündeki üye kategori sağ tıklayın (örneğin, seçin **yöntemleri** bir sınıf düğümünde.  
  
3.  Tıklatın **Gizle bölme**.  
  
     Seçili bölme tür kapsayıcısından kaybolur.  
  
##  <a name="HideMembers"></a>Bir türdeki tek tek üyeleri Gizle  
  
1.  Sınıf Tasarımcısı'nda bir sınıf diyagramı dosyasını açın ve seçin.  
  
2.  Gizlemek istediğiniz türde üyeye sağ tıklayın.  
  
3.  Tıklatın **Gizle**.  
  
     Seçili üye tür kapsayıcısından kaybolur.  
  
##  <a name="DisplayHiddenCompartmentsAndMemberrs"></a>Bir türde gizli bölmeler ve üyeleri Göster  
  
1.  Sınıf Tasarımcısı'nda bir sınıf diyagramı dosyasını açın ve seçin.  
  
2.  Gizli bölmeyi içeren türün adına sağ tıklayın.  
  
3.  Tıklatın **tüm üyeleri Göster**.  
  
     Tüm gizli bölmeler ve üyeler tür kapsayıcısında görünür.  
  
##  <a name="HideAssociationAndInheritance"></a>İlişkileri Gizle  
  
1.  Sınıf Tasarımcısı'nda bir sınıf diyagramı dosyasını açın ve seçin.  
  
2.  Gizlemek istediğiniz ilişkilendirme veya devralma çizgisine sağ tıklayın.  
  
3.  Tıklatın **Gizle** ilişkilendirme satırları ve tıklatın **devralma satırı gizlemek** devralma satırlar için.  
  
4.  Tıklatın **tüm üyeleri Göster**.  
  
     Tüm gizli bölmeler ve üyeler tür kapsayıcısında görünür.  
  
##  <a name="DisplayAssociationAndInheritance"></a>Gizli ilişkileri göster  
  
1.  Sınıf Tasarımcısı'nda bir sınıf diyagramı dosyasını açın ve seçin.  
  
2.  Gizli ilişkilendirmeyi veya devralmayı içeren türün adına sağ tıklayın.  
  
 Tıklatın **tüm üyeleri Göster** ilişkilendirme satırları ve tıklatın **Göster temel sınıf** veya **türetilmiş sınıfları Göster** devralma satırlar için.  
  
##  <a name="RemoveCodeAndShape"></a>Bir şekli bir sınıf diyagramdan Kaldır  
 Türün temelini oluşturan koda etkisi olmaksızın, bir tür şeklini sınıf diyagramından kaldırabilirsiniz. Tür şekillerinin bir sınıf diyagramından kaldırılması yalnızca o diyagramı etkiler: Türü tanımlayan temel kod ve türü görüntüleyen diğer diyagramlar bundan etkilenmez.  
  
1.  Sınıf diyagramında, diyagramdan kaldırmak istediğiniz tür şeklini seçin.  
  
2.  Üzerinde **Düzenle** menüsünde seçin **diyagramdan Kaldır**.  
  
     Tür şekli ve varsa bu şekle bağlı ilişkilendirme ya da devralma çizgileri bundan böyle diyagramda görünmez.  
  
##  <a name="DeleteTypeShapeAndCode"></a>Türü şekli ve arka plandaki kod silme  
  
1.  Tasarım yüzeyinde şekle sağ tıklayın.  
  
2.  Seçin **Sil kod** ve bağlam menüsünden.  
  
     Şekil diyagramdan kaldırılır ve temelini oluşturan kod projeden silinir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıf diyagramları (Sınıf Tasarımcısı) ile çalışma](../ide/working-with-class-diagrams-class-designer.md)   
 [Nasıl yapılır: üye gösterimi ile ilişkilendirme gösterimi (Sınıf Tasarımcısı) arasındaki Değiştir](../ide/how-to-change-between-member-notation-and-association-notation-class-designer.md)   
 [Nasıl yapılır: Varolan türleri (Sınıf Tasarımcısı) görüntüleme](../ide/how-to-view-existing-types-class-designer.md)   
 [Görüntüleme türleri ve ilişkileri (Sınıf Tasarımcısı)](../ide/viewing-types-and-relationships-class-designer.md)