---
title: IDebugEngineProgram2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngineProgram2
helpviewer_keywords:
- IDebugEngineProgram2 interface
ms.assetid: 151003a9-2e4d-4acf-9f4d-365dfa6b9596
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 896370d83634580e46f666a8fb9f56f768bf06a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengineprogram2"></a>IDebugEngineProgram2
Bu arabirim çok iş parçacıklı hata ayıklama desteği sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugEngineProgram2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı aynı anda birden çok iş parçacıklarının hata ayıklamayı desteklemek için bu arabirimi uygular. Bu arabirimi uygulayan aynı nesne üzerinde uygulanır [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Kullanım [QueryInterface](/cpp/atl/queryinterface) bu arabirimden elde etmek için bir `IDebugProgram2` arabirimi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugEngineProgram2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Durdur](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)|Tüm iş parçacıklarını bu programı çalıştırmayı durdurur.|  
|[WatchForThreadStep](../../../extensibility/debugger/reference/idebugengineprogram2-watchforthreadstep.md)|İzleyen yürütme (veya yürütme için İzlemeyi Durdur) için verilen iş parçacığı üzerinde gerçekleşmesi için.|  
|[WatchForExpressionEvaluationOnThread](../../../extensibility/debugger/reference/idebugengineprogram2-watchforexpressionevaluationonthread.md)|İfade değerlendirme programı durdurulmuş olsa bile verilen iş parçacığı üzerinde gerçekleşmesi için izin verir (veya izin vermez).|  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio çağrıları bu arabirim yanıt olarak bir [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) olay ve program "İş parçacığı adım İzle" ve "İzleme için ifade değerlendirme üzerinde iş parçacığı" durumlarını ayarlamak için. [Durdur](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) her adlı program durdurulacak; bu yöntem program tüm iş parçacıklarını sonlandırma olanağı verir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)