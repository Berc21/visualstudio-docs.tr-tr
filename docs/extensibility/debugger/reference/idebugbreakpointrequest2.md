---
title: IDebugBreakpointRequest2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBreakpointRequest2
helpviewer_keywords:
- IDebugBreakpointRequest2 interface
ms.assetid: 01ac4013-96f9-4235-b289-f55f9e99558f
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f458d8efcf1a4b466cc48dfd9dca10fa356a6304
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbreakpointrequest2"></a>IDebugBreakpointRequest2
Bu arabirim oluşturmak ve herhangi bir türde kesme noktası bağlamak gereken bilgileri temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugBreakpointRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Oturum hata ayıklama Yöneticisi'ni (SDM) genellikle bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Hata ayıklama altyapısı (DE) bir çağrıyla bu arabirimin aldığı [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) bekleyen bir kesme noktası oluşturmak için. Çağrı [GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md) bu arabirim DE alabilirsiniz.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugBreakpointRequest2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)|Bu bir kesme noktası istek kesme noktası konum türünü alır.|  
|[GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)|Bu kesme isteği açıklar kesme noktası isteği bilgilerini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Programın sonra ayıklanacak yüklendiğinde, çağrı [bağlamak](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) program istenen konuma bekleyen bir kesme noktası bağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)   
 [GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)   
 [Bağlama](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)