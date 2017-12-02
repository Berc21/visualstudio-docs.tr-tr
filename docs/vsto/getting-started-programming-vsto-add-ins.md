---
title: "Başlarken VSTO eklentilerini programlamaya | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.ProjectItem.Outlook
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], getting started
- add-ins [Office development in Visual Studio], getting started
ms.assetid: 9ac1e6ea-9511-4633-80f9-dc7641f22b63
caps.latest.revision: "60"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 932827db3c12c3376dd74605c55e1bfed3c3e978
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="getting-started-programming-vsto-add-ins"></a>VSTO Eklentilerini Programlamaya Başlama
  Microsoft Office uygulamalarını otomatikleştirmek, uygulamanın özelliklerini genişletmek ve uygulamanın kullanıcı arabirimini (UI) özelleştirmek için VSTO eklentileri kullanabilirsiniz. Visual Studio kullanarak oluşturabileceğiniz Office çözümlerinin diğer türleri için VSTO eklentileri nasıl karşılaştırmak hakkında bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
## <a name="creating-vsto-add-in-projects"></a>VSTO eklentisi projelerine oluşturma  
 İçinde VSTO eklenti proje şablonlarından birini kullanarak VSTO eklenti projeleri oluşturma **yeni proje** iletişim kutusu. Bu şablonlar gerekli derleme başvurularını ve proje dosyalarını içerir. Visual Studio, çoğu uygulamada Office için VSTO eklentisi proje şablonları sağlar.  
  
 Bir VSTO eklenti projesi oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md). Proje şablonları hakkında daha fazla bilgi için bkz: [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md).  
  
## <a name="developing-vsto-add-in-projects"></a>VSTO eklentisi projelerine geliştirme  
 VSTO eklenti projesindeki oluşturduğunuzda, Visual Studio otomatik olarak ThisAddIn.vb oluşturur (içinde [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]) veya ThisAddIn.cs (C# ' ta) kod dosyası. Bu dosyayı içeren `ThisAddIn` VSTO eklentinizi için temel sağlayan sınıf. Bu sınıf üyeleri için VSTO eklentisi yüklü veya kaldırıldığında, ana bilgisayar uygulamasının nesne modeline erişme ve uygulamanın özelliklerini genişletmek için kodu çalıştırmak için kullanabilirsiniz. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
## <a name="automating-applications-by-using-the-object-models"></a>Nesne modelleri kullanarak uygulamaları otomatikleştirme  
 Microsoft Office uygulamalarının nesne modelleri bir VSTO eklenti karşı programlama yapabilirsiniz birçok türü ortaya çıkarır. Bu tür, uygulamayı otomatikleştirmek için kullanabilirsiniz. Örneğin, program aracılığıyla oluşturma ve Outlook içinde bir e-posta iletisi gönderin veya bir belgeyi açmasına ve içeriği Word'de ekleyin. Kodda ana bilgisayar uygulamasının nesne modeline erişme hakkında daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
 Belirli Microsoft Office uygulamalarının nesne modelleri hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md)  
  
-   [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md)  
  
-   [Outlook nesne modeline genel bakış](../vsto/outlook-object-model-overview.md)  
  
-   [InfoPath çözümleri](../vsto/infopath-solutions.md)  
  
-   [PowerPoint çözümleri](../vsto/powerpoint-solutions.md)  
  
-   [Proje çözümleri](../vsto/project-solutions.md)  
  
-   [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)  
  
## <a name="customizing-the-user-interface-of-applications"></a>Uygulamalar kullanıcı arabirimini özelleştirme  
 Bir VSTO eklenti kullanarak konak uygulamasının kullanıcı arabirimini özelleştirmek için birçok farklı yol vardır:  
  
-   Excel ve Word için belge yönetilen denetimler ekleyebilirsiniz. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
-   Uygulama destekliyorsa, Şerit özelleştirebilirsiniz. Daha fazla bilgi için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md).  
  
-   Uygulama destekliyorsa, özel görev bölmesini oluşturabilirsiniz. Daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).  
  
-   Outlook için özel form bölgesi oluşturabilirsiniz. Daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
-   Tüm Microsoft Office uygulamaları için VSTO eklentinizi içinde Windows Forms görüntüleyebilirsiniz.  
  
 Microsoft Office UI uygulamaları özelleştirme hakkında daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 VSTO eklentileri oluşturma konusunda bilgi almak için aşağıdaki izlenecek bakın:  
  
-   [İzlenecek yol: Excel için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)  
  
-   [İzlenecek yol: Outlook için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)  
  
-   [İzlenecek yol: PowerPoint için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)  
  
-   [İzlenecek yol: Proje için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)  
  
-   [İzlenecek yol: Word için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)  
  
 Bu izlenecek yollar, Office geliştirme araçlarını Visual Studio ve programlama modeli VSTO eklentileri için dağıtır.  
  
 Office projelerindeki ortak görevlerin bazıları size yol konuların listesi için bkz: [Office programlama ortak görevlerin](../vsto/common-tasks-in-office-programming.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Başlarken &#40; Office geliştirme Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)  
  
  