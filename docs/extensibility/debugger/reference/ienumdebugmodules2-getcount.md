---
title: IEnumDebugModules2::GetCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IEnumDebugModules2::GetCount
helpviewer_keywords:
- IEnumDebugModules2::GetCount
ms.assetid: f4def3d2-7cc9-4cd2-9649-3b7e00a76220
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e3e3915dcbcb9fb96c4bae1d5b44fbbbfc3a59f0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugmodules2getcount"></a>IEnumDebugModules2::GetCount
Sabit listede öğe sayısını döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetCount(  
   ULONG* pcelt  
);  
```  
  
```csharp  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pcelt`  
 [out] Sabit listede öğe sayısını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca belirten her zamanki COM numaralandırması arabirimi parçası olmayan `Next`, `Clone`, `Skip`, ve `Reset` yöntemleri uygulanması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)