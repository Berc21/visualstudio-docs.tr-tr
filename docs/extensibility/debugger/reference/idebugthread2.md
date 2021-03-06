---
title: IDebugThread2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugThread2
helpviewer_keywords:
- IDebugThread2 interface
ms.assetid: 221b4b1b-4a26-466e-bc29-5eff800fab13
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: dca773ca63e2ab6bbc852648d2dea92b0b9813d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugthread2"></a>IDebugThread2
Bu arabirim bir programı çalıştıran bir iş parçacığı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugThread2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE) tek bir program yürütme iş parçacığı temsil etmek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md) şu anda etkin iş parçacığı temsil eden bu arabirimi elde edilir.  
  
 Bu arabirim, ayrıca bir kesme noktası isteği oluşturulurken kullanılır (bkz [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)).  
  
 Bu arabirim bağlama veya hata kesme noktası çözülürken de döndürülür (bkz [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) ve [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)).  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugThread2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)|Bu iş parçacığı için yığın çerçeveleri listesini alır.|  
|[GetName](../../../extensibility/debugger/reference/idebugthread2-getname.md)|İş parçacığı adını alır.|  
|[SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)|İş parçacığı adını ayarlar.|  
|[GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)|Bir iş parçacığı çalıştığı program alır.|  
|[CanSetNextStatement](../../../extensibility/debugger/reference/idebugthread2-cansetnextstatement.md)|Sonraki deyim verilen yığın çerçevesi ve kod bağlamına ayarlayıp ayarlayamayacağını belirler.|  
|[SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)|Sonraki deyim verilen yığın çerçevesi ve kod bağlamını ayarlar.|  
|[GetThreadId](../../../extensibility/debugger/reference/idebugthread2-getthreadid.md)|Sistem iş parçacığı tanımlayıcısını alır.|  
|[Askıya alma](../../../extensibility/debugger/reference/idebugthread2-suspend.md)|Bir iş parçacığı askıya alır.|  
|[Devam et](../../../extensibility/debugger/reference/idebugthread2-resume.md)|Bir iş parçacığı sürdürür.|  
|[GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)|Bir iş parçacığı açıklayan özellikleri alır.|  
|[GetLogicalThread](../../../extensibility/debugger/reference/idebugthread2-getlogicalthread.md)|Bu fiziksel iş parçacığı ile ilişkili mantıksal iş parçacığı alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tek bir fiziksel iş parçacığı birden çok programlarında, birden fazla çalıştırılabildiği `IDebugThread2` birden fazla programdan aynı fiziksel iş parçacığı temsil edebilir.  
  
 Kesme noktası veya özel durum oluştuğunda bir olay çağırarak gönderilen [olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md). Bu yöntem bağımsız değişkenlerinden biri bir `IDebugThread2` geçerli iş parçacığının temsil eden arabirim. [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) elde etmek için kullanılan [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) geçerli yığın çerçevesi için arabirim.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)