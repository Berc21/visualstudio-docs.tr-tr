---
title: "Nasıl yapılır: NET Framework uygulamasını hizmeti ve profil oluşturucu komut satırını kullanarak bellek verileri toplama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fa072fc-05fe-4420-99c0-51d2ea3ac4ce
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: bb9a80d81b05f759ef90f292bd4201103876aab3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-instrument-a-net-framework-service-and-collect-memory-data-by-using-the-profiler-command-line"></a>Nasıl yapılır: Profil Oluşturucu Komut Satırını Kullanarak .NET Framework Hizmetini İzleme ve Bellek Verileri Toplama
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Gereci için profil oluşturma araçları komut satırı araçları bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hizmet ve bellek kullanım verileri toplar. Bellek ayırma verileri toplayabilir veya bellek ayırma ve nesne yaşam verisi toplayabilirsiniz.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Bilgisayar başlatıldıktan sonra hizmeti yeniden başlatılamıyor, bir hizmeti izleme yöntemiyle profil olamaz, işletim sistemi başlatıldığında, bu tür bir hizmet başlatın.  
>   
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64 bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
## <a name="starting-the-profiling-session"></a>Profil oluşturma oturumu başlatılıyor  
 Performans verileri toplamak için bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hizmeti, kullandığınız [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) uygun ortam değişkenlerini başlatmak için araç ve [VSInstr.exe](../profiling/vsinstr.md) bir Araçlı oluşturmak için aracı Hizmet ikili dosyasının bir kopyası.  
  
 Profil oluşturma için yapılandırmak için hizmeti barındıran bilgisayarın yeniden başlatılması gerekir. Hizmet ayrıca el ile ve Hizmet Denetim Yöneticisi'nden başlamalıdır. Profil Oluşturucu başlatın ve sonra Başlat [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hizmet.  
  
 İzleme eklenmiş bileşen yürütüldüğünde, bellek verileri bir veri dosyası otomatik olarak toplanır. Duraklatma ve veri toplama sırasında profil oluşturma oturumu sürdürün.  
  
 Profil oluşturma oturumu sona erdirmek için hizmet kapatın ve açıkça profil oluşturucuyu kapatın. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizleme öneririz.  
  
#### <a name="to-begin-profiling-a-net-framework-service"></a>.NET Framework hizmet profil oluşturmayı başlatmak için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Kullanım **Vsınstr** hizmeti ikili Araçlı bir sürümünü oluşturmak için aracı.  
  
3.  Hizmet denetimi özgün ikili Araçlı sürümle için Yöneticisi'ni kullanın. Hizmet başlatma türünü manuel olarak ayarlandığından emin olun.  
  
4.  Profil oluşturma ortam değişkenleri başlatır. Tür:  
  
     **VSPerfClrEnv** {**/globaltracegc** &#124; **/globaltracegclife**}  
  
    -   **/globaltracegc** ve **/globaltracegclife** bellek ayırma ve nesne yaşam verisi toplama etkinleştirin.  
  
        |Seçenek|Açıklama|  
        |------------|-----------------|  
        |**/globaltracegc**|Bellek ayırma yalnızca verileri toplar.|  
        |**/globaltracegclife**|Bellek ayırma ve nesne yaşam verisi toplar.|  
  
5.  Bilgisayarı yeniden başlatın.  
  
6.  Bir komut istemi penceresi açın.  
  
7.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd**[/start](../profiling/start.md) **: izleme**[/çıkış](../profiling/output.md) **:** `OutputFile` [`Options`]  
  
    -   **/Başlat: çakışma** seçeneği profil oluşturucu başlatır.  
  
    -   **/Çıktı:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile`Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:sample** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri hizmetler için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|ASP.NET çalışan işlemin sahibi olan hesabın etki alanı ve kullanıcı adını belirtir. İşlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa, bu seçeneği gereklidir. İşlem sahibi, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma. ASP.NET uygulamasını farklı bir oturumda çalışıyorsa, bu seçeneği gereklidir. Oturum kimliği, Windows Görev Yöneticisi'nin İşlemler sekmesinde oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/waitstart](../profiling/waitstart.md)[**:**`Interval`]|Bir hata döndürmeden önce başlatmak profil oluşturucu için beklenecek saniye sayısını belirtir. Varsa `Interval` belirtilmezse, profil oluşturucu sonsuza kadar bekler. Varsayılan olarak, **/start** hemen döndürür.|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Profil Oluşturucu ile veri toplama başlatmak için duraklatıldı, ekleme **/globaloff** için seçenek **/start** komut satırı. Kullanım **/globalon** profil sürdürmek için.|  
    |[/ sayacı](../profiling/counter.md) **:**`Config`|İşlemci performansı sayaç yapılandırma dosyasında belirtilen bilgi toplar. Sayaç bilgileri her profil olay, toplanan veriler eklenir.|  
    |[/wincounter](../profiling/wincounter.md) **:**`WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:**`Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:**`Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
8.  Gerekirse, hizmeti başlatın.  
  
9. Hizmete profil oluşturucu ekleme. Tür:  
  
     **VSPerfCmd / ekleme:** `PID`&#124;`ProcessName`  
  
    -   İşlem kimliği veya hizmetin işlem adı belirtin. Windows Görev Yöneticisi'nde işlem kimlikleri ve adları tüm çalışan işlemleri görüntüleyebilirsiniz.  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hizmet çalışırken, başlatma ve durdurma dosya ile veri yazma tarafından veri toplama denetleyebilirsiniz **VSPerfCmd.exe** seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki çiftleri **VSPerfCmd** seçenekleri başlatma ve durdurma veri toplama. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**`PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:**`TID`|Başlatır (**/threadon**) veya durdurulduğunda (**/threadoff**) Kimlikli iş parçacığı tarafından belirtilen iş parçacığı için veri toplama (`TID`).|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için Kapat Araçlı bileşenini çalıştıran uygulama sonra Başlat **VSPerfCmd** [shutdown](../profiling/shutdown.md) profil oluşturucu kapatmak ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv /globaloff** komutu profil ortam değişkenleri temizler.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Hizmet Denetimi Yöneticisi'nden hizmetini durdurun.  
  
2.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd Shutdown**  
  
3.  Tüm profil oluşturmayı tamamladıktan sonra profil ortam değişkenleri temizleyin. Tür:  
  
     **VSPerfClrEnv /globaloff**  
  
     İzleme eklenmiş modülü özgün ile değiştirin. Gerekirse, hizmet başlangıç türünü yeniden yapılandırın.  
  
4.  Bilgisayarı yeniden başlatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)   
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)