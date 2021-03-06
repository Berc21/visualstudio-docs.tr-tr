---
title: "CA1064: Özel durumlar genel olmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1064
- ExceptionsShouldBePublic
helpviewer_keywords:
- ExceptionsShouldBePublic
- CA1064
ms.assetid: 83eb224c-2456-4368-acf4-3b3378e67759
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b376de69c288a084ff3bb33aba1e1b8a0bc881e5
ms.sourcegitcommit: 3285243d6c0521266053340fe06505885d12178b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2018
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064: Özel durumlar genel olmamalıdır
|||  
|-|-|  
|TypeName|ExceptionsShouldBePublic|  
|CheckId|CA1064|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Bir ortak olmayan özel doğrudan türetilen <xref:System.Exception>, <xref:System.SystemException>, veya <xref:System.ApplicationException>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Dahili bir özel durum yalnızca kendi iç kapsam içinde görünür olur. İç kapsam dışında kalan özel durumlardan sonra, sadece basit istisnalar istisna yakalamak için kullanılabilir. İç özel durum öğesinden devralınan <xref:System.Exception>, <xref:System.SystemException>, veya <xref:System.ApplicationException>, harici kod ne yapacağını özel durumla bilmesi için yeterli bilgiye sahip değil.  
  
 Ancak, temel olarak için iç özel duruma daha sonra kullanılan genel bir özel durum kodu varsa, daha fazla kod çıkışı temel özel durumla akıllı bir şeyler kuramaz varsaymak uygun olur. Genel özel durum tarafından sağlanan değerinden daha fazla bilgi gerekir <xref:System.Exception>, <xref:System.SystemException>, veya <xref:System.ApplicationException>.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Özel durum Genel hale getirmek veya iç özel durum olmayan ortak bir özel durum türetilen <xref:System.Exception>, <xref:System.SystemException>, veya <xref:System.ApplicationException>.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Özel durum, kendi iç kapsamda yakalanan tüm durumlarda eminseniz bu kural bir iletiden engelleyin.  
  
## <a name="example"></a>Örnek  
 Özel durum sınıfı doğrudan özel durumundan türetilen ve iç olduğu için bu kural ilk örnek yöntemi üzerinde FirstCustomException ateşlenir. Sınıf de doğrudan özel durumundan türetilen rağmen sınıf ortak bildirildiğinden kural SecondCustomException sınıfında etkinleşmez. Doğrudan türemiyor çünkü üçüncü sınıfı kural ayrıca başlatılmıyor <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, veya <xref:System.ApplicationException?displayProperty=fullName>.  
  
 [!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../code-quality/codesnippet/CSharp/ca1064-exceptions-should-be-public_1.cs)]
