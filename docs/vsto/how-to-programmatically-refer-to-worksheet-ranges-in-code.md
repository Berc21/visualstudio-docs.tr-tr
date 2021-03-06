---
title: "Nasıl yapılır: program aracılığıyla çalışma sayfası aralıklarına başvuran | Microsoft Docs"
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
- ranges, referring to
- worksheets, referring to ranges
- referring to worksheet ranges
- Excel [Office development in Visual Studio], referring to worksheet ranges
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 001efb4609059ba68a0a6a5f9c30d2f416805013
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-refer-to-worksheet-ranges-in-code"></a>Nasıl yapılır: Koddaki Çalışma Sayfası Aralıklarına Program Aracılığıyla Bakma
  Benzer bir işlem içeriğine başvurmak için kullanacağınız bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi veya yerel bir Excel aralık nesnesi.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>NamedRange denetimi kullanma  
 Aşağıdaki örnek, bir <xref:Microsoft.Office.Tools.Excel.NamedRange> bir çalışma sayfasına ve aralıktaki hücreye metin ekler.  
  
#### <a name="to-refer-to-a-namedrange-control"></a>NamedRange denetimi başvurmak için  
  
1.  Bir dizeyi atamak <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> özelliği <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim. Bu kod sayfa sınıfında değil yerleştirilmelidir `ThisWorkbook` sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#46](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#46)]
     [!code-vb[Trin_VstcoreExcelAutomation#46](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#46)]  
  
## <a name="using-native-excel-ranges"></a>Yerel Excel aralıklarını kullanma  
 Aşağıdaki örnek, yerel bir Excel aralığı çalışma sayfasına ekler ve aralıktaki hücreye metin ekler.  
  
#### <a name="to-refer-to-a-native-range-object"></a>Yerel aralık nesnesine başvurmak için  
  
1.  Bir dizeyi atamak <xref:Microsoft.Office.Interop.Excel.Range.Value2%2A> aralığın özelliği.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#47](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#47)]
     [!code-vb[Trin_VstcoreExcelAutomation#47](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#47)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Aralıklarla çalışma](../vsto/working-with-ranges.md)   
 [Nasıl yapılır: program aracılığıyla çalışma sayfalarında yazım denetimi](../vsto/how-to-programmatically-check-spelling-in-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki aralıklara stilleri uygulayın](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla otomatik olarak doldurma artımlı şekilde değişen verilerle birlikte aralıkları](../vsto/how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data.md)   
 [Nasıl yapılır: program aracılığıyla çalışma sayfası aralıklarına metin arama](../vsto/how-to-programmatically-search-for-text-in-worksheet-ranges.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  