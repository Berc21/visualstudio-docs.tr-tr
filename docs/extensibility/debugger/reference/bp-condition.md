---
title: BP_CONDITION | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BP_CONDITION
helpviewer_keywords:
- BP_CONDITION structure
ms.assetid: 407f87a3-2878-429b-8c65-b68feb36622a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9ccc0b142e87acd3a09840f8c72f5fe1a35bc0a4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bpcondition"></a>BP_CONDITION
Altında bir kesme noktası harekete koşullar açıklanmaktadır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _BP_CONDITION {   
   IDebugThread2* pThread;  
   BP_COND_STYLE  styleCondition;  
   BSTR           bstrContext;  
   BSTR           bstrCondition;  
   UINT           nRadix;  
} BP_CONDITION;  
```  
  
```csharp  
public struct BP_CONDITION {   
   public IDebugThread2 pThread;  
   public uint          styleCondition;  
   public string        bstrContext;  
   public string        bstrCondition;  
   public uint          nRadix;  
};  
```  
  
## <a name="members"></a>Üyeler  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) kesme içeren uygulamayı etkin iş parçacığı temsil eden nesne.  
  
 `styleCondition`  
 Arasında bir değer [BP_COND_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md) bu kesme noktası durum stilini açıklayan numaralandırması.  
  
 `bstrContext`  
 Kesme noktası konumu.  
  
 `bstrCondition`  
 Kesme noktası Tetikleme koşulu.  
  
 `nRadix`  
 Herhangi bir sayısal bilgi değerlendirmede kullanılacak sayı tabanını.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı üyesi olan [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) ve [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) yapıları.  
  
 Bu yapı ayrıca bir parametre olarak geçirilen [SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md) ve [SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [BP_COND_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md)