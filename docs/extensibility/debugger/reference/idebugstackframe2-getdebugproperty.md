---
title: IDebugStackFrame2::GetDebugProperty | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugStackFrame2::GetDebugProperty
helpviewer_keywords:
- IDebugStackFrame2::GetDebugProperty
ms.assetid: 02c2fa04-1424-4bca-9936-feaecd2afab6
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4d4e26c0008cb52fd5bafda45e33dbbe9b395237
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugstackframe2getdebugproperty"></a>IDebugStackFrame2::GetDebugProperty
Yığın çerçevesi özelliklerini açıklamasını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetDebugProperty (   
   IDebugProperty2** ppDebugProp  
);  
```  
  
```csharp  
int GetDebugProperty (   
   out IDebugProperty2 ppDebugProp  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppDebugProp`  
 [out] Döndürür bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) Bu yığın çerçevesi özelliklerini açıklayan nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağırma [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) uygun filtreleri yöntemiyle yerel değişkenler, yöntem parametreleri, kaydeder ve yığın çerçevesi ile ilişkili "Bu" işaretçi alabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)