---
title: "Nasıl yapılır: program aracılığıyla bir veri kaynağı Office belgesinden önbelleğe | Microsoft Docs"
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
- Office applications [Office development in Visual Studio], data
- datasets [Office development in Visual Studio], caching
- StartCaching method
- data caching [Office development in Visual Studio], programmatically
- data [Office development in Visual Studio], caching
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 09d4b46aaa68a92ffb9ddfe70f329e97a1b7526d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-cache-a-data-source-in-an-office-document"></a>Nasıl Yapılır: Veri Kaynağını Programlamayla Office Belgesinden Önbelleğe Alma
  Program aracılığıyla bir veri nesnesi bir belge veri önbelleğindeki çağırarak ekleyebileceğiniz `StartCaching` gibi bir konak yöntemi öğesi bir <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook>, veya <xref:Microsoft.Office.Tools.Excel.Worksheet>. Bir veri nesnesi çağırarak veri önbelleğinden kaldırma `StopCaching` konak öğesinin yöntemi.  
  
 `StartCaching` Yöntemi ve `StopCaching` yöntemi her ikisi de özeldir, ancak bu IntelliSense içinde görüntülenir.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Kullandığınızda `StartCaching` veri önbelleğine, veri nesnesi bir veri nesnesi ekleme yöntemi ile bildirilmesi gerekmez <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> özniteliği. Ancak, veri nesnesi veri önbelleğine eklenecek belirli gereksinimleri karşılaması gerekir. Daha fazla bilgi için bkz: [veri önbelleğe alma](../vsto/caching-data.md).  
  
### <a name="to-programmatically-cache-a-data-object"></a>Program aracılığıyla bir veri nesnesini önbelleğe almak için  
  
1.  Veri nesnesi bir yöntem içinde değil sınıf düzeyinde bildirin. Bu örnekte, bildirdiğiniz varsayılır bir <xref:System.Data.DataSet> adlı `dataSet1` programlı olarak önbelleğe almak istediğiniz.  
  
     [!code-csharp[Trin_VstcoreDataExcel#12](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#12)]
     [!code-vb[Trin_VstcoreDataExcel#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#12)]  
  
2.  Veri nesnesi örneği ve'ı çağırın `StartCaching` yöntemi geçişi veri nesnesi adına ve belge veya çalışma sayfası örneği.  
  
     [!code-csharp[Trin_VstcoreDataExcel#13](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#13)]
     [!code-vb[Trin_VstcoreDataExcel#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#13)]  
  
### <a name="to-stop-caching-a-data-object"></a>Bir veri nesnesini önbelleğe alma işlemini durdurmak için  
  
1.  Çağrı `StopCaching` yöntemi geçişi veri nesnesi adına ve belge veya çalışma sayfası örneği. Bu örnek, sahibi olduğunuzu varsayar. bir <xref:System.Data.DataSet> adlı `dataSet1` önbelleğe alma işlemini durdurmak istediğiniz.  
  
     [!code-csharp[Trin_VstcoreDataExcel#14](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#14)]
     [!code-vb[Trin_VstcoreDataExcel#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#14)]  
  
    > [!NOTE]  
    >  Çağırmayın `StopCaching` için olay işleyicisinden `Shutdown` bir belgenin ya da çalışma olay. Zamana göre `Shutdown` olayı, çok geç veri önbelleğini değiştirmek için. Hakkında daha fazla bilgi için `Shutdown` olayı bkz [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Verileri önbelleğe alma](../vsto/caching-data.md)   
 [Nasıl yapılır: veri kullanımı için çevrimdışı veya sunucuda önbelleğe alma](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [Nasıl yapılır: bir parola korumalı belgede veriyi önbelleğe alma](../vsto/how-to-cache-data-in-a-password-protected-document.md)   
 [Sunucudaki belgelerde verilere erişme](../vsto/accessing-data-in-documents-on-the-server.md)   
 [Verileri Kaydetme](/visualstudio/data-tools/saving-data)  
  
  