---
title: IDebugReference2::GetDerivedMostReference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugReference2::GetDerivedMostReference
helpviewer_keywords: IDebugReference2::GetDerivedMostReference
ms.assetid: 07253b74-7d39-48e0-8e85-ac8dfd919f6e
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 018f843e9e62430c780df1d3d15f06634a31908d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugreference2getderivedmostreference"></a>IDebugReference2::GetDerivedMostReference
Bir başvuru türetilmiş çoğu referansını alır. Daha sonraki kullanımlar için ayrılmıştır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetDerivedMostReference(   
   IDebugReference2** ppDerivedMost  
);  
```  
  
```csharp  
int GetDerivedMostReference(   
   out IDebugReference2 ppDerivedMost  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppDerivedMost`  
 [out] Döndürür bir [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) türetilmiş çoğu özelliği temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her zaman döndürür `E_NOTIMPL`.  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin, bu özellik uygulayan bir nesne tanımlarsa `ClassRoot` ancak aslında, örnekleme olduğu `ClassDerived` öğesinden türetilen `ClassRoot`, sonra da bu yöntemi döndürür bir [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) nesnesi bir başvuru temsil eden `ClassDerived` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)