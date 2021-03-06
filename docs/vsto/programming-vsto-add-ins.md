---
title: VSTO eklentilerini programlamaya | Microsoft Docs
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.ProjectItem.Addin
- VST.ProjectItem.AddinProject
- thisAddIn
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ICustomTaskPaneConsumer interface
- add-ins [Office development in Visual Studio], programming
- IRibbonExtensibility interface
- UI customizing [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], application-level add-ins
- programming [Office development in Visual Studio], application-level add-ins
- ThisAddIn class
- user interfaces [Office development in Visual Studio], customizing
- writing code for Office solutions
- host items [Office development in Visual Studio], AddIn
- application development [Office development in Visual Studio], application-level add-ins
- add-ins [Office development in Visual Studio], ThisAddIn class
- application-level add-ins [Office development in Visual Studio], ThisAddIn class
- FormRegionStartup interface
- ThisAddIn_Startup
- application-level add-ins [Office development in Visual Studio], programming
- ThisAddIn_Shutdown
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 58b6d40e2da962587b44e4b73c8331b3fba5590f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="programming-vsto-add-ins"></a>VSTO Eklentilerini Programlama
  Bir VSTO eklenti oluşturarak Microsoft Office uygulaması genişlettiğinizde, karşı doğrudan kod yazma `ThisAddIn` projenizdeki sınıfı. Bu sınıf, Microsoft Office konak uygulamasının nesne modeline erişme, uygulamanın kullanıcı arabirimini (UI) özelleştirme ve VSTO eklentinizi diğer Office çözümlerine nesneleri gösterme gibi görevleri gerçekleştirmek için kullanabilirsiniz.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 Bazı yönlerini VSTO eklentisi projelerine kod yazma, diğer Visual Studio Proje türleri farklıdır. Bu farklılıklar birçoğu Office nesne modelleri için yönetilen kod gösterilen şekilde hatalardır. Daha fazla bilgi için bkz: [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md).  
  
 Visual Studio'da Office geliştirme araçlarını kullanarak oluşturabilirsiniz VSTO eklentileri ve çözümlerin diğer türleri hakkında genel bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
## <a name="using-the-thisaddin-class"></a>ThisAddIn sınıfını kullanma  
 VSTO eklenti kodunuzu yazmaya başlayabilirsiniz `ThisAddIn` sınıfı. Visual Studio ThisAddIn.vb otomatik olarak bu sınıf oluşturur (içinde [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]) veya ThisAddIn.cs (C# ' ta) kod dosyası, VSTO eklenti projesindeki. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Microsoft Office uygulaması VSTO eklentinizi yüklediğinde otomatik olarak bu sınıfın örneğini sizin için oluşturur.  
  
 İki varsayılan olay işleyicileri vardır `ThisAddIn` sınıfı. VSTO Eklenti yüklendiğinde kodu çalıştırmak için kodu ekleyin `ThisAddIn_Startup` olay işleyicisi. VSTO Eklenti kaldırılmadan hemen önce kodu çalıştırmak için kodu ekleyin `ThisAddIn_Shutdown` olay işleyicisi. Bu olay işleyicileri hakkında daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
> [!NOTE]  
>  Outlook'ta, varsayılan olarak `ThisAddIn_Shutdown` olay işleyicisi için VSTO eklentisi kaldırıldığında her zaman çağrılmaz. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
### <a name="accessing-the-object-model-of-the-host-application"></a>Ana bilgisayar uygulamasının nesne modeline erişme  
 Ana bilgisayar uygulamasının nesne modeline erişmek için `Application` alanını `ThisAddIn` sınıfı. Bu alan konak uygulamanın geçerli örneği temsil eden bir nesne döndürür. Dönüş değeri türü aşağıdaki tabloda `Application` her VSTO eklenti projesindeki alan.  
  
|ana bilgisayar uygulaması|Dönüş değeri türü|  
|----------------------|-----------------------|  
|Microsoft Office Excel|<xref:Microsoft.Office.Interop.Excel.Application>|  
|Microsoft Office InfoPath|<xref:Microsoft.Office.Interop.InfoPath.Application>|  
|Microsoft Office Outlook|<xref:Microsoft.Office.Interop.Outlook.Application>|  
|Microsoft Office PowerPoint|<xref:Microsoft.Office.Interop.PowerPoint.Application>|  
|Microsoft Office Project|Microsoft.Office.Interop.MSProject.Application|  
|Microsoft Office Visio|Microsoft.Office.Interop.Visio.Application|  
|Microsoft Office Word|<xref:Microsoft.Office.Interop.Word.Application>|  
  
 Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir `Application` Microsoft Office Excel için VSTO eklenti içinde yeni bir çalışma kitabı oluşturmak için alan. Bu örnek çalıştırılmak üzere tasarlanmıştır `ThisAddIn` sınıfı.  
  
```vb  
Dim newWorkbook As Excel.Workbook = Me.Application.Workbooks.Add()  
```  
  
```csharp  
Excel.Workbook newWorkbook = this.Application.Workbooks.Add(System.Type.Missing);  
```  
  
 Dışından aynı şeyi yapmak için `ThisAddIn` sınıfı, kullanın `Globals` nesne erişimi `ThisAddIn` sınıfı. Hakkında daha fazla bilgi için `Globals` nesne için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  
  
```vb  
Dim newWorkbook As Excel.Workbook = Globals.ThisAddIn.Application.Workbooks.Add()  
```  
  
```csharp  
Excel.Workbook newWorkbook = Globals.ThisAddIn.Application.Workbooks.Add(System.Type.Missing);  
```  
  
 Belirli Microsoft Office uygulamalarının nesne modelleri hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Excel Nesne Modeline Genel Bakış](../vsto/excel-object-model-overview.md)  
  
-   [Word Nesne Modeline Genel Bakış](../vsto/word-object-model-overview.md)  
  
-   [Outlook Nesne Modeline Genel Bakış](../vsto/outlook-object-model-overview.md)  
  
-   [InfoPath Çözümleri](../vsto/infopath-solutions.md)  
  
-   [PowerPoint Çözümleri](../vsto/powerpoint-solutions.md)  
  
-   [Proje Çözümleri](../vsto/project-solutions.md)  
  
-   [Visio Nesne Modeline Genel Bakış](../vsto/visio-object-model-overview.md)  
  
###  <a name="AccessingDocuments"></a>Office uygulaması başlatıldığında belgeye erişme  
 Tüm [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] uygulamaları ve hiçbiri başlattığınızda bir belge otomatik olarak açılmasını [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] uygulamaları bunları başlattığınızda bir belge açın. Bu nedenle, kodda eklemeyin `ThisAdd-In_Startup` kod açılması için bir belge gerektiriyorsa olay işleyicisi. Bunun yerine, bir kullanıcı oluşturur veya bir belgeyi açtığında, Office uygulaması oluşturan bir olay bu kodu ekleyin. Böylece, kodunuzu bir işlem gerçekleştirmeden önce bir belge açık olduğunda garanti edebilir.  
  
 Yalnızca kullanıcı bir belge oluşturur veya var olan bir belgeyi açtığında aşağıdaki kod örneğinde bir Word belgesini çalışır.  
  
 [!code-csharp[Trin_WordAddIn_Menus#3](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/thisaddin.cs#3)]
 [!code-vb[Trin_WordAddIn_Menus#3](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/thisaddin.vb#3)]  
  
### <a name="thisaddin-members-to-use-for-other-tasks"></a>Diğer görevler için kullanılacak ThisAddIn üyeleri  
 Aşağıdaki tablo diğer ortak görevler açıklar ve hangi üyelerinin gösterir `ThisAddIn` sınıfı görevleri gerçekleştirmek için kullanabilirsiniz.  
  
|Görev|Kullanılacak üye|  
|----------|-------------------|  
|VSTO eklenti için VSTO eklentisi yüklendiğinde başlatmak için kod çalıştırın.|Kodu ekleyin `ThisAddIn_Startup` yöntemi. Bu olay için varsayılan işleyicisidir <xref:Microsoft.Office.Tools.AddInBase.Startup> olay. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).|  
|VSTO Eklenti kaldırılmadan önce VSTO eklenti tarafından kullanılan kaynakları temizlemek için kodu çalıştırın.|Kodu ekleyin `ThisAddIn_Shutdown` yöntemi. Bu olay için varsayılan işleyicisidir <xref:Microsoft.Office.Tools.AddInBase.Shutdown> olay. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md). **Not:** varsayılan Outlook'ta `ThisAddIn_Startup` olay işleyicisi için VSTO eklentisi kaldırıldığında her zaman çağrılmaz. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).|  
|Özel görev bölmesini görüntüler.|Kullanım `CustomTaskPanes` alan. Daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).|  
|VSTO eklentinizi diğer Microsoft Office çözümlerine nesneleri kullanıma sunar.|Geçersiz kılma <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> yöntemi. Daha fazla bilgi için bkz: [VSTO eklentileri diğer Office Çözümlerinden gelen çağırma kodda](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).|  
|Bir özellik genişletilebilirlik arabirimi uygulama tarafından Microsoft Office sistemi özelleştirin.|Geçersiz kılma <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> arabirimini uygulayan bir sınıf örneği döndürülecek yöntemi. Daha fazla bilgi için bkz: [özelleştirme kullanıcı Arabirimi özellikleri tarafından kullanarak genişletilebilirlik arabirimleri](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md). **Not:** Şerit UI'si özelleştirmek için ayrıca kılabilirsiniz <xref:Microsoft.Office.Tools.AddInBase.CreateRibbonExtensibilityObject%2A> yöntemi.|  
  
### <a name="understanding-the-design-of-the-thisaddin-class"></a>ThisAddIn sınıfı tasarımını anlama  
 ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], <xref:Microsoft.Office.Tools.AddIn> bir arabirimdir. `ThisAddIn` Sınıfı türer <xref:Microsoft.Office.Tools.AddInBase> sınıfı. Taban sınıfı üyeleri tüm çağrıları için iç uygulaması yönlendiren <xref:Microsoft.Office.Tools.AddIn> arabiriminde [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
 Outlook için VSTO eklentisi projelerine `ThisAddIn` Microsoft.Office.Tools.Outlook.OutlookAddIn sınıf .NET Framework 3.5 hedefleyen projelerde ve öğesinden türer sınıfı <xref:Microsoft.Office.Tools.Outlook.OutlookAddInBase> 'i hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Temel sınıflar form bölgesini desteklemek için bazı ek işlevsellik sağlar. Form bölgeleri hakkında daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
## <a name="customizing-the-user-interface-of-microsoft-office-applications"></a>Microsoft Office uygulamaları kullanıcı arabirimini özelleştirme  
 Bir VSTO eklentisini kullanarak, Microsoft Office UI uygulamaları programlı olarak özelleştirebilirsiniz. Örneğin, Şeriti özelleştirmek, özel görev bölmesini görüntülemek veya özel form bölgesini Outlook içinde oluşturun. Daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
 Visual Studio tasarımcılar ve özel görev bölmeleri, Şerit özelleştirmelerini ve Outlook form bölgeleri oluşturmak için kullanabileceğiniz sınıflar sağlar. Bu tasarımcılar ve sınıflar bu özellikleri özelleştirme işlemi basitleştirmeye yardım eder. Daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md), [Şerit Tasarımcısı](../vsto/ribbon-designer.md), ve [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
 Bu özellikler sınıflar ve tasarımcıları tarafından desteklenmeyen bir şekilde özelleştirmek istiyorsanız, bu özellikleri uygulayarak özelleştirebilirsiniz bir *genişletilebilirlik arabirimi* VSTO eklentinizi içinde. Daha fazla bilgi için bkz: [özelleştirme kullanıcı Arabirimi özellikleri tarafından kullanarak genişletilebilirlik arabirimleri](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md).  
  
 Ayrıca, kullanıcı Arabirimi, Word belgelerini ve Excel çalışma kitaplarını belgeleri ve çalışma kitaplarını davranışını genişleten konak öğeleri oluşturma tarafından değiştirebilirsiniz. Bu belgelere ve çalışma kitaplarına yönetilen denetimler eklemenize olanak sağlar. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="calling-code-in-vsto-add-ins-from-other-solutions"></a>VSTO eklentilerinde diğer çözümlerden kod çağırma  
 VSTO eklentinizi diğer Office çözümleri dahil olmak üzere diğer çözümlerle içindeki nesneleri getirebilir. VSTO eklentinizi diğer çözümlerin kullanması için etkinleştirmek istediğiniz bir hizmet sağlarsa, bu yararlıdır. Bir web hizmetinden finansal verileri hesaplamalar gerçekleştirir. Microsoft Office Excel için VSTO eklenti varsa, örneğin, diğer çözümleri bu hesaplamalar çağırarak Excel VSTO eklenti çalışma zamanında gerçekleştirebilirsiniz.  
  
 Daha fazla bilgi için bkz: [VSTO eklentileri diğer Office Çözümlerinden gelen çağırma kodda](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri geliştirme](../vsto/developing-office-solutions.md)   
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [VSTO eklentilerinde diğer Office Çözümlerinden kod çağırma](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)   
 [İzlenecek yol: Bir VSTO eklentisinde VBA'dan kod çağırma](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md)   
 [Genişletilebilirlik arabirimlerini kullanarak kullanıcı Arabirimi özelliklerini özelleştirme](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Office Çözümlerinde Kod Yazma](../vsto/writing-code-in-office-solutions.md)  
  
  