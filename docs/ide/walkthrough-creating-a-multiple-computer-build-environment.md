---
title: "İzlenecek yol: ortam derleme birden çok bilgisayarda oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, building on multiple computers
- build environment, MSBuild
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 65b4394b0f06dbcf995e8924833870a455bba348
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="walkthrough-creating-a-multiple-computer-build-environment"></a>İzlenecek yol: Birden Çok Bilgisayarda Derleme Ortamı Oluşturma

Visual Studio bir ana bilgisayara yükleyerek bir yapı ortamı kuruluşunuz içinde oluşturabilir ve böylece katılabilmesi için çeşitli dosyalarını ve ayarlarını başka bir bilgisayara ardından kopyalama oluşturur. Visual Studio diğer bir bilgisayara yüklemeniz gerekmez.

Bu belge hakları yazılım dışarıdan yeniden dağıtmanız veya üçüncü taraflara derleme ortamları sağlamak amacıyla confer değil.

> Sorumluluk reddi<br /><br /> Bu belgede sağlanan bir "olarak-olan" olarak. Özetlenen adımları Test ettiğimiz olsa da, her yapılandırma ayrıntısına sınanacak yapamıyoruz. Belge öğrenilen ek bilgileri ile güncel kalmasını dener. URL ve diğer Internet Web sitesi başvuruları dahil olmak üzere bu belgede belirtilen bilgiler ve görüntüler bildirim yapılmadan değiştirilebilir. Microsoft veya burada belirtilen bilgiler göre zımni hiçbir garanti vermez. Kullanım riski size aittir.<br /><br /> Bu belge, herhangi bir Microsoft ürünü üzerinde hiçbir fikri mülkiyet hakkı sağlamaz. Kopyalayabilir ve bu belgeyi şirket içinde kullanmak başvuru amaçlıdır.<br /><br /> Microsoft hiçbir öneride bulunmak, Yorumlar ya da bu belgeye ilişkin diğer geribildirim ("geri bildirim") vermek için zorunda değilsiniz. Ancak, gönüllü sağladığınız geribildirim Microsoft Products ve ilgili özellikleri ya da hangi sırayla bağlı kendi ürünlerini geliştirmek için diğer üçüncü taraflarca dayanıyordu diğer belgeleri (topluca "Microsoft Offerings") kullanılabilir. Buna uygun olarak, bu belgenin ya da Microsoft uygulandıkları Offerings herhangi bir sürümü üzerinde Feedback verirseniz, kabul: (a) Microsoft serbestçe kullanın, yeniden oluşturma, lisans, dağıtmak ve aksi durumda herhangi bir Microsoft görüşlerinize tanımış olursunuz Teklifi; (b), ayrıca olmadan üçüncü taraflara, ücretsiz olarak, yalnızca diğer ürünleri kullanın veya sizin Geribildiriminiz içeren herhangi belirli kısımlarını bir Microsoft Product ile arabirim oluşturmak üzere etkinleştirmek gerekli olan patent haklarını vermeniz; ve (c) ederiz düşünmek için bir neden olan Microsoft'a (i) herhangi bir patent, telif hakkı veya diğer fikri mülkiyet talep veya herhangi bir üçüncü taraf sağındaki tabi olan Microsoft veremezsiniz; veya herhangi bir Microsoft Offering geribildirimler veya böyle geri bildirim veya diğer Microsoft fikri mülkiyet için lisanslı veya aksi türetilmiş Lisans Koşulları'nı (II) konu ile herhangi bir üçüncü taraf paylaşılan.

Bu kılavuz, aşağıdaki işletim sistemlerinden karşı MSBuild komut satırında yürütme ve Team Foundation Build kullanarak doğrulandı.

- Windows 8 (x86 ve x64)
- Windows 7 Ultimate
- Windows Server 2008 R2 Standard

 Bu izlenecek adımları tamamladıktan sonra bu tür uygulamalar oluşturmak için birden çok bilgisayarda ortamı kullanabilirsiniz:

- Windows 8 SDK'yı C++ Masaüstü uygulamaları
- .NET Framework 4. 5'i hedefleyen Visual Basic veya C# Masaüstü uygulamaları

 Birden çok bilgisayarda ortamı, bu tür uygulamalar oluşturmak için kullanılamaz:

- UWP uygulamalar. UWP uygulamalar oluşturmak için Visual Studio derleme bilgisayara yüklemeniz gerekir.
- .NET Framework 4 veya önceki hedef Masaüstü uygulamaları. Bu tür uygulamalar oluşturmak için ya da Visual Studio veya .NET başvurusu derlemeler ve araçlar (SDK'dan Windows 7.1) yapı bilgisayara yüklemeniz gerekir.

 Bu kılavuzda, bu iki bölüme ayrılır:

- [Bilgisayarlara yazılım yükleme](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#InstallingSoftware)

- [Ana bilgisayardan yapı bilgisayara dosyaları kopyalama](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CopyingFiles)

- [Kayıt defteri ayarları oluşturma](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CreatingRegistry)

- [Yapı bilgisayarında ortam değişkenlerini ayarlama](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#SettingEnvVariables)

- [İçin Genel Derleme Önbelleği (GAC) ve yapı bilgisayarında MSBuild derlemeleri yükleme](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#InstallingMSBuildToGAC)

- [Proje oluşturma](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#BuildingProjects)

- [Böylece kaynak denetimine iade derleme ortamı oluşturma](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CreatingForSourceControl)

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio yüklü .NET masaüstü geliştirme iş yükü ile.

## <a name="InstallingSoftware">Bilgisayarlara yazılım yükleme</a>

İlk olarak, ana bilgisayarın ayarlarını yapın ve yapı bilgisayarın ayarlarını yapın.

Visual Studio ana bilgisayara yükleyerek, dosya ve yapı bilgisayarı daha sonra kopyalayacak ayarları oluşturun. Visual Studio yükleyebileceğiniz bir x86 veya bir x64 bilgisayar ancak derleme bilgisayarın mimarisine ana bilgisayarın mimarisiyle eşleşmelidir.

1. Visual Studio ana bilgisayara yükleyin.

2. Yapı bilgisayarda .NET Framework 4.5 yükleyin. Yüklü olduğunu doğrulamak için kayıt defteri değerini HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework anahtar emin olun Setup\NDP\v4\Full@Version "4.5" ile başlar.

## <a name="CopyingFiles">Ana bilgisayardan yapı bilgisayara dosyaları kopyalama</a>

Bu bölüm, belirli dosyaları, derleyicileri, derleme araçları, MSBuild varlıklar ve ana bilgisayardan kayıt defteri ayarları derleme bilgisayara kopyalama kapsar. Bu yönergeler, Visual Studio ana bilgisayarda varsayılan konumda yüklediğiniz varsayılır; başka bir konumda yüklü değilse, adımları uygun şekilde ayarlayın.

- Bir x86 üzerinde bilgisayar, varsayılan konumu C:\Program Files\Microsoft Visual Studio 11.0\:
- X x64 üzerinde bilgisayar, varsayılan konumu C:\Program Files (x86) \Microsoft Visual Studio 11.0\:

Program dosyaları klasörü adı yüklü olan işletim sistemine bağlıdır dikkat edin. Bir x86 üzerinde bilgisayar adıdır \Program Files\\; x x64 bilgisayar adıdır \Program Files (x86)\\. Sistem Mimarisi bağımsız olarak, bu kılavuzda Program dosyaları klasörü % ProgramFiles % gösterir.

> [!NOTE]
> Yapı bilgisayarında tüm ilgili dosyaları aynı sürücüde olmalıdır; Ancak, bu sürücünün sürücü harfini Visual Studio ana bilgisayarında yüklü olduğu sürücü için sürücü harfi farklı olabilir. Her iki durumda da, bu belgenin sonraki bölümlerinde açıklanan kayıt defteri girdileri oluşturduğunuzda dosyalarının konumunu dikkate alması gerekir.

#### <a name="to-copy-the-windows-sdk-files-to-the-build-computer"></a>Yapı bilgisayara Windows SDK dosyaları kopyalamak için

1. Yalnızca SDK Windows 8 için Windows yüklü varsa, bu klasörleri yinelemeli olarak ana bilgisayardan yapı bilgisayara kopyalayın:

    - %ProgramFiles%\Windows Kits\8.0\bin\

    - %ProgramFiles%\Windows Kits\8.0\Catalogs\

    - %ProgramFiles%\Windows Kits\8.0\DesignTime\

    - %ProgramFiles%\Windows Kits\8.0\include\

    - %ProgramFiles%\Windows Kits\8.0\Lib\

    - %ProgramFiles%\Windows Kits\8.0\Redist\

    - %ProgramFiles%\Windows Kits\8.0\References\

     Ayrıca bu diğer Windows 8 Setleri varsa...

    - Microsoft Windows değerlendirme ve Dağıtım Seti

    - Microsoft Windows Sürücü paketi

    - Microsoft Windows Donanım onay Seti

     .. yapılandırılmıştır yüklü olan dosyalar önceki adımda listelenen %ProgramFiles%\Windows Kits\8.0\ klasörlere ve lisans koşullarını bu dosyaları için yapı server hakları izin vermeyebilir. Dosyaları yapı bilgisayarınıza kopyalanan olup olmadığını doğrulamak her yüklü Windows Seti için Lisans Koşulları'nı denetleyin. Lisans Koşulları'nı yapı server hakları izin verme dosyaları yapı bilgisayardan kaldırın.

2. Aşağıdaki klasörler yinelemeli olarak ana bilgisayardan yapı bilgisayara kopyalayın:

    - %ProgramFiles%\Microsoft SDKs\Windows\v8.0A\bin\NETFX 4.0 Tools\

    - %ProgramFiles%\Common Files\Merge Modules\

    - %ProgramFiles%\Microsoft Visual Studio 11.0\VC\

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\Tools\ProjectComponents\

    - %ProgramFiles%\MSBuild\Microsoft.Cpp\v4.0\V110\

    - %ProgramFiles%\Reference Assemblies\Microsoft\Framework\\.NETCore\v4.5\

    - %ProgramFiles%\Reference Assemblies\Microsoft\Framework\\.NETFramework\v4.5\

3. Bu dosyalar ana bilgisayardan yapı bilgisayara kopyalayın:

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\msobj110.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\mspdb110.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\mspdbcore.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\mspdbsrv.exe

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\msvcdis110.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\Tools\makehm.exe

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\Tools\VCVarsQueryRegistry.bat

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\Tools\vsvars32.bat

4. Yalnızca derleme çıkışları yapı bilgisayarında çalıştırırsanız aşağıdaki Visual C++ çalışma zamanı kitaplıkları gereklidir — Örneğin, otomatik test parçası olarak. Dosyalar genellikle %ProgramFiles%\Microsoft Visual Studio 11.0\VC\redist\x86\ veya sistem mimarisi bağlı olarak %ProgramFiles%\Microsoft Visual Studio 11.0\VC\redist\x64\ klasörü altında alt klasörler bulunur. X86 üzerinde sistemleri, \Windows\System32\ klasörüne kopyala x86 ikili dosyaları. X64 üzerinde sistemleri, kopya x86 ikili Windows\SysWOW64\ klasörü ve x64 Windows\System32\ klasörüne ikili dosyaları.

    - \Microsoft.VC110.ATL\atl110.dll

    - \Microsoft.VC110.CRT\msvcp110.dll

    - \Microsoft.VC110.CRT\msvcr110.dll

    - \Microsoft.VC110.CXXAMP\vcamp110.dll

    - \Microsoft.VC110.MFC\mfc110.dll

    - \Microsoft.VC110.MFC\mfc110u.dll

    - \Microsoft.VC110.MFC\mfcm110.dll

    - \Microsoft.VC110.MFC\mfcm110u.dll

    - \Microsoft.VC110.MFCLOC\mfc110chs.dll

    - \Microsoft.VC110.MFCLOC\mfc110cht.dll

    - \Microsoft.VC110.MFCLOC\mfc110deu.dll

    - \Microsoft.VC110.MFCLOC\mfc110enu.dll

    - \Microsoft.VC110.MFCLOC\mfc110esn.dll

    - \Microsoft.VC110.MFCLOC\mfc110fra.dll

    - \Microsoft.VC110.MFCLOC\mfc110ita.dll

    - \Microsoft.VC110.MFCLOC\mfc110jpn.dll

    - \Microsoft.VC110.MFCLOC\mfc110kor.dll

    - \Microsoft.VC110.MFCLOC\mfc110rus.dll

    - \Microsoft.VC110.OPENMP\vcomp110.dll

5. \Debug_NonRedist\x86\ veya \Debug_NonRedist\x64\ klasöründen yapı bilgisayara açıklandığı gibi yalnızca aşağıdaki dosyaları kopyalayın [hata ayıklama yürütülebilir bir Test Makinesi çalıştırmayı hazırlama](/cpp/ide/preparing-a-test-machine-to-run-a-debug-executable). Başka bir dosya kopyalanabilir.

    - \Microsoft.VC110.DebugCRT\msvcp110d.dll

    - \Microsoft.VC110.DebugCRT\msvcr110d.dll

    - \Microsoft.VC110.DebugCXXAMP\vcamp110d.dll

    - \Microsoft.VC110.DebugMFC\mfc110d.dll

    - \Microsoft.VC110.DebugMFC\mfc110ud.dll

    - \Microsoft.VC110.DebugMFC\mfcm110d.dll

    - \Microsoft.VC110.DebugMFC\mfcm110ud.dll

    - \Microsoft.VC110.DebugOpenMP\vcomp110d.dll

##  <a name="CreatingRegistry">Kayıt defteri ayarları oluşturma</a>
 MSBuild ayarlarını yapılandırmak için kayıt defteri girdileri oluşturmanız gerekir.

#### <a name="to-create-registry-settings"></a>Kayıt defteri ayarları oluşturmak için

1. Kayıt defteri girdileri için üst klasör tanımlayın. Tüm kayıt defteri girdilerini aynı ana anahtarı altında oluşturulur. Bir x86 üzerinde üst anahtarını bilgisayardır HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. Üzerinde bir x64 ana anahtarı HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft bilgisayardır\\. Sistem Mimarisi bağımsız olarak, bu kılavuzda üst anahtara % RegistryRoot % gösterir.

    > [!NOTE]
    > Ana bilgisayarınız mimarisini yapı bilgisayarınızın farklıysa, her bilgisayarda uygun üst anahtarını kullandığınızdan emin olun. Dışarı aktarma işlemini otomatik hale getirme, bu özellikle önemlidir.
    >
    > Ayrıca, yapı bilgisayarda ana bilgisayara kullanmakta olduğunuz olandan farklı bir sürücü harfi kullanıyorsanız, eşleştirmek için kayıt defteri girdilerinin değerlerini değiştirdiğinizden emin olun.

2. Aşağıdaki kayıt defteri girdileri yapı bilgisayarda oluşturun. Dizeleri bu girdilerinin tümü (tür kayıt defterinde "REG_SZ" ==). Bu girişler değerleri aynı ana bilgisayarda karşılaştırılabilir girişlerinin değerleri ayarlayın.

    - %RegistryRoot%\\.NETFramework\v4.0.30319\AssemblyFoldersEx\VCMSBuild Public Assemblies@(Default)

    - %RegistryRoot%\Microsoft SDKs\Windows\v8.0@InstallationFolder

    - %RegistryRoot%\Microsoft SDKs\Windows\v8.0A@InstallationFolder

    - %RegistryRoot%\Microsoft SDKs\Windows\v8.0A\WinSDK-NetFx40Tools@InstallationFolder

    - %RegistryRoot%\Microsoft SDKs\Windows\v8.0A\WinSDK-NetFx40Tools-x86@InstallationFolder

    - %RegistryRoot%\VisualStudio\11.0@Source Directories

    - %RegistryRoot%\VisualStudio\11.0\Setup\VC@ProductDir

    - %RegistryRoot%\VisualStudio\SxS\VC7@FrameworkDir32

    - %RegistryRoot%\VisualStudio\SxS\VC7@FrameworkDir64

    - %RegistryRoot%\VisualStudio\SxS\VC7@FrameworkVer32

    - %RegistryRoot%\VisualStudio\SxS\VC7@FrameworkVer64

    - %RegistryRoot%\VisualStudio\SxS\VC7@11.0

    - %RegistryRoot%\VisualStudio\SxS\VS7@11.0

    - %RegistryRoot%\Windows Kits\Installed Roots@KitsRoot

    - %RegistryRoot%\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath

    - %RegistryRoot%\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath10

    - %RegistryRoot%\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath11

     Bilgisayar üzerinde bir x64 oluşturmak, ayrıca aşağıdaki kayıt defteri girişi oluşturun ve nasıl ayarlanacağını belirlemek için ana bilgisayara bakın.

    - %RegistryRoot%\Microsoft SDKs\Windows\v8.0A\WinSDK-NetFx40Tools-x64@InstallationFolder

     Yapı bilgisayarsa x64 ve MSBuild 64-bit sürümünü kullanmak istediğiniz ya da x x64 üzerinde Team Foundation Server yapı hizmeti kullanıyorsanız, bilgisayarın yerel 64 bit kayıt defterinde aşağıdaki kayıt defteri girdileri oluşturmalısınız. Bu girişler ayarlamak nasıl belirlemek için ana bilgisayara bakın.

    - HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\Setup\VS@ProductDir

    - HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath

    - HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath10

    - HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath11

## <a name="SettingEnvVariables">Yapı bilgisayarında ortam değişkenlerini ayarlama</a>

MSBuild yapı bilgisayarda kullanmak üzere PATH ortam değişkenleri ayarlamanız gerekir. Değişkenleri ayarlamak için vcvarsall.bat kullanabilirsiniz veya bunları el ile yapılandırabilirsiniz.

### <a name="to-use-vcvarsallbat-to-set-environment-variables"></a>Ortam değişkenleri ayarlamak üzere Vcvarsall.bat kullanmak için

- Yapı bilgisayarda bir komut istemi penceresi açın ve % Program Files%\Microsoft Visual Studio 11.0\VC\vcvarsall.bat çalıştırın. Kullanmak istediğiniz araç takımı belirtmek için komut satırı bağımsız değişkeni kullanabilirsiniz — x86, yerel x64 veya x64 çapraz derleyici. Bir komut satırı bağımsız değişkeni, araç takımı kullanılan x86 belirtmezseniz.

     Bu tabloda vcvarsall.bat için desteklenen bağımsız değişkenleri açıklanmaktadır:

    |Vcvarsall.bat bağımsız değişkeni|Derleyici|Bilgisayar mimarisi oluşturma|Derleme çıktı mimarisi|
    |----------------------------|--------------|---------------------------------|-------------------------------|
    |x86 (varsayılan)|32-bit yerel|x86, x64|x86|
    |x86_amd64|Çapraz x64|x86, x64|X64|
    |amd64|x64 yerel|X64|X64|

     Vcvarsall.bat başarıyla tamamlanırsa — diğer bir deyişle, hata iletisi görüntülenir — bir sonraki adımı atlayın ve adresindeki devam [yükleme MSBuild derlemeler için Genel Derleme Önbelleği (GAC) ve yapı bilgisayarında](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#InstallingMSBuildToGAC) bu belgenin bölüm .

### <a name="to-manually-set-environment-variables"></a>Ortam değişkenleri el ile ayarlamak için

1. Komut satırı ortamı el ile yapılandırmak için bu yolu PATH ortam değişkenine ekleyin:

    - %Program Files%\Microsoft Visual Studio 11.0\Common7\IDE

2. İsteğe bağlı olarak, aşağıdaki yollardan çözümlerinizi oluşturmak için MSBuild kullanma kolaylaştırmak için PATH değişkenine de ekleyebilirsiniz.

     Yerel 32-bit MSBuild kullanmak istiyorsanız, bu yollar PATH değişkenine ekleyin:

    - %Program Files%\Microsoft SDKs\Windows\v8.0A\bin\NETFX 4.0 Tools

    - %windir%\Microsoft.NET\Framework\v4.0.30319

     Yerel 64 bit MSBuild kullanmak istiyorsanız, bu yollar PATH değişkenine ekleyin:

    - %Program Files%\Microsoft SDKs\Windows\v8.0A\bin\NETFX 4.0 Tools\x64

    - %windir%\Microsoft.NET\Framework64\v4.0.30319

## <a name="InstallingMSBuildToGAC">İçin Genel Derleme Önbelleği (GAC) ve yapı bilgisayarında MSBuild derlemeleri yükleme</a>

MSBuild bazı ek derlemeler GAC yapı bilgisayarda yüklü olmasını gerektirir.

1. Aşağıdaki derlemeler ana bilgisayardan yapı bilgisayara kopyalayın. GAC yüklenecek olduğundan, burada onları yapı bilgisayarında yerleştirdiğiniz önemli değildir.

    - %ProgramFiles%\MSBuild\Microsoft.Cpp\v4.0\v110\Microsoft.Build.CPPTasks.Common.v110.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\CommonExtensions\Microsoft\VC\Project\Microsoft.VisualStudio.Project.VisualC.VCProjectEngine.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\PublicAssemblies\Microsoft.VisualStudio.VCProjectEngine.dll

2. GAC derlemelerini yüklemek için yapı bilgisayarda gacutil.exe bulun — genellikle, %ProgramFiles%\Microsoft SDKs\Windows\v8.0A\bin\NETFX 4.0 araçlarında\\. Bu klasör bulamadığında adımlarını yineleyin [dosyaları ana bilgisayardan yapı bilgisayara kopyalama](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CopyingFiles) Bu izlenecek yol bölümü.

     Yönetici haklarına sahip bir komut istemi penceresi açın ve her dosya için bu komutu çalıştırın:

     **Gacutil -i \<dosyası >**

    > [!NOTE]
    > Bir derlemenin tam olarak GAC içine yüklemek yeniden başlatma gerekebilir.

## <a name="BuildingProjects">Proje oluşturma</a>

Team Foundation Yapı oluşturmak için kullanabileceğiniz [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] projeler ve çözümler veya oluşturabilir bunları komut satırında. Projeleri derlemek için Team Foundation Build kullandığınızda, sistem mimarisi karşılık gelen MSBuild yürütülebilir çağırır. Komut satırında MSBuild 32 bit veya 64-bit MSBuild kullanabilir ve PATH ortam değişkenini ayarlayarak veya yürütülebilir mimarisi özgü MSBuild doğrudan çağırma tarafından MSBuild mimarisini seçebilirsiniz.

Komut isteminde MSBuild.exe kullanmak için aşağıdaki komutu, içinde çalıştığı *solution.sln* çözümünüzü adı için bir yer tutucudur.

**MSBuild** *solution.sln*

MSBuild komut satırında kullanma hakkında daha fazla bilgi için bkz: [komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md).

> [!NOTE]
> Derleme için [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] projeleri, "v110" Platform araç takımı kullanmanız gerekir. Düzenlenecek istemiyorsanız [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] proje dosyalarını, bu komut satırı bağımsız değişkeni kullanarak Platform araç takımı ayarlayabilirsiniz:
>
> **MSBuild** *solution.sln* **/p:PlatformToolset v110 =**

## <a name="CreatingForSourceControl">Böylece kaynak denetimine iade derleme ortamı oluşturma</a>

GAC'ing dosyaları veya kayıt defteri ayarlarını değiştirme gerektirmez ve çeşitli bilgisayarlara dağıtılabilir bir yapı ortamı oluşturabilirsiniz. Aşağıdaki adımlarda bunu yapmanın tek yoludur. Yapı ortamınızın benzersiz özellikleri için aşağıdaki adımları uyarlayın.

> [!NOTE]
> Böylece tracker.exe derleme sırasında bir hata oluşturmayacaksa artımlı oluşturma devre dışı bırakmanız gerekir. Artımlı yapı devre dışı bırakmak için bu yapı parametreyi ayarlayın:
>
> **MSBuild** *solution.sln* **/p:TrackFileAccess = false**

1. Ana bilgisayara bir "Deposu" dizin oluşturun.

     Bu adımları deposu % dizine bakın.

2. Bölümünde açıklandığı gibi dosya ve dizinleri kopyalamak [dosyaları ana bilgisayardan yapı bilgisayara kopyalama](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CopyingFiles) bölümü altında yeni oluşturduğunuz % deposu % dizininde yapıştırın dışında bu kılavuzun. Örneğin, %Depot%\Windows Kits\8.0\bin Kits\8.0\bin\ %ProgramFiles%\Windows kopyalama\\.

3. Dosyaları % deposu % yapıştırılırken bu değişiklikleri yapın:

    - In %Depot%\MSBuild\Microsoft.Cpp\v4.0\v110\Microsoft.CPP.Targets, \Microsoft.Cpp.InvalidPlatforms.targets\\, \Microsoft.cppbuild.targets\\, and \Microsoft.CppCommon.targets\\, change every instance of

         AssemblyName="Microsoft.Build.CppTasks.Common.v110, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"

         to

         AssemblyFile="$(VCTargetsPath11)Microsoft.Build.CppTasks.Common.v110.dll".

         Önceki Adlandırma GAC'ed olan derleme kullanır.

    - In %Depot% \MSBuild\Microsoft.Cpp\v4.0\v110\Microsoft.CPPClean.Targets, change every instance of

         AssemblyName="Microsoft.Build.CppTasks.Common.v110, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"

         to

         AssemblyFile="$(VCTargetsPath11)Microsoft.Build.CppTasks.Common.v110.dll".

4. .Props dosyası oluşturma — Örneğin, Partner.AutoImports.props—and bunu projelerinizi içeren klasörün kökünde koyun. Bu dosya, MSBuild tarafından çeşitli kaynakları bulmak için kullanılan değişkenleri ayarlamak için kullanılır. Değişkenleri bu dosya tarafından ayarlanmamışsa, diğer .props dosyaları ve kayıt defteri değerlerine dayanan .targets dosyaları tarafından ayarlanır. Tüm kayıt defteri değerlerini ayarlama değil çünkü bu değişkenleri boş olur ve yapı başarısız olmasına neden olabilir. Bunun yerine, bu Partner.AutoImports.props için ekleyin:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <!-- This file must be imported by all project files at the top of the project file. -->
    <Project ToolsVersion="4.0"
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <PropertyGroup>
    <VCTargetsPath>$(DepotRoot)MSBuild\Microsoft.Cpp\v4.0\v110\</VCTargetsPath>
    <VCTargetsPath11>$(DepotRoot)MSBuild\Microsoft.Cpp\v4.0\v110\</VCTargetsPath11>
    <MSBuildExtensionsPath>$(DepotRoot)MSBuild</MSBuildExtensionsPath>
    <MSBuildExtensionsPath32>$(DepotRoot)MSBuild</MSBuildExtensionsPath32>
    <VCInstallDir_110>$(DepotRoot)Microsoft Visual Studio 11.0\VC\</VCInstallDir_110>
    <VCInstallDir>$(VCInstallDir_110)</VCInstallDir>
    <WindowsKitRoot>$(DepotRoot)Windows Kits\</WindowsKitRoot>
    <WindowsSDK80Path>$(WindowsKitRoot)</WindowsSDK80Path>
    <WindowsSdkDir_80>$(WindowsKitRoot)8.0\</WindowsSdkDir_80>
    <WindowsSdkDir>$(WindowsSDKDir_80)</WindowsSdkDir>
    <WindowsSdkDir_80A>$(DepotRoot)Microsoft SDKs\Windows\v8.0A\</WindowsSdkDir_80A>
    </PropertyGroup>
    </Project>
    ```

5. Her proje dosyalarınıza, sonra en üstte aşağıdaki satırı ekleyin `<Project Default Targets...>` satır.

    ```xml
    <Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), Partner.AutoImports.props))\Partner.AutoImports.props"/>
    ```

6. Komut satırı ortamı aşağıdaki gibi değiştirin:

    - Ayarlama deposu =*1. adımda oluşturduğunuz deposu dizininin konumu*

    - Yolu ayarla = % path %; *MSBuild konumunu bilgisayarda*; %D epot%\Windows\System32;%D epot%\Windows\SysWOW64;%D epot%\Microsoft Visual Studio 11.0\Common7\IDE\

         Yerel 64 bit yapı için 64-bit MSBuild gelin.

## <a name="see-also"></a>Ayrıca bkz.

[Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama](/cpp/ide/preparing-a-test-machine-to-run-a-debug-executable)  
[Komut Satırı Başvurusu](../msbuild/msbuild-command-line-reference.md)