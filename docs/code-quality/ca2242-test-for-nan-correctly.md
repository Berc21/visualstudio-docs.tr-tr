---
title: "CA2242: NaN için doğru sınayın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TestForNaNCorrectly
- CA2242
helpviewer_keywords:
- CA2242
ms.assetid: e12dcffc-e255-4e1e-8fdf-3c6054d44abe
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b79c2d180bab62239dcace4bcf5b49195d339946
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2242-test-for-nan-correctly"></a>CA2242: NaN için doğru sınayın
|||  
|-|-|  
|TypeName|TestForNaNCorrectly|  
|CheckId|CA2242|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Bir ifadenin bir değeri karşı test <xref:System.Single.NaN?displayProperty=fullName> veya <xref:System.Double.NaN?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.Double.NaN?displayProperty=fullName>, bir sayı değil temsil eder, sonuçları bir aritmetik işlemin tanımlanmamış olduğunda. Bir değer arasında eşitlik testleri herhangi bir ifade ve <xref:System.Double.NaN?displayProperty=fullName> her zaman döndürür `false`. Bir değer arasında eşitsizlik testleri herhangi bir ifade ve <xref:System.Double.NaN?displayProperty=fullName> her zaman döndürür `true`.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltin ve doğru bir değeri temsil edip etmediğini belirlemek için <xref:System.Double.NaN?displayProperty=fullName>, kullanın <xref:System.Single.IsNaN%2A?displayProperty=fullName> veya <xref:System.Double.IsNaN%2A?displayProperty=fullName> değeri test etmek için.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, hatalı bir değer karşı test iki ifadeye gösterir <xref:System.Double.NaN?displayProperty=fullName> ve doğru şekilde kullanan bir ifade <xref:System.Double.IsNaN%2A?displayProperty=fullName> değeri test etmek için.  
  
 [!code-vb[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/VisualBasic/ca2242-test-for-nan-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/CSharp/ca2242-test-for-nan-correctly_1.cs)]