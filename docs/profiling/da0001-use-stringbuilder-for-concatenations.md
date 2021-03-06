---
title: 'DA0001: Birleştirmeler için StringBuilder kullanın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.DA0001
- vs.performance.rules.DAUseStringBuilder
- vs.performance.1
- vs.performance.rules.DA0001
ms.assetid: a7cc7613-ad5f-48c8-bd2b-56372cc12dfc
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8e7393d3a42193c5d25eadc40fcbc02a38cfcdfd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="da0001-use-stringbuilder-for-concatenations"></a>DA0001: Birleştirmeler için StringBuilder kullanın
|||  
|-|-|  
|Kural Kimliği|DA0001|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemleri|Örnekleme<br /><br /> İzleme|  
|İleti|Dize birleştirmeler için StringBuilder kullanmayı düşünün|  
|İleti türü|Uyarı|  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma verileri önemli bir kısmının System.String.Concat çağrıları aynıdır. Kullanmayı <xref:System.Text.StringBuilder> birden çok parçalı dizelerden oluşturmak için sınıfı.  
  
## <a name="rule-description"></a>Kural Tanımı  
 A <xref:System.String> nesnesidir değişmez. Bu nedenle, dize kendilerine herhangi bir değişiklik yeni bir dize nesnesi ve özgün çöp koleksiyonu oluşturur. Dize birleştirme işleçleri kullanın veya String.Concat açıkça çağırın Bu davranış aynı olup + veya +=... Varsa program performans düşebilir zaman karakter sıkı bir döngü içindeki bir dizeye eklenen gibi bu yöntemleri sık denir.  
  
 StringBuilder sınıfını değişebilir bir nesnedir ve System.String, bu sınıfın bir örneğini değiştirmek StringBuilder yöntemlerde çoğunu o aynı örneğine başvuru dönün. Karakterleri eklemek veya bir StringBuilder örneğine metin ekleyin ve kaldırın veya yeni bir örneğini ayırma ve orijinal örnek silmek için gerek kalmadan örnekteki karakterleri değiştirin.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gitmek için hata listesi penceresini iletisinde çift [işlev Ayrıntıları görünümü](../profiling/function-details-view.md) örnekleme, profil verileri. Dize birleştirme en sık rastlanan kullanılmasını sağlamak program bölümlerini bulur. StringBuilder sınıfını sık dize birleştirme işlemleri dahil olmak üzere karmaşık dize işlemeleri için kullanın.  
  
 Dizeleri ile birlikte çalışma hakkında daha fazla bilgi için [dize işlemleri](http://go.microsoft.com/fwlink/?LinkId=177816) bölümünü [bölüm 5 - yönetilen kod performansı artırma](http://go.microsoft.com/fwlink/?LinkId=177817) Microsoft Patterns and Practices Kitaplığı'nda.