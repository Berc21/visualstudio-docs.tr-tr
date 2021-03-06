---
title: "Toplama ayrıntılı zamanlama verileri araçları kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Profiling Tools,instrumentation method
- instrumentation profiling method
ms.assetid: e9deb370-c459-45ac-84d3-14d646590d05
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7bc5b81349c64c3b3422fb16b9cf578d0b8496ea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="collecting-detailed-timing-data-by-using-instrumentation"></a>İzleme Kullanarak Ayrıntılı Zamanlama Verileri Toplama
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Profil oluşturma araçları izleme yöntemini profil kodu bir modülün bir kopyasını yerleştirir. Kodu her giriş, çıkış ve işlevlerin işlev çağrısı modülünde bir çalıştırma profili oluşturma sırasında kaydeder. Araçları yöntem kodunuzu bir bölümünü hakkında ayrıntılı zamanlama bilgi toplama ve girdi ve çıktı işlemleri uygulama performansı üzerindeki etkisini anlamak için kullanışlıdır.  
  
 Aşağıdaki yordamlardan birini kullanarak izleme yöntemini belirtebilirsiniz:  
  
-   Profil Oluşturma Sihirbazı'nın ilk sayfasında, seçin **Araçları**.  
  
-   Üzerinde **performans Gezgini** araç, **yöntemi** tıklatın **Araçları**.  
  
-   Üzerinde **genel** select performans oturumu için Özellikler iletişim kutusunun sayfası **Araçları**.  
  
## <a name="common-tasks"></a>Ortak Görevler  
 Ek seçenekler belirtebilirsiniz *Performans oturumunu***özellik sayfaları** performans oturumunun iletişim kutusu. Bu iletişim kutusunu açmak için:  
  
-   İçinde **performans Gezgini**, performans oturumu adına sağ tıklayın ve ardından **özellikleri**.  
  
 Aşağıdaki tabloda yer alan görevler, belirtebilirsiniz seçenekleri açıklanmıştır *Performans oturumunu***özellik sayfaları** izleme metodunu kullanarak profil, iletişim kutusu.  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|Üzerinde **genel** sayfasında .NET bellek ayırma ve yaşam verisi ekleyin ve oluşturulan profil oluşturma veri (.vsp) dosyası adlandırma ayrıntılarını belirtin.|-   [.NET bellek ayırma ve yaşam süresi verilerini toplama](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Nasıl yapılır: performans veri dosyası adlandırma seçeneklerini ayarlama](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Üzerinde **başlatma** sayfa birden fazla .exe projeleri, solution.specify başlatmak için uygulama ve başlangıç sıralarına varsa.|-   [Nasıl yapılır: başlatma için ikili dosya belirtme](../profiling/how-to-specify-the-binary-to-start.md)|  
|Üzerinde **ikili dosyaları** sayfasında, modüllerin Araçlı kopyaları için bir konum belirtin. Varsayılan olarak, tamamlanmış bir yedekleme klasörüne taşınır.|-   [Nasıl yapılır: izleme eklenmiş ikili dosyaları yeniden konumlandırma](../profiling/how-to-relocate-instrumented-binaries.md)|  
|Üzerinde **katman etkileşim** sayfasında, çalıştırmak profil ADO.NET çağrısı veri ekleyin.|-   [Katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md)|  
|Üzerinde **Araçları** sayfasında, ek yükü, profili oluşturma profili ASP.NET Web sayfalarında JavaScript kodu azaltmak için profil kısa işlevleri dışlama ve öncesinde ve sonrasında bir komut isteminde çalıştırmak için komutları belirtin izleme işlemi.|-   [Nasıl yapılır: hariç tutma veya kısa işlevleri izlemeden içerir](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)<br />-   [Nasıl yapılır: Web sayfalarında JavaScript kodu profili](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [Nasıl yapılır: ön ve son izleme komutları belirtme](../profiling/how-to-specify-pre-and-post-instrument-commands.md)|  
|Üzerinde **CPU sayaçları** sayfasında, profil oluşturma veri eklemek için bir veya daha fazla işleyici performans sayaçları belirtin.|-   [Nasıl yapılır: CPU sayaç verileri toplama](../profiling/how-to-collect-cpu-counter-data.md)|  
|Üzerinde **Windows olaylarını** sayfasında, örnekleme verileri toplamak için bir veya daha fazla olay izleme için Windows (ETW) olayları seçin.|-   [Nasıl yapılır: Windows (ETW) toplamak için olay izleme](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|  
|Üzerinde **Windows sayaçları** sayfasında, profil oluşturma verileri işaretleri olarak eklemek için bir veya daha fazla işletim sistemi performans sayaçları belirtin.|-   [Nasıl yapılır: Windows sayaç verileri toplama](../profiling/how-to-collect-windows-counter-data.md)|  
|Üzerinde **Gelişmiş** sayfasında, programa Vsınstr araçları da dahil etmek veya belirli işlevler hariç seçenekleri gibi geçirmek istediğiniz ek seçenekleri belirtin.|-   [Nasıl yapılır: ek izleme seçeneklerini belirtme](../profiling/how-to-specify-additional-instrumentation-options.md)<br />-   [Nasıl yapılır: belirli işlevler için araçları sınırlama](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [Vsınstr](../profiling/vsinstr.md)|