---
title: IDebugCustomAttribute | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCustomAttribute
helpviewer_keywords:
- IDebugCustomAttribute interface
ms.assetid: c5ae41e9-00b9-4cca-871d-b8de9ef390d1
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 48aeab8a09d4916c31c5e2b781427988cf352b25
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcustomattribute"></a>IDebugCustomAttribute
Bu arabirim özel bir özniteliği temsil eder ve adı, üst ve öznitelik sınıfı türü sağlayabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugCustomAttribute : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Sembol sağlayıcısı, bir simge ile ilişkilendirilen özel öznitelikleri desteklemek için bu arabirimi uygular. Bu, genellikle kendi nesne üzerinde uygulanır.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [sonraki](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md) bu arabirimini döndürür. Çağrı [EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md) yöntemi döndürür [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) arabirimi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugCustomAttribute`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetParentField](../../../extensibility/debugger/reference/idebugcustomattribute-getparentfield.md)|Geçerli özniteliğin bağlı olduğu alan alır.|  
|[GetAttributeTypeField](../../../extensibility/debugger/reference/idebugcustomattribute-getattributetypefield.md)|Özel öznitelik sınıfı türünü alır.|  
|[GetName](../../../extensibility/debugger/reference/idebugcustomattribute-getname.md)|Özel öznitelik adını alır.|  
|[GetAttributeBytes](../../../extensibility/debugger/reference/idebugcustomattribute-getattributebytes.md)|Bir BLOB bayt öznitelik bilgileri alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Özel bir öznitelik için C belirli bir sınıf veya yöntemi ile ilgili özel meta verileri sağlayan # bir yapıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sembol sağlayıcısı arabirimleri](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)