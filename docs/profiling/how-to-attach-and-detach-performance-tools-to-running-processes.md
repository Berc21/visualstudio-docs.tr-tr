---
title: "Nasıl yapılır: ekleme ve çalışan işlemleri için performans araçları ayırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.attach
helpviewer_keywords:
- performance tools, attach process
- profiling tools, detach process
- profiling tools, attach process
- performance tools, detach process
- profiler
ms.assetid: 56a99c39-e7f6-4f48-ae56-04ab8e022bf7
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e847e1295e4514f8e1c327f207a6ae7166c892df
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-attach-and-detach-performance-tools-to-running-processes"></a>Nasıl yapılır: ekleme ve ayırma işlemleri çalıştırmanın performans araçları
Profil Oluşturucu ekleme veya örnekleme ve toplama performans verilerini daha kolay hale getirmek için bir çalışan işlemden ayırmak için kullanılabilir. Uygulama yükleme süresi hakkında veri toplamayı önlemek istiyorsanız veya sonraki bir işlem performansını izlemek için belirli bir durumu ulaştığında bir işlem profili için bu yöntemi kullanın.  
  
> [!NOTE]
>  Ekleme ve ayırma işlemleri içinden aşağıdaki adımları uygulamak [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] tümleşik geliştirme environmnent (IDE). Komut satırı araçlarını kullanma hakkında daha fazla bilgi için bkz: [komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md). Profil hizmetleri hakkında daha fazla bilgi için bkz: [profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md).  
  
 Bilgisayarın yönetici tarafından ayarlanan kullanıcı erişimi izinleri profiline kullanılabilir işlemleri bağlıdır. Örneğin, bir kullanıcı hesabı aşağıdakilerden herhangi biri için izni olabilir:  
  
-   Yönetici sürücü ve hizmeti başlatmak için ayarladığınızda, özellikleri, profil Gelişmiş.  
  
-   Yalnızca (etki alanı kullanıcıları) profil örnek.  
  
-   Herkes için profil oluşturma erişimini.  
  
 Daha fazla bilgi için bkz: [profil oluşturma ve Windows Vista Güvenliği](../profiling/profiling-and-windows-vista-security.md) ve yönetim Seçenekleri'nde [VSPerfCmd](../profiling/vsperfcmd.md).  
  
### <a name="to-attach-to-a-running-process"></a>Bir çalışan işleme iliştirilemiyor  
  
1.  Üzerinde **hata ayıklama** menüsündeki **profil oluşturucu**, ardından **performans Gezgini**ve ardından **Attach**.    
  
     **Profil oluşturucu ekleme işlemi için** iletişim kutusu görüntülenir.  
  
2.  Eklemek istediğiniz işlemin adını tıklatın.  
  
3.  Tıklatın **Attach**.  
  
### <a name="to-detach-from-a-running-process"></a>Bir çalışan işlemden ayırmak için  
  
1.  n **hata ayıklama** menüsündeki **profil oluşturucu**, ardından **performans Gezgini**ve ardından **ayırma**. 
  
     **Profil oluşturucu ekleme işlemi için** iletişim kutusu görüntülenir.  
  
2.  Ayırmak istediğiniz görüntü adına tıklayın.  
  
3.  Tıklatın **Detach**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri toplama denetimi](../profiling/controlling-data-collection.md)   
 [Performans oturumuna genel bakış](../profiling/performance-session-overview.md)   
 [Nasıl yapılır: Başlangıç ve bitiş performans verileri toplama](../profiling/how-to-start-and-end-performance-data-collection.md)   
 [Profil oluşturma ve Windows Vista güvenliği](../profiling/profiling-and-windows-vista-security.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)