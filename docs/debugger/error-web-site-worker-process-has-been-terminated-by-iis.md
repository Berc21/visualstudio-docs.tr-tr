---
title: "Hata: Web sitesi çalışan işlemi IIS tarafından sonlandırıldı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.web_server_process_terminated
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: fb7a0220cf6650aeeb12ec6549d112a39918de3f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-web-site-worker-process-has-been-terminated-by-iis"></a>Hata: Web sitesi çalışan işlemi IIS tarafından sonlandırıldı
Hata ayıklayıcı Web sitesinde kodu yürütme durduruldu. Bu, Internet Information Services'ın (IIS) çalışan işlem yanıt durmuş varsaymak neden oldu. Bu nedenle, IIS çalışan işlemi sona erdirildi.  
  
 Hata ayıklamak devam etmek için IIS çalışan işlemi devam etmek izin verecek şekilde yapılandırmanız gerekir. Bu hata iletisi, IIS 7'den önceki IIS sürümleriyle görünmez.  
  
### <a name="to-configure-iis-7-to-allow-the-worker-process-to-continue"></a>IIS 7'yi devam etmek çalışan işlemi izin verecek şekilde yapılandırmak için  
  
1.  Açık **Yönetimsel Araçlar** penceresi.  
  
    1.  Tıklatın **Başlat**ve ardından **Denetim Masası**.  
  
    2.  İçinde **Denetim Masası**, seçin **Klasik Görünüm'e geçiş**gerekirse, çift tıklayın ve ardından **Yönetimsel Araçlar**.  
  
2.  İçinde **Yönetimsel Araçlar** penceresinde çift **Internet Information Services (IIS) Yöneticisi'ni**.  
  
     IIS Yöneticisi'ni açar.  
  
3.  İçinde **bağlantıları** bölmesinde genişletin \<bilgisayar adı > düğümü gerekiyorsa.  
  
4.  Altında \<bilgisayar adı > düğümü tıklatın **uygulama havuzları**.  
  
5.  İçinde **uygulama havuzları** listesinde, uygulamanızın çalıştığı havuzunun adını sağ tıklatın ve ardından **Gelişmiş ayarları**.  
  
6.  İçinde **Gelişmiş ayarları** iletişim kutusunda, bulun **işlem modeli** bölümünde ve aşağıdaki eylemlerden birini gerçekleştirin:  
  
    -   Ayarlama **Ping etkinleştirilmiş** için **False**.  
  
    -   Ayarlama **Ping en büyük yanıt süresi** 90 saniyeden daha büyük bir değer.  
  
     Ayarı **Ping etkinleştirilmiş** için **False** IIS çalışan işlemi hala çalışıyor ve hata ayıklaması işleminizi durduruncaya kadar çalışan işlem etkin tutar denetlemesini durdurur. Ayarı **Ping en büyük yanıt süresi** IIS çalışan işlemi izlemeye devam etmek için büyük bir değere izin verir.  
  
7.  Tıklatın **Tamam** kapatmak için **Gelişmiş ayarları** iletişim kutusu.  
  
8.  IIS Yöneticisi'ni kapatın ve **Yönetimsel Araçlar** penceresi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)