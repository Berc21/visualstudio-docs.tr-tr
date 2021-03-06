---
title: "Taşınabilirlik uyarıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.PortabilityRules
helpviewer_keywords:
- portability warnings
- managed code analysis warnings, portability warnings
- warnings, portability
ms.assetid: 902e859a-2153-4970-baaa-8a5b4a11806f
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: efd2d56700c70b27771623e618f61675b174da01
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="portability-warnings"></a>Taşınabilirlik Uyarıları
Taşınabilirlik uyarıları taşınabilirlik farklı işletim sistemleri arasında destekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1900: Değer tür alanları taşınabilir olmalıdır](../code-quality/ca1900-value-type-fields-should-be-portable.md)|Bu kural, bir açık düzeni özniteliğini kullanarak bildirilen yapıları 64-bit işletim sistemlerinde yönetilmeyen kod için sıralanmış zaman doğru uyuşacağı denetler.|  
|[CA1901: P/Invoke bildirimleri taşınabilir olmalıdır](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|Bu kural her parametre boyutunu ve P/Invoke dönüş değerini değerlendirir ve bunların boyut 32-bit ve 64-bit işletim sistemlerinde yönetilmeyen kod için sıralanmış doğru olduğunu doğrular.|  
|[CA1903: Yalnızca hedeflenen çerçeveden API kullanın](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|Bir üye veya tür, bir üye veya projedeki hedeflenen çerçeve ile birlikte dahil edilmemiş hizmet paketinde tanıtılmış türü kullanır.|