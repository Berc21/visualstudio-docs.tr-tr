---
title: "C çalışma zamanı kitaplığını kullanmadan çalışma zamanı kullanarak denetler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.runtime
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- run-time errors, error checks
- CRT, run-time checks
- debugger, native run-time checks
- run-time errors, run-time checks
- run-time checks, /RTC option
- debugging [Visual Studio], run-time routines
ms.assetid: 30ed90f3-9323-4784-80a4-937449eb54f6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: fc81dd57ca6a91cd748da82c792c2bbeca88bb25
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="using-run-time-checks-without-the-c-run-time-library"></a>C Çalışma Zamanı Kitaplığını Kullanmadan Çalışma Zamanı Denetimlerini Kullanma
C çalışma zamanı kitaplığı olmadan programınızı bağlantı varsa, kullanarak **/NODEFAULTLIB**ve çalışma zamanı denetimleri kullanmak istiyorsanız, RunTmChk.lib ile bağlamanız gerekir.  
  
 `_RTC_Initialize`çalışma zamanı denetimleri için programınızın başlatır. C çalışma zamanı kitaplığı ile bağlantı değil varsa, programınızı çağırmadan önce çalışma zamanı hata denetimleri ile derlenmiş olup olmadığını görmek için denetlemelisiniz `_RTC_Initialize`aşağıdaki gibi:  
  
```  
#ifdef __MSVC_RUNTIME_CHECKS  
    _RTC_Initialize();  
#endif  
```  
  
 C çalışma zamanı kitaplığı ile bağlantı değil, ayrıca adlı bir işlev tanımlamalıdır `_CRT_RTC_INITW`. `_CRT_RTC_INITW`Kullanıcı tanımlı işlev raporlama işlevi, aşağıdaki gibi varsayılan hata olarak yükler:  
  
```  
// C version:  
_RTC_error_fnW __cdecl _CRT_RTC_INITW(  
        void *res0, void **res1, int res2, int res3, int res4)  
{  
    // set the error handler.  
    return &MyErrorFunc;   
}  
  
// C++ version:  
extern "C" _RTC_error_fnW __cdecl _CRT_RTC_INITW(  
       void *res0, void **res1, int res2, int res3, int res4)  
{  
    // set the error handler:  
    return &MyErrorFunc;  
}  
```  
  
 Raporlama işlevi varsayılan hata yükledikten sonra ek hata raporlama işlevleri ile yükleyebilirsiniz `_RTC_SetErrorFuncW`. Daha fazla bilgi için bkz: [_RTC_SetErrorFuncW](/cpp/c-runtime-library/reference/rtc-seterrorfuncw).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: yerel çalışma zamanı denetimlerini kullanma](../debugger/how-to-use-native-run-time-checks.md)