---
title: "Özellikleri ve yöntemleri genişletilmiş proje alt türleri tarafından | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project subtypes, extended methods
- project subtypes, extended properties
ms.assetid: 2b9833bf-8551-4ae1-93db-197ba645c65e
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 288e8f680d12aeffb2979c3f0d89b44b0553b62e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="properties-and-methods-extended-by-project-subtypes"></a>Özellikleri ve yöntemleri proje alt türleri tarafından Genişletilmiş
Proje alt çok temel projesinin bir Toplayıcı oluşturulur çünkü proje davranışını etkilemek için güç sahiptir. Bu bölümde bazı gelişmiş veya proje alt türleri tarafından değiştirilen özellikler özetlenmektedir.  
  
## <a name="features-gained-by-aggregation"></a>Toplama tarafından elde edilen özellikleri  
 Aşağıdaki tabloda birçok temel projelerinde geçersiz kılmak proje türlerinde olanaklı kılmaktadır yöntem özetler.  
  
|Toplama tarafından geçersiz kılınmış yöntemleri|Proje alt türü|  
|---------------------------------------|---------------------|  
|Gelen <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>:<br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.SetProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetGuidProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.SetGuidProperty%2A>|Bir proje alt sağlar<br /><br /> -Başlık ve proje düğümüne simgesini değiştirin.<br />-Proje tamamen geçersiz `Browse` nesnesi.<br />-Proje adlandırılabilir olup olmadığını denetler.<br />-Denetim sıralama düzeni.<br />-Dinamik Yardım control kullanıcı bağlamı.|  
|Gelen <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>:<br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.GetItemContext%2A>|Bağlamsal hangi hizmetlerin tasarımcıları ve editörler için sağlanan denetlemek bir proje alt sağlar.|  
|Gelen <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>:<br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A><br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>|Bir proje alt sağlar<br /><br /> -Komut yönlendirme için proje komutları içinde katılın.<br />-Ekleyin, kaldırın veya ortam komutları proje ve Çözüm Gezgini etkin komutlar devre dışı bırakın.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>|Kullanıcı, görür filtrelemek proje alt etkinleştirir **Yeni Öğe Ekle** iletişim kutusu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGeneratorFactory>|Bir proje alt sağlar<br /><br /> -Bir dosya uzantısı verilen varsayılan oluşturucu belirler.<br />-İnsan okunabilir oluşturucu adı için bir COM nesnesi eşleyin.|  
  
## <a name="properties-used-by-project-subtypes"></a>Proje alt türleri tarafından kullanılan özellikleri  
 Ortam ve temel proje sistemi özelliklerinden kullanabilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID> ve <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> proje sisteminin çeşitli özellikleri denetlemek bir proje alt etkinleştirmek için aşağıdaki tabloda ayrıntılı numaralandırmalar.  
  
|VSHPROPID özelliği|Proje alt türü|  
|------------------------|---------------------|  
|`AddItemTemplatesGuid`|İçeriğini denetlemek bir proje alt verir **Öğe Ekle** iletişim kutusu. Proje alt yeni bir şablon dizinlerini belirtimi sağlamak, yeni tür öğe eklemek, var olan öğeleri kaldırmak ve temel projenin öğelerin alt kümesine reorganıze **Öğe Ekle** iletişim kutusu.|  
|`PropertyPagesCLSIDList`|Eklemek veya yapılandırma bağımsız özellik sayfaları kaldırmak bir proje alt sağlar.|  
|`CfgPropertyPagesCLSIDList`|Eklemek veya yapılandırma bağımlı özellik sayfaları kaldırmak bir proje alt sağlar.|  
|`ExtObjectCATID`|Otomasyon genişletici project veya project öğesi nesneleri genişletici catID öğrenerek sağlamak bir proje alt sağlar. Örneğin, özel bir proje alt sağlayabilir `Project.Extender("<subtype>")` nesnesi.|  
|`BrowseObjectCATID`|Bir Otomasyon Extender sağlamak bir proje alt verir `Browse` genişletici catID bilerek nesne. Örneğin, bir proje alt ek özellikler ekleyebilirsiniz <xref:EnvDTE.Project.Properties%2A> koleksiyonu.|  
|`CfgBrowseObjectCATID`|İçin proje yapılandırma Gözat nesnesi Otomasyon genişletici sağlamak bir proje alt sağlar. Örneğin, bir proje alt ek özellikler ekleyebilirsiniz <xref:EnvDTE.Configuration.Properties%2A> koleksiyonu.|  
|`CfgExtObjectCATID`|Otomasyon genişletici için yapılandırma nesnesi sağlamak bir proje alt sağlar.|  
|`DefaultPlatformName`|Projenin yapılandırma nesneler için platform adını belirlemek bir proje alt sağlar.|  
  
 Temel Proje yukarıdaki özelliklerinin varsayılan uygulamasını sağlar. Temel Proje bunlar çağırarak alır `QueryInterface` için <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> en dıştaki proje alt üzerinde böylece uygulama özelliklerini geçersiz kılmak proje alt sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje Alt Türleri Tasarımı](../../extensibility/internals/project-subtypes-design.md)