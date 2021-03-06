---
title: WaitStart | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2e7fc09c29c0aa5ca708953b1c8aa3e008c06c38
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="waitstart"></a>WaitStart
WaitStart seçeneği yalnızca profil oluşturucu başlatıldı başlatıldığında ya da belirtilen sayıda saniye geçtikten sonra dönmek VSPerfCmd.exe başlatma alt komutunun neden olur. Varsayılan olarak, başlangıç komut hemen döndürür. Başlangıç alt komut profil oluşturucu başlatılırken olmadan döndürürse, bir hata döndürülür. Saniye sayısını belirtilmezse, başlatma komutunun sonsuza kadar bekler.  
  
 Bu profil oluşturucu başlatıldı güvence altına almaya toplu iş dosyalarında WaitStart seçeneği kullanışlıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Seconds`  
 Başlangıç alt komutun dönmeden önce beklenecek saniye sayısı.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 WaitStart seçeneği yalnızca başlangıç alt komutu ile kullanılabilir.  
  
 **Çıkış:**`filename`  
 Çıktı dosyası adını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Bu toplu iş dosyası örneği başlatma komutunun başlatmak profil oluşturucu 5 saniye bekler.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5  
if not %errorlevel% 0 goto :error_tag  
VSPerfCmd.exe /Launch:TestApp.exe  
goto :end  
:error_tag  
@echo Could not start Profiler!  
@echo Error %errorlevel%  
:end  
```