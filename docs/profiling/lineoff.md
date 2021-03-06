---
title: LineOff | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76082063-20ef-47ae-ad64-81b43b654865
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ebab610e9f684cf55054fae6916e6d1b1fb40d67
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="lineoff"></a>LineOff
Örnekleme profili oluşturma yöntemi kullanırken varsayılan olarak, profil oluşturucu kaynak kodu satır sayısı ve satır numarası uzaklık verilerini toplar. VSPerfCmd **LineOff** seçeneği devre dışı bırakır satır numarası veri toplama VSPerfCmd uygulamayı başlatmak için kullanıldığında. Profil oluşturma verilerini işleve toplanır ne zaman düzey **LineOff** belirtilir.  
  
 Kullanabileceğiniz **LineOff** yalnızca **başlatma** seçeneği ve yalnızca zaman profil oluşturucu örnekleme için kullanarak başlatıldı **Başlat**:**örnek** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Launch:AppName /LineOff [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **LineOff** seçeneği içeren bir komut satırında yalnızca kullanılabilir **başlatma** seçeneği.  
  
 **Başlatma:**`AppName`  
 Belirtilen uygulamayı başlatır ve profil oluşturma örnekleme yöntemi ile başlar.  
  
## <a name="example"></a>Örnek  
 Bu örnek uygulama ve profil oluşturucu başlatır ve satır düzeyi örnekleme devre dışı bırakır.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /LineOff  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)