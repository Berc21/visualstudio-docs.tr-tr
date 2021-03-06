---
title: IDebugProperty3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProperty3
helpviewer_keywords:
- IDebugProperty3 interface
ms.assetid: 8f9be68d-4490-4eca-8f6b-8a10ed77e226
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 853d6f4f4f4b9bef54b35c1f2277e3112c1fe31d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugproperty3"></a>IDebugProperty3
Bu arabirim için destek sağlar:  
  
-   Özellik ile ilişkilendirilmiş rasgele uzun bir dize alınıyor.  
  
-   Benzersiz bir kimlik özelliği ile ilişkilendirme.  
  
-   Bir özellik için özel görüntüleyiciler listesi alınıyor.  
  
-   Ortaya çıkan hataları rapor olanağı bir özelliğin değerini ayarlama  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugProperty3 : IDebugProperty2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE) bu arabirimi uygulayan aynı nesne üzerinde uygulayan [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) uzun dizeleri, özellik kimlikleri ve özel görüntüleyiciler için destek sağlamak için.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [QueryInterface](/cpp/atl/queryinterface) üzerinde bir `IDebugProperty2` bu arabirimi sağlamak için arabirim.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Kaynağından devralındı yöntemleri yanı sıra `IDebugProperty2`, `IDebugProperty3` arabirimi aşağıdaki yöntemleri sunar.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)|Özellik ile ilişkilendirilmiş dize uzunluğunu döndürür.|  
|[GetStringChars](../../../extensibility/debugger/reference/idebugproperty3-getstringchars.md)|Bir kullanıcı tarafından sağlanan arabellek dize döndürür.|  
|[CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)|Bu özellik için benzersiz bir kimliği oluşturur.|  
|[DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md)|Bu özellik için benzersiz kimlik bozar.|  
|[GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)|Bu özellik ile görüntülenebilir özel görüntüleyiciler sayısını döndürür.|  
|[GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)|Bu özellik ile görüntülenebilir özel görüntüleyiciler listesini döndürür.|  
|[SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)|Herhangi bir sorun oluştu, hata iletisi döndüren, bu özelliğin değerini ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md) oturum hata ayıklama Yöneticisi bir özelliğin değeri ayarlanamadı (SDM) için tercih edilen yöntemdir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)