---
title: "Nasıl yapılır: program aracılığıyla çalışma sayfası açıklamalarını görüntüleme | Microsoft Docs"
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
- worksheets, comments
- comments, worksheets
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c43e33030cffc78bc8ee4a0665c9334bc6e8bca7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-display-worksheet-comments"></a>Nasıl yapılır: Program Aracılığıyla Çalışma Sayfası Açıklamalarını Görüntüleme
  Program aracılığıyla gösterebilir ve Microsoft Office Excel çalışma sayfası açıklamaları gizleyebilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-display-all-comments-on-a-worksheet-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde çalışma sayfasındaki tüm açıklamaları görüntülemek için  
  
1.  Ayarlama <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> özelliğine **true** açıklamaları; göstermek istiyorsanız, aksi takdirde **false**. Bu kod sayfa sınıfında değil yerleştirilmelidir `ThisWorkbook` sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#31)]  
  
### <a name="to-display-all-comments-on-a-worksheet-in-an-application-level-vsto-add-in"></a>Çalışma sayfasındaki uygulama düzeyinde VSTO eklenti tüm açıklamaları görüntülemek için  
  
1.  Ayarlama <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> özelliğine **true** açıklamaları; göstermek istiyorsanız, aksi takdirde **false**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#21)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla ekleme ve silme çalışma sayfası açıklamaları](../vsto/how-to-programmatically-add-and-delete-worksheet-comments.md)   
 [Konak Öğelerine ve Denetimlerine Genel Bakış](../vsto/host-items-and-host-controls-overview.md)  
  
  