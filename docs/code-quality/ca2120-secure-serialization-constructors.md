---
title: "CA2120: Serileştirme oluşturucularının güvenliğini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2120
- SecureSerializationConstructors
helpviewer_keywords:
- SecureSerializationConstructors
- CA2120
ms.assetid: e9989da1-55a0-43f8-9aa9-da86afae3b41
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e28d76315b3ef5844bd9b525764e6f5a5111ef56
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2120-secure-serialization-constructors"></a>CA2120: Serileştirme oluşturucularının güvenliğini sağlayın
|||  
|-|-|  
|TypeName|SecureSerializationConstructors|  
|CheckId|CA2120|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Tür uygular <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirimi, bir temsilci ya da arabirimi değildir ve kısmen güvenilen arayanlara izin veren bir derlemede bildirilir. Alan bir oluşturucu türüne sahip bir <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> nesne ve <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> nesne (seri hale getirme Oluşturucusu imzası). Bu oluşturucu tarafından güvenlik denetimi güvenli değildir, ancak bir veya daha fazla türü normal kurucularda güvenli.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, özel serileştirme destekleyen türler için geçerlidir. Bunu uygularsa bir tür özel serileştirme destekleyen <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirimi. Seri hale getirme Oluşturucusu gereklidir ve seri durumundan veya kullanılarak serileştirilmiş nesneler yeniden oluşturmak için kullanılan <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> yöntemi. Seri hale getirme Oluşturucusu ayırır ve nesneleri başlatır olduğundan, normal oluşturucular üzerinde mevcut olan güvenlik denetimleri de seri hale getirme Oluşturucu mevcut olması gerekir. Bu kural ihlal varsa, yalnızca bir örneği oluşturulamadı, bunu yapmak için seri hale getirme Oluşturucusu kullanabilirsiniz.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için diğer oluşturucular koruma olanlar aynı güvenlik taleplerini serileştirme Oluşturucusu koruyun.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Kural ihlal engelleme.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.  
  
 [!code-csharp[FxCop.Security.SerialCtors#1](../code-quality/codesnippet/CSharp/ca2120-secure-serialization-constructors_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2229: Serileştirme oluşturucularını uygulayın](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2237: ISerializable türleri SerializableAttribute ile işaretleyin](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>