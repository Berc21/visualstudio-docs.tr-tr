---
title: "Arayan Aranan görünümü - .NET bellek örnekleme verileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Caller/Callee view
ms.assetid: 36f5b4de-5686-4f40-9e72-f4aee27d833c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 275ec14b1b6a0d43d2c8fdb88bbf1056db86d097
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="callercallee-view---net-memory-sampling-data"></a>Arayan/Aranan görünümü - .NET bellek örnekleme verileri
Arayan/Aranan görünümü .NET bellek profili oluşturma seçili işlev ve üst ve alt işlevleri için verileri görüntüler. Arayan/Aranan görünümü üç kılavuzları içerir.  
  
 **Geçerli işlevi** Orta kılavuzunda görüntülenir ve bellek profili oluşturma seçili işlevi hakkında bilgi gösterir. Tüm örneklenen işlev çağrıları değerlerini içerir.  
  
 **Geçerli işlevini çağırdı işlevleri** üst kılavuzunda görüntülenir ve arayan (üst) işlevi gelen çağrıları tarafından üretildi. Seçili (geçerli) işlevinin değeri miktarını gösterir.  
  
 **Geçerli işlev tarafından çağrılan işlevler** alt kılavuzunda görüntülenir ve alt işlevi geçerli bir işlev tarafından çağrıldığında profil oluşturma verilerini seçili işlevi ' Aranan (alt) işlevleri için bellek miktarını gösterir.  
  
 Geçerli işlev satır yapmak için bir çağıran veya Aranan işlevi satırı çift tıklatın.  
  
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
|**Türü**|İşlev Bağlam:<br /><br /> **0** -geçerli işlevi<br /><br /> **1** -geçerli işlevi çağıran bir işlev<br /><br /> **2** -geçerli işlev tarafından çağrılan bir işlevi<br /><br /> Yalnızca [VSPerfReport](../profiling/vsperfreport.md) komut satırı raporlar.|  
|**Düzeyi**|Çağrı ağacı işlevinde derinliği. Yalnızca [VSPerfReport](../profiling/vsperfreport.md) komut satırı raporlar.|  
|**Kapsayıcı ayırmaları**|-Geçerli işlev için profil oluşturma işlevi tarafından ayrılan nesne sayısını çalıştırın. Bu sayı, aranan işlevlerde oluşturulan nesneleri içerir.<br />-Çağıran işlev için geçerli işlev çağrıları bu işlevden tarafından oluşturulan dahil ayrılmasını sayısı.<br />-Çağrılan işlev için geçerli işlev tarafından çağrılan bu işlev örnekleri tarafından ayrılan nesne sayısı. Çağrılan işlev tarafından çağrılan işlevler tarafından yapılan ayırmaları sayısını içerir.|  
|**Kapsayıcı ayırmaları %**|Profil çalıştırdığınızda oluşturulan tüm nesneler yüzdesi bu işlevin kapsayıcı ayırmaları yoktu.|  
|**Özel ayırmaları**|-Geçerli işlev, işlev kodunu işlev gövdesi yürütülürken oluşturulan nesneleri sayısı için (diğer bir deyişle, ne zaman işlevi çağrı yığını üstünde olduğu). Sayı işlev tarafından adı veriliyordu işlevlerinde oluşturulan nesneleri içermez.<br />-Çağıran işlev için geçerli işlev çağrıları bu işlevden tarafından oluşturulan özel ayrılmasını sayısı.<br />-Çağrılan işlev için geçerli işlev tarafından çağrılan bu işlev örnekleri tarafından oluşturulan nesne sayısı. Sayı çağrılan işlev tarafından çağrılan işlevler tarafından oluşturulan nesneleri içermez.|  
|**Özel ayırmaları %**|Profil çalıştırdığınızda oluşturulan tüm nesneler yüzdesi bu işlevin kapsayıcı ayırmaları yoktu.|  
|**Kapsayıcı bayt**|-Geçerli işlev için profil oluşturma işlevi tarafından ayrılan belleğin bayt sayısını çalıştırın. Bu işlev tarafından adı veriliyordu işlevlerinde ayrılmış bellek sayısını içerir.<br />-Çağıran işlevi için oluşturulmuş geçerli işlevinin dahil bayt sayısı çağıran işlevi tarafından çağırır.<br />-Çağrılan işlev için geçerli işlevi gelen çağrıları tarafından oluşturulan bu işlev örnekleri tarafından ayrılan bayt sayısı. Çağrılan işlev tarafından çağrılan işlevler tarafından ayrılan bayt sayısını içerir.|  
|**Kapsayıcı bayt %**|Profil çalışmasını ayrılan tüm bayt bellek yüzdesi bu işlevin kapsayıcı ayırmaları yoktu.|  
|**Özel bayt sayısı**|-Geçerli işlev için profil oluşturma işlevi tarafından ayrılan belleğin bayt sayısını çalıştırın. Bu sayı, geçerli işlev tarafından çağrılan işlevler tarafından ayrılmış bellek içermez.<br />-Çağıran işlev için geçerli işlevi çağıran işlevi gelen çağrıları tarafından oluşturulan özel bayt sayısı.<br />-Çağrılan işlev için geçerli işlevi gelen çağrıları tarafından oluşturulan işlevi örnekleri tarafından ayrılan bayt sayısı. Çağrılan işlev tarafından çağrılan işlevler tarafından ayrılan bayt sayısı dahil değildir.|  
|**Özel bayt %**|Profil çalışmasını ayrılan tüm bayt bellek yüzdesi bu işlevin özel ayırmaları yoktu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: rapor görünümü sütunlarını özelleştirme](../profiling/how-to-customize-report-view-columns.md)   
 [Arayan/Aranan görünümü - NET bellek izleme verileri](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [Arayan / Aranan görünümü - örnekleme verileri](../profiling/caller-callee-view-sampling-data.md)   
 [Arayan/Aranan görünümü - izleme verileri](../profiling/caller-callee-view-instrumentation-data.md)