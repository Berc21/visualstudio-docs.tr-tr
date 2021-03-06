---
title: "CA2140: Saydam kod güvenlik kritik nesnelerine başvurmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2129
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2140
helpviewer_keywords:
- CA2140
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2129
ms.assetid: 251a12da-0557-47f5-a4f7-0229d590ae7b
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0970bd3a05975707cbbac3f79dbece234adb16ae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2140-transparent-code-must-not-reference-security-critical-items"></a>CA2140: Saydam kod güvenlik kritik nesnelerine başvurmamalıdır
|||  
|-|-|  
|TypeName|TransparentMethodsMustNotReferenceCriticalCode|  
|CheckId|CA2140|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Saydam bir yöntem:  
  
-   bir güvenlik kritik güvenlik özel durum türü işleme  
  
-   Güvenlik kritik türü işaretlenmiş bir parametre içeriyor  
  
-   Güvenlik kritik kısıtlamalarına sahip genel bir parametre içeriyor  
  
-   Güvenlik kritik türünde yerel bir değişken var  
  
-   Güvenlik kritik olarak işaretlenmiş bir türe başvurur  
  
-   Güvenlik kritik olarak işaretlenmiş bir yöntemi çağırır  
  
-   Güvenlik kritik olarak işaretlenmiş bir alana başvurur  
  
-   Güvenlik kritik olarak işaretlenmiş bir tür döndürür  
  
## <a name="rule-description"></a>Kural Tanımı  
 İle işaretlenen code öğesi <xref:System.Security.SecurityCriticalAttribute> güvenlik açısından kritik bir özniteliktir. Saydam bir yöntem, kritik güvenlik öğesini kullanamaz. Saydam bir tür güvenlik kritik türü kullanmayı deneyip denemeyeceğini bir <xref:System.TypeAccessException>, <xref:System.MethodAccessException> , veya <xref:System.FieldAccessException> tetiklenir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için aşağıdakilerden birini yapın:  
  
-   Güvenlik açısından kritik kodu ile kullanan code öğesi işaretlemek <xref:System.Security.SecurityCriticalAttribute> özniteliği  
  
     \-veya -  
  
-   Kaldırma <xref:System.Security.SecurityCriticalAttribute> güvenlik kritik olarak işaretlenmiş ve bunun yerine bunları işaretlediğiniz kod öğeleri özniteliğinden <xref:System.Security.SecuritySafeCriticalAttribute> veya <xref:System.Security.SecurityTransparentAttribute> özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örneklerde, saydam bir yöntemi, bir güvenlik kritik genel koleksiyon, güvenlik kritik alanı ve bir güvenlik kritik yöntemi başvurmak çalışır.  
  
 [!code-csharp[FxCop.Security.CA2140.TransparentMethodsMustNotReferenceCriticalCode#1](../code-quality/codesnippet/CSharp/ca2140-transparent-code-must-not-reference-security-critical-items_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Security.SecurityTransparentAttribute>   
 <xref:System.Security.SecurityCriticalAttribute>   
 <xref:System.Security.SecurityTransparentAttribute>   
 <xref:System.Security.SecurityTreatAsSafeAttribute>   
 <xref:System.Security?displayProperty=fullName>