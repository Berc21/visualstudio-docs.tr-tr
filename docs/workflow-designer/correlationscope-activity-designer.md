---
title: "CorrelationScope etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.CorrelationScope.UI
ms.assetid: 75f20664-9042-464d-8e2b-148d365a2286
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3a8798e653148e07baff5f0fb70c2ff56f7d4a16
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="correlationscope-activity-designer"></a>CorrelationScope etkinlik Tasarımcısı
**CorrelationScope** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.ServiceModel.Activities.CorrelationScope> kullanarak alt Mesajlaşma etkinlikleri örtük yönetim sağlar etkinliği bir <xref:System.ServiceModel.Activities.CorrelationHandle> nesnesi.

## <a name="the-correlationscope-activity"></a>CorrelationScope etkinliği
 <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> Özellik belirtir <xref:System.ServiceModel.Activities.CorrelationHandle> alt Mesajlaşma etkinlikleri yönetmek için kullanılır. <xref:System.ServiceModel.Activities.Send> Ve <xref:System.ServiceModel.Activities.Receive> içinde yer alan aktiviteler <xref:System.ServiceModel.Activities.CorrelationScope.Body%2A> kullanmak üzere yapılandırılmış <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> içeren özelliğini <xref:System.ServiceModel.Activities.CorrelationScope> bağıntı gerçekleştirme etkinliği.

### <a name="using-the-correlationscope-activity-designer"></a>CorrelationScope etkinlik Tasarımcısı'nı kullanarak
 **CorrelationScope** etkinlik Tasarımcısı bulunabilir **ileti** kategorisini **araç**, hangi tıklayarak erişildiğinde **araçkutusu** sol tarafındaki sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **CorrelationScope** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini. Bu oluşturur bir <xref:System.ServiceModel.Activities.CorrelationScope> varsayılan etkinlik **DisplayName** CorrelationScope biri. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **CorrelationScope** etkinlik Tasarımcısı veya **DisplayName** kutusunun **özellikleri** penceresi.

 Belirtmek için <xref:System.ServiceModel.Activities.CorrelationHandle> Mesajlaşma etkinlikleri alt tarafından kullanılan, yanındaki üç nokta düğmesini tıklatın **CorrelatesWith** alanındaki **özellikleri** görüntülemek için penceresi **ifade Düzenleyicisi**  iletişim kutusu. Bu özellik ayrıca etkinlik Tasarımcı yüzeyine ayarlayabilirsiniz.

 İçinde kendi tasarımcıları bırakarak içinde bağıntı kapsamlı etkinlikleri belirtilen **gövde** içinde kutusunda **CorrelationScope** Tasarımcısı.

### <a name="the-correlationscope-properties"></a>CorrelationScope özellikleri
 Aşağıdaki tabloda <xref:System.ServiceModel.Activities.CorrelationScope> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler olabilir ya da düzenlenen **özellikleri** penceresi veya [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Tasarımcısı yüzey ve genellikle her ikisinde de.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.ServiceModel.Activities.InitializeCorrelation> etkinlik.|
|<xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A>|False|Belirtir <xref:System.ServiceModel.Activities.CorrelationHandle> alt Mesajlaşma etkinlikleri yönetmek için kullanılır. Bu özellik ayarlamazsanız <xref:System.ServiceModel.Activities.CorrelationScope> örtülü oluşturur <xref:System.ServiceModel.Activities.CorrelationHandle> otomatik olarak.|
|<xref:System.ServiceModel.Activities.CorrelationScope.Body%2A>|False|Bağıntı kapsamı içindeki etkinlikleri belirtir.|

## <a name="see-also"></a>Ayrıca bkz.

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Alma](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Gönder](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)