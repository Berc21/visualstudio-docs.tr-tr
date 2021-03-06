---
title: "Güvenlik ve yerleştirilmiş yardımcı derlemeler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- key pairs for strong-named assemblies
- strong-named assemblies, security considerations
- satellite assemblies, localized
- code signing, assemblies
- security [Visual Studio], assemblies
- strong-named assemblies, localized
- assemblies [Visual Studio], security
- localization, satellite assemblies
ms.assetid: 6d953840-b301-47d5-8d34-30c1b29b5071
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5f2834e267e2494f62f5cfed9121a0a94a22afb0
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2018
---
# <a name="security-and-localized-satellite-assemblies"></a>Güvenlik ve Yerleştirilmiş Yardımcı Derlemeler

Ana derleme güçlü adlandırma kullanıyorsa, uydu derlemeleri ana derlemeyle aynı özel anahtar ile imzalanmalıdır. Ortak/özel anahtar çifti eşleşmiyor ana ve uydu derlemelerini, kaynaklarınız arasında yüklü değil İmzalama derlemeler hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir derlemeyi tanımlayıcı adla oturum](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name).  
  
 Genel olarak, kuruluşunuzun imzalama grubu veya özel anahtar ile oturum açma dış imzalama kuruluş olması gerekebilir. Özel anahtarı hassas yapısı nedeniyle budur: erişim kısıtlıdır genellikle birkaç kişi. Geliştirme sırasında Gecikmeli imzalama kullanabilirsiniz. Daha fazla bilgi için bkz: [Gecikmeli bir derleme imzalama](/dotnet/framework/app-domains/delay-sign-assembly).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Derleme güvenliği konuları](/dotnet/framework/app-domains/assembly-security-considerations)  - [anahtar güvenlik kavramları](/dotnet/standard/security/key-security-concepts)   
- [.NET Framework Tabanlı Uluslararası Uygulamalara Giriş](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
- [Uygulamaları Yerelleştirme](../ide/localizing-applications.md)   
- [Uygulamaları Genelleştirme ve Yerelleştirme](../ide/globalizing-and-localizing-applications.md)