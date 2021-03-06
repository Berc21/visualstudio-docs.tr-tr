---
title: "DA0024: Aşırı GC CPU süresi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.DA0024
- vs.performance.24
- vs.performance.rules.DA0024
ms.assetid: 228872da-77d0-4da5-b455-ac57fb1867c9
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 931dd6f37273954dbbdbc8465e514c6db2be590d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="da0024-excessive-gc-cpu-time"></a>DA0024: Aşırı GC CPU Süresi
|||  
|-|-|  
|Kural Kimliği|DA0024|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|GC % zamanı çok yüksek. Çöp toplama yükünü aşırı miktarda yoktur.|  
|Kural türü|Uyarı|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma sırasında toplanan sistem performans verileri, toplam uygulama işleme zamanı ile karşılaştırıldığında, çöp toplama harcanan süre miktarını aşırı yüksek olduğunu gösterir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Microsoft .NET ortak dil çalışma zamanı (CLR) uygulama artık kullanır nesneleri belleği geri almasını atık toplayıcı kullanan bir otomatik bellek yönetimi mekanizması sağlar. Çöp toplayıcı nesil odaklı birçok ayırmaları kısa süreli duymadığını ' dir. Yerel değişkenler, örneğin, kısa süreli olmalıdır. Yeni oluşturulan nesneleri oluşturma 0 (gen 0) başlatın ve bunlar uygulama hala bunları kullanıyorsa, ne zaman bunlar bir atık toplama çalıştırın ve son olarak 2. nesil geçiş varlığını sürdürmesini 1. nesil için ilerleme durumu.  
  
 Kuşak 0 nesnelerinin sık ve genellikle çok verimli bir şekilde toplanır. 1. nesil nesneler daha az sıklıkta ve daha az verimli bir şekilde toplanır. Son olarak, 2. nesil uzun süreli nesneleri bile daha az sıklıkta toplanan. Çalıştır tam atık toplama olduğundan, 2. nesil koleksiyonu da en pahalı bir işlemdir.  
  
 Çöp toplama harcanan süre miktarını toplam uygulama işleme süresi ile karşılaştırıldığında aşırı yüksek olduğunda bu kural ateşlenir.  
  
> [!NOTE]
>  Çöp Toplama süresi oranını zaman harcanan önemlidir, ancak değil aşırı toplam uygulama işleme süresi ile karşılaştırıldığında [DA0023: yüksek GC CPU süresi](../profiling/da0023-high-gc-cpu-time.md) yerine bu kural uyarı etkinleşir.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gitmek için Hata Listesi penceresi iletisinde çift [işaretleri Görünüm](../profiling/marks-view.md) profil oluşturma veri. Bul **.NET CLR bellek\\% GC zamanı** sütun. Olup olmadığını program yürütme belirli aşamaları yönetilen bellek çöp toplama yükü diğer aşamalar ağır olduğu belirler. % GC zamanı değerlerini çöp toplama oranını değer karşılaştırma bildirilen **# Gen 0 koleksiyonları**, **# Gen 1 koleksiyonları**, **# Gen 2 koleksiyonları** değerleri .  
  
 % GC değerindeki zamanı uygulamanın gerçekleştirme çöp toplama işleme toplam miktarı için orantılı geçirdiği süreyi rapor dener. Bazı durumlarda % GC değerindeki zamanı çok yüksek bir değere bildirebilirsiniz, ancak aşırı çöp toplama nedeniyle değil unutmayın. % GC değerindeki zamanı hesaplanan biçimi hakkında daha fazla bilgi için bkz: [fark arasındaki performans verileri tarafından bildirilen farklı araçları - 4](http://go.microsoft.com/fwlink/?LinkId=177863) girişi **Maoni'nın blog** MSDN'de. Sayfa hataları yaşanan veya uygulama tarafından diğer daha yüksek öncelik iş makinedeki çöp toplama sırasında geçersiz kılınırsa, GC sayaç zamanında % bu ek gecikmeler yansıtır.