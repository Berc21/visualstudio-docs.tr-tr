---
title: "Nasıl yapılır: program aracılığıyla sıfırlama Word belgelerinde aralıkları | Microsoft Docs"
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
- documents [Office development in Visual Studio], resetting ranges
- ranges, resetting in documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 08a2b57c9f30fab0b975ecf84ef8e0fb3127d346
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-reset-ranges-in-word-documents"></a>Nasıl yapılır: Word Belgelerinde Aralıkları Program Aracılığıyla Sıfırlama
  Kullanım <xref:Microsoft.Office.Interop.Word.Range.SetRange%2A> Microsoft Office Word belgesinde var olan bir aralığı yeniden boyutlandırmak için yöntem.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-reset-an-existing-range"></a>Var olan bir aralığı sıfırlamak için  
  
1.  Belgedeki ilk yedi karakter ile başlayan bir başlangıç aralığı ayarlayın.  
  
     Aşağıdaki kod örneği bir belge düzeyi özelleştirmelerinde kullanılabilir.  
  
     [!code-vb[Trin_VstcoreWordAutomation#43](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#43)]
     [!code-csharp[Trin_VstcoreWordAutomation#43](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#43)]  
  
     Aşağıdaki kod örneği, bir VSTO eklenti kullanılabilir. Bu kod, etkin belgeyi kullanır.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#43](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#43)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#43](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#43)]  
  
2.  Kullanım <xref:Microsoft.Office.Interop.Word.Range.SetRange%2A> ikinci cümlenin aralıkta başlatıp beşinci cümlede sonunda sonlandırmak için.  
  
     [!code-vb[Trin_VstcoreWordAutomation#44](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#44)]
     [!code-csharp[Trin_VstcoreWordAutomation#44](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#44)]  
  
## <a name="document-level-customization-example"></a>Belge düzeyi özelleştirme örnek  
  
#### <a name="to-reset-an-existing-range-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde var olan bir aralığı sıfırlamak için  
  
1.  Aşağıdaki örnek bir belge düzeyi özelleştirme için tam bir örnek gösterilmektedir. Bu kodu kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#42](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#42)]
     [!code-csharp[Trin_VstcoreWordAutomation#42](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#42)]  
  
## <a name="vsto-add-in-example"></a>VSTO eklentileri örneği  
  
#### <a name="to-reset-an-existing-range-in-an-vsto-add-in"></a>Bir VSTO eklenti içinde var olan bir aralığı sıfırlamak için  
  
1.  Aşağıdaki örnek, VSTO eklenti için tam bir örnek gösterilir. Bu kodu kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#42](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#42)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#42](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#42)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: belgelerde aralıkları program aracılığıyla genişletme](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla başlangıç ve bitiş karakterlerini aralıkları alma](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Nasıl yapılır: Belgelerde Aralıkları veya Seçimleri Program Aracılığıyla Daraltma](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)  
  
  