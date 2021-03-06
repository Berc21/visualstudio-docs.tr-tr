---
title: "Nasıl yapılır: bir WCF iş akışı hizmeti uygulaması oluşturma | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 12d675ac-27d8-4d86-ba16-6f7688f8c841
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 03c7aed27c4dc092a1cf4d8ba51a10a4aac0741b
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-create-a-wcf-workflow-service-application"></a>Nasıl yapılır: bir WCF iş akışı hizmeti uygulaması oluştur

[!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] İş akışı hizmeti iletileri işlem sınırlarındaki istemciler ve kendilerini arasında iletmek dağıtılmış iletişim hizmetleri uygulamalardır. Hizmet tarafı hizmet sözleşmesini uygulama bildirimli olarak iş akışı etkinlikleri yoluyla yapılır [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] eski iş akışı hizmetleri .NET Framework 3.5 için benzer bir şekilde.

### <a name="to-create-a-wcf-workflow-service-application"></a>Bir WCF iş akışı hizmeti uygulaması oluşturmak için

1.  Başlat [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje...** .

     **Yeni proje** iletişim kutusu açılır.

3.  İçinde **yüklü şablonlar** bölmesinde, **WCF** veya **iş akışı** da **Visual C#** veya **Visual Basic** seçim dilinin bağlı olarak gruplandırmaları.

4.  Orta bölmede seçin **WCF iş akışı hizmeti uygulaması**.

5.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.

6.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.

7.  İçinde **çözüm** kutusunda, yeni bir çözüm oluşturmak ve ardından seçin **Tamam**.

    > [!NOTE]
    > Varolan bir çözümü bir iş akışı konsol uygulama eklemek istiyorsanız, bu çözümde açmak [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], çözüme sağ tıklayın **Çözüm Gezgini**seçip **Ekle**, ardından  **Yeni proje...**  açmak için **yeni proje** iletişim kutusu. Bu yordamda yukarıda açıklandığı gibi devam edin.

8.  Proje şablonu bir hizmet tanımı XAML olarak oluşturur. Windows iş akışı Tasarımcısı ile Tasarım görünümüne açılır bir <xref:System.Activities.Statements.Sequence> içeren bir dizi etkinlik <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply> etkinlikler.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: Etkinlik Oluşturma](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)
- [İş Akışı Projesi Oluşturma](../workflow-designer/creating-a-workflow-project.md)