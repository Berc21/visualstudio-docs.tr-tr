---
title: "Nasıl yapılır: ClickOnce dağıtımı'nda bağımsız Önkoşullar için destek URL'sini belirtme | Microsoft Docs"
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
- ClickOnce deployment, prerequisites
- ClickOnce deployment, URLs
ms.assetid: 590742c3-a286-4160-aa75-7a441bb2207b
caps.latest.revision: "10"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 4a73d6cd0996f3f0e91b5a5381ee1b8ccd58a2a1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment"></a>Nasıl yapılır: Bir ClickOnce Dağıtımı'nda Bağımsız Önkoşullar için Destek URL'sini Belirtme
A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım için istemci bilgisayarda kullanılabilir olması gereken önkoşulları test [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamasını çalıştırmak için. Gerekli en düşük sürümü bunlar [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], işletim sistemi ve genel derleme önbelleğinde (GAC) önceden herhangi bir derleme sürümü. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], ancak bu önkoşullardan hiçbirini kendisi yükleyemez; bir önkoşul bulunmazsa, sadece yüklemeyi durdurur ve yüklemenin neden başarısız açıklayan bir iletişim kutusu görüntüler.  
  
 Önkoşulları yüklemek için iki yöntem vardır. Önyükleyici uygulama kullanarak bunları yükleyebilirsiniz. Alternatif olarak, önkoşul bulunamazsa, hangi kullanıcılara iletişim kutusunda görüntülenen bir destek URL'si bağımsız Önkoşullar için belirtebilirsiniz. Bu URL tarafından başvurulan sayfa gereken önkoşulları yüklemek için yönergeleri için bağlantıları içerebilir. Bir uygulama bağımsız bir önkoşul için destek URL'sini belirlemezse [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] tanımlanmış olması durumunda bir bütün olarak uygulama için dağıtım bildiriminde belirtilen destek URL'sini görüntüler.  
  
 Sırada [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], Mage.exe ve MageUI.exe tüm oluşturmak için kullanılabilir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtımlarda, bu araçları hiçbiri doğrudan destek bağımsız Önkoşullar için destek URL'sini belirtme. Bu belge, dağıtımınızın değiştirmek açıklar uygulama bildirimi ve bunlar için dağıtım bildirimi URL'leri destekler.  
  
### <a name="specifying-a-support-url-for-an-individual-prerequisite"></a>Bağımsız bir önkoşul için destek URL'sini belirtme  
  
1.  Uygulama bildirimi (.manifest dosyası) açın, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bir metin düzenleyicisinde uygulama.  
  
2.  Bir işletim sistemi önkoşulu için ekleme `supportUrl` özniteliğini `dependentOS` öğe:  
  
    ```  
     <dependency>  
        <dependentOS supportUrl="http://www.adatum.com/MyApplication/wrongOSFound.htm">  
          <osVersionInfo>  
            <os majorVersion="5" minorVersion="1" buildNumber="2600" servicePackMajor="0" servicePackMinor="0" />  
          </osVersionInfo>  
        </dependentOS>  
      </dependency>  
    ```  
  
3.  Belirli bir ortak dil çalışma zamanı sürümü için bir önkoşul için ekleme `supportUrl` özniteliğini `dependentAssembly` ortak dil çalışma zamanı bağımlılık belirtiyor girişi:  
  
    ```  
      <dependency>  
        <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" supportUrl=" http://www.adatum.com/MyApplication/wrongClrVersionFound.htm">  
          <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="4.0.30319.0" />  
        </dependentAssembly>  
      </dependency>  
    ```  
  
4.  Genel derleme önbelleğinde önceden derleme için bir önkoşul için ayarlanmış `supportUrl` için `dependentAssembly` gerekli derleme belirtir öğe:  
  
    ```  
      <dependency>  
        <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" supportUrl=" http://www.adatum.com/MyApplication/missingSampleGACAssembly.htm">  
          <assemblyIdentity name="SampleGACAssembly" version="5.0.0.0" publicKeyToken="04529dfb5da245c5" processorArchitecture="msil" language="neutral" />  
        </dependentAssembly>  
      </dependency>  
    ```  
  
5.  İsteğe bağlı. .NET Framework 4 hedefleyen uygulamalar açmak için dağıtım bildirimi (.application dosya), [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bir metin düzenleyicisinde uygulama.  
  
6.  .NET Framework 4 önkoşulları eklemek `supportUrl` özniteliğini `compatibleFrameworks` öğe:  
  
    ```  
    <compatibleFrameworks  xmlns="urn:schemas-microsoft-com:clickonce.v2" supportUrl="http://adatum.com/MyApplication/CompatibleFrameworks.htm">  
      <framework targetVersion="4.0" profile="Client" supportedRuntime="4.0.30319" />  
      <framework targetVersion="4.0" profile="Full" supportedRuntime="4.0.30319" />  
    </compatibleFrameworks>  
    ```  
  
7.  Uygulama bildirimini el ile değiştirmiş sonra Dijital sertifikanızı kullanarak uygulama bildirimi yeniden oturum sonra güncelleştirme ve gerekir dağıtım bildirimi de yeniden oturum açın. Mage.exe kullanın veya MageUI.exe SDK araçlarını kullanarak bu dosyaları yeniden olarak bağlı olarak, bu görevi gerçekleştirmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] el ile yaptığınız değişiklikler siler. Bildirimlerini yeniden imzalamak için Mage.exe kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: yeniden imzalama uygulama ve dağıtım bildirimlerini](../deployment/how-to-re-sign-application-and-deployment-manifests.md).  
  
## <a name="net-framework-security"></a>.NET Framework Güvenliği  
 Uygulama kısmi güvende çalışacak şekilde işaretlenmişse destek URL'si iletişim kutusunda görüntülenmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [İzlenecek yol: Bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [\<compatibleFrameworks > öğesi](../deployment/compatibleframeworks-element-clickonce-deployment.md)   
 [ClickOnce ve Authenticode](../deployment/clickonce-and-authenticode.md)   
 [Uygulama Dağıtımının Önkoşulları](../deployment/application-deployment-prerequisites.md)