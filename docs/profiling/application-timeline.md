---
title: "Visual Studio'da XAML uygulamaları kaynak tüketimini çözümlemek | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df7d854b-0a28-45a9-8a64-c015a4327701
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 340ef03d7b9449f6fc9ee50a4c24afff03120e6f
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="analyze-resource-consumption-and-ui-thread-activity-xaml"></a>Kaynak tüketimini ve kullanıcı Arabirimi iş parçacığı etkinliği (XAML) çözümler.
Kullanım **uygulama zaman çizelgesi** bulmak ve uygulama etkileşim düzeltmek için Profil Oluşturucu ile ilgili performans sorunları XAML uygulamaları. Bu araç, uygulamaları kaynak tüketimini ayrıntılı bir görünümünü sağlayarak XAML uygulamalarının performansını artırmaya yardımcı olur. UI çerçeveler (düzeni ve işleme) hazırlama, ağ ve disk isteklere hizmet uygulamanızı ve uygulama başlatma, sayfa yükleme ve Windows yeniden boyutlandırma gibi senaryolarda zamanın analiz edebilirsiniz.  
  
 **Uygulama zaman çizelgesi** ile başlar araçları biri **hata ayıklama / Performans Profil Oluşturucu...**  komutu.  
  
 Bu araç değiştirir **XAML UI yanıtlama hızı** Visual Studio 2013 için tanılama araç takımı parçası olan aracı.  
  
 Aşağıdaki platformlarda bu aracı kullanabilirsiniz:  
  
1.  Evrensel Windows uygulamaları (üzerinde Windows 10)  
  
2.  Windows 8.1  
  
4.  Windows Presentation Foundation (.Net 4.0 ve üstü)  
  
5.  Windows 7  
  
> [!NOTE]
>  Toplamak ve CPU kullanım verilerini ve enerji Tüketim verileri ile birlikte çözümlemek **ApplicationTimeline** veri. Bkz: [ile veya olmadan hata ayıklayıcı Profil Araçları çalıştıran](../profiling/running-profiling-tools-with-or-without-the-debugger.md).
  
##  <a name="BKMK_Collect_Timeline_data_for_your_app"></a>Uygulama zaman çizelgesi verileri toplama  
 Yerel makinenize, bağlı bir aygıt, Visual Studio simulator veya Öykünücüler veya uzak bir aygıt, uygulamanızın yanıtlama hızı profil. Bkz: [ile veya olmadan hata ayıklayıcı Profil Araçları çalıştıran](../profiling/running-profiling-tools-with-or-without-the-debugger.md).
  
> [!TIP]
>  Mümkünse, doğrudan cihazda uygulamayı çalıştırın. Uygulama performansı simulator'da gözlenen veya bir Uzak Masaüstü Bağlantısı gerçek performans aygıtta aynı olmayabilir. Diğer taraftan, Visual Studio uzak araçlar kullanarak veri toplama performans verilerini etkilemez.  
  
 Temel adımlar şunlardır:  
  
1.  XAML uygulamanızı açın.  
  
2.  Tıklatın **hata ayıklama / Performans Profil Oluşturucu...** . Profil Araçları .diagsession penceresinde bir listesini görürsünüz.  
  
3.  Seçin **uygulama zaman çizelgesi** ve ardından **Başlat** pencerenin altındaki.  
  
    > [!NOTE]
    >  VsEtwCollector.exe çalıştırmak için izninizi isteyen bir kullanıcı hesabı denetimi penceresinde görebilirsiniz. **Evet**'i tıklayın.  
  
4.  Uygulamanızı performans verilerini toplamak için profil ilgilendiğiniz senaryosu çalıştırabilirsiniz.  
  
5.  Profil oluşturmayı durdurmak için geri .diagsession penceresine geçiş yapın ve **durdurmak** pencerenin üstündeki.  
  
     Visual Studio toplanan verileri analiz eder ve sonuçları görüntüler.  
  
     ![Zaman Çizelgesi Profil Oluşturucusu rapor](../profiling/media/timeline_base.png "TIMELINE_Base")  
  
##  <a name="BKMK_Analyze_Timeline_profiling_data"></a>Zaman Çizelgesi profil oluşturma verilerini analiz  
 Profil oluşturma verilerini topladıktan sonra analizinizi başlatmak için aşağıdaki adımları kullanabilirsiniz:  
  
1.  Bilgileri inceleyin **kullanıcı Arabirimi iş parçacığı kullanımı** ve **Visual işleme (FPS)** grafiklerde ve analiz etmek istediğiniz zaman aralığını seçin için zaman çizelgesi gezinti çubukları kullanın.  
  
2.  Bilgileri kullanarak **kullanıcı Arabirimi iş parçacığı kullanımı** veya **Visual işleme (FPS)** grafikler, ayrıntıları inceleyin **zaman çizelgesi ayrıntıları** olası nedenlerini bulmak için görünümü yanıt hızını görünen herhangi olmaması için.  
  
###  <a name="BKMK_Report_scenarios_categories_and_events"></a>Rapor senaryoları, kategoriler ve olaylar  
 **Uygulama zaman çizelgesi** aracı zamanlama verileri senaryoları, kategoriler ve XAML performansı ile ilgili olayları görüntüler.  
  
###  <a name="BKMK_Diagnostic_session_timeline"></a>Tanılama oturumu zaman çizelgesi  
 ![Performans ve tanılama zaman çizelgesi](../profiling/media/diaghub_timelinewithusermarks.png "DIAGHUB_TimelineWithUserMarks")  
  
 Sayfanın üstündeki cetvel profili bilgileri için zaman çizelgesi gösterir. Bu zaman çizelgesi hem de geçerli **kullanıcı Arabirimi iş parçacığı kullanımı** grafik ve **Visual verimlilik** grafik. Zaman çizelgesinin bir bölümü seçmek için, zaman çizelgesindeki gezinti çubuklarını sürükleyerek raporun kapsamını daraltabilirsiniz.  
  
 Zaman çizelgesi ayrıca, eklediğiniz kullanıcı işaretlerini ve uygulamanın etkinleştirme yaşam döngüsü olaylarını da görüntüler.  
  
###  <a name="BKMK_UI_thread_utilization_graph"></a>Kullanıcı Arabirimi iş parçacığı kullanım grafiği  
 ![CPU Utilization Graph](../profiling/media/timeline_cpuutilization.png "TIMELINE_CpuUtilization")  
  
 **Kullanıcı Arabirimi iş parçacığı kullanımı (%)** grafiktir sırasında toplama aralığı için bir kategori göreli harcanan süreyi görüntüler bir çubuk grafiği.  
  
###  <a name="BKMK_Visual_throughput_FPS_graph"></a>Görsel geçiş (FPS) grafiği  
 ![Görsel geçiş grafiği](../profiling/media/timeline_visualthroughput.png "TIMELINE_VisualThroughput")  
  
 **Visual işleme (FPS)** çizgi grafiği, uygulama için kullanıcı Arabirimi ve birleşim parçacığında kare / saniye (FPS) gösterir.  
  
###  <a name="BKMK_Timeline_details_"></a>Zaman Çizelgesi ayrıntıları  
 Ayrıntılar görünümü, burada çözümleme rapor zaman çoğunu harcama ' dir. CPU kullanımı UI çerçevesi alt sistemi veya CPU tüketilen sistem bileşeni tarafından kategorilere, uygulamanızın ayrıntılı görünümünü gösterir.  
  
 Aşağıdaki olaylar desteklenir:  
  
|||  
|-|-|  
|**Ayrıştırma**|Ayrıştırma XAML dosyaları ve oluşturma nesneleri için harcanan süre.<br /><br /> Genişleyen bir **ayrıştırma** düğümünde **zaman çizelgesi ayrıntıları** sonucunda kök olay Ayrıştırılan tüm XAML dosyaları bağımlılık zinciri görüntüler. Bu, gereksiz dosya ayrıştırma ve nesne oluşturma performans hassas senaryolarda tanımlamak ve bunları en iyi duruma getirmek olanak tanır.|  
|**Düzen**|Büyük uygulamalarda, aynı anda ekranda öğeleri binlerce gösterilebilir. Bu bir düşük UI kare hızı ve buna bağlı olarak zayıf uygulama yanıt hızını neden olabilir. Düzen olay doğru şekilde her öğe (Düzenle, ölçü, ApplyTemplate, ArrangeOverride ve ArrangeOverride harcanan zaman) düzenlemeyi maliyetini belirler ve bölüm düzeni geçişinde sürdü görsel ağaçlar oluşturur. Bu görselleştirmenin mantıksal ağaçları hangisinin ayıklama gerektiğini ya da diğer erteleme mekanizmaları düzeni geçişi en iyi duruma getirme değerlendirmek için kullanabilirsiniz.|  
|**İşleme**|Çizim XAML öğeleri ekranda geçirilen süre.|  
|**I/0**|Harcanan zamanı yerel diskten veya üzerinden erişilen ağ kaynaklarına veri alma [Microsoft Windows Internet (WinINet) API](https://msdn.microsoft.com/en-us/library/windows/desktop/aa385331.aspx).|  
|**Uygulama kodu**|Ayrıştırma veya düzenine ilgili olmayan uygulama (kullanıcı) kod çalıştırırken için harcanan süre.|  
|**XAML diğer**|XAML çalışma zamanı kod çalıştırırken için harcanan süre.|  
  
> [!TIP]
>  Seçin **CPU kullanımı** ile birlikte aracı **uygulama zaman çizelgesi** Aracı kullanıcı Arabirimi iş parçacığı üzerinde yürütme görünümü uygulama yöntemleri için profil oluşturma başlattığınızda. Uzun süre çalışan uygulama kodu bir arka plan iş parçacığı taşıma UI yanıt hızını artırabilir.  
  
####  <a name="BKMK_Customizing_Timeline_details_"></a>Zaman Çizelgesi ayrıntıları özelleştirme  
 Kullanım **zaman çizelgesi ayrıntıları** sıralama, filtreleme ve ek açıklamalar belirtmek için araç **zaman çizelgesi ayrıntıları** girişleri görüntüleyin.  
  
|||  
|-|-|  
|**Sıralama ölçütü**|Başlangıç saati veya olayları uzunluğunu göre sıralayın.|  
|![Olayları çerçevesi tarafından grup](../profiling/media/timeline_groupbyframes.png "TIMELINE_GroupByFrames")|Ekler veya bir üst düzey kaldırır **çerçeve** olayları çerçevesi tarafından grupları kategorisi.|  
|![Filtre zaman çizelgesi ayrıntıları listesi](../profiling/media/timeline_filter.png "TIMELINE_Filter")|Seçili kategorileri ve olayları uzunluğunu listeyi filtreler.|  
|![Zaman Çizelgesi ayrıntıları bilgileri özelleştirin](../profiling/media/timeline_viewsettings.png "TIMELINE_ViewSettings")|Ek açıklamalar olayları belirtmenize olanak sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF ekibi blogu: Yeni kullanıcı Arabirimi Performans Analizi aracını WPF uygulamaları için](http://blogs.msdn.com/b/wpf/archive/2015/01/16/new-ui-performance-analysis-tool-for-wpf-applications.aspx)  
 [C++, C# ve Visual Basic kullanarak UWP uygulamaları için performansı en iyi yöntemler](http://msdn.microsoft.com/en-us/567bcefa-5da5-4e42-a4b8-1358c71adfa2)   
 [WPF Uygulama Performansını İyileştirme](/dotnet/framework/wpf/advanced/optimizing-wpf-application-performance)  
 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Özellik turu profil oluşturma](../profiling/profiling-feature-tour.md)
