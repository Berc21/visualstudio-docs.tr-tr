---
title: "CA1057: Dize URI aşırı yüklemeleri System.Uri aşırı çağrı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1057
- StringUriOverloadsCallSystemUriOverloads
helpviewer_keywords:
- StringUriOverloadsCallSystemUriOverloads
- CA1057
ms.assetid: ef1e983e-9ca7-404b-82d7-65740ba0ce20
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: afc7f989cc8b1ff04e5b7b6207663365246b6626
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1057-string-uri-overloads-call-systemuri-overloads"></a>CA1057: Dize URI aşırı yüklemeleri System.Uri aşırı yüklemelerini çağırır
|||  
|-|-|  
|TypeName|StringUriOverloadsCallSystemUriOverloads|  
|CheckId|CA1057|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Yalnızca bir dize parametresi ile değiştirilmesi tarafından farklı yöntemi aşırı bir tür bildirir bir <xref:System.Uri?displayProperty=fullName> parametre ve dize parametresi alan aşırı alan aşırı çağırmaz <xref:System.Uri> parametresi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Yalnızca dizesiyle aşırı farklı olduğundan /<xref:System.Uri> parametresi dize Tekdüzen Kaynak Tanımlayıcısı (URI) göstermek için varsayılır. Bir URI'nın dize sunumu ayrıştırma ve hataları kodlama eğilimindedir ve güvenlik açıklarına yol açabilir. <xref:System.Uri> Sınıfı, güvenli ve güvenli bir şekilde bu hizmetleri sağlar. Avantajlarından yararlanmasını <xref:System.Uri> çağrı dize aşırı sınıfı, <xref:System.Uri> dize bağımsız değişkeni kullanan aşırı yükleme.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bir örneğini oluşturur, böylece URI dize gösterimini kullanan yöntemi yeniden uygulamak <xref:System.Uri> dize bağımsız değişkeni kullanarak sınıf ve daha sonra geçirir <xref:System.Uri> sahip aşırı nesnesine <xref:System.Uri> parametresi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Dize parametresi bir URI temsil etmez, bu kural bir uyarıdan gizlemek güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir doğru uygulanan dize aşırı gösterir.  
  
 [!code-csharp[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/CSharp/ca1057-string-uri-overloads-call-system-uri-overloads_1.cs)]
 [!code-cpp[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/CPP/ca1057-string-uri-overloads-call-system-uri-overloads_1.cpp)]
 [!code-vb[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/VisualBasic/ca1057-string-uri-overloads-call-system-uri-overloads_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2234: Dizeler yerine System.Uri nesneleri gönderin](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)  
  
 [CA1056: URI özellikleri dize olmamalıdır](../code-quality/ca1056-uri-properties-should-not-be-strings.md)  
  
 [CA1054: URI parametreleri dizeler olmamalıdır](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)  
  
 [CA1055: URI dönüş değerleri dizeler olmamalıdır](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)