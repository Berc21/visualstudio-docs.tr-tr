---
title: IDebugProperty2::GetMemoryContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProperty2::GetMemoryContext
helpviewer_keywords:
- IDebugProperty2::GetMemoryContext
ms.assetid: 91793d25-790f-4881-a5c0-d0458e534514
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 34c5baa75b2bc4f63f3b5dd4bcb5a23e49fe5010
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugproperty2getmemorycontext"></a>IDebugProperty2::GetMemoryContext
Özellik değerinin bellek bağlamını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetMemoryContext (   
   IDebugMemoryContext2** ppMemory  
);  
```  
  
```csharp  
int GetMemoryContext(  
   out IDebugMemoryContext2 ppMemory  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppMemory`  
 [out] Döndürür [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) bu özellik ile ilişkilendirilmiş bellek temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde hata kodunu döndürür. Döndürür `S_GETMEMORYCONTEXT_NO_MEMORY_CONTEXT` almak için bellek bağlam ise.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)