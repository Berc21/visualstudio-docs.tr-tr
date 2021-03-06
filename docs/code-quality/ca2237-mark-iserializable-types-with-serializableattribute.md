---
title: "CA2237: ISerializable türleri SerializableAttribute ile | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2237
- MarkISerializableTypesWithSerializable
helpviewer_keywords:
- MarkISerializableTypesWithSerializable
- CA2237
ms.assetid: 9bd6bb24-a527-43dd-9952-043c0c694f46
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 75f16ce8a3158e9340c3215968f8df0170ab2c44
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2237-mark-iserializable-types-with-serializableattribute"></a>CA2237: ISerializable türleri SerializableAttribute ile işaretleyin
|||  
|-|-|  
|TypeName|MarkISerializableTypesWithSerializable|  
|CheckId|CA2237|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Harici olarak görünen bir türü uygulayan <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirimi ve türü işaretlenmemiş ile <xref:System.SerializableAttribute?displayProperty=fullName> özniteliği. Kural, temel türü seri hale getirilebilir olmayan türetilmiş türler yoksayar.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Ortak dil çalışma zamanı tarafından seri hale getirilebilir olarak tanınması için türleri ile işaretlenmelidir <xref:System.SerializableAttribute> türü özel seri hale getirme yordamı uygulaması aracılığıyla kullanıyorsa bile özniteliği <xref:System.Runtime.Serialization.ISerializable> arabirimi.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için uygulama <xref:System.SerializableAttribute> öznitelik türü.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Uygulama etki alanları arasında düzgün çalışması için seri hale getirilebilir gerektiğinden bir özel durum sınıfları için bu kuraldan gizlemek değil.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir. Açıklamadan çıkarın <xref:System.SerializableAttribute> özniteliği kural karşılamak için satır.  
  
 [!code-vb[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/VisualBasic/ca2237-mark-iserializable-types-with-serializableattribute_1.vb)]
 [!code-csharp[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/CSharp/ca2237-mark-iserializable-types-with-serializableattribute_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2236: ISerializable türler üzerinde taban sınıf yöntemlerini çağırın](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240: ISerializable'ı doğru uygulayın](../code-quality/ca2240-implement-iserializable-correctly.md)  
  
 [CA2229: Serileştirme oluşturucularını uygulayın](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: Serileştirme yöntemlerini doğru uygulama](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2235: Tüm serileştirilebilir olmayan alanları işaretleyin](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
  
 [CA2239: İsteğe bağlı alanlar için seri durumdan çıkarma metotları sağlayın](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: Serileştirme oluşturucularının güvenliğini sağlayın](../code-quality/ca2120-secure-serialization-constructors.md)