---
title: "Nasıl yapılır: derleme olayları belirtme (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pre-build events
- events [Visual Studio], builds
- post-build events
- build events [Visual Studio]
- builds [Visual Studio], events
ms.assetid: b4ce1ad9-5215-4b6f-b6a2-798b249aa335
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 1fcba0ef7abec3c8f5d71d34b8ff4e19e047d50b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-build-events-c"></a>Nasıl Yapılır: Derleme Olayları Belirtme (C#)
Derleme olayları yapı başlamadan önce veya yapı tamamlandıktan sonra çalışan komutlar belirtmek için kullanın. Yalnızca derleme derleme işlemindeki bu noktalarına başarıyla ulaşırsa derleme olaylarını yürütülür.  
  
 Bir proje yapılandırıldığında ön derleme olayları PreBuildEvent.bat adlı bir dosyaya eklenir ve sonrası derleme olayları PostBuildEvent.bat adlı bir dosyaya eklenir. Hata denetimi emin olmak istiyorsanız, kendi hata denetimi komutları derleme adımlarını ekleyin.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="how-to-specify-pre-build-and-post-build-events"></a>Oluşturma öncesi ve sonrası derleme olayları belirtme  
  
#### <a name="to-specify-a-build-event"></a>Derleme olayının belirtmek için  
  
1.  İçinde **Çözüm Gezgini**, yapı olay belirtmek istediğiniz projeyi seçin.  
  
2.  Üzerinde **proje** menüsünde tıklatın **özellikleri**.  
  
3.  Seçin **yapı olayları** sekmesi.  
  
4.  İçinde **oluşturma öncesi olay komut satırı** kutusunda, yapı olay sözdizimi belirtin.  
  
    > [!NOTE]
    >  Oluşturma öncesi olaylar proje güncel olduğundan ve hiçbir derleme tetiklenir çalıştırmayın.  
  
5.  İçinde **oluşturma sonrası olay komut satırı** kutusunda, yapı olay sözdizimi belirtin.  
  
    > [!NOTE]
    >  Ekleme bir `call` .bat dosyaları çalıştıran tüm sonrası derleme komutları önce deyim. Örneğin, `call C:\MyFile.bat` veya `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
6.  İçinde **oluşturma sonrası olay çalıştırmak** kutusunda, ne oluşturma sonrası olay çalıştırmak için koşullar altında belirtin.  
  
    > [!NOTE]
    >  Uzun sözdizimi eklemek veya seçmek için herhangi bir derleme makrolarından [oluşturma öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md), üç nokta düğmesini (**...** ) düzenleme kutusu görüntülemek için.  
  
     Yapı olay sözdizimi geçerli bir komut isteminde veya bir .bat dosyasında herhangi bir komuttan içerebilir. Bir toplu iş dosyası adı tarafından gelmelidir `call` tüm komutlar yürütülür emin olmak için.  
  
     **Not** oluşturma öncesi veya oluşturma sonrası olay başarıyla tamamlanmazsa, başarılı bir eylem gösteren bir ile dışında sıfır (0), çıkış kodu olay eyleminizi sağlayarak yapı sonlandırabilir.  
  
## <a name="example-how-to-change-manifest-information-by-using-a-post-build-event"></a>Örnek: Bir oluşturma sonrası olay kullanarak bildirim bilgileri değiştirmek nasıl  
 Aşağıdaki yordam en düşük işletim sistemi sürümünün uygulama bildiriminde bir oluşturma sonrası olay adlı bir .exe komutunu kullanarak nasıl ayarlanacağını gösterir (. proje dizininde exe.manifest dosyası). En düşük işletim sistemi sürümünü 4.10.0.0 gibi dört bölümden oluşan bir sayıdır. Bunu yapmak için komut değişir `<dependentOS>` bildirim bölümünü:  
  
```  
<dependentOS>  
   <osVersionInfo>  
      <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
   </osVersionInfo>  
</dependentOS>  
```  
  
#### <a name="to-create-an-exe-command-to-change-the-application-manifest"></a>Uygulama bildirimini değiştirmek için bir .exe komut oluşturmak için  
  
1.  Komutu için bir konsol uygulaması oluşturun. Gelen **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#**, tıklatın **Windows**ve ardından **konsol uygulaması** şablonu. Proje adı `ChangeOSVersionCS`.  
  
3.  Program.cs içinde aşağıdaki satırı ekleyin `using` dosyanın en üstüne deyimlerini:  
  
    ```  
    using System.Xml;  
    ```  
  
4.  İçinde `ChangeOSVersionCS` ad alanı, yerine `Program` sınıfı uygulama aşağıdaki kod ile:  
  
    ```  
    class Program  
    {  
       /// <summary>  
       /// This function will set the minimum operating system version for a ClickOnce application.  
       /// </summary>  
       /// <param name="args">  
       /// Command Line Arguments:  
       /// 0 - Path to application manifest (.exe.manifest).  
       /// 1 - Version of OS  
       ///</param>  
       static void Main(string[] args)  
       {  
          string applicationManifestPath = args[0];  
          Console.WriteLine("Application Manifest Path: " + applicationManifestPath);  
  
          // Get version name.  
          Version osVersion = null;  
          if (args.Length >=2 ){  
             osVersion = new Version(args[1]);  
          }else{  
             throw new ArgumentException("OS Version not specified.");  
          }  
          Console.WriteLine("Desired OS Version: " + osVersion.ToString());  
  
          XmlDocument document;  
          XmlNamespaceManager namespaceManager;  
          namespaceManager = new XmlNamespaceManager(new NameTable());  
          namespaceManager.AddNamespace("asmv1", "urn:schemas-microsoft-com:asm.v1");  
          namespaceManager.AddNamespace("asmv2", "urn:schemas-microsoft-com:asm.v2");  
  
          document = new XmlDocument();  
          document.Load(applicationManifestPath);  
  
          string baseXPath;  
          baseXPath = "/asmv1:assembly/asmv2:dependency/asmv2:dependentOS/asmv2:osVersionInfo/asmv2:os";  
  
          // Change minimum required operating system version.  
          XmlNode node;  
          node = document.SelectSingleNode(baseXPath, namespaceManager);  
          node.Attributes["majorVersion"].Value = osVersion.Major.ToString();  
          node.Attributes["minorVersion"].Value = osVersion.Minor.ToString();  
          node.Attributes["buildNumber"].Value = osVersion.Build.ToString();  
          node.Attributes["servicePackMajor"].Value = osVersion.Revision.ToString();  
  
          document.Save(applicationManifestPath);  
       }  
    }  
    ```  
  
     Komut iki bağımsız değişkeni alır: uygulama bildirimi yolunu (oluşturma işlemi genellikle Projectname.publish bildirimi oluşturur, klasör) ve yeni işletim sistemi sürümü.  
  
5.  Projeyi oluşturun. Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
6.  .Exe dosyası gibi bir dizine kopyalayın `C:\TEMP\ChangeOSVersionVB.exe`.  
  
 Ardından, uygulama bildirimi değiştirmek için bir oluşturma sonrası olay Bu komutta çağırır.  
  
#### <a name="to-invoke-a-post-build-event-to-modify-the-application-manifest"></a>Uygulama bildirimini değiştirmek için bir oluşturma sonrası olay çağırmak için  
  
1.  Yayımlanacak projeyi için bir Windows uygulaması oluşturun. Gelen **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#**, tıklatın **Windows Klasik Masaüstü**ve ardından **Windows Forms uygulaması** Şablon. Proje adı `CSWinApp`.  
  
3.  Seçili proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
4.  Proje Tasarımcısı'nda bulmak **Yayımla** sayfasında ve ayarlama **konum yayımlama** için `C:\TEMP\`.  
  
5.  Tıklayarak projeyi yayımlama **Şimdi Yayımla**.  
  
     Bildirim dosyası oluşturulur ve koyun `C:\TEMP\CSWinApp_1_0_0_0\CSWinApp.exe.manifest`. Bildirim görüntülemek için dosyaya sağ tıklayın, **birlikte Aç**seçin **program listesinden**ve ardından **not defteri**.  
  
     Arama için dosyasında `<osVersionInfo>` öğesi. Örneğin, sürüm olabilir:  
  
    ```  
    <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
    ```  
  
6.  Proje Tasarımcısı'nda tıklatın **yapı olayları** sekmesinde **düzen oluşturma sonrası** düğmesi.  
  
7.  İçinde **oluşturma sonrası olay komut satırı** kutusunda, aşağıdaki komutu yazın:  
  
     `C:\TEMP\ChangeOSVersionCS.exe "$(TargetPath).manifest" 5.1.2600.0`  
  
     Projesi derlerken, bu komut uygulama bildiriminde en düşük işletim sistemi sürümü için 5.1.2600.0 değiştirin.  
  
     Çünkü `$(TargetPath)` makrosu oluşturulmasını, yürütülebilir dosyanın tam yolunu ifade `$(TargetPath)`.manifest depo Directory'de oluşturulan uygulama bildirimi belirtin. Yayımlama, daha önce belirlediğiniz yayımlama konumu için bu bildirimi kopyalayacak.  
  
8.  Projeyi yeniden yayımlayın. Git **Yayımla** sayfasında ve tıklayın **Şimdi Yayımla**.  
  
     Bildirim yeniden görüntüleyin. Bildirimini görüntülemek için yayımlama dizinini açın, dosyaya sağ tıklayın, **birlikte Aç**seçin **program listesinden**ve ardından **not defteri**.  
  
     Sürüm şimdi şöyle olmalıdır:  
  
    ```  
    <os majorVersion="5" minorVersion="1" buildNumber="2600" servicePackMajor="0" />  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme olayları sayfası, Proje Tasarımcısı (C#)](../ide/reference/build-events-page-project-designer-csharp.md)   
 [Derleme öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)   
 [Nasıl yapılır: derleme olayları belirtme (Visual Basic)](../ide/how-to-specify-build-events-visual-basic.md)   
 [Derleme ve Oluşturma](../ide/compiling-and-building-in-visual-studio.md)