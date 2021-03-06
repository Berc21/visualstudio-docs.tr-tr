---
title: "Nasıl yapılır: program aracılığıyla geçerli Outlook öğesini belirleme | Microsoft Docs"
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
- mail items [Office development in Visual Studio], current
- e-mail [Office development in Visual Studio], current item
- SelectionChange event
- Outlook [Office development in Visual Studio], current item
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: de17e299e98a46a82547bc38dfecd17a9f5aea58
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-determine-the-current-outlook-item"></a>Nasıl yapılır: Program Aracılığıyla Geçerli Outlook Öğesini Belirleme
  Bu örnek Explorer.SelectionChange olay adı geçerli klasörde ve seçili öğe hakkında bazı bilgileri görüntülemek için kullanır. Kod, daha sonra seçilen öğeyi görüntüler.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Örnek  
 [!code-vb[Trin_OL_CurrentItem#1](../vsto/codesnippet/VisualBasic/Trin_OL_CurrentItem/thisaddin.vb#1)]
 [!code-csharp[Trin_OL_CurrentItem#1](../vsto/codesnippet/CSharp/Trin_OL_CurrentItem/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Randevu, kişi ve Microsoft Office Outlook e-posta öğeleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Outlook nesne modeline genel bakış](../vsto/outlook-object-model-overview.md)   
 [Nasıl yapılır: program aracılığıyla klasörü ada göre alma](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [Nasıl yapılır: Program Aracılığıyla Belirli bir Kişi Arama](../vsto/how-to-programmatically-search-for-a-specific-contact.md)  
  
  