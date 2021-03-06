---
title: "InitializeCorrelation etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.InitializeCorrelation.UI
ms.assetid: 4c54f34c-ee84-42a6-abb0-ec260c1ccb76
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f6f39f25e7a4cf589b43fcf3b3f84b9784241961
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="initializecorrelation-activity-designer"></a>InitializeCorrelation etkinlik Tasarımcısı
**InitializeCorrelation** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.ServiceModel.Activities.InitializeCorrelation> ileti gönderirken ya da bunları alırken önce arasında bir bağlantı kurmak için kullanılan etkinlik.

## <a name="the-initializecorrelation-activity"></a>InitializeCorrelation etkinliği
 Bir <xref:System.ServiceModel.Activities.InitializeCorrelation> etkinlik bağıntıları gönderme veya bir ileti alma olmadan başlatmak için kullanılır. Genellikle bağıntı gönderirken ya da bir mesaj alarak başlatılır. Bir ileti gönderilen veya alınan önce bağıntı kurulmalıdır kullanırsanız <xref:System.ServiceModel.Activities.InitializeCorrelation> bağıntı başlatılamadı.

### <a name="using-the-initializecorrelation-activity-designer"></a>InitializeCorrelation etkinlik Tasarımcısı'nı kullanarak
 **InitializeCorrelation** etkinlik Tasarımcısı bulunabilir **ileti** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç kutusu**  sekmesi [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **InitializeCorrelation** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini. Bu oluşturur bir <xref:System.ServiceModel.Activities.InitializeCorrelation> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> InitializeCorrelation.The, <xref:System.Activities.Activity.DisplayName%2A> üstbilgisinde düzenlenebilir **InitializeCorrelation** etkinlik Tasarımcısı veya  **DisplayName** kutusunun **özellikleri** penceresi.

 <xref:System.ServiceModel.Activities.CorrelationHandle> Olabilir belirtir **bağıntı** alanındaki **özellikleri** penceresinde **InitializeCorrelation** etkinlik Tasarımcı yüzeyine.

 Üç nokta düğmesini yanı sıra **CorrelationData** alanındaki **özellikleri** penceresi veya "Görünümü..." İpucu metni **InitializeCorrelation** etkinlik Tasarımcısı Yüzey görüntüler **başlatma bağıntı** iletişim kutusu içinde belirtebilirsiniz bağıntı işleyici ve bunu başlatmak için kullanılan anahtar-değer çiftleri. Bu iletişim kutusunu kullanma hakkında daha fazla bilgi için bkz: [türü koleksiyon Düzenleyicisi iletişim kutusu](../workflow-designer/type-collection-editor-dialog-box.md) konu.

### <a name="the-initializecorrelation-properties"></a>InitializeCorrelation özellikleri
 Aşağıdaki tabloda <xref:System.ServiceModel.Activities.InitializeCorrelation> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri düzenlenebilecek **özellikleri** penceresi veya [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.ServiceModel.Activities.InitializeCorrelation> etkinlik. InitializeCorrelation varsayılan değerdir.<br /><br /> Ancak kolay için varsayılan olmayan bir değer kullanımını <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil gibi bir değer kullanmak için en iyi bir uygulamadır.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.Correlation%2A>|False|<xref:System.ServiceModel.Activities.CorrelationHandle> Bağıntı iş akışı etkinlikleri ilişkilendirmek için kullanılır.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>|False|İletileri iş akışı örneği ile ilişkilendirir bağıntı veri sözlüğü.<br /><br /> Kullanım **başlatma bağıntı** yapılandırmak için iletişim kutusunu <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>. Kullanımı hakkında daha fazla bilgi için bu iletişim kutusunu bkz [türü koleksiyon Düzenleyicisi iletişim kutusu](../workflow-designer/type-collection-editor-dialog-box.md) konu.|

## <a name="see-also"></a>Ayrıca bkz.

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [Alma](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Gönder](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)