---
title: "Kimliğe göre performans kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a1c934c-4798-4df9-a8ef-eb17ef06b6a2
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f93c78df2128be830865026039552652fe901a8c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="performance-rules-by-id"></a>Kimliğe Göre Performans Kuralları
|Uyarı|Açıklama|  
|-------------|-----------------|  
|[DA0001: Birleştirmeler için StringBuilder kullanın](../profiling/da0001-use-stringbuilder-for-concatenations.md)|Profil oluşturma verileri önemli bir kısmının System.String.Concat çağrıları aynıdır. Kullanmayı <xref:System.Text.StringBuilder> birden çok parçalı dizelerden oluşturmak için sınıfı.|  
|[DA0002: VSPerfCorProf.dll eksik](../profiling/da0002-vsperfcorprof-dll-is-missing.md)|Profil Oluşturucu VSPerfCorProf.dll profil çalışması sırasında bulunamadı. Profil Oluşturucu verilerin toplanması için komut satırı araçları gerekli ortam değişkenlerini başlatmak için VSPerfCLREnv.cmd aracını kullanarak olmadan kullanıldığında, bu uyarıyı oluşur.|  
|[DA0003: Pek çok çekirdek örneği](../profiling/da0003-many-kernel-samples.md)|Uygulama için toplanan çağrı yığını örnekleri önemli bir kısmının çekirdek modunda yürütülüyor. Farklı bir profil oluşturma yöntemini kullanarak uygulamanızı profil göz önünde bulundurun.|  
|[DA0004: Yüksek işlemci kullanımı](../profiling/da0004-high-processor-usage.md)|İşlemci (CPU) kullanımı izleme metodunu kullanarak toplanan verileri profil önemli ölçüde yüksek. Örnekleme profili oluşturma yöntemi bir CPU profil bağlı uygulama zaman kullanmayı düşünün.|  
|[DA0005: Sık sık kullanılan GC2 koleksiyonları](../profiling/da0005-frequent-gc2-collections.md)|Çok sayıda .NET bellek nesneleri nesil 2 çöp toplama kazanılır.|  
|[DA0006: Değer türleri için geçersiz kılma Equals()](../profiling/da0006-override-equals-parens-for-value-types.md)|Equals yöntemi veya ortak değer türünün eşitlik işleçleri çağrıları profil oluşturma verileri önemli bir kısmının aynıdır. Daha verimli bir yöntem uygulayın.|  
|[DA0007: denetim akışı için özel durumlar kullanmaktan kaçının](../profiling/da0007-avoid-using-exceptions-for-control-flow.md)|.NET Framework özel durum işleyicileri yüksek oranda profil oluşturma verileri çağrılır. Oluşturulan özel durum sayısını azaltmak için diğer denetim akışı mantığı kullanmayı düşünün.|  
|[DA0008: toplanan örnek az](../profiling/da0008-few-samples-collected.md)|Yalnızca birkaç örnek profil Çalıştır toplanan. Daha önemli sonuçlar için uzun bir veya daha hızlı çalışmasını örnekleme hızını göz önünde bulundurun.|  
|[DA0009: JIT yüksek % zaman](http://msdn.microsoft.com/en-us/b60c1767-515c-41d9-81c2-c70d0b7024fd)|Uygulama yürütme zamanı önemli bir yüzdesinde yalnızca içinde anında (JIT) derleyicide harcandığını.|  
|[DA0010: Pahalı GetHashCode](../profiling/da0010-expensive-gethashcode.md)|Profil oluşturma verileri önemli bir kısmının türü GetHashCode yöntemi çağrıları aynıdır veya yöntemi bellek ayırır.|  
|[DA0011: Pahalı CompareTo](../profiling/da0011-expensive-compareto.md)|CompareTo Yöntemi türü pahalıdır veya bellek ayırır.|  
|[DA0012: Önemli miktarda yansıma](../profiling/da0012-significant-amount-of-reflection.md)|Profil oluşturma verileri önemli bir kısmının çağrıları InvokeMember ve GetMember gibi System.Reflection yöntemleri veya MemberInvoke gibi türü yöntemleri için aynıdır. Şunları yapabilirsiniz, bu yöntemleri bağımlı derlemeleri yöntemleri için erken bağlama değiştirerek göz önünde bulundurun.|  
|[DA0013: Yüksek kullanım String.Split veya String.Substring kullanımı](../profiling/da0013-high-usage-of-string-split-or-string-substring.md)|System.String.Split veya System.String.Substring yöntemi çağrıları profil oluşturma verileri signifiicant bölümündedir. Bir alt dizesi dize varlığı için sınıyorsanız System.String.IndexOf veya System.String.IndexOfAny kullanmayı düşünün.|  
|[DA0014: aşırı yüksek hızda diske etkin bellek Sayfalaması](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md)|Profil oluşturma Çalıştır toplanan sistem performans verileri için ve diskten etkin bellek Sayfalaması bir son derece yüksek oranda çalıştırmak profil boyunca oluştuğunu gösterir. Disk belleği oranları genellikle bu düzeyde, uygulama performansı ve yanıt hızını etkiler. Bellek ayırma algoritmaları düzeltilmesi tarafından azaltmayı deneyin. Uygulamanızın bellek gereksinimleri göz önünde bulundurun gerekebilir. Daha fazla belleğe sahip bir bilgisayarda yeniden profil çalışıyor.|  
|[DA0017: diske etkin bellek Sayfalaması yüksek hızda](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|Profil oluşturma Çalıştır toplanan sistem performans verileri için ve diskten etkin bellek Sayfalaması bir yüksek oranda çalıştırmak profil boyunca oluştuğunu gösterir. Disk belleği oranları genellikle bu düzeyde, uygulama performansı ve yanıt hızını etkiler. Bellek ayırma algoritmaları düzeltilmesi tarafından azaltmayı deneyin. Uygulamanızın bellek gereksinimleri göz önünde bulundurun gerekebilir. Daha fazla belleğe sahip bir bilgisayarda yeniden profil çalışıyor.|  
|[DA0018: 32 bit uygulama çalışan işlemi tarafından yönetilen bellek sınırlarında](../profiling/da0018-32-bit-application-running-at-process-managed-memory-limits.md)|Profil oluşturma çalışması sırasında toplanan sistem verilerini, .NET Framework bellek yığınlardaki yönetilen yığınlardaki için bir 32 bit işlemde büyüyebilir en büyük boyutu yaklaşıldığında gösterir. Bildirilen değer profili süreci etkinken maksimum yığın değerini gözlenir. Uygulama tarafından yönetilen kaynaklarının kullanımını en iyi duruma getirme göz önünde bulundurun.|  
|[DA0021: Yüksek oranda Gen 1 çöp koleksiyonları](../profiling/da0021-high-rate-of-gen-1-garbage-collections.md)|1. nesil nesil 0 veri koleksiyonuna karşılaştırıldığında atık toplama içinde bellek for.NET Framework nesneleri önemli bir kısmının geri profil oluşturma sırasında toplanan sistem performans verilerini gösterir.|  
|[DA0022: Yüksek oranda Gen 2 çöp koleksiyonları](../profiling/da0022-high-rate-of-gen-2-garbage-collections.md)|2. nesil nesil 0 karşılaştırıldığında çöp toplama ve nesil 1 çöp koleksiyonları içinde bellek for.NET Framework nesneleri önemli bir kısmının geri profil oluşturma sırasında toplanan sistem performans verilerini gösterir.|  
|[DA0023: Yüksek GC CPU süresi](../profiling/da0023-high-gc-cpu-time.md)|Profil oluşturma sırasında toplanan sistem performans verileri, toplam uygulama işleme süresi ile karşılaştırıldığında, çöp toplama harcanan süre miktarını önemli olduğunu gösterir.|  
|[DA0024: Aşırı GC CPU süresi](../profiling/da0024-excessive-gc-cpu-time.md)|Profil oluşturma sırasında toplanan sistem performans verileri, toplam uygulama işleme zamanı ile karşılaştırıldığında, çöp toplama harcanan süre miktarını aşırı yüksek olduğunu gösterir.|  
|[DA0026: Aşırı Çekirdek CPU süresi işleme](../profiling/da0026-excessive-kernel-cpu-time-processing.md)|Çekirdek modunda yürütüldü oranı CPU süresi, kullanıcı modunda harcanan süreyi aştı. Yeniden profil oluşturma ve yüksek çekirdek modu yürütme sürelerinin nedenini belirlemek için sistem çağrıları (syscalls) sayısı örnekleme göz önünde bulundurun.|  
|[DA0029: Desteklenmeyen CLR sürümü](../profiling/da0029-unsupported-clr-version.md)|.NET Framework'te profil oluşturma araçları tarafından desteklenmeyen sürüm 1.1 kullanan bir uygulama profili çalışıyorsunuz.|  
|[DA0030: Veritabanı projeleri için katman etkileşim ölçümleri toplayın](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md)|Çağrılar <xref:System.Data> yöntemleridir profil oluşturma verileri önemli bir kısmının ve Çalıştır profil katman etkileşim verileri toplanmadı. Yeniden profil oluşturmak ve katman etkileşim verileri ekleme göz önünde bulundurun.|  
|[DA0038: Yüksek oranda kilit çakışmaları](../profiling/da0038-high-rate-of-lock-contentions.md)|Toplanan sistem performans verilerini profil oluşturma verileri, önemli ölçüde yüksek oranda kilit çakışmaları uygulama yürütmesi sırasında oluştuğunu gösterir. Yeniden çekişmeleri nedenini bulmak için eşzamanlılık profili oluşturma yöntemi kullanarak profil oluşturmayı düşünün.|  
|[DA0039: Çok yüksek oranda kilit çakışmaları](../profiling/da0039-very-high-rate-of-lock-contentions.md)|Toplanan sistem performans verilerini profil oluşturma verileri, bir aşırı yüksek oranda kilit çakışmaları uygulama yürütmesi sırasında oluştuğunu gösterir. Yeniden Çekişme nedenini bulmak için eşzamanlılık profili oluşturma yöntemi kullanarak profil oluşturmayı düşünün.|  
|[DA0501: Ortalama CPU kullanımının profili oluşturuluyor işlem.](../profiling/da0501-average-cpu-consumption-by-the-process-being-profiled.md)|Bu ileti bir işlemci yönergeleri uygulamadan çalıştırmakla meşgul zamanın yüzde olarak bildirir. Bildirilen ortalama profili oluşturuluyor işlem etkin olan tüm ölçüm aralıklarında değerdir. Değerini birden fazla işlemciye sahip bir makinede % 100'den büyük olabilir.|  
|[DA0502: Maksimum CPU kullanımının profili oluşturuluyor işlemi](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|Bu ileti, en yüksek işlemci yönergeleri uygulamadan çalıştırmakla meşgul zamanı yüzdesi bildirir. Profili oluşturuluyor işlem etkin olan tüm ölçüm aralıkları arasında bildirilen en büyük değeri bildirilen değerdir. Yüzde birden çok işlemciye sahip bir makinede % 100'den büyük olabilir.|  
|[DA0503: Ortalama çalışma kümesinin profili oluşturuluyor işlem için bayt cinsinden](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|Bu ileti ortalama işlem şu anda bayt (çalışma kümesi) kullanarak fiziksel bellek miktarını raporlar. İşlem çalışma kümesi şu anda fiziksel bellekte bulunan işlem adres alanından sayfaları temsil eder.|  
|[DA0504: En büyük çalışma kümesinin profili oluşturuluyor işlem için bayt cinsinden](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|Bu ileti en fazla bayt cinsinden işlem kullanmakta olduğu fiziksel bellek miktarını raporlar. İşlem çalışma kümesi şu anda fiziksel bellekte bulunan işlem adres alanından sayfaları temsil eder. Profil oluşturma etkinken bu kural işlemin çalışma kümesi için maksimum değeri bildirir.|  
|[DA0505: Ortalama özel bayt sayısının profili oluşturuluyor işlemi için ayrılmış](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|Bu ileti ortalama işlem bayt (özel bayt) şu anda ayrılmış sanal bellek miktarı bildirir. Özel bayt yalnızca işlem içinde çalışan iş parçacıkları tarafından erişilebilecek bir işlem tarafından ayrılan sanal bellek konumlarını temsil eder.|  
|[DA0506: Maksimum özel bayt sayısının profili oluşturuluyor işlemi için ayrılmış](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|Bu ileti en fazla işlem bayt (özel bayt) şu anda ayrılmış sanal bellek miktarı bildirir. Özel bayt yalnızca işlem içinde çalışan iş parçacıkları tarafından erişilebilecek bir işlem tarafından ayrılan sanal bellek konumlarını temsil eder.|