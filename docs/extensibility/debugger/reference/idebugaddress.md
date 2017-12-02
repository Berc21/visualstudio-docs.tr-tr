---
title: IDebugAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugAddress
helpviewer_keywords: IDebugAddress interface
ms.assetid: bc709ff7-4966-4f36-9af2-690efe2cea1d
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9f009002e9c454b1e10cac13c297e067da9c44ff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugaddress"></a>IDebugAddress
Bu arabirim öğeyi adresini temsil eder. Sembol işleyici tarafından döndürülür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugAddress : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Bir simge sağlayıcısı bir nesnenin bir adresi temsil etmek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim birçok arabirimlerindeki birçok yöntemleri döndürür.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki yöntem bu arabirimi uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)|Alır bir [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) bir nesne ve konumunu açıklayan yapısı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sembol sağlayıcı nesne ve belirli bir kapsam (örneğin, işlev, yöntemi veya sınıf) içinde konumunu temsil etmek için bu arabirimi döndürür. Bu arabirim döndürülen ve sembol sağlayıcısı ve ifadesi çeşitli yöntemlere iletilen değerlendirici. Normalde, simge sağlayıcısı bu arabirim içeriğini yorumlamak için gereken tek varlıktır.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sembol sağlayıcısı arabirimleri](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)