---
title: IDebugAlias::Dispose | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugAlias::Dispose
helpviewer_keywords:
- IDebugAlias::Dispose method
ms.assetid: e84909a4-d378-4f48-bf25-2c014c77c8e3
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: adc458c518baedfd8c5495ea3599ea4bbb21e9f2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugaliasdispose"></a>IDebugAlias::Dispose
Bu diğer adı kaldırılmak üzere işaretler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Dispose();  
```  
  
```csharp  
int Dispose();  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem çağrıldığında, diğer ad artık mevcut değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)