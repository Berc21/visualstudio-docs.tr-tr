---
title: "Bir güvenlik duvarı veya proxy sunucunun arkasındaki Visual Studio yükleme | Microsoft Docs"
description: 
ms.custom: 
ms.date: 08/01/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs
ms.assetid: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3862c6ed49e00ffa3800cccbedb2b846823418ed
ms.sourcegitcommit: 06cdc1651aa7f45e03d260080da5a623d6258661
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2018
---
# <a name="install-visual-studio-behind-a-firewall-or-proxy-server"></a>Bir güvenlik duvarı veya proxy sunucunun arkasındaki Visual Studio yükleme

Visual Studio yükleyicisi, çeşitli etki alanlarına ve indirme sunucularını dosyaları indirir. Bu sayfa, dağıtım betikleri güvenilir olarak "Beyaz" isteyebilirsiniz etki alanı URL'leri listeler.

Ortamınız için Mümkünse, HTTP ve HTTPS protokolleri aşağıdaki alanlarıyla eklemeyi düşünün.

## <a name="microsoft-domains"></a>Microsoft etki alanları
| Etki Alanı | Amaç |
| ------ | ------- |
| go.microsoft.com | Kurulum URL çözümleme |
| aka.MS | Kurulum URL çözümleme |
| download.visualstudio.microsoft.com | Paketleri indirme konumu Kurulumu |
| download.microsoft.com | Paketleri indirme konumu Kurulumu |
| download.visualstudio.com | Paketleri indirme konumu Kurulumu |
| dl.xamarin.com | Paketleri indirme konumu Kurulumu |
| visualstudiogallery.msdn.microsoft.com | Visual Studio uzantıları konumu indirin |
| www.visualstudio.com | Belge konumu |
| docs.microsoft.com | Belge konumu |
| msdn.microsoft.com | Belge konumu |
| www.microsoft.com | Belge konumu |
| *.windows.net | Oturum açma konumu |
| *.microsoftonline.com | Oturum açma konumu |
| *.live.com | Oturum açma konumu |


## <a name="non-microsoft-domains"></a>Microsoft olmayan etki alanları
| Etki Alanı | Bu iş yükleri yükler |
| ------ | ------- |
| archive.apache.org |  JavaScript ile Mobil Geliştirme <br />(Cordova) |
| cocos2d-x.org | C++ ile oyun geliştirme <br />(Cocos) |
| download.epicgames.com | C++ ile oyun geliştirme <br />(Unreal Engine) |
| download.oracle.com | JavaScript ile Mobil Geliştirme <br />(Java SDK) <br /><br />.NET ile Mobil Geliştirme <br />(Java SDK) |
| download.unity3d.com | Unity ile oyun geliştirme <br />(Unity) |
| netstorage.unity3d.com | Unity ile oyun geliştirme <br /> (Unity) |
| dl.google.com | JavaScript ile Mobil Geliştirme <br />(Android SDK ve NDK, öykünücüsü) <br /><br />.NET ile Mobil Geliştirme <br />(Android SDK ve NDK, öykünücüsü) |
| www.incredibuild.com | C++ ile oyun geliştirme <br />(IncrediBuild) |
| incredibuildvs2017i.azureedge.net | C++ ile oyun geliştirme <br />(IncrediBuild) |
| www.python.org | Python geliştirme <br />(Python) <br /><br />Veri bilimi ve analitik uygulamalar <br />(Python) |

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.
* [Visual Studio 2017 yükleyin](install-visual-studio.md)
* [Visual Studio 2017 yüklemek için komut satırı parametreleri kullanın](use-command-line-parameters-to-install-visual-studio.md)
  * [Komut satırı parametresi örnekleri](command-line-parameter-examples.md)
  * [İş yükü ve bileşen kimliği başvurusu](workload-and-component-ids.md)
* [Visual Studio 2017 ağ tabanlı yüklemesini oluşturma](create-a-network-installation-of-visual-studio.md)
  * [Visual Studio çevrimdışı yükleme için gerekli sertifikaları yükleyin](install-certificates-for-visual-studio-offline.md)
* [Yanıt dosyası ile Visual Studio yüklemesini otomatikleştirme](automated-installation-with-response-file.md)
* [Visual Studio’yu dağıtırken ürün anahtarlarını otomatik olarak uygulama](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [Visual Studio 2017 Kurumsal dağıtımlar için Varsayılanlarını Ayarla](set-defaults-for-enterprise-deployments.md)
* [Paket önbelleğini devre dışı bırakma veya taşıma](disable-or-move-the-package-cache.md)
* [Visual Studio ağ tabanlı yüklemesini güncelleştirme](update-a-network-installation-of-visual-studio.md)
* [Visual Studio 2017 dağıtımları denetim güncelleştirmeleri](controlling-updates-to-visual-studio-deployments.md)
* [Visual Studio örneklerini algılamaya ve yönetmeye yönelik araçlar](tools-for-managing-visual-studio-instances.md)
