---
title: "Visual Studio ortamında Office projeleri | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.ProjectItem.WordDocument
- VST.ProjectItem.ExcelWorkbook
- VST.ProjectItem.ExcelTemplate
- VST.ProjectItem.ExcelSheet
- VST.ProjectItem.BlueprintCode
- VST.ProjectItem.Word
- VST.ProjectItem.Excel
- VST.ProjectItem.AddinProject
- Designer_Microsoft.VisualStudio.OfficeTools.Excel.Design.WorksheetDesigner
- VST.ProjectItem.ExtendedBluePrint
- VST.ProjectItem.WordTemplate
- Designer_Microsoft.VisualStudio.OfficeTools.Word.Design.DocumentDesigner
- VST.Designer.ExcelVST.Designer.Word
- VST.ProjectItem.ExtendedBlueprintCode
- VST.ProjectItem.BluePrint
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio]
- hidden files [Office development in Visual Studio]
- project files [Office development in Visual Studio], hidden
- Office development in Visual Studio, documents in Visual Studio
- design view, Excel
- designers, Office development in Visual Studio
- Office documents [Office development in Visual Studio]
- Office documents [Office development in Visual Studio], about documents in Visual Studio
- designers [Office development in Visual Studio]
- Word designer
- Word [Office development in Visual Studio], Word designer
- Visual Studio, Office documents in
- worksheets [Office development in Visual Studio]
- VST.Designer.ExcelVST.Designer.Word
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a937f98a11ab9c8cb9723637be902808dce86563
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="office-projects-in-the-visual-studio-environment"></a>Visual Studio Ortamında Office Projeleri
  Microsoft Office projeleri, Visual Studio'daki diğer proje türlerine (Windows Forms projeleri gibi) benzer bir geliştirme deneyimine sahiptir. Proje öğeleri Office projesi oluşturduğunuzda veya açtığınızda görüntülenen **Çözüm Gezgini**. Belge düzeyinde projeler için, belge (yani, Word belgesi veya Excel çalışma kitabı) Visual Studio'da açılır ve belge bir görsel tasarımcı gibi davranır.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="project-items-in-solution-explorer"></a>Çözüm Gezgini'nde Proje Öğeleri  
 Belge düzeyi projede **Çözüm Gezgini** aşağıdaki varsayılan öğeleri görüntüler:  
  
-   Projenin özelleştirdiği belge, çalışma kitabı ve sayfa düğümleri. Bu düğümler; belge, çalışma kitabı ve sayfalar ile ilişkili kod dosyaları için kapsayıcı işlevi görür.  
  
-   Projenin özelleştirdiği belge, çalışma kitabı ve sayfalar ile ilişkili kod dosyaları. Word projelerinde, kod dosyaları Word belgesi veya şablonu ile ilişkilidir. Excel projelerinde, kod dosyaları Excel çalışma kitabı veya şablonuyla ve çalışma kitabı veya şablondaki her bir çalışma sayfası ve grafik sayfası ile ilişkilidir.  
  
-   Doğrudan düzenlemeniz için tasarlanmamış gizli proje dosyaları. Daha fazla bilgi için bkz: [gizli proje dosyalarını](#hiddenfiles).  
  
 Bir VSTO eklenti projesindeki **Çözüm Gezgini** aşağıdaki varsayılan öğeleri görüntüler:  
  
-   Uygulama düğümü. Bu düğümü aynı ana bilgisayar uygulaması gibi adda **Word**, **Excel**, veya **Outlook**. Bu uygulama düğümü ThisAddIn kod dosyasını içerir. Ayrıca sağlar **Namespace konak öğesi için** özelliği. Bu özellik hakkında daha fazla bilgi için bkz: [Office projelerinde Özellikler](../vsto/properties-in-office-projects.md).  
  
-   ThisAddIn kod dosyası. Bu dosyayı oluşturulan içeren `ThisAddIn` VSTO eklentinizi için sınıf. Bu sınıf hakkında daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
-   Doğrudan düzenlemeniz için tasarlanmamış gizli proje dosyaları. Daha fazla bilgi için bkz: [gizli proje dosyalarını](#hiddenfiles).  
  
### <a name="temporary-certificates"></a>Geçici Sertifikalar  
 Office projeleri de dahil adlı geçici bir sertifika *proje adı*_TemporaryKey.pfx. Bu sertifika, geliştirme sırasında projenin uygulama ve dağıtım bildirimlerini imzalamak için kullanılır. Daha fazla bilgi için bkz: [Office çözümlerine güven verme](../vsto/granting-trust-to-office-solutions.md) ve [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md).  
  
###  <a name="hiddenfiles"></a>Gizli proje dosyaları  
 Bazı proje dosyaları varsayılan olarak gizlidir. Bu dosyalar Visual Studio tarafından oluşturulur ve proje türüne göre farklılık gösterir. Gizli dosyaları görüntülemek için tıklatın **tüm dosyaları göster** içinde **Çözüm Gezgini**.  
  
 Gizli proje dosyalarında değişiklik yapmayın. Bu dosyaların doğrudan değiştirilmesi desteklenmez ve projenizin bozulmasına neden olabilir. Gizli proje dosyaları, belgede belirli değişiklikler olduğu durumlarda yeniden oluşturulur. Gizli bir proje dosyasında el ile değişiklikler yaparsanız, dosya yeniden oluşturulduğunda bu değişiklikler kaybolur.  
  
## <a name="document-designer-in-document-level-projects"></a>Belge Düzeyinde Projelerde Belge Tasarımcısı  
 Excel ve Word için belge düzeyinde projeler, Visual Studio'da projenizle ilişkili belgeyi barındıran bir tasarımcı sunar. Tasarımcı, Visual Studio ortamının dışına çıkmadan belgede değişiklik yapmanızı sağlar.  
  
 Tasarımcıda bir belgeyi açmak için kod dosyasına çift tıklayarak **Çözüm Gezgini** belge ile ilişkili. Örneğin, çalışma sayfasını açmak için **Sheet1** Excel projesinde Tasarımcısı'nda çift **Sheet1** kod dosyası.  
  
 Belgeyi tasarımcıda değiştirirken, Office uygulamasının yerel işlevselliğinden yararlanabilirsiniz. Örneğin, belgeye veya bir çalışma sayfasına metin girebilir veya tablo ya da grafik ekleme gibi görevleri gerçekleştirmek için Şerit'i kullanabilirsiniz. Varsayılan olarak, klavye kısayolu eşlemeleri Visual Studio eşlemelerine varsayılan olur. Office kullanılacak klavye eşlemeleri bunun yerine, ayarları altında değiştirmek **Microsoft Office Klavyesi ayarları** düğümünde **seçenekleri** iletişim kutusundaki **Araçları** menüsü .  
  
### <a name="controls-on-documents"></a>Belgeler Üzerindeki Denetimler  
 Sürükleyebilirsiniz *konak denetimlerini* ve Windows Forms denetimleri Visual Studio'dan **araç** belge tasarım yüzeyine. Konak denetimleri Office nesnelerinin özelleşmiş sürümleri olup (Word içerik denetimleri ve Excel aralıkları gibi), Visual Studio ile oluşturulmuş Office projelerinde kullanılabilirler. Konak denetimlerinin karşılık gelen Office nesnelerinde bulunmayan, veri bağlama ve ek olaylar gibi ilave özellikleri vardır.  
  
 Daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md) ve [Office belgeleri genel bakış Windows Forms denetimleri](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
### <a name="excel-worksheets-and-workbooks-in-the-designer"></a>Tasarımcıda Excel Çalışma Sayfaları ve Çalışma Kitapları  
 Bir çalışma sayfasını tasarımcıda açtığınızda, çalışma sayfasını doğrudan Excel'de açtığınızda yaptığınız gibi değiştirebilirsiniz. Bir çalışma sayfası hücresine çift tıklarsanız hücre düzenleme moduna geçer. Konak denetimi içeren bir hücreye çift tıklarsanız, kod düzenleyicisi açılır ve Visual Studio denetim için varsayılan olay işleyicisini oluşturur. Diğer çalışma sayfalarına gitmek için tasarımcının en altında çalışma sayfası sekmelerine tıklayabilirsiniz.  
  
 Çalışma kitabını tasarımcıda açtığınızda tasarım yüzeyi bulunmaz. Çalışma kitabına ilişkin tasarım görünümü tasarımcıyı dolduran büyük bir bileşen alanıdır.  
  
 Çalışma kitabının ve çalışma kitabındaki tüm sayfaların ilişkili birer kod dosyası vardır. Her kod dosyası oluşturulan bir içerir *konak öğesi* çalışma kitabını veya sayfayı temsil eden sınıf. Daha fazla bilgi için bkz: [otomatikleştirme Excel genişletilmiş nesneleri kullanarak tarafından](../vsto/automating-excel-by-using-extended-objects.md).  
  
### <a name="word-documents-in-the-designer"></a>Tasarımcıda Word Belgeleri  
 Belgeyi tasarımcıda açtığınızda, doğrudan Word'de açtığınızda yaptığınız gibi değiştirebilirsiniz. Belgedeki bir sözcüğe çift tıklarsanız, sözcük seçili hale gelir. Ancak sözcük bir konak denetiminin içindeyse, kod düzenleyicisi açılır ve Visual Studio denetim için varsayılan olay işleyicisini oluşturur.  
  
 Belgenin ilişkili bir kod dosyası vardır. Oluşturulan bir kod dosyasını içeren *konak öğesi* belgeyi temsil eden sınıf. Daha fazla bilgi için bkz: [belge konak öğesi](../vsto/document-host-item.md).  
  
### <a name="design-mode-vs-run-time-mode"></a>Modu ve tasarlayın. Çalıştırma modu  
 Bir belge Visual Studio ortamında açık olduğunda, her zaman içinde *Tasarım modunda*. Bazı görevler (örneğin, belge yüzeyine bir konak denetimi sürüklemek gibi) sadece tasarım modunda gerçekleştirebilir.  
  
 Belgede görüntülemek için *çalıştırma modu*, uygulama ve belgeyi Visual Studio'nun dışında açmanız gerekir. Ayrıca, projeyi derleyip çalıştırabilirsiniz ve böylece, belge ve uygulama otomatik olarak Visual Studio'nun dışında açılır.  
  
## <a name="code-editor"></a>Kod Düzenleyicisi  
 Kod Düzenleyicisi çözümünüzdeki görünür kod dosyalarını görüntüleyip değiştirebilmenizi sağlar. Bu dosyalar çözümünüzün davranışını tanımlayan kodu içerir.  
  
 Kod Düzenleyicisi hakkında daha fazla bilgi için bkz: [kod ve Metin Düzenleyici'de kod yazma](/visualstudio/ide/writing-code-in-the-code-and-text-editor). Office projelerinde kod yazma hakkında daha fazla bilgi için bkz: [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md).  
  
## <a name="properties-window"></a>Özellikler Penceresi  
 **Özellikleri** penceresinde seçili proje öğeleri özelliklerini **Çözüm Gezgini**ve denetimleri veya belgede gibi Tasarımcısı'nda seçtiğiniz kullanıcı Arabirimi öğeleri için bir Belge düzeyi projesi. Bazı özellikler uygulamaya ve belgeye özgü olurken, bazı özellikler tüm projeler genelinde aynıdır.  
  
## <a name="data-sources-window"></a>Veri Kaynakları Penceresi  
 Kullanabileceğiniz **veri kaynakları** penceresinde bir veri kaynağı belgenin üzerine sürükleyin ve denetimi oluşturmak için belge düzeyi Office projelerindeki veri kaynağına bağlı. Daha fazla bilgi için bkz: [Visual Studio'da verilere denetimler bağlama](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Office Projelerinde Özellikler](../vsto/properties-in-office-projects.md)  
  
  