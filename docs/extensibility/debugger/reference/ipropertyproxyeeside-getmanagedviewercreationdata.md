---
title: IPropertyProxyEESide::GetManagedViewerCreationData | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
helpviewer_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
ms.assetid: c4eb4d60-8816-4d52-bc8d-dffd4f066499
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 53964947ac69cb9b4958bff0a8a6fd4ffa0a8afa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ipropertyproxyeesidegetmanagedviewercreationdata"></a>IPropertyProxyEESide::GetManagedViewerCreationData
Bu Görüntüleyici örneği oluşturmak için bu özellik türü Görüntüleyicisi'nde ilgili bilgileri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetManagedViewerCreationData(  
   BSTR*                  assemName,  
   IEEDataStorage**       assemBytes,  
   IEEDataStorage**       assemPdb,  
   BSTR*                  className,  
   ASSEMBLYLOCRESOLUTION* alr,  
   BOOL*                  replacementOk  
);  
```  
  
```csharp  
int GetManagedViewerCreationData(  
   out string                     assemName,  
   out IEEDataStorage             assemBytes,  
   out IEEDataStorage             assemPdb,  
   out string                     className,  
   out enum_ASSEMBLYLOCRESOLUTION alr,  
   out int                        replacementOk  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `assemName`  
 [out] Bu nesne bulunduran derlemenin adını döndürür.  
  
 `assemBytes`  
 [out] Döndürür bir [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) (Bu, bir null değer hiçbir bayt varsa) bu nesnenin derleme baytları içeren bir nesne.  
  
 `assemPdb`  
 [out] Döndürür bir `IEEDataStorage` simgeyi içeren bir nesne, bu nesne için (Bu, bir null değer varsa bir simge depo) bilgileri depolar.  
  
 `className`  
 [out] Bu nesneyi içeren sınıf adını döndürür.  
  
 `alr`  
 [out] Arasında bir değer döndürür [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) derlemesinin konumunu belirten numaralandırma.  
  
 `replacementOk`  
 [out] Sıfır olmayan bir değer döndürür (`TRUE`) bu nesnenin değeri değiştirilebilir; sıfır (`FALSE`) nesne salt okunur ise.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, tür görselleştiricilerde yönetilen bir Görüntüleyici örneği oluşturmak için kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)