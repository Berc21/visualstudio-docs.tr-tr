---
title: "CA1415: P çağırır doğru bildirin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a9edc52bbc1cd05ed1a3a726dcfb49f26574ccc1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415: P/Invoke'ları doğru bildirin
|||  
|-|-|  
|TypeName|DeclarePInvokesCorrectly|  
|CheckId|CA1415|  
|Kategori|Microsoft.Interoperability|  
|Yeni Değişiklik|Bölünemez-P/Invoke parametresi bildiren derlemenin dışından görülemeyen durumunda. Bir parametre bildirdiğinden P/Invoke derlemenin dışından görülebilir varsa - kesiliyor.|  
  
## <a name="cause"></a>Sebep  
 Bir platform çağırma yöntemi hatalı bildirilmiş.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir platform yöntemi erişimleri yönetilmeyen kodu çağırma ve kullanılarak tanımlanmış `Declare` anahtar sözcük [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] veya <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. Şu anda, bu kural için platform çağırma ÇAKIŞAN yapısı parametresi için bir işaretçi Win32 işlevleri hedef yöntem bildirimleri ve ilgili yönetilen parametresi için bir işaretçi değil benzeyen bir <xref:System.Threading.NativeOverlapped?displayProperty=fullName> yapısı.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için doğru platform bildirin yöntemini çağırma.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Platform çağırma kuralı ihlal ve kural karşılayan yöntemleri aşağıdaki örnekte gösterildiği.  
  
 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../code-quality/codesnippet/CSharp/ca1415-declare-p-invokes-correctly_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilmeyen kod ile birlikte çalışma](/dotnet/framework/interop/index)