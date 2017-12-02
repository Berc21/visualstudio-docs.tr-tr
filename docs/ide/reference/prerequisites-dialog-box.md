---
title: "Önkoşullar iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Microsoft.VisualStudio.Publish.BaseProvider.Dialog.Bootstrapper
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords: Prerequisites dialog box
ms.assetid: 53ac863c-77a0-409b-91e5-7a4bd8b8474e
caps.latest.revision: "75"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 68e326d8045733fc4f491c51405ed51414a92afd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="prerequisites-dialog-box"></a>Önkoşullar İletişim Kutusu
Bu iletişim kutusu, hangi önkoşul bileşenlerinin yüklü olduğu, nasıl yükleneceğini ve paketleri yüklü olan sıra belirtir.  
  
 Bu iletişim kutusunu erişmek için bir proje düğümünde seçin **Çözüm Gezgini**ve ardından **proje** menüsünde tıklatın **özellikleri**. Zaman **Proje Tasarımcısı** görünen tıklatın **Yayımla** sekmesi. Üzerinde **Yayımla** sayfasında, **Önkoşullar**. Kurulum projeleri için üzerinde **proje** menüsünde tıklatın **özellikleri**. Zaman **özellik sayfaları** iletişim kutusu görüntülenirse, tıklatın **Önkoşullar**.  
  
## <a name="uielement-list"></a>UIElement Listesi  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|**Önkoşul bileşenlerini yüklemek için Kurulum programını oluşturun**|Böylece, uygulamanızda bağımlılık sırasını önce yüklenecek önkoşul bileşenleri uygulamanızın Kurulum programını (Setup.exe) içerir. Varsayılan olarak, bu seçenek seçilidir. Seçilmezse, hiçbir Setup.exe oluşturulur.|  
|**Yüklemek için hangi Önkoşullar seçin**|Bileşenleri gibi yüklenip yüklenmeyeceğini belirtir [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)], Crystal Reports ve benzeri.<br /><br /> Örneğin, onay kutusunu seçerek yanına **SQL Server 2005 Express Edition SP2**, Kurulum programı bu bileşen hedef bilgisayar üzerinde yüklü olduğundan ve zaten yüklü değilse yükleyin olup olmadığını doğrulayın belirtin.<br /><br /> Önkoşul her paket hakkında ayrıntılı bilgi için bu konunun ilerleyen bölümlerinde önkoşul bilgilerini tabloya bakın.|  
|**Microsoft Update için daha yeniden dağıtılabilir bileşenleri seçin**|Bu bağlantıya tıkladıklarında, alan için [bileşenleri yeniden dağıtmak için önyükleyici paketleri](http://go.microsoft.com/fwlink/?LinkId=208835) güncelleştirmeleri denetlemek için Web sitesi.|  
|**Bileşen satıcısının web sitesinden önkoşulları**|Önkoşul bileşenlerinin satıcısının Web sitesinden yüklenmesini belirtir. Varsayılan seçenek budur.|  
|**Önkoşulları Uygulamamla aynı konumdan indir**|Önkoşul bileşenlerinin uygulamayla aynı konumda yüklenmesini belirtir. Bu, tüm önkoşul yayımlama konumuna kopyalar. Bu seçeneğin çalışması için önkoşul paketleri geliştirme bilgisayarında olmalıdır.|  
|**Önkoşulları aşağıdaki konumdan indir**|Ön koşul bileşenleri seçtiğiniz konumdan yüklenmesi belirtir. Kullanabileceğiniz **Gözat** düğmesine tıklayarak bir konum seçin.|  
  
## <a name="prerequisites-information"></a>Önkoşul bilgileri  
 Görünür önkoşul bileşenleri **Önkoşullar** iletişim kutusu aşağıdaki listede arasından farklı. Listelenen önkoşul **Önkoşullar iletişim kutusu** ilk kez iletişim kutusunu açtığınızda otomatik olarak ayarlanır. Projenin hedef çerçevesi daha sonra değiştirirseniz, yeni hedef Framework'ü el ile eşleşecek şekilde önkoşulları gerekecektir.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|**.NET framework 3.5 SP1**|Bu paket aşağıdaki yükler:<br /><br /> -.NET framework sürüm 2.0, 3.0 ve 3.5.<br />-(X86) ve 64-bit (x64) 32-bit işletim sistemlerinde tüm .NET Framework sürümleri için destek.<br />-Dil paketleri paket ile yüklenen her bir .NET Framework sürümü için.<br />-Hizmet paketleri .NET Framework 2.0 ve 3.0 için.<br /><br /> .NET framework 3.0, Windows Vista ile eklenir ve .NET Framework 3.5 ile birlikte [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. 32-bit işletim sistemleri ve hedef Framework'ü kümesi için derlenmiş tüm Visual Basic ve Visual C# projeleri için .NET framework 3.5 gereklidir **.NET Framework 3.5**ve Visual Basic ve Visual C# projeleri 64-bit işletim sistemleri için derlenmiş. (IA64 desteklenmiyor.) Varsayılan olarak tüm CPU mimarisi için Visual Basic ve Visual C# projeleri derlenmiş unutmayın. Daha fazla bilgi için bkz: [Visual Studio çoklu sürüm desteğine genel bakış](../../ide/visual-studio-multi-targeting-overview.md), [.NET Framework yeniden dağıtma](http://msdn.microsoft.com/en-us/a18d0456-fd89-493e-97f4-756505bfe287), ve [64-bit uygulamalar için önkoşulları dağıtma](../../deployment/deploying-prerequisites-for-64-bit-applications.md).<br /><br /> Varsayılan olarak, bu öğe seçilir.|  
|**.NET framework 3.5 SP1 istemci profili**|.NET Framework istemci profili tam .NET Framework 3.5 istemci uygulamaları hedefleyen SP1 bir alt kümesidir. Windows Presentation Foundation (WPF), Windows Formları, Windows Communication Foundation (WCF) ve ClickOnce özellikleri kolaylaştırılmış kümesini sağlar. Bu hızlı dağıtım senaryoları WPF, Windows Forms, WCF ve konsol uygulamaları için .NET Framework istemci profili hedefleyen sağlar. Daha fazla bilgi için bkz: [.NET Framework istemci profili](/dotnet/framework/deployment/client-profile).|  
|**Microsoft .NET Framework 4 (x86 hem x64)**|Bu paketi x86 hem x64 platformlar için .NET Framework 4 yükler.<br /><br /> Daha fazla bilgi için bkz: [Visual Studio çoklu sürüm desteğine genel bakış](../../ide/visual-studio-multi-targeting-overview.md), [.NET Framework yeniden dağıtma](http://msdn.microsoft.com/en-us/a18d0456-fd89-493e-97f4-756505bfe287), ve [64-bit uygulamalar için önkoşulları dağıtma](../../deployment/deploying-prerequisites-for-64-bit-applications.md).<br /><br /> Varsayılan olarak, bu öğe seçilir.|  
|**Microsoft .NET Framework 4 istemci profili (x86 hem x64)**|.NET Framework 4 istemci profili istemci uygulamaları hedefler tam .NET Framework 4'ün bir alt kümesidir. Windows Presentation Foundation (WPF), Windows Formları, Windows Communication Foundation (WCF) ve ClickOnce özellikleri kolaylaştırılmış kümesini sağlar. Bu hızlı dağıtım senaryoları WPF, Windows Forms ve konsol uygulamaları için .NET Framework 4 istemci profili hedefleyen sağlar. Daha fazla bilgi için bkz: [.NET Framework istemci profili](/dotnet/framework/deployment/client-profile).|  
|**Microsoft Office 2007 birincil birlikte çalışma derlemeleri**|Bu paket için 2007 birincil birlikte çalışma derlemeleri yükler Microsoft Office ürünlerinin. Birincil birlikte çalışma derlemesi bir Microsoft Office uygulamasının COM tabanlı nesne modeli ile etkileşim kurmak yönetilen kod sağlar. Daha fazla bilgi için bkz: [Office birincil birlikte çalışma derlemeleri](/office-dev/office-dev/office-primary-interop-assemblies).|  
|**Microsoft Visual Basic PowerPacks sürüm 10.0**|Power Packs eklentiler, denetimleri, bileşenleri ve araçları, Visual Basic uygulamalarını geliştirmeye yardımcı olmak için ' dir. Bu sürüm içerir <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> sağlayan bir Windows formunda içeriğini yazdırmak, bileşeni ve değiştirilmemiş çalıştırmak Visual Basic 6.0 yazıcı kod etkinleştirir yazıcı uyumluluk kitaplığı.|  
|**.NET 2.0 için Microsoft Visual F # çalışma zamanı**|Visual F # çalışma zamanı kitaplıkları x86 hem x64 işletim geleneksel nesne yönelimli ve kesinlik temelli (yordamsal) programlamaya yanı sıra işlevsel programlama için destek sağlayan sistemleri için bu paketi yükler. Uygulama veya onun bileşenleri yazılan durumunda Visual F # ve .NET Framework 2.0, .NET Framework 3.0 veya .NET Framework 3.5 bu paketin yüklenmesi gerekir.<br /><br /> Daha fazla bilgi için bkz: [F # dili başvurusu](http://msdn.microsoft.com/Library/16b706f8-b5f2-4ff7-b2c1-64df33cd6adf).|  
|**.NET 4.0 için Microsoft Visual F # çalışma zamanı**|Visual F # çalışma zamanı kitaplıkları x86 hem x64 işletim geleneksel nesne yönelimli ve kesinlik temelli (yordamsal) programlamaya yanı sıra işlevsel programlama için destek sağlayan sistemleri için bu paketi yükler. Uygulama veya onun bileşenleri yazılan durumunda Visual F # ve .NET Framework 4 bu paketin yüklenmesi gerekir.<br /><br /> Daha fazla bilgi için bkz: [F # dili başvurusu](http://msdn.microsoft.com/Library/16b706f8-b5f2-4ff7-b2c1-64df33cd6adf).|  
|**Microsoft Visual Studio 2010 Rapor Görüntüleyicisi**|Bu paket, raporlama Windows Forms ve ASP.NET uygulamaları için zengin veri eklemek için kullanabileceğiniz Rapor Görüntüleyicisi denetimleri yükler.|  
|**Office çalışma zamanı (x86 hem x64) için Microsoft Visual Studio 2010**|Visual Studio'da Office geliştirici araçları ile Microsoft Office özelleştirilmiş işletme çözümleri oluşturmak için kullanımı kolay, tümleşik araçlar sunar. Bir kullanıcı arabirimi olarak Office uygulamalarını kullanmaktadır yönetilen, akıllı istemci çözümleri oluşturabilirsiniz. Dağıtım ve Bakım kolayca güvenli çözümler oluşturmak geliştiriciler araçları sağlar.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: Office çözümünü kullanarak ClickOnce tarafından yayımlama](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8).|  
|**SQL Server 2005 Express Edition SP2 (x 86)**|Microsoft SQL Server 2005 Express Edition SP2, temel aldığı veritabanı uygulaması bu paketi yükler [!INCLUDE[sqprsqext](../../ide/reference/includes/sqprsqext_md.md)]. SQL Server Express, Microsoft SQL Server Desktop Engine (MSDE) için yerini almıştır. SQL Server Express ücretsizdir ve (sözleşmenize tabidir) yeniden dağıtılabilir ve hem istemci veritabanı hem de bir temel sunucu veritabanı olarak çalışır. Bu SQL Server 2005, aşağıdaki farklar dışında aynıdır:<br /><br /> -Hiçbir kurumsal özelliklerini destekler.<br />-Bir CPU sınırlıdır.<br />-arabellek havuzu için 1 gigabayt (GB) bellek sınırı.<br />-4 GB veritabanları için en büyük boyutu.|  
|**SQL Server 2008 Express**|Bu paket, Microsoft SQL Server 2008 Express, Microsoft SQL Server 2008, küçük bir web, sunucu veya Masaüstü uygulamaları için ideal bir veritabanı boş bir sürümünü yükler. Ücretsiz geliştirme ve üretim için kullanılabilir. Ücretsiz [kayıt](http://go.microsoft.com/fwlink/?LinkId=130380) SQL Server 2008 Express uygulama ile dağıtmak için gereklidir.<br /><br /> Önyükleyici davranışını aşağıda verilmiştir:<br /><br /> -Bilgisayarda SQL Server 2008 Express ya da daha sonra varsa, SQL Server 2008 Express veya daha sonra bilgisayar kalır.<br />-Bilgisayar herhangi bir sürümü SQL Server 2008 Express veya üzeri yoksa, paketin en son SQL Server 2008 Express SP1 sürümünü yükler.<br /><br /> SQL Server 2008 Express hakkında daha fazla bilgi için [http://go.microsoft.com/fwlink/?LinkId=183586](http://go.microsoft.com/fwlink/?LinkId=183586).|  
|**Visual C++ 2010 Çalışma zamanı kitaplıkları (IA64)**|Microsoft Windows işletim sistemi için programlama için yordamlar sağlayan Visual C++ çalışma zamanı kitaplıkları Itanium mimarisi için bu paketi yükler. Bu yordamlar C ve C++ dilleri tarafından sağlanmayan birçok genel programlama görevleri otomatik hale getirme.<br /><br /> Daha fazla bilgi için bkz: [C çalışma zamanı kitaplığı başvurusu](/cpp/c-runtime-library/c-run-time-library-reference).|  
|**Visual C++ 2010 Çalışma zamanı kitaplıkları (x64)**|Bu paket Microsoft Windows işletim sistemi için programlama için yordamlar sağlar sistemleri işletim x64 için Visual C++ çalışma zamanı kitaplıkları yükler. Bu yordamlar C ve C++ dilleri tarafından sağlanmayan birçok genel programlama görevleri otomatik hale getirme.<br /><br /> Daha fazla bilgi için bkz: [C çalışma zamanı kitaplığı başvurusu](/cpp/c-runtime-library/c-run-time-library-reference).|  
|**Visual C++ 2010 Çalışma zamanı kitaplıkları (x86)**|Bu paket Microsoft Windows işletim sistemi için programlama için yordamlar sağlar sistemleri işletim x86 için Visual C++ çalışma zamanı kitaplıkları yükler. Bu yordamlar C ve C++ dilleri tarafından sağlanmayan birçok genel programlama görevleri otomatik hale getirme.<br /><br /> Daha fazla bilgi için bkz: [C çalışma zamanı kitaplığı başvurusu](/cpp/c-runtime-library/c-run-time-library-reference).|  
|**Windows Installer 3.1**|Windows Installer Kurulum projeleri yüklemesini sağlayan Microsoft Windows Installer yeniden dağıtılabilir, sürüm 3.1, bu paketi yükler. Windows Server 2003 SP1 ve sonraki sürümleriyle birlikte önceden yüklenir.<br /><br /> Varsayılan olarak, bu öğe seçilir.|  
|**Windows Installer 4.5**|Bu paketi Windows Installer Kurulum projeleri yüklemesini sağlayan Microsoft Windows Installer yeniden dağıtılabilir, sürüm 4.5 yükler.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yayımla Sayfası, Proje Tasarımcısı](../../ide/reference/publish-page-project-designer.md)   
 [Uygulama dağıtımının önkoşulları](../../deployment/application-deployment-prerequisites.md)   
 [.NET Framework yeniden dağıtma](http://msdn.microsoft.com/en-us/a18d0456-fd89-493e-97f4-756505bfe287)   
 [64-bit uygulamalar için önkoşulları dağıtma](../../deployment/deploying-prerequisites-for-64-bit-applications.md)   
 [Visual Studio çoklu sürüm desteğine genel bakış](../../ide/visual-studio-multi-targeting-overview.md)