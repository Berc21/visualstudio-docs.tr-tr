---
title: "Nasıl yapılır: ClickOnce güven istemi davranışını yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, install without prompting
- deploying applications [ClickOnce], trust prompt
- ClickOnce applications, install without prompting
- ClickOnce applications, trust prompt
- ClickOnce deployment, trust prompt
ms.assetid: cc04fa75-012b-47c9-9347-f4216be23cf2
caps.latest.revision: "11"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 8822d0aa9947dccbdfabc43d7090b52eba7d0844
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-the-clickonce-trust-prompt-behavior"></a>Nasıl yapılır: ClickOnce Güven İstemi Davranışını Yapılandırma
Son kullanıcıların Windows Forms uygulamaları, Windows Presentation Foundation uygulamaları, konsol uygulamaları, WPF tarayıcı gibi ClickOnce uygulamalarını yükleme seçeneği izin verilip verilmeyeceğini denetlemek için ClickOnce güven istemi yapılandırabilirsiniz uygulamaları ve Office çözümleri. Güven istemi her son kullanıcının bilgisayarda kayıt defteri anahtarlarını ayarlayarak yapılandırın.  
  
 Aşağıdaki tabloda her beş bölgeler (Internet, UntrustedSites, Bilgisayarım, LocalIntranet ve TrustedSites) uygulanabilir yapılandırma seçeneklerini gösterir.  
  
|Seçenek|Kayıt defteri ayarı değeri|Açıklama|  
|------------|----------------------------|-----------------|  
|Güven istemi etkinleştirin.|`Enabled`|Böylece son kullanıcıların ClickOnce uygulamalarını güven verebilirsiniz ClickOnce güven istemi görüntülenir.|  
|Güven istemi kısıtlayın.|`AuthenticodeRequired`|ClickOnce güven istemi yalnızca ClickOnce uygulamaları yayımcıyı tanımlayan bir sertifikayla imzalanmış görüntülenir.|  
|Güven istemi devre dışı bırakın.|`Disabled`|ClickOnce güven istemi açıkça güvenilir bir sertifika ile imzalanmamış herhangi bir ClickOnce uygulaması için görüntülenmez.|  
  
 Aşağıdaki tabloda her bölge için varsayılan davranış gösterir. Uygulamalar sütunu Windows Forms uygulamaları, Windows Presentation Foundation uygulamaları, WPF tarayıcı uygulamaları ve konsol uygulamaları gösterir.  
  
|Bölge|Uygulamalar|Office çözümleri|  
|----------|------------------|----------------------|  
|`MyComputer`|`Enabled`|`Enabled`|  
|`LocalIntranet`|`Enabled`|`Enabled`|  
|`TrustedSites`|`Enabled`|`Enabled`|  
|`Internet`|`Enabled`|`AuthenticodeRequired`|  
|`UntrustedSites`|`Disabled`|`Disabled`|  
  
 Etkinleştirme, kısıtlama veya ClickOnce güven istemi devre dışı bırakarak bu ayarları geçersiz kılabilirsiniz.  
  
## <a name="enabling-the-clickonce-trust-prompt"></a>ClickOnce güven istemi etkinleştirme  
 Son kullanıcılara bu bölgeden gelen herhangi bir ClickOnce uygulamasını çalıştırma ve yükleme seçeneğiyle gösterilmesini istediğiniz zaman bir bölge için güven istemi etkinleştirin.  
  
#### <a name="to-enable-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>Kayıt Defteri Düzenleyicisi'ni kullanarak ClickOnce güven istemi etkinleştirmek için  
  
1.  Kayıt Defteri Düzenleyicisi'ni açın:  
  
    1.  Tıklatın **Başlat**ve ardından **çalıştırmak**.  
  
    2.  İçinde **açık** kutusuna `regedit32`ve ardından **Tamam**.  
  
2.  Aşağıdaki kayıt defteri anahtarını bulun:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Anahtar mevcut değilse oluşturun.  
  
3.  Aşağıdaki alt anahtarları olarak ekleyin **dize değeri**, zaten, aşağıdaki tabloda gösterilen ilişkili değerler ile mevcut değil.  
  
    |Dize değeri alt anahtarı|Değer|  
    |-------------------------|-----------|  
    |`Internet`|`Enabled`|  
    |`UntrustedSites`|`Disabled`|  
    |`MyComputer`|`Enabled`|  
    |`LocalIntranet`|`Enabled`|  
    |`TrustedSites`|`Enabled`|  
  
     Office çözümleri için `Internet` varsayılan değere sahip `AuthenticodeRequired` ve `UntrustedSites` değerine sahip `Disabled`. Diğerleri için `Internet` varsayılan değere sahip `Enabled`.  
  
#### <a name="to-enable-the-clickonce-trust-prompt-programmatically"></a>ClickOnce güven istemi programlı olarak etkinleştirmek için  
  
1.  Visual Studio'da bir Visual Basic veya Visual C# konsol uygulaması oluşturun.  
  
2.  Düzenlemek için Program.vb veya Program.cs dosyasını açın ve aşağıdaki kodu ekleyin.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Enabled")  
    key.SetValue("LocalIntranet", "Enabled")  
    key.SetValue("Internet", "Enabled")  
    key.SetValue("TrustedSites", "Enabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Enabled");  
    key.SetValue("LocalIntranet", "Enabled");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "Enabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Derleme ve uygulamayı çalıştırın.  
  
## <a name="restricting-the-clickonce-trust-prompt"></a>ClickOnce güven istemi kısıtlama  
 Güven istemi kısıtlayabilirsiniz, böylece çözümleri kullanıcılar için bir güven kararı istenir önce kimlik bilmesinin Authenticode sertifikaları ile imzalanmalıdır.  
  
#### <a name="to-restrict-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>Kayıt Defteri Düzenleyicisi'ni kullanarak ClickOnce güven istemi kısıtlamak için  
  
1.  Kayıt Defteri Düzenleyicisi'ni açın:  
  
    1.  Tıklatın **Başlat**ve ardından **çalıştırmak**.  
  
    2.  İçinde **açık** kutusuna `regedit`ve ardından **Tamam**.  
  
2.  Aşağıdaki kayıt defteri anahtarını bulun:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Anahtar mevcut değilse oluşturun.  
  
3.  Aşağıdaki alt anahtarları olarak ekleyin **dize değeri**, zaten, aşağıdaki tabloda gösterilen ilişkili değerler ile mevcut değil.  
  
    |Dize değeri alt anahtarı|Değer|  
    |-------------------------|-----------|  
    |`UntrustedSites`|`Disabled`|  
    |`Internet`|`AuthenticodeRequired`|  
    |`MyComputer`|`AuthenticodeRequired`|  
    |`LocalIntranet`|`AuthenticodeRequired`|  
    |`TrustedSites`|`AuthenticodeRequired`|  
  
#### <a name="to-restrict-the-clickonce-trust-prompt-programmatically"></a>ClickOnce güven istemi programlı olarak kısıtlamak için  
  
1.  Visual Studio'da bir Visual Basic veya Visual C# konsol uygulaması oluşturun.  
  
2.  Düzenlemek için Program.vb veya Program.cs dosyasını açın ve aşağıdaki kodu ekleyin.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "AuthenticodeRequired")  
    key.SetValue("LocalIntranet", "AuthenticodeRequired")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "AuthenticodeRequired")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "AuthenticodeRequired");  
    key.SetValue("LocalIntranet", "AuthenticodeRequired");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "AuthenticodeRequired");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Derleme ve uygulamayı çalıştırın.  
  
## <a name="disabling-the-clickonce-trust-prompt"></a>ClickOnce güven istemi devre dışı bırakma  
 Böylece son kullanıcıların kendi güvenlik ilkesinde zaten güvenilmiyor çözümleri yüklemek için seçeneği verilmez güven istemi devre dışı bırakabilirsiniz.  
  
#### <a name="to-disable-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>ClickOnce güven istemi Kayıt Defteri Düzenleyicisi'ni kullanarak devre dışı bırakmak için  
  
1.  Kayıt Defteri Düzenleyicisi'ni açın:  
  
    1.  Tıklatın **Başlat**ve ardından **çalıştırmak**.  
  
    2.  İçinde **açık** kutusuna `regedit`ve ardından **Tamam**.  
  
2.  Aşağıdaki kayıt defteri anahtarını bulun:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Anahtar mevcut değilse oluşturun.  
  
3.  Aşağıdaki alt anahtarları olarak ekleyin **dize değeri**, zaten, aşağıdaki tabloda gösterilen ilişkili değerler ile mevcut değil.  
  
    |Dize değeri alt anahtarı|Değer|  
    |-------------------------|-----------|  
    |`UntrustedSites`|`Disabled`|  
    |`Internet`|`Disabled`|  
    |`MyComputer`|`Disabled`|  
    |`LocalIntranet`|`Disabled`|  
    |`TrustedSites`|`Disabled`|  
  
#### <a name="to-disable-the-clickonce-trust-prompt-programmatically"></a>ClickOnce güven istemi program aracılığıyla devre dışı bırakmak için  
  
1.  Visual Studio'da bir Visual Basic veya Visual C# konsol uygulaması oluşturun.  
  
2.  Düzenlemek için Program.vb veya Program.cs dosyasını açın ve aşağıdaki kodu ekleyin.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Disabled")  
    key.SetValue("LocalIntranet", "Disabled")  
    key.SetValue("Internet", "Disabled")  
    key.SetValue("TrustedSites", "Disabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Disabled");  
    key.SetValue("LocalIntranet", "Disabled");  
    key.SetValue("Internet", "Disabled");  
    key.SetValue("TrustedSites", "Disabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
  
    ```  
  
3.  Derleme ve uygulamayı çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce ve Authenticode](../deployment/clickonce-and-authenticode.md)   
 [Güvenilir Uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md)   
 [Nasıl yapılır: ClickOnce güvenlik ayarlarını etkinleştir](../deployment/how-to-enable-clickonce-security-settings.md)   
 [Nasıl yapılır: ClickOnce uygulaması için bir güvenlik bölgesi ayarlama](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Nasıl yapılır: sınırlı izinler ile ClickOnce uygulamasında hata ayıklama](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Nasıl yapılır: ClickOnce uygulamaları için bir istemci bilgisayara güvenilir bir yayımcı Ekle](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [Nasıl yapılır: Uygulama ve Dağıtım Bildirimlerini Yeniden İmzalama](../deployment/how-to-re-sign-application-and-deployment-manifests.md)