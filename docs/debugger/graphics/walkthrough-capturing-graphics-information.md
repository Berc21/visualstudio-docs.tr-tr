---
title: "İzlenecek yol: Grafik bilgilerini yakalama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48f12f6e-57b4-48ec-a145-89fa71a42424
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 990385be9d9518826f764a59529a1cff61467506
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-capturing-graphics-information"></a>İzlenecek Yol: Grafik Bilgilerini Yakalama
Bu kılavuzda nasıl kullanılacağı ortaya [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] grafik Tanılama'yı el ile bir Direct3D uygulamasından grafik bilgilerini yakalama.  
  
 Bu kılavuzda bu görevler gösterilmektedir:  
  
-   Grafik tanılama uygulamanıza takma  
  
-   Graf bilgilerini yakalama  
  
## <a name="capturing-graphics-information"></a>Graf bilgilerini yakalama  
 Grafik tanılama araçları kullanmak için öncelikle kullanır. Grafik bilgilerini yakalama gerekir. Yakalama etkinleştirmek için **Başlat tanılama** başlatıldığında grafik tanılama uygulamanıza olanak komutu.  
  
#### <a name="to-enable-the-capture-of-graphics-information-after-a-project-or-solution-is-loaded"></a>Proje ya da çözüm sonra grafik bilgilerini yakalama etkinleştirmek için yüklenir  
  
1.  İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], grafik bilgilerini yakalama istediğiniz uygulama için bir proje veya çözüm dosyasını yükleyin.  
  
2.  Grafik tanılama araç çubuğunda seçin **Başlat tanılama**.  
  
#### <a name="to-enable-the-capture-of-graphics-information-without-loading-a-project-or-solution"></a>Proje ya da çözüm yüklemeden grafik bilgilerini yakalama etkinleştirmek için  
  
1.  Menü çubuğunda seçin **dosya**, **açık**, **proje/çözüm**. **Proje Aç** iletişim kutusu görüntülenir.  
  
2.  Yürütülebilir dosya, grafik bilgilerini yakalama ve ardından istediğiniz uygulama için bir proje veya çözüm dosyası yerine belirtin **açık**.  
  
3.  Menü çubuğunda seçin **hata ayıklama**, **grafik**, **Başlat tanılama**.  
  
 Uygulamayı başlatın ve işleme çerçeveler olduktan sonra grafik bilgilerini yakalayabilirsiniz.  
  
#### <a name="to-capture-graphics-information"></a>Grafik bilgilerini yakalama  
  
-   Grafik tanılama araç çubuğunda seçin **yakalama** düğmesi. ![Grafik yakalama düğme simgesi](media/debuggingdirectxgraphics.png "DebuggingDirectXGraphics")  
  
     veya  
  
     Odakta uygulamayla basın **Print Screen**.  
  
 Bir çerçeve bilgilerini yakalama her zaman grafik tanılama Direct3D olaylar ve ilişkili durumunu kaydeder ve bu verileri bir grafik günlüğüne ekler. Yeni bir grafik günlük her bir grafik Tanılama oturumu için oluşturulur. Grafik günlükleri hakkında daha fazla bilgi için bkz: [genel bakış](overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuzda grafik bilgilerini el ile yakalama gösterilmektedir. Sonraki adım olarak, bu seçenek göz önünde bulundurun:  
  
-   Grafik tanılama araçlarını kullanarak yakalanan grafik bilgilerini çözümlemeyi öğrenin. Bkz: [genel bakış](overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Grafik Bilgilerini Yakalama](capturing-graphics-information.md)