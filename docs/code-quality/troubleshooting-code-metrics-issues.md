---
title: "Kod ölçümleri sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f31d0f5d236327db483c9698579c8c03129acd64
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-code-metrics-issues"></a>Kod Ölçümleri Sorunlarını Giderme
Kod ölçümleri toplarken aşağıdaki sorunlardan bazıları karşılaşabilirsiniz:  
  
-   [Visual Studio 2010 kod karmaşıklığı hesaplamalar değişiklikleri](#Changes_in_Visual_Studio_2010_code_complexity_calculations)  
  
##  <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a>Visual Studio 2010 kod karmaşıklığı hesaplamalar değişiklikleri  
 Aynı işlevi için Kod Karmaşıklığı ölçüm hesaplanır, ancak [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] önceki sürümleri tarafından hesaplanan ölçüm farklı olabilir [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] aşağıdaki durumlar için:  
  
-   Daha fazla catch blokları ya da bir işlev içeriyor. Önceki sürümlerinde [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], catch blokları hesaplamadaki dahil. İçinde [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)], her catch bloğu karmaşıklığını işlevi karmaşıklığını eklenir.  
  
-   İşlev switch (seçin durumda VB) ifadesi içermektedir. Derleyici arasındaki farklılıklar [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] ve önceki sürümleri, başarısızlığı durumları içeren bazı switch deyimleri için farklı MSIL kodu oluşturabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen Kodun Ölçüm Karmaşıklığı ve Bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)