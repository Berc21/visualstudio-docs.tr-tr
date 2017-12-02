---
title: IDebugExpressionEvaluator2::SetCallback | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugExpressionEvaluator2::SetCallback
- SetCallback
ms.assetid: 31e3a99e-e784-44a3-8b19-cc5ef31ed546
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1e2ee116f7ed858121c41628515991ed4903cb15
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugexpressionevaluator2setcallback"></a>IDebugExpressionEvaluator2::SetCallback
Hata ayıklayıcı altyapısı (DE) ölçüm ayarları okumak için kullanacağı geri çağırma arabirimi belirtmek ifade değerlendiricisi (EE) sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetCallback (  
   IDebugSettingsCallback2* pCallback  
);  
```  
  
```csharp  
int SetCallback (  
   IDebugSettingsCallback2 pCallback  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pCallback`  
 [in] İçin ayarları geri kullanmak için arabirim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir ifade değerlendiricisi ölçüm ayarları okumak için kullanabileceğiniz oturum hata ayıklama Yöneticisi bir arabirim sağlar. Üzerinde ölçümleri okumak için uzaktan hata ayıklama içinde yararlıdır [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] bilgisayar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler için bu yöntemi uygulaması nasıl gösterir bir **CEE** gösteren nesne [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md) arabirimi.  
  
```cpp  
HRESULT CEE::SetCallback(IDebugSettingsCallback2* in_pCallback)  
{  
    // precondition  
    INVARIANT( this );  
  
    // function body  
    if (NULL != this->m_LanguageSpecificUseCases.pfSetCallback)  
    {  
        EEDomain::fSetCallback DomainVal =  
        {  
            in_pCallback  
        };  
  
        BOOL bSuccess = (*this->m_LanguageSpecificUseCases.pfSetCallback)(DomainVal);  
        ENSURE( bSuccess );  
    }  
  
    // postcondition  
    INVARIANT( this );  
  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)