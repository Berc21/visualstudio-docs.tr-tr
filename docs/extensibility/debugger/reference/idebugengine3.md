---
title: IDebugEngine3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngine3
helpviewer_keywords:
- IDebugEngine3 interface
ms.assetid: 8bdf4bb7-3b5d-4991-8981-772d4f6bb656
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f601cd38b5546d79f97e1c15a7c33c5de7df5d03
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengine3"></a>IDebugEngine3
Bir veya daha fazla modülü hata ayıklama denetimleri tek hata ayıklama altyapısı (DE) temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugEngine3 : IDebugEngine2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 (Simgeler destekliyorsa) Bu arabirim JustMyCode durumunu etkinleştirmek için özel SE tarafından uygulanır. Simgeler ve JustMyCode destekliyorsa, bu arabirim tarafından DE uygulanmalıdır.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim, oturum hata ayıklama Yöneticisi'ni (simgeleri yükleneceği konumlardan kullanıcı seçeneklerini geçirmek için SDM) tarafından çağrılır. Bu örneği oluşturulduğunda altyapısı GUID ayarlamak için de adlı (Bu GUID altyapısı kayıt zaman ölçümleri temel alır). SDM de JustMyCode durumunu ayarlamaya ve belirli bir duruma hata ayıklayıcı tarafından bilinen tüm özel durumları ayarlamak için bu arabirimi çağırır.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Kaynağından devralındı yöntemleri yanı sıra [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md), `IDebugEngine3` arabirimi aşağıdaki yöntemleri sunar.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)|DE aramak için hata ayıklama simgeleri kullanacağı yolu veya yolları ayarlar.|  
|[LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)|Yüklenen kendi simgeleri henüz uygulanmamış olan tüm modülleri simgelerini yükler.|  
|[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)|DE JustMyCode bilgilerini söyler.|  
|[SetEngineGuid](../../../extensibility/debugger/reference/idebugengine3-setengineguid.md)|DE GUID ölçümleri ayarlar.|  
|[SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md)|Belirtilen bir durum şu anda bekleyen tüm özel durumları ayarlayın.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)