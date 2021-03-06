---
title: "Nasıl yapılır: program aracılığıyla Word tabloları oluşturma | Microsoft Docs"
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
- documents [Office development in Visual Studio], adding tables
- tables [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: cdec862635ff011049f48176b28b31835ca33139
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-create-word-tables"></a>Nasıl yapılır: Program Aracılığıyla Word Tabloları Oluşturma
  <xref:Microsoft.Office.Interop.Word.Tables> Koleksiyon üyesi olduğu <xref:Microsoft.Office.Interop.Word.Document>, <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Interop.Word.Selection>, ve <xref:Microsoft.Office.Interop.Word.Range> sınıfları bu içeriklerden herhangi birinde bir tablo oluşturabileceğiniz anlamına gelir. Kullandığınız <xref:Microsoft.Office.Interop.Word.Tables.Add%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Tables> koleksiyonu belirtilen aralıkta tablo ekleyin.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="creating-tables-in-document-level-customizations"></a>Belge düzeyi özelleştirmelerindeki tabloları oluşturma  
  
#### <a name="to-add-a-simple-table-to-a-document"></a>Basit bir tablo bir belgeye eklemek için  
  
-   Kullanım <xref:Microsoft.Office.Interop.Word.Tables.Add%2A> üç satır ve belgenin başlangıcına dört sütun içeren bir tablo ekleme yöntemi.  
  
     Aşağıdaki kod örneğini kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#86](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#86)]
     [!code-csharp[Trin_VstcoreWordAutomation#86](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#86)]  
  
 Bir tablo oluşturduğunuzda otomatik olarak eklendiğinden <xref:Microsoft.Office.Interop.Word.Tables> koleksiyonu <xref:Microsoft.Office.Tools.Word.Document> konak öğesi. Ardından tablo öğe numarası tarafından kullanarak başvurabilirsiniz <xref:Microsoft.Office.Interop.Word.Tables.Item%2A> aşağıdaki kodda gösterildiği gibi özelliği.  
  
#### <a name="to-refer-to-a-table-by-item-number"></a>Madde numarasına göre bir tabloya başvurmak için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Word.Tables.Item%2A> özelliği ve başvurmak istediğiniz tablonun öğe numarasını sağlayın.  
  
     Aşağıdaki kod örneğini kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#87](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#87)]
     [!code-csharp[Trin_VstcoreWordAutomation#87](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#87)]  
  
 Her <xref:Microsoft.Office.Interop.Word.Table> nesnesi de sahip bir <xref:Microsoft.Office.Interop.Word.Table.Range%2A> biçimlendirme ayarlamanıza olanak tanır özelliği öznitelikleri.  
  
#### <a name="to-apply-a-style-to-a-table"></a>Bir tabloya bir stil uygulamak için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Word.Table.Style%2A> tabloya Word yerleşik stil uygulamak için özellik.  
  
     Aşağıdaki kod örneğini kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#88](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#88)]
     [!code-csharp[Trin_VstcoreWordAutomation#88](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#88)]  
  
## <a name="creating-tables-in-vsto-add-ins"></a>VSTO eklentilerinde tabloları oluşturma  
  
#### <a name="to-add-a-simple-table-to-a-document"></a>Basit bir tablo bir belgeye eklemek için  
  
-   Kullanım <xref:Microsoft.Office.Interop.Word.Tables.Add%2A> üç satır ve belgenin başlangıcına dört sütun içeren bir tablo ekleme yöntemi.  
  
     Aşağıdaki kod örneğinde etkin belgeye bir tablo ekler. Bu örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#86](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#86)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#86](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#86)]  
  
 Bir tablo oluşturduğunuzda otomatik olarak eklendiğinden <xref:Microsoft.Office.Interop.Word.Tables> koleksiyonu <xref:Microsoft.Office.Interop.Word.Document>. Ardından tablo öğe numarası tarafından kullanarak başvurabilirsiniz <xref:Microsoft.Office.Interop.Word.Tables.Item%2A> aşağıdaki kodda gösterildiği gibi özelliği.  
  
#### <a name="to-refer-to-a-table-by-item-number"></a>Madde numarasına göre bir tabloya başvurmak için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Word.Tables.Item%2A> özelliği ve başvurmak istediğiniz tablonun öğe numarasını sağlayın.  
  
     Aşağıdaki kod örneğinde etkin belgeyi kullanır. Bu örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#87](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#87)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#87](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#87)]  
  
 Her <xref:Microsoft.Office.Interop.Word.Table> nesnesi de sahip bir <xref:Microsoft.Office.Interop.Word.Table.Range%2A> biçimlendirme ayarlamanıza olanak tanır özelliği öznitelikleri.  
  
#### <a name="to-apply-a-style-to-a-table"></a>Bir tabloya bir stil uygulamak için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Word.Table.Style%2A> tabloya Word yerleşik stil uygulamak için özellik.  
  
     Aşağıdaki kod örneğinde etkin belgeyi kullanır. Bu örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#88](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#88)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#88](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#88)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla metin ve Word tablolarında hücrelere biçimlendirme ekleme](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)   
 [Nasıl yapılır: program aracılığıyla Word tablolarına satır ve sütun ekleme](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)   
 [Nasıl yapılır: belge özellikleriyle Word tablolarını program aracılığıyla doldurma](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  