---
title: IDebugEngineLaunch2::TerminateProcess | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngineLaunch2::TerminateProcess
helpviewer_keywords:
- IDebugEngineLaunch2::TerminateProcess
ms.assetid: f7039e7f-5f57-4222-9ad2-11a66b2da6e0
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 87531db8930e4ca977b2d7dbe48a4afeb5affa7d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugenginelaunch2terminateprocess"></a>IDebugEngineLaunch2::TerminateProcess
Bir işlemi sonlandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT TerminateProcess (   
   IDebugProcess2* pProcess  
);  
```  
  
```csharp  
int TerminateProcess (   
   IDebugProcess2 pProcess  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pProcess`  
 [in] Bir [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) sonlandırılacak işlemi temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrı [CanTerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-canterminateprocess.md) bu yöntemi çağırmadan önce yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [CanTerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-canterminateprocess.md)