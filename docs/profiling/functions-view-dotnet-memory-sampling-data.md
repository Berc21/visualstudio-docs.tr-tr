---
title: "İşlevler görünümü - .NET bellek örnekleme verileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Functions view
ms.assetid: 5d9c6302-2ffd-430e-9535-13ce795f9f7c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 92d2df0182f976af36e9182d080ef6b51130c826
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="functions-view---net-memory-sampling-data"></a>İşlevler görünümü - .NET bellek örnekleme verileri
.NET bellek ayırma örnekleme yöntemini kullanarak toplanan verileri profil işlevleri görünümünü ayırmaları sayısı ve boyutu raporları ve profil oluşturma çalışması sırasında bellek tahsis işlevleri listeler.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**İşlem kimliği**|İşlemi çalıştırmak profil oluşturma kimliği (PID).|  
|**İşlem adı**|İşlemin adı.|  
|**Modül adı**|İşlevi içeren modülü adı.|  
|**Modül yolu**|İşlevi içeren modülü yolu.|  
|**Kaynak dosya**|Bu işlev için tanım içeriyor kaynak dosya.|  
|**İşlev adı**|İşlev tam adı.|  
|**İşlev satır numarası**|Bu işlev kaynak dosyadaki başlangıç satır sayısı.|  
|**İşlev adresi**|İşlev adresi.|  
|**Kapsayıcı ayırmaları**|Bu işlev ve onun alt işlevlerde ayrılan nesneleri toplam sayısı.|  
|**Kapsayıcı ayırmaları %**|Profil çalışmasını ayrılan tüm nesneleri yüzdesi bu işlevin kapsayıcı ayırmaları yoktu.|  
|**Özel ayırmaları**|İşlev, doğrudan çağrı yığını üstünde yürütülürken zaman, oluşturulan nesnelerin sayısı. Bu sayı, alt işlevlerde oluşturulan nesneleri içermez.|  
|**Özel ayırmaları %**|Profil çalışmasını ayrılan tüm nesneleri yüzdesi bu işlevin özel ayırmaları yoktu.|  
|**Kapsayıcı bayt**|Bu işlev ve onun alt işlevleri tarafından ayrılan belleğin bayt sayısı.|  
|**Kapsayıcı bayt %**|Profil çalışmasını ayrılan tüm bayt bellek yüzdesi bu işlevin kapsayıcı bayt yoktu.|  
|**Özel bayt sayısı**|Bu işlev tarafından ancak alt işlevleri tarafından ayrılan belleğin bayt sayısı.|  
|**Özel bayt %**|Profil çalışmasını ayrılan tüm bayt bellek yüzdesi bu işlevin özel bayt yoktu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler görünümü - izleme](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [İşlevler görünümü](../profiling/functions-view-sampling-data.md)   
 [İşlevler Görünümü](../profiling/functions-view-instrumentation-data.md)