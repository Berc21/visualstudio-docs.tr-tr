---
title: "Özel bir ağda uygulamaları güvenilir listeye almayı URL'leri | Microsoft Docs"
ms.custom: 
ms.date: 09/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 94348821e44b5ed07e3df5e4859796342919a833
ms.sourcegitcommit: cc288456329aefca1fdaa7ce74751ce195985c14
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/17/2017
---
# <a name="whitelisting-urls-in-a-private-network"></a>Özel bir ağda uygulamaları güvenilir listeye almayı URL'leri

Visual Studio, bir güvenlik duvarı gibi bir güvenlik uygulaması kullanan özel bir ağda Visual Studio kullanıyorsanız, bazı ağ kaynaklarına bağlanmak mümkün olmayabilir. Bu kaynaklar, oturum açma ve lisans, NuGet ve Azure Hizmetleri için Visual Studio Team Services (VSTS) içerir. Visual Studio bu kaynaklardan biri bağlanamazsa, aşağıdaki hata iletisini görürsünüz:

  **Temel alınan bağlantı kapatıldı: Gönder beklenmeyen bir hata oluştu**

Visual Studio, ağ kaynaklarına bağlanmak için Aktarım Katmanı Güvenliği (TLS) 1.2 protokolünü kullanır. Visual Studio TLS 1.2 kullandığı durumlarda bazı özel ağlar üzerindeki güvenlik gereçlerinin bazı sunucu bağlantılarını Engellemesi. Hatayı düzeltmek için aşağıdaki URL'ler bağlantılarında etkinleştirin:

- https://management.core.windows.net

- https://app.vssps.visualstudio.com

- https://login.microsoftonline.com

- https://login.live.com

- https://go.microsoft.com

- https://graph.windows.net

- https://app.vsspsext.VisualStudio.com

- *. azurewebsites.net (Azure bağlantıları için)

- *. nuget.org (NuGet bağlantılar için)

- *.visualstudio.com

- CDN.vsassets.io (ana içerik teslim ağı veya CDN, içerik)

- *. gallerycdn.vsassets.io (ana bilgisayar VSTS uzantıları)

- static2.sharepointonline.com (Visual Studio office doku yazı tipleri gibi UI Seti kullanır ana bilgisayar kaynakları)

> [!NOTE]
> Özel olarak sahip olunan NuGet sunucu URL'leri Yukarıdaki listeye dahil. %APPData%\Nuget\NuGet.Config dosyasını açarak kullanmakta olduğunuz NuGet sunucularını denetleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Proxy gerekli Yetkilendirme hatası](../ide/reference/proxy-authorization-required.md)  
[Visual Studio tarafından kullanılan Internet kaynakları](../ide/connected-environment.md)  
[Bir güvenlik duvarı veya proxy sunucunun arkasındaki Visual Studio yükleme](../install/install-visual-studio-behind-a-firewall-or-proxy-server.md)