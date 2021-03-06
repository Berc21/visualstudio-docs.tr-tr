---
title: "Genel Performans oturumunu ayarlama seçenekleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.general
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 36e27189102fbab8e698320c49bd008adf1eda50
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="setting-general-performance-session-options"></a>Genel Performans Oturumunu Ayarlama Seçenekleri

Koleksiyon yöntemini ve Visual Studio Profil Araçları performans oturumu için profil oluşturma veri adlandırma kuralları ayarlayabilirsiniz **genel** performans oturumu için Özellikler iletişim kutusunun sayfası. Bu iletişim kutusu açmak için **performans Gezgini**, performans oturumu sağ tıklatın ve ardından **özellikleri**.

## <a name="choosing-data-collection-methods"></a>Veri toplama yöntemi seçme

Altındaki seçeneklerden birini seçerek temel toplama yöntemi ayarlayın **koleksiyonu profil**. Aşağıdaki tabloda aşağıdaki seçenekleri açıklanmıştır:

|||
|-|-|
|**Örnekleme**. Örnekleme yöntemi düzenli aralıklarla profil bilgilerini toplar. Bu yöntem, işlemci kullanım sorunları bulmak için yararlıdır ve çoğu performans araştırmalar başlatmak için önerilen yöntemdir.|- [Örnekleme kullanarak performans istatistikleri toplama](../profiling/collecting-performance-statistics-by-using-sampling.md)|
|**İzleme**. İzleme yöntemi her giriş, çıkış ve işlevlerin işlev çağrısı modülünde bir çalıştırma profili oluşturma sırasında kaydeder kod profili oluşturma bir modülün bir kopyasını içine yerleştirir. Bu yöntem, kodunuzu bir bölümünü hakkında ayrıntılı zamanlama bilgi toplama ve girdi ve çıktı işlemleri uygulama performansı üzerindeki etkisini anlamak için kullanışlıdır.|- [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)|
|**Eşzamanlılık**. Eşzamanlılık yöntemi blokları yürütme gibi bir iş parçacığı zaman bekler, kodunuzu boşaltılacak Uygulama kaynağı erişimi kilitli her olay için verileri toplar. Bu yöntem, çok iş parçacıklı uygulamalar çözümlemek için kullanışlıdır.|- [İş parçacığı ve işlem eşzamanlılık verileri toplama](../profiling/collecting-thread-and-process-concurrency-data.md)|

 Örnekleme veya izleme yöntemleri kullanarak .NET bellek verileri toplayabilir. Altında veri türünü seçin **.NET bellek profili oluşturma**.

|||
|-|-|
|**.NET nesne ayırma bilgilerini toplamak**. Varsayılan olarak, veri sayısını ve boyutunu tahsis edilen nesnelerin içerir. Seçin veya etkinleştirmek veya .NET bellek verileri toplama devre dışı bırakmak için bu onay kutusunu temizleyin.<br /><br /> **Ayrıca .NET nesne ömrü bilgileri toplamak**. Bellek nesneleri geri kazanmak için kullanılan atık toplama nesli hakkındaki verileri eklemek için bu onay kutusunu seçin.|- [.NET bellek ayırma ve yaşam süresi verilerini toplama](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)|

 Burada, duraklatma, sürdürme ve profil oluşturmayı durdurmak, bir uygulamaya profil başladığında bir profil oluşturma oturumu sayfası görüntülenir.

 ![Profil oluşturma oturumu sayfa](../profiling/media/prof_profilingsessionpage.png "PROF_ProfilingSessionPage")

## <a name="setting-profiling-data-file-options"></a>Profil oluşturma veri dosyası seçeneklerini ayarlama

|||
|-|-|
|**Rapor**. Varsayılan olarak, profil oluşturma veri (.vsp) dosyası profili uygulamanın adı verilir ve çözüm ya da proje klasöründe bulunur. Bir tarih dizesi de ada eklenir ve artan bir sayı yinelenen adları Aksi durumda olması gereken veri dosyalarına eklenir. Bu seçenekleri değiştirebilirsiniz.|- [Nasıl yapılır: performans veri dosyası adlandırma seçeneklerini ayarlama](../profiling/how-to-set-performance-data-file-name-options.md)|