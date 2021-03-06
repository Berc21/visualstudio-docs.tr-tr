---
title: "CA1032: Standart özel durum oluşturucuları uygulayın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1032
- ImplementStandardExceptionConstructors
helpviewer_keywords:
- CA1032
- ImplementStandardExceptionConstructors
ms.assetid: a8623c56-273a-4c95-8d83-95911a042be7
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 640aacaf67ba20e801ac9657aeff20b091c5032e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1032-implement-standard-exception-constructors"></a>CA1032: Standart özel durum oluşturucuları uygulayın
|||  
|-|-|  
|TypeName|ImplementStandardExceptionConstructors|  
|CheckId|CA1032|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir tür genişletir <xref:System.Exception?displayProperty=fullName> ve tüm gerekli oluşturucular bildirmiyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Özel durum türleri aşağıdaki oluşturucular uygulamanız gerekir:  
  
-   Ortak NewException()  
  
-   Ortak NewException(string)  
  
-   Ortak NewException (dize, özel durum)  
  
-   korumalı veya özel NewException (SerializationInfo, StreamingContext)  
  
 Yapıcıların tüm ayarlamasını sağlamaktaki başarısızlık, istisnalarla başa çıkmayı zorlaştırabilir. Örneğin, imzası Oluşturucusu `NewException(string, Exception)` tarafından diğer özel durumlar nedeniyle özel durum oluşturmak için kullanılır. Oluşturma ve bir iç (iç içe) özel durum içerir, özel durum örneği throw bu oluşturucuyu, hangi yönetilen kod böyle bir durumda yapmalısınız olduğu. İlk üç özel durum oluşturucuları kurala göre ortak. Dördüncü Oluşturucusu korumasız sınıflardaki korumalı ve korumalı sınıflar, özel ' dir. Daha fazla bilgi için bkz: [CA2229: Serileştirme oluşturucularını uygulayın](../code-quality/ca2229-implement-serialization-constructors.md)  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için eksik oluşturucular özel durumu ekleyin ve doğru erişilebilirlik sahip olduğunuzdan emin olun.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Genel oluşturucular için farklı erişim düzeyi kullanarak ihlaline neden olduğunda bir uyarı bu kuraldan bastırmak güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal eden bir özel durum türünü ve doğru şekilde uygulanan bir özel durum türü içerir.  
  
 [!code-csharp[FxCop.Design.ExceptionMultipleCtors#1](../code-quality/codesnippet/CSharp/ca1032-implement-standard-exception-constructors_1.cs)]