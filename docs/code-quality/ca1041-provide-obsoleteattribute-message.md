---
title: "CA1041: ObsoleteAttribute iletisi sağlayın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a7536130842c78ca2c00bab1afc3caf842e02cba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: ObsoleteAttribute iletisi sağlayın
|||  
|-|-|  
|TypeName|ProvideObsoleteAttributeMessage|  
|CheckId|CA1041|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir tür veya üye kullanarak işaretlenmiş bir <xref:System.ObsoleteAttribute?displayProperty=fullName> sahip olmayan özniteliği kendi <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> belirtilen özelliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.ObsoleteAttribute>kullanım dışı kitaplık türleri ve üyeleri işaretlemek için kullanılır. Kitaplık tüketiciler herhangi bir tür ya da kullanımdan kaldırılmış olarak işaretlenmiş üye kullanımını kaçınmalısınız. Desteklenmiyor ve daha sonra kitaplık sürümlerinden sonuç kaldırılacaktır olmasıdır. Ne zaman bir tür veya üye işaretlenmiş kullanarak <xref:System.ObsoleteAttribute> derlenir, <xref:System.ObsoleteAttribute.Message%2A> özniteliğin özelliği görüntülenir. Bu eski türü veya üye kullanıcı bilgilerini sağlar. Bu bilgiler genellikle ne kadar eski türü içerir veya üye kitaplığı tasarımcıları ve kullanmak için tercih edilen değiştirme tarafından desteklenmez.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için add `message` parametresi <xref:System.ObsoleteAttribute> Oluşturucusu.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan çünkü engelleme <xref:System.ObsoleteAttribute.Message%2A> özelliği geçersiz tür veya üye hakkında önemli bilgiler sağlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, doğru bildirilen sahip bir geçersiz üye gösterir <xref:System.ObsoleteAttribute>.  
  
 [!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
 [!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
 [!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ObsoleteAttribute?displayProperty=fullName>