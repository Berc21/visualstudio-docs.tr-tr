---
title: "Evrensel Windows Platformu (UWP) uygulamaları geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 10/24/2017
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eac59cb6-f12e-4a77-9953-6d62b164a643
caps.latest.revision: "48"
author: stevehoag
ms.author: shoag
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: a696a0b827cc8fe367390efbba01c2a18ff178bb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="develop-apps-for-the-universal-windows-platform-uwp"></a>Evrensel Windows Platformu (UWP) uygulamaları geliştirme
Evrensel Windows platformu ve bizim bir Windows çekirdek ile aynı uygulama tüm Windows 10 cihazından telefonları masaüstlerine çalıştırabilirsiniz. Bu Evrensel Windows uygulamaları Evrensel Windows uygulaması geliştirme araçlarını Visual Studio ile oluşturun.  
  
 ![Evrensel Windows platformu](../cross-platform/media/uwp_coreextensions.png "UWP_CoreExtensions")  
  
 Uygulamanızı Windows 10 telefon, Windows 10 Masaüstü veya Xbox çalıştırın. Aynı uygulama paketi kadar! Windows 10 tek, birleşik çekirdek başlanmasıyla, bir uygulama paketi tüm platformlarda çalıştırabilirsiniz. Birkaç platformları, platforma özgü davranışları yararlanmak için uygulamanızın ekleyebilirsiniz SDK'ları uzantılıdır. Örneğin, bir uzantı SDK Mobile Windows phone'da basılan geri düğmesini işler. Projenizde uzantı SDK başvurursanız, yalnızca bu SDK bu platformda olup olmadığını test etmek için çalışma zamanı denetimleri ekleyin. Her platform için aynı uygulama paketi nasıl sahip olan!  
  
 **Windows Çekirdeği nedir?**  
  
 Tüm Windows 10 platformları arasında ortak bir çekirdek sağlamak için ilk olarak, Windows bulunanad. Bir ortak kaynak, bir ortak Windows çekirdek, bir dosya g/ç yığını ve bir uygulama modeli yoktur. UI için yalnızca bir XAML kullanıcı Arabirimi çerçevesi ve bir HTML UI çerçevesi yoktur. Uygulamanızı farklı Windows 10 cihazlarda çalıştırmak kolay yaptık için harika bir uygulama oluşturmaya odaklanabilirsiniz.  
  
 **Evrensel Windows platformu tam olarak nedir?**  
  
Evrensel Windows platformu basitçe, sözleşmeler ve sürümleri koleksiyonudur. Bunlar burada, uygulamanızın çalıştırabilirsiniz hedefine izin verir. Artık, bir işletim sistemini de hedeflemek; Şimdi bir veya daha fazla cihaz aileleri hedefleyin. Daha fazla ayrıntı okuyarak öğrenin [Evrensel Windows platformu giriş](/windows/uwp/get-started/universal-application-platform-guide).  
  
## <a name="requirements"></a>Gereksinimler  
 Evrensel Windows uygulama geliştirme araçları, uygulamanızın farklı cihazlarda nasıl göründüğünü görmek için kullanabileceğiniz Öykünücüler gelir. Bu Öykünücüler kullanmak istiyorsanız, bir fiziksel makine bu yazılımı yüklemeniz gerekir. Fiziksel makine Windows 8.1 (x64) Professional edition çalıştırmanız gerekir ya da daha yüksek ve Hyper-V istemcisi ve ikinci düzey adres çevirisi (SLAT) destekleyen bir işlemciye sahip. Visual Studio bir sanal makinede yüklü olduğunda Öykünücüler kullanılamaz.  
  
 Gereksinim duyduğunuz yazılım listesi aşağıdadır:  
  
-   [Windows 10](http://windows.microsoft.com/windows/downloads). Visual Studio 2017 UWP geliştirme yalnızca Windows 10 destekler. Daha fazla ayrıntı için bkz: Visual Studio [Platform Desteği](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs) ve [sistem gereksinimleri](https://www.visualstudio.com/en-us/productinfo/vs2017-system-requirements-vs).   
  
-   [Visual Studio](https://www.visualstudio.com/downloads/). İsteğe bağlı Evrensel Windows platformu geliştirme iş yükü de gerekir.  

     ![UWP iş yükü](media/uwp_workload.png)
  
Bu yazılım yüklemeden sonra Windows 10 Cihazınızı geliştirme için etkinleştirmeniz gerekir. Bkz: [cihazınız geliştirme için etkinleştirme](/windows/uwp/get-started/enable-your-device-for-development). Artık her bir Windows 10 cihaz için bir geliştirici lisansı gerekir.  
    
## <a name="universal-windows-apps"></a>Evrensel Windows uygulamaları  
C#, Visual Basic, C++ veya JavaScript Windows 10 cihazlar için evrensel Windows platformu uygulamasını oluşturmak için tercih edilen geliştirme dilini seçin. Okuma [ilk uygulamanızı oluşturma](/windows/uwp/get-started/your-first-app) veya izleme [araçları için Windows 10 genel bakış](http://channel9.msdn.com/Series/ConnectOn-Demand/229) video.
  
Var olan Windows mağazası 8.1 uygulamaları, Windows Phone 8.1 uygulamaları ya da Visual Studio 2015 ile oluşturulan Evrensel Windows uygulamaları varsa, bu uygulamaların son Evrensel Windows platformu kullanmak için bağlantı noktası gerekir. Bkz: [taşıma Windows çalışma zamanı UWP 8.x](/windows/uwp/porting/w8x-to-uwp-root).
  
Evrensel Windows uygulamanız oluşturduktan sonra Windows 10 cihazında yüklemek veya Windows Mağazası'na göndermek için uygulamanızı paketleme gerekir. Bkz: [paketleme uygulamaları](/windows/uwp/packaging/index).

## <a name="see-also"></a>Ayrıca bkz.
[Visual Studio’da Platformlar Arası Mobil Geliştirme](../cross-platform/cross-platform-mobile-development-in-visual-studio.md)  
