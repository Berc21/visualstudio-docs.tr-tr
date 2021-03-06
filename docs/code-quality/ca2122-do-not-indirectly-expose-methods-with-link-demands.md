---
title: "CA2122: bağlantı talepleri olan yöntemleri dolaylı olarak gösterme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2122
- DoNotIndirectlyExposeMethodsWithLinkDemands
helpviewer_keywords:
- DoNotIndirectlyExposeMethodsWithLinkDemands
- CA2122
ms.assetid: 3eda58e7-c6ec-41c3-8112-ae0841109c6a
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fc1d8c2ea663862e44b3092b0e2b8489eff3df6f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2122-do-not-indirectly-expose-methods-with-link-demands"></a>CA2122: Bağlantı talepleri olan yöntemleri dolaylı olarak açığa çıkarmayın
|||  
|-|-|  
|TypeName|DoNotIndirectlyExposeMethodsWithLinkDemands|  
|CheckId|CA2122|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Genel veya korumalı üyesi olan bir [bağlantı talepleri](/dotnet/framework/misc/link-demands) ve tüm güvenlik denetimleri gerçekleştirmez bir üyesi tarafından çağrılır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bağlantı talebi, yalnızca o anki çağırıcı izinlerini denetler. Bir üye `X` hiçbir güvenlik taleplerini arayanlar ve korunan kodu bir bağlantı isteği tarafından çağıran gerekli izne kullanabilirsiniz olmadan çağrı yapar `X` korumalı üye erişmek için.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bir güvenlik ekleyen [veri ve modelleme](/dotnet/framework/data/index) veya isteğe bağlı üyesine böylece artık bağlantı isteğe bağlı korumalı üye için güvenli erişim sağlar.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan güvenle gizlemek için kodunuzu operations veya zararlı bir şekilde kullanılabilir kaynaklarına kendi arayanlar vermez emin olmanız gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler kuralını ihlal eden bir kitaplığı ve kitaplığın zayıflık gösteren bir uygulama gösterir. Örnek kitaplığı birlikte kural ihlal iki yöntem sunar. `EnvironmentSetting` Yöntemi, bir bağlantı isteği Kısıtlanmamış erişim için ortam değişkenleri tarafından güvenlidir. `DomainInformation` Yöntemi çağırmadan önce kendi arayanlar hiçbir güvenlik taleplerini yapar `EnvironmentSetting`.  
  
 [!code-csharp[FxCop.Security.UnsecuredDoNotCall#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki uygulama güvenli kitaplık üyesini çağırır.  
  
 [!code-csharp[FxCop.Security.TestUnsecuredDoNot1#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_2.cs)]  
  
 Bu örnek şu çıkışı üretir.  
  
 **Güvenli olmayan üye değerinden: seattle.corp.contoso.com**   
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenli kodlama yönergeleri](/dotnet/standard/security/secure-coding-guidelines)   
 [Bağlantı talepleri](/dotnet/framework/misc/link-demands)   
 [Veri ve Modelleme](/dotnet/framework/data/index)