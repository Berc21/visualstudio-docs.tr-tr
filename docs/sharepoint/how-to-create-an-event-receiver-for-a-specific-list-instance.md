---
title: "Nasıl yapılır: belirli bir liste örneği için olay alıcı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, event receivers
- event receivers [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 66801e82f64e23ee24e66c63a62dd895c58389dc
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-an-event-receiver-for-a-specific-list-instance"></a>Nasıl yapılır: Belirli bir Liste Örneği için Olay Alıcı Oluşturma
  Bir liste örneği olay alıcısı herhangi bir örneğine listesi tanımını gerçekleşen olaylara yanıt verir. Olay alıcı şablonunu belirli listesi örneği hedefleme etkinleştirmez olsa da, belirli bir liste örneği olaylara yanıt için bir liste tanımı için kapsamlı bir olay alıcısı değiştirebilirsiniz.  
  
 Belirli bir liste örneği, olay alıcısı için Elements.xml de hedeflemek için yerini `ListTemplateId` ile `ListUrl` ve liste örneği URL'sini ekleyin.  
  
## <a name="creating-a-list-instance-event-receiver"></a>Bir liste örneği olay alıcı oluşturma  
 Aşağıdaki adımlar bir özel Duyurular listesi örneğinde gerçekleşen olaylara yanıt için bir liste öğesi olay alıcı değiştirme gösterir.  
  
#### <a name="to-modify-an-event-receiver-to-respond-to-a-specific-list-instance"></a>Belirli bir liste örneği için yanıtlamak için olay alıcı değiştirmek için  
  
1.  Bir tarayıcıda SharePoint sitesini açın.  
  
2.  Gezinti bölmesinde **listeler** bağlantı.  
  
3.  İçinde **tüm Site içeriğini** sayfasında, **oluşturma** bağlantı.  
  
4.  İçinde **oluşturma** iletişim kutusunda, seçin **duyuruları** yazın, duyuruyu ad **TestAnnouncements**ve ardından **oluşturma**düğmesi.  
  
5.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], bir olay alıcı projesi oluşturun.  
  
6.  İçinde **ne tür bir olay alıcısına istiyor musunuz?** listesinde, seçin **liste öğesi olayları**.  
  
    > [!NOTE]  
    >  Örneğin, bir liste tanımına kapsamları olay alıcısı herhangi bir diğer tür öğesini de seçebilirsiniz **listesi e-posta olayları** veya **liste iş akışı olayları**.  
  
7.  İçinde **öğesinin ne olay kaynağı olmalıdır?** listesinde, seçin **duyuruları**.  
  
8.  İçinde **aşağıdaki olayları işlemek** listesinde **öğeyi eklenen** onay kutusunu işaretleyin ve ardından **son** düğmesi.  
  
9. İçinde **Çözüm Gezgini**, EventReceiver1 altında Elements.xml açın.  
  
     Olay alıcısı şu anda aşağıdaki satırı kullanarak Duyurular listesi tanımını başvuruyor:  
  
    ```  
    <Receivers ListTemplateId="104">  
    ```  
  
     Bu satırı aşağıdaki metni değiştirin:  
  
    ```  
    <Receivers ListUrl="Lists/TestAnnouncements">  
    ```  
  
     Bu yeni gerçekleşen olaylara yanıt vermesi için olay alıcı yönlendirir **TestAnnouncements** oluşturduğunuz Duyurular listesi. Değiştirebileceğiniz `ListURL` SharePoint sunucusu üzerindeki herhangi bir liste örneğine başvuru özniteliği.  
  
10. İçin olay alıcı kod dosyasını açın ve ItemAdding yönteminde kesme noktası yerleştirin.  
  
11. Derleme ve çözümü çalıştırmak için F5 tuşuna seçin.  
  
12. SharePoint'te seçin **TestAnnouncements** Gezinti bölmesinde bağlantı.  
  
13. Seçin **Yeni duyuru Ekle** bağlantı.  
  
14. Duyuru için bir başlık girin ve ardından **kaydetmek** düğmesi.  
  
     Yeni öğe özel Duyurular listesine eklendiğinde, kesme noktası isabet dikkat edin.  
  
15. Devam etmek için F5 tuşuna seçin.  
  
16. Gezinti Bölmesi'nde seçin **listeler** bağlamak ve ardından **duyuruları** bağlantı.  
  
17. Yeni bir duyuru ekleyin.  
  
     Alıcı yalnızca özel duyuru listesi örneği olayları yanıt verecek şekilde yapılandırıldığından, olay alıcı üzerinde yeni bir duyuru tetiklemez bildirimi **TestAnnouncements**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: olay alıcısı oluşturma](../sharepoint/how-to-create-an-event-receiver.md)   
 [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  