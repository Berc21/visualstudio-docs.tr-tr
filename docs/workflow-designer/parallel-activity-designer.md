---
title: "Paralel etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Parallel.UI
ms.assetid: 0306dc3b-075a-4091-ac3a-96486fbabed5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2d40a016631632ace52257d7086d4b1dca87520f
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="parallel-activity-designer"></a>Paralel etkinlik Tasarımcısı
<xref:System.Activities.Statements.Parallel> Etkinlik alt etkinlikler koleksiyonu eşzamanlı olarak yürütür.

## <a name="the-parallel-activity"></a>Paralel etkinlik
 <xref:System.Activities.Statements.Parallel> Etkinlik kendi alt etkinlikler depolayan bir <xref:System.Activities.Statements.Parallel.Branches%2A> koleksiyonu. Kullanım <xref:System.Activities.Statements.Parallel> yerine etkinlik <xref:System.Activities.Statements.Sequence> alt etkinliklerin bazıları boş giderseniz etkinlik.

 <xref:System.Activities.Statements.Parallel> Etkinliği olan bir <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> bir kullanıcı tarafından belirtilen içeren özelliği [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ifade. <xref:System.Activities.Statements.Parallel> Etkinlik her dal tamamlandıktan sonra bu özellik değerlendirir. Değerlendirilirse **True**, sonra <xref:System.Activities.Statements.Parallel> etkinlik tamamlandıktan dala çalıştırmadan. Varsa <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> için değerlendirmez **True**, sonra <xref:System.Activities.Statements.Parallel> tüm alt etkinliklerinin tamamlandığında etkinliği tamamlar.

### <a name="using-the-parallel-activity-designer"></a>Paralel etkinlik Tasarımcısı'nı kullanarak
 **Paralel** etkinlik Tasarımcısı bulunabilir **akış denetimi** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sol tarafındaki sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **Paralel** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlik tasarımcıları normalde yerleştirilir, örneğin, bir içinde**Dizisi** etkinlik Tasarımcısı. İçine bırakmadan sonra [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], oluşturduğu bir <xref:System.Activities.Statements.Parallel> içeren varsayılan etkinlik bir <xref:System.Activities.Activity.DisplayName%2A> , **paralel**

 Bir etkinlik eklemek için <xref:System.Activities.Statements.Parallel.Branches%2A> paralel etkinlik koleksiyonu sürükleyin bazı diğer etkinlik Tasarımcısı'ndan **araç** ve üçgen bırakın **paralel** etkinlik Tasarımcısı. Üçgenler dallarda etkinlikleri flank. Bu yordamı tekrarlayarak ek etkinlikler eklenebilir. Etkinlikler, bunların içinde bırakarak sıralanabilir **paralel** etkinlik Tasarımcısı.

### <a name="parallel-activity-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda paralel etkinlik özellikleri
 Aşağıdaki tabloda paralel etkinlik özelliklerini gösterir ve Tasarımcısı'nda nasıl kullanıldığını açıklar.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Etkinlik Tasarımcısı kolay görünen adını başlığı belirtir. Varsayılan değer **paralel**. Değer, isteğe bağlı olarak düzenlenebilir **özellikleri** ızgara veya doğrudan başlığındaki etkinlik Tasarımcısı.|
|<xref:System.Activities.Statements.Parallel.Branches%2A>|Doğru|Yürütülecek alt etkinlikler koleksiyonunu içerir.|
|<xref:System.Activities.Statements.Parallel.CompletionCondition%2A>|False|Bir dal tamamlandıktan sonra değerlendirilir. Değerlendirilirse **doğru**, ardından zamanlanmış dalları iptal edilir. Bu özellik ayarlı değil ya da değerlendiren **yanlış**, tüm alt etkinliklerinin tamamlandığında etkinliği tamamlar. Varsayılan değer **null**.|

## <a name="see-also"></a>Ayrıca bkz.

- [Sırası](../workflow-designer/sequence-activity-designer.md)
- [ParallelForEach\<T>](../workflow-designer/parallelforeach-t-activity-designer.md)
- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)