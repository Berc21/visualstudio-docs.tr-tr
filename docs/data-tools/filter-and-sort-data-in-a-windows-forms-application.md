---
title: "Bir Windows Forms uygulamasındaki verileri sıralamak ve filtre | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- row states, filtering
- data views, sorting
- row version, filtering
- row states
- data views, filtering
- sorting datasets, using data views
- dataset filtering, using data views
ms.assetid: f4f100f1-776d-46dc-b2fd-5b35b98d9561
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 58117773f1f5fb973bf3ab741425d3ad7492c63f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="filter-and-sort-data-in-a-windows-forms-application"></a>Filtreleme ve bir Windows Forms uygulamasındaki verileri sıralama
Ayarlayarak verilere filtre <xref:System.Windows.Forms.BindingSource.Filter%2A> özelliği istenen kayıtları döndüren bir dize ifadesi.  
  
 Ayarlayarak verileri sıralamak <xref:System.Windows.Forms.BindingSource.Sort%2A> özelliği için sütun adı, sıralamak istediğiniz; append `DESC` azalan sırada sıralar veya eklemek için `ASC` artan sırada sıralamak için.  
  
> [!NOTE]
>  Uygulamanızı kullanmıyorsa <xref:System.Windows.Forms.BindingSource> bileşenleri filtreleyebilir ve verileri kullanarak sıralama <xref:System.Data.DataView> nesneleri. Daha fazla bilgi için bkz: [DataView](/dotnet/framework/data/adonet/dataset-datatable-dataview/dataviews).  
  
## <a name="to-filter-data-by-using-a-bindingsource-component"></a>BindingSource bileşenini kullanarak verileri filtrelemek için  
  
-   Ayarlama <xref:System.Windows.Forms.BindingSource.Filter%2A> döndürmek istediğiniz ifade özelliğine. Örneğin, aşağıdaki kod müşterilerle döndürür bir `CompanyName` "B" ile başlar:  
  
     [!code-csharp[VbRaddataDisplaying#6](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_1.cs)]
     [!code-vb[VbRaddataDisplaying#6](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_1.vb)]  
  
## <a name="to-sort-data-by-using-a-bindingsource-component"></a>BindingSource bileşenini kullanarak verileri sıralama  
  
-   Ayarlama <xref:System.Windows.Forms.BindingSource.Sort%2A> sıralamak istediğiniz sütunu özelliğine. Örneğin, aşağıdaki kodu müşteriler sıralandığı `CompanyName` sütununu azalan düzende:  
  
     [!code-csharp[VbRaddataDisplaying#7](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_2.cs)]
     [!code-vb[VbRaddataDisplaying#7](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_2.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)