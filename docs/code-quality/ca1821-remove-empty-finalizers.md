---
title: "CA1821: Boş Sonlandırıcıları kaldırın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 98aebdcc889cdd3bd2bbe124b00a572e066b0e4a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: Boş sonlandırıcıları kaldırın
|||  
|-|-|  
|TypeName|RemoveEmptyFinalizers|  
|CheckId|CA1821|  
|Kategori|Microsoft.Performance|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir tür boş, yalnızca temel tür sonlandırıcıyı çağıran veya koşullu olarak yöntemleri yayılan yalnızca çağıran bir sonlandırıcı uygular.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Güncelleştirirken, nesne kullanım süresini izleme söz konusu olduğunda ek performans yükü nedeniyle sonlandırıcılardan kaçının. Nesne topladığı önce atık toplayıcı sonlandırıcıyı çalıştırın. Başka bir deyişle, iki koleksiyon nesnesi toplamak için gerekli olacaktır. Boş bir Sonlandırıcısı bu ek yükü bir fayda eklenen doğurur.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Boş sonlandırıcıyı kaldırın. Bir sonlandırıcı hata ayıklama için gereklidir, tüm sonlandırıcıyı içine `#if DEBUG / #endif` yönergeleri.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural gelen iletiyi bastırmak değil. Sonlandırma gizlemek için hata performansı düşürür ve hiçbir avantaj sağlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kaldırılmalıdır boş bir Sonlandırıcısı, içine bir sonlandırıcı gösterir `#if DEBUG / #endif` yönergeleri ve kullandığı bir sonlandırıcı `#if DEBUG / #endif` yönergeleri doğru.  
  
 [!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../code-quality/codesnippet/CSharp/ca1821-remove-empty-finalizers_1.cs)]