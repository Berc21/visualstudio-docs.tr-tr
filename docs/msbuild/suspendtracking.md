---
title: SuspendTracking | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SuspendTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SuspendTracking
ms.assetid: f5e06e5a-8083-444c-99c1-07ba834226b5
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0a7f7923f476d6c6bee4f8a5d6eda0c6c7b6fb87
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="suspendtracking"></a>SuspendTracking
Geçerli bağlamda izleme askıya alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp 
HRESULT WINAPI SuspendTracking(void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir **HRESULT** ile **başarılı** izleme askıya alınırsa biti ayarlanmamış.  
  
## <a name="requirements"></a>Gereksinimler  
 **Header:** FileTracker.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ResumeTracking](../msbuild/resumetracking.md)