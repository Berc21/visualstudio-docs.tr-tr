---
title: "CA2119: Özel arabirimleri karşılayan yöntemleri mühürleyin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SealMethodsThatSatisfyPrivateInterfaces
- CA2119
helpviewer_keywords:
- CA2119
- SealMethodsThatSatisfyPrivateInterfaces
ms.assetid: 483d02e1-cfaf-4754-a98f-4116df0f3509
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b61a3e81ff7be1ff868f2dd9ce42dd5cb10522cb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2119-seal-methods-that-satisfy-private-interfaces"></a>CA2119: Özel arabirimleri karşılayan yöntemleri mühürleyin
|||  
|-|-|  
|TypeName|SealMethodsThatSatisfyPrivateInterfaces|  
|CheckId|CA2119|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Geçersiz kılınabilir yöntemi uygulaması devralınabilir bir ortak türü sağlar bir `internal` (`Friend` Visual Basic'te) arabirimi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Arabirim yöntemleri uygulama türüne göre değiştirilemez ortak erişilebilirlik vardır. Bir iç arabirim arabirimi tanımlayan derleme dışında uygulanacak amaçlanmamıştır bir sözleşme oluşturur. Bir iç arabirimini kullanarak bir yöntem uygulayan genel bir tür `virtual` (`Overridable` Visual Basic'te) değiştiricisi dışında derleme türetilmiş bir tür tarafından geçersiz kılınacak yöntemi sağlar. İkinci bir tür tanımlayıcı derlemesindeki yöntemini çağırır ve yalnızca iç sözleşme bekler, bunun yerine, bir dış derlemesindeki geçersiz kılınan yöntemi yürütüldüğünde davranışı tehlikeye. Bu bir güvenlik açığı oluşturur.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için aşağıdakilerden birini kullanarak derlemenin dışından kılınmasının yöntemi engelle:  
  
-   Bildiren türü olun `sealed` (`NotInheritable` Visual Basic'te).  
  
-   Bildiren türü erişilebilirliğini değiştirme `internal` (`Friend` Visual Basic'te).  
  
-   Tüm ortak oluşturucu bildiren türünden kaldırın.  
  
-   Kullanmadan yöntemi uygulaması `virtual` değiştiricisi.  
  
-   Yöntem açıkça uygulama.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu uyarıdan gizlemek güvenlidir inceledikten sonra hiçbir güvenlik sorunları varsa, kural dışında derleme yöntemi geçersiz kılınırsa Etkilenme olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `BaseImplementation`, bu kural, ihlal ediyor.  
  
 [!code-cpp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_1.cpp)]
 [!code-csharp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_1.cs)]
 [!code-vb[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_1.vb)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, önceki örnekte sanal yöntemi uyarlamasını yararlanan.  
  
 [!code-cpp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_2.cpp)]
 [!code-csharp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_2.cs)]
 [!code-vb[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_2.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimleri](/dotnet/csharp/programming-guide/interfaces/index)   
 [Arabirimler](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)