---
title: "Nasıl yapılır: belgelerden tüm açıklamaları program aracılığıyla kaldırma | Microsoft Docs"
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
- documents [Office development in Visual Studio], removing comments
- comments, removing from documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4210a300b8ad39005dcb6584bdc0345a9424f0fe
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-remove-all-comments-from-documents"></a>Nasıl yapılır: Belgelerden Tüm Açıklamaları Program Aracılığıyla Kaldırma
  Microsoft Office Word belgesinden tüm açıklamaları kaldırmak için TümAçıklamalarıSil yöntemini kullanın.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-remove-all-comments-from-a-document-that-is-part-of-a-document-level-customization"></a>Belge düzeyi özelleştirme parçası olan bir belgedeki tüm açıklamaları kaldırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Word.Document.DeleteAllComments%2A> yöntemi `ThisDocument` projenizdeki sınıfı. Bu kod örneği kullanmak için çalıştırın `ThisDocument` sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#119)]  
  
### <a name="to-remove-all-comments-from-a-document-by-using-an-vsto-add-in"></a>Bir VSTO eklenti kullanarak bir belgedeki tüm açıklamaları kaldırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word._Document.DeleteAllComments%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Document> açıklamaları kaldırmak istediğiniz.  
  
     Aşağıdaki kod örneğinde, etkin belgedeki tüm açıklamaları kaldırır. Bu kod örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#119)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: belgelerde metne program aracılığıyla açıklamaları ekleme](../vsto/how-to-programmatically-add-comments-to-text-in-documents.md)   
 [Belge Konak Öğesi](../vsto/document-host-item.md)  
  
  