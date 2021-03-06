---
title: POPDIRLISTFUNC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8503afb26ec8dc244db39dff5bddcc6d3b733896
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
Verilen bir geri çağırma işlevini budur [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) dizinleri ve (isteğe bağlı olarak), kaynak denetimi altında olduğunu bulmak için dosya adları topluluğu güncelleştirmek için işlevi.  
  
 `POPDIRLISTFUNC` Yalnızca dizin ve dosya adları için geri çağırma'nin çağrılabilir (verilen listesinde `SccPopulateDirList` işlevi) olan gerçekte kaynak denetimi altında.  
  
## <a name="signature"></a>İmza  
  
```cpp  
typedef BOOL (*POPDIRLISTFUNC)(  
   LPVOID pvCallerData,  
   BOOL bFolder,  
   LPCSTR lpDirectoryOrFileName  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 pvCallerData  
 [in] Verilen kullanıcı değeri [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md).  
  
 bKlasör  
 [in] `TRUE` varsa adlarında `lpDirectoryOrFileName` bir dizin; Aksi takdirde adı bir dosya adı değil.  
  
 lpDirectoryOrFileName  
 [in] Kaynak kodu denetimi altında bir dizin veya dosya adı tam yerel yolu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 IDE uygun hata kodunu döndürür:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|İşleme devam edin.|  
|SCC_I_OPERATIONCANCELED|İşlemeyi durdur.|  
|SCC_E_xxx|Tüm uygun kaynak denetimi hata işleme durdurmanız gerekir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `fOptions` parametresinin `SccPopulateDirList` işlevi içeriyor `SCC_PDL_INCLUDEFILES` bayrak sonra da bu liste büyük olasılıkla dizin adlarını yanı sıra dosya adları içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDE tarafından uygulanan geri arama işlevleri](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)   
 [Hata Kodları](../extensibility/error-codes.md)