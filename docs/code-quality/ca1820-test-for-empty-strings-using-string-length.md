---
title: 'CA1820: Dize uzunluğunu kullanarak boş dizeler için sınayın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d044f09ca26b65506bcfb7466f59da73acfad1e4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820: Dize uzunluğunu kullanarak boş dizeler için sınayın
|||  
|-|-|  
|TypeName|TestForEmptyStringsUsingStringLength|  
|CheckId|CA1820|  
|Kategori|Microsoft.Performance|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Dize boş dizeye kullanarak karşılaştırılır <xref:System.Object.Equals%2A?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Karşılaştırma dizeleri kullanarak <xref:System.String.Length%2A?displayProperty=fullName> özelliği veya <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName> yöntemdir kullanmaktan daha önemli ölçüde daha hızlı <xref:System.Object.Equals%2A>. Bunun nedeni, <xref:System.Object.Equals%2A> ya da daha önemli ölçüde daha fazla MSIL yönergelerini çalıştıran nesnedir <xref:System.String.IsNullOrEmpty%2A> ya da almak için yürütülen yönerge sayısını <xref:System.String.Length%2A> özellik değerine ve sıfır olarak karşılaştırır.  
  
 Bilmeniz gereken, <xref:System.Object.Equals%2A> ve <xref:System.String.Length%2A> == 0 boş dizeler için farklı şekilde davranır. Değeri alınacak çalışırsanız <xref:System.String.Length%2A> boş bir dize özelliği, ortak dil çalışma zamanı oluşturur bir <xref:System.NullReferenceException?displayProperty=fullName>. Boş bir dize ve boş dize arasında bir karşılaştırma gerçekleştirirseniz, ortak dil çalışma zamanı bir özel durum değil; Karşılaştırma döndürür `false`. Null sınaması bu iki yaklaşım göreli performansını önemli ölçüde etkilemez. Hedeflerken [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)], kullanın <xref:System.String.IsNullOrEmpty%2A> yöntemi. Aksi takdirde kullanın <xref:System.String.Length%2A> karşılaştırma mümkün olduğunca ==.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için kullanılacak karşılaştırma değiştirmek <xref:System.String.Length%2A> özelliği ve test için boş bir dize. Hedefleme varsa [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)], kullanın <xref:System.String.IsNullOrEmpty%2A> yöntemi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Performans sorunu değilse bir uyarı bu kuraldan gizlemek güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, boş bir dize aramak için kullanılan farklı teknikleri gösterilmektedir.  
  
 [!code-csharp[FxCop.Performance.StringTest#1](../code-quality/codesnippet/CSharp/ca1820-test-for-empty-strings-using-string-length_1.cs)]