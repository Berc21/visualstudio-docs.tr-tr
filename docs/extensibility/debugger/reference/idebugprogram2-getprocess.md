---
title: IDebugProgram2::GetProcess | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgram2::GetProcess
helpviewer_keywords:
- IDebugProgram2::GetProcess
ms.assetid: 1d602485-ebaf-451c-9165-f2e226f20a90
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0202433bdae8583eaab6cbca2fbf1e2c9cde08bc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2getprocess"></a>IDebugProgram2::GetProcess
Bu programı çalıştırmayı işlem alın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetProcess(  
   IDebugProcess2** ppProcess  
);  
```  
  
```csharp  
int GetProcess(  
   out IDebugProcess2 ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppProcess`  
 [out] Döndürür [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) işlemi temsil eden arabirim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama altyapısı (DE) uygulayan sürece [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md) arabirimi, bu yöntem DE'ın uyarlamasını döndürmelidir her zaman `E_NOTIMPL` SE de ve bu nedenle çalıştığından işlemi yapamazsınız belirleyemediğinden Bu yöntemin bir uygulaması, karşılar.  
  
 Uygulama `IDebugEngineLaunch2` arabirimi anlamına gelir DE bir işlem; oluşturulacağını bilmeniz gerekir bu nedenle DE'ın uyarlamasını [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) arabirimidir çalışır durumda hangi işlemin bilebilirler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)