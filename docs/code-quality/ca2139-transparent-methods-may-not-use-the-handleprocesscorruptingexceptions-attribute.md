---
title: "CA2139: Saydam yöntemler HandleProcessCorruptingExceptions özniteliğini kullanamaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2139
ms.assetid: 45a0328a-add7-40f9-8934-dff59beb02b3
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3852955704bb218ac252d4c4c5edbbf1a0f5927c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute"></a>CA2139: Saydam yöntemler HandleProcessCorruptingExceptions özniteliğini kullanamaz
|||  
|-|-|  
|TypeName|TransparentMethodsMustNotHandleProcessCorruptingExceptions|  
|CheckId|CA2139|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Saydam bir yöntem ile işaretlenmiş <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> özniteliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural saydam ve bir işlemi kullanarak özel durum bozulmasını işlemek girişiminde herhangi bir yöntemini harekete <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> özniteliği. Özel durum bozulmasını bir tür özel durumlar CLR sürüm 4.0 özel durum sınıflandırılması işlemdir <xref:System.AccessViolationException>. HandleProcessCorruptedStateExceptionsAttribute özniteliği, sadece kritik güvenlik yöntemleri tarafından kullanılır ve saydam bir yöntem uygulanırsa yoksayılır. İşlem bozulan özel durumları işlemek için bu yöntem güvenlik açısından kritik veya güvenlik güvenli kritik duruma gerekir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için kaldırmak <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> özniteliği ya da yöntemiyle işaretleyin <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, saydam bir yöntem ile işaretlenen <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> özniteliği ve kural başarısız olur. Yöntemi de ile işaretlenmelidir <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği.  
  
 [!code-csharp[FxCop.Security.CA2139.TransparentMethodsMustNotHandleProcessCorruptingExceptions#1](../code-quality/codesnippet/CSharp/ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute_1.cs)]