---
title: "Form bölgesine çalışma zamanında erişme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Inspectors [Office development in Visual Studio]
- Explorers [Office development in Visual Studio]
- form regions [Office development in Visual Studio], accessing at run time
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 70e9a970251aa5b95cff5983f5e2ce5e0c804a61
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="accessing-a-form-region-at-run-time"></a>Form Bölgesine Çalışma Zamanında Erişme
  
  
|Uygulandığı öğe:|  
|----------------|  
|Bu konudaki bilgiler, yalnızca aşağıdaki Microsoft Office proje türleri ve sürümleri için geçerlidir. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).<br /><br /> **Proje türü**<br /><br /> -VSTO eklentisi projelerine<br /><br /> **Microsoft Office sürümü**<br /><br /> -   [!INCLUDE[Outlook_14_short](../vsto/includes/outlook-14-short-md.md)]|  
  
 Kullanım `Globals` erişim form bölgeleri sınıfına her yerden Outlook projenizin içinde. Hakkında daha fazla bilgi için `Globals` sınıfı için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="accessing-form-regions-that-appear-in-a-specific-outlook-inspector-window"></a>Belirli Outlook Inspector penceresinde görünen Form bölgeleri erişme  
 Belirli bir Outlook Denetçisi'nde görüntülenen tüm form bölgeleri erişmek için arama `FormRegions` özelliği `Globals` sınıfı ve geçirin bir <xref:Microsoft.Office.Interop.Outlook.Inspector> denetçisi temsil eden nesne.  
  
 Aşağıdaki örnek, geçerli olarak odaklanmış Denetçisi'nde görünen form bölgesi koleksiyonunu alır. Bu örnek daha sonra bir form bölgesi adı koleksiyondaki erişen `formRegion1` ve metin kutusunda görüntülenen metni ayarlar `Hello World`.  
  
 [!code-vb[Trin_Outlook_FR_Access#2](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#2)]
 [!code-csharp[Trin_Outlook_FR_Access#2](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#2)]  
  
## <a name="accessing-form-regions-that-appear-in-a-specific-outlook-explorer-window"></a>Belirli Outlook Explorer penceresinde görünen Form bölgeleri erişme  
 Belirli bir Outlook Explorer'da görünen tüm form bölgeleri erişmek için arama `FormRegions` özelliği `Globals` sınıfı ve geçirin bir <xref:Microsoft.Office.Interop.Outlook.Explorer> Explorer temsil eden nesne.  
  
 Aşağıdaki örnek, geçerli olarak odaklanmış Explorer'da görünen form bölgeleri koleksiyonunu alır. Bu örnek daha sonra bir form bölgesi adı koleksiyondaki erişen `formRegion1` ve metin kutusunda görüntülenen metni ayarlar `Hello World`.  
  
 [!code-vb[Trin_Outlook_FR_Access#3](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#3)]
 [!code-csharp[Trin_Outlook_FR_Access#3](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#3)]  
  
## <a name="accessing-all-form-regions"></a>Tüm Form bölgeleri erişme  
 Tüm gezginler ve tüm denetçiler görünür tüm form bölgeleri erişmek için arama `FormRegions` özelliği `Globals` sınıfı.  
  
 Aşağıdaki örnekte tüm gezginler ve tüm denetçiler görünür form bölgeleri koleksiyonunu alır. Bu örnek daha sonra adlandırılmış bir form bölgesi erişen `formRegion1` ve metin kutusunda görüntülenen metni ayarlar `Hello World`.  
  
 [!code-vb[Trin_Outlook_FR_Access#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#1)]
 [!code-csharp[Trin_Outlook_FR_Access#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#1)]  
  
## <a name="accessing-controls-on-a-form-region"></a>Bir Form bölgesi denetimlere erişme  
 Kullanarak bir form bölgesi erişim denetimlere `Globals` sınıfı, olmalısınız denetimleri koduna erişilebilir dışında form bölgesi kod dosyası.  
  
### <a name="form-regions-designed-in-the-form-region-designer"></a>Form bölgesi Tasarımcısı'nda tasarlanan form bölgeleri  
 C# ' ta erişmek istediğiniz her denetim değiştiricisi değiştirin. Bunu yapmak için her denetim form bölgesi Tasarımcısı'nda seçin ve değiştirin **değiştiricileri** özelliğine **dahili** veya **ortak** içinde **özellikleri** penceresi. Örneğin, değiştirirseniz **değiştiricisi** özelliği `textBox1` için **dahili**, erişebilirsiniz `textBox1` yazarak `Globals.FormRegions.FormRegion1.textBox1`.  
  
 Visual Basic for değiştiricisi değiştirmeniz gerekmez.  
  
### <a name="imported-form-regions"></a>İçeri aktarılan Form bölgeleri  
 Outlook'ta tasarlanan form bölgesini içeri aktardığınızda, form bölgesi üzerindeki her denetim erişim değiştiricisi özel olur. Form bölgesi tasarımcısını alınmış bir form bölgesini değiştirmek için kullanamadığından denetimde değiştiricisi değiştirmek için bir yolu yoktur **özellikleri** penceresi.  
  
 Form bölgesi kod dosyası dışındaki bir denetime erişimi etkinleştirmek için bu denetim döndürülecek form bölgesi kod dosyasında bir özellik oluşturun.  
  
 Özellikler C# ' ta oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bildirme ve kullanma okuma yazma özellikleri &#40; C &#35; Programlama Kılavuzu &#41; ](/dotnet/csharp/programming-guide/classes-and-structs/how-to-declare-and-use-read-write-properties).  
  
 Visual Basic'de özellikler oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir özelliği (Visual Basic) oluşturma](/dotnet/visual-basic/programming-guide/language-features/procedures/how-to-create-a-property).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Outlook Form bölgeleri oluşturma yönergeleri](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [İzlenecek yol: Outlook Form Bölgesi Tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Nasıl yapılır: Outlook eklenti projesine Form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Outlook Form bölgelerindeki özel eylemler](../vsto/custom-actions-in-outlook-form-regions.md)   
 [Form bölgesini Outlook ileti sınıfıyla ilişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md)   
 [İzlenecek yol: Outlook'ta tasarlanan Form bölgesini içeri aktarma](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)   
 [Nasıl yapılır: Outlook Form bölgesini görüntülemesini engelleme](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)   
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [Çalışma Zamanında Şeride Erişme](../vsto/accessing-the-ribbon-at-run-time.md)  
  
  