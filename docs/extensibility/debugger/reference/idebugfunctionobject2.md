---
title: IDebugFunctionObject2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugFunctionObject2 interface
ms.assetid: 56b2fdff-146d-4138-a34c-59a9c65a3ddd
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bbf52230b93357e85326f868254cf1d5c5a9dbb9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionobject2"></a>IDebugFunctionObject2
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bir işlevi temsil eder ve geliştirir [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugFunctionObject2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Bir ifade değerlendiricisi (EE) bir işlevi temsil etmek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim yöntemleri erteleneceği içeriğiyle **IDebugFunctionObject** aşağıdaki yollarla:  
  
-   **IDebugEvaluate** yöntemi bayraklarını alır.  
  
-   **CreateObject** bayrakları ve bir zaman aşımı yöntemi alır.  
  
-   **CreateStringObjectWithLength** yöntemi bir uzunluğunu alır.  
  
## <a name="methods"></a>Yöntemler  
 Bu arabirim, aşağıdaki yöntemlerden uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject2-createobject.md)|Verilen değerlendirme bayrağını ayarlar ve bir zaman aşımı değeri bir oluşturucu kullanan bir nesne oluşturur.|  
|[CreateStringObjectWithLength](../../../extensibility/debugger/reference/idebugfunctionobject2-createstringobjectwithlength.md)|Belirtilen uzunlukta bir dize nesnesi oluşturur.|  
|[Değerlendir](../../../extensibility/debugger/reference/idebugfunctionobject2-evaluate.md)|İşlev çağrılarını ve sonuçta elde edilen değer bir nesne olarak döndürür.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll