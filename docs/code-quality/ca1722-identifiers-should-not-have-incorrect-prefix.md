---
title: "CA1722: Tanımlayıcıların hatalı öneki olmalıdır değil | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IdentifiersShouldNotHaveIncorrectPrefix
- CA1722
helpviewer_keywords:
- CA1722
- IdentifiersShouldNotHaveIncorrectPrefix
ms.assetid: c3313c51-d004-4f9a-a0d1-6c4c4a1fb1e6
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 141adcf6e21c7e0c8d737411988e73fbfbece805
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1722-identifiers-should-not-have-incorrect-prefix"></a>CA1722: Tanımlayıcıların önekleri yanlış olmamalıdır
|||  
|-|-|  
|TypeName|IdentifiersShouldNotHaveIncorrectPrefix|  
|CheckId|CA1722|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Tanımlayıcı hatalı bir ön ekine sahip.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kural gereği, programlama öğelerinin belirli bir önek ile başlayan adları vardır.  
  
 Tür adları belirli bir önek yoksa ve bir 'C' önüne değil. Bu kural ihlalleri 'CMyClass' gibi tür adları için raporlar ve 'Önbellek' gibi tür adları ihlali bildirmiyor.  
  
 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır öğrenme eğrisini azaltır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Önek tanımlayıcıdan kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1715: Tanımlayıcıların önekleri doğru olmalıdır](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)