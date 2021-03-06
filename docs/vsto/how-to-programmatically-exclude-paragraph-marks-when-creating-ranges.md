---
title: "Nasıl yapılır: aralık oluştururken program aracılığıyla paragraf işaretlerini dışlama | Microsoft Docs"
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
- documents [Office development in Visual Studio], excluding paragraphs
- ranges, excluding paragraph marks in Word
- documents [Office development in Visual Studio], paragraph marks
- paragraphs, controlling structure
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 37af64898686da4f09730f5b46fbbfa0936ddd0e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-exclude-paragraph-marks-when-creating-ranges"></a>Nasıl yapılır: Aralık Oluştururken Program Aracılığıyla Paragraf İşaretlerini Hariç Tutma
  Oluşturduğunuz her bir <xref:Microsoft.Office.Interop.Word.Range> bir paragraf paragraf işaretlerini gibi tüm yazdırılamayan karakterler temel nesne aralığında dahil edilir. Hedef paragrafa kaynak paragrafı metin eklemek isteyebilirsiniz. Daha sonra hedef paragraf farklı paragraflara ayırmak istemiyorsanız kaynak paragrafın paragraf işaretlerini önce kaldırmalısınız. Ayrıca, paragraf işaretleri içinde paragraf biçimlendirme bilgilerini kaydedildiği varolan paragrafa aralık eklediğinizde bunu dahil istemeyebilirsiniz.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Aşağıdaki örnek yordamı iki dize değişkenleri bildirir, etkin belgedeki ilk ve ikinci paragraf içeriğini alır ve içerikler karşılıklı değiştirilir. Örnek, ardından kullanarak paragraf işaretçisini aralıktan kaldırma gösterir <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> yöntemi ve paragraf içine metin ekleme.  
  
### <a name="to-control-paragraph-structure-when-inserting-text"></a>Metin eklerken paragraf yapısını denetlemek için  
  
1.  İlk ve ikinci paragraf için iki aralık değişkeni oluşturun ve kullanarak içeriklerini alın <xref:Microsoft.Office.Interop.Word.Range.Text%2A> özelliği.  
  
     Aşağıdaki kod örneği bir belge düzeyi özelleştirmelerinde kullanılabilir.  
  
     [!code-vb[Trin_VstcoreWordAutomation#27](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#27)]
     [!code-csharp[Trin_VstcoreWordAutomation#27](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#27)]  
  
     Aşağıdaki kod örneği, bir uygulama düzeyinde VSTO eklenti kullanılabilir. Bu kod, etkin belgeyi kullanır.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#27](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#27)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#27](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#27)]  
  
2.  Ata <xref:Microsoft.Office.Interop.Word.Range.Text%2A> iki paragraf arasında metni değiştirme özelliği.  
  
     [!code-vb[Trin_VstcoreWordAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#28)]
     [!code-csharp[Trin_VstcoreWordAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#28)]  
  
3.  Her aralığı sırayla seçin ve sonuçları bir ileti kutusu içinde görüntülemek için duraklatabilirsiniz.  
  
     [!code-vb[Trin_VstcoreWordAutomation#29](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#29)]
     [!code-csharp[Trin_VstcoreWordAutomation#29](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#29)]  
  
4.  Ayarlama `firstRange` kullanarak <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> yöntemi paragraf işaretçisini artık bir parçası olan böylece `firstRange`.  
  
     [!code-vb[Trin_VstcoreWordAutomation#30](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#30)]
     [!code-csharp[Trin_VstcoreWordAutomation#30](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#30)]  
  
5.  Yeni bir dize atama ilk paragraf metni kalan Değiştir <xref:Microsoft.Office.Interop.Word.Range.Text%2A> aralığın özelliği.  
  
     [!code-vb[Trin_VstcoreWordAutomation#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#31)]
     [!code-csharp[Trin_VstcoreWordAutomation#31](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#31)]  
  
6.  Metni değiştirin `secondRange`, paragraf işaretlerini de dahil olmak üzere.  
  
     [!code-vb[Trin_VstcoreWordAutomation#32](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#32)]
     [!code-csharp[Trin_VstcoreWordAutomation#32](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#32)]  
  
7.  Seçin `firstRange` ve sonuçları bir ileti kutusu içinde görüntülemek için Duraklat ve aynı yapmak `secondRange`.  
  
     Bu yana `firstRange` tanımlandığından paragraf işaretlerini dışlamak için özgün paragrafın biçimlendirme korunur. Ancak, paragraf işaretlerini üzerinden bir cümle eklenmiş `secondRange`, ayrı paragraf kaldırılıyor.  
  
     [!code-vb[Trin_VstcoreWordAutomation#33](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#33)]
     [!code-csharp[Trin_VstcoreWordAutomation#33](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#33)]  
  
     Belge orijinal durumuna geri yükleyebilmeniz için her iki aralıkları özgün içeriği dize olarak kaydedildi.  
  
8.  Yeniden ayarlama gereksinimini `firstRange` kullanarak paragraf işaretlerini dahil etmek için <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> yöntemi için bir karakterin konumu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#34](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#34)]
     [!code-csharp[Trin_VstcoreWordAutomation#34](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#34)]  
  
9. `secondRange` klasörünü silin. Bu üç paragraf özgün konumuna geri yükler.  
  
     [!code-vb[Trin_VstcoreWordAutomation#35](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#35)]
     [!code-csharp[Trin_VstcoreWordAutomation#35](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#35)]  
  
10. Özgün paragraf metnini geri `firstRange`.  
  
     [!code-vb[Trin_VstcoreWordAutomation#36](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#36)]
     [!code-csharp[Trin_VstcoreWordAutomation#36](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#36)]  
  
11. Kullanım <xref:Microsoft.Office.Interop.Word.Range.InsertAfter%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Range> sonra özgün paragraf iki içerik yerleştirmek için nesne `firstRange`ve ardından `firstRange`.  
  
     [!code-vb[Trin_VstcoreWordAutomation#37](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#37)]
     [!code-csharp[Trin_VstcoreWordAutomation#37](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#37)]  
  
## <a name="document-level-customization-example"></a>Belge düzeyi özelleştirme örnek  
  
#### <a name="to-control-paragraph-structure-when-inserting-text-in-document-level-customizations"></a>Belge düzeyi özelleştirmelerindeki metin eklerken paragraf yapısını denetlemek için  
  
1.  Aşağıdaki örnek bir belge düzeyi özelleştirme için tam yöntemini gösterir. Bu kodu kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#26)]
     [!code-csharp[Trin_VstcoreWordAutomation#26](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#26)]  
  
## <a name="vsto-add-in-example"></a>VSTO eklentileri örneği  
  
#### <a name="to-control-paragraph-structure-when-inserting-text-in-an-vsto-add-in"></a>Bir VSTO eklenti metin eklerken paragraf yapısını denetlemek için  
  
1.  Aşağıdaki örnek, VSTO eklenti için tam yöntemi gösterir. Bu kodu kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#26)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#26](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#26)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: belgelerde aralıkları program aracılığıyla genişletme](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla daraltma aralıkları veya seçimleri](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [Nasıl yapılır: Word belgelerine program aracılığıyla metin ekleme](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [Nasıl yapılır: program aracılığıyla sıfırlama Word belgelerinde aralıkları](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  