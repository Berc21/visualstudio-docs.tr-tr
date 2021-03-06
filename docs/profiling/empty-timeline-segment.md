---
title: "Boş zaman çizelgesi segmenti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.empty
helpviewer_keywords:
- Concurrency Visualizer, empty timeline segment
ms.assetid: f37b301f-3edc-4e56-8084-feec2dc5a9b1
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 026c6cd05ae926228cab5ab2cb52d389cd021d2a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="empty-timeline-segment"></a>Boş Zaman Çizelgesi Segmenti
Eşzamanlılık görselleştiricisi, bir zaman çizelgesi boş bölümüdür nedeni de (beyaz bir arka plana sahip) kanal türüne bağlıdır.  
  
-   CPU iş parçacığı kanal için bu iş parçacığı zaman çizelgesi bu kısmı sırasında yoktu anlamına gelir. İş parçacığında düşünüyorsanız yakınlaştırma denetimini kullanarak veya yatay kaydırma yürütülen bölümünde bulabilirsiniz.  
  
-   Bir g/ç kanalı için hiçbir disk erişimi zamandaki o noktada hedef işlem adına oluştu anlamına gelir.  
  
-   DirectX kanalı için hiçbir GPU iş zaman çizelgesi bu kısmı sırasında hedef işlem adına gerçekleştirilip gerçekleştirilmediğine anlamına gelir.  
  
-   İşaretçi kanalı için hiçbir işaretçileri oluşturulan anlamına gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Parçacıkları görünümü](../profiling/threads-view-parallel-performance.md)   
 [Yakınlaştırma Denetimi (İş Parçacıkları Görünümü)](../profiling/zoom-control-threads-view.md)