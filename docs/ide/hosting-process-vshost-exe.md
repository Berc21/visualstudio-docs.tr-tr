---
title: "Barındırma süreci (vshost.exe) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- vshost.exe
- hosting process
ms.assetid: c6b9e2be-f18d-4d75-ac52-56d55784734b
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 716d19362495fccf475a068a28a9fe2acbe27b53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-process-vshostexe"></a>Barındırma Süreci (vshost.exe)
Barındırma işlemi, Visual Studio'da, hata ayıklama performansını artırır, kısmi güven hata ayıklamasını etkinleştirir ve tasarım zamanı ifade değerlendirmesi olanak sağlayan bir özelliktir. Barındırma işlemi dosyaları vshost dosya adı içerir ve projenizin çıkış klasörüne yerleştirilir. Daha fazla bilgi için bkz: [hata ayıklama ve barındırma işlemi](../debugger/debugging-and-the-hosting-process.md).  
  
> [!NOTE]
>  İşlem dosyaları barındırma (. vshost.exe) Visual Studio tarafından kullanılacak olan ve doğrudan Çalıştır olmamalıdır veya uygulamanızla birlikte dağıtılabilir.  
  
## <a name="improved-debugging-performance"></a>Hata ayıklama performansı  
 Barındırma işlemi bir uygulama etki alanı oluşturur ve hata ayıklayıcı uygulama ile ilişkilendirir. Bu görevleri gerçekleştirmek tanıtmak belirgin bir zamanı hata ayıklama arasındaki gecikme başlatılır ve çalışan uygulamanın zaman başlar. Uygulama etki alanı oluşturma ve hata ayıklayıcı arka planda ilişkilendirme ve uygulama etki alanı kaydetme performansını artırmak barındırma işlemi yardımcı olur ve arasında hata ayıklayıcı durumunu uygulamayı çalıştırır. Uygulama etki alanları hakkında daha fazla bilgi için bkz: [uygulama etki alanları](/dotnet/framework/app-domains/application-domains).  
  
## <a name="partial-trust-debugging"></a>Kısmi güven hata ayıklama  
 Kısmi güven uygulama olarak uygulama belirtilen [güvenlik sayfası](../ide/reference/security-page-project-designer.md) , **Proje Tasarımcısı**. Kısmen güvenilen uygulamada hata ayıklama özel başlatma uygulama etki alanının gerektirir. Bu başlatma barındırma işlemi tarafından işlenir.  
  
## <a name="design-time-expression-evaluation"></a>Tasarım zamanı ifade değerlendirmesi  
 Tasarım zamanı ifade değerlendirmesi koddan test etmenizi sağlar **hemen** uygulamayı çalıştırmak zorunda kalmadan penceresi. Barındırma işlemi tasarım zamanı ifade değerlendirmesi sırasında bu kodu yürütür. Daha fazla bilgi için bkz: [komut penceresi](../ide/reference/immediate-window.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama ve barındırma işlemi](../debugger/debugging-and-the-hosting-process.md)   
 [Nasıl yapılır: barındırma sürecini devre dışı bırakma](../ide/how-to-disable-the-hosting-process.md)   
 [Komut penceresi](../ide/reference/immediate-window.md)   
 [Uygulama Etki Alanları](/dotnet/framework/app-domains/application-domains)