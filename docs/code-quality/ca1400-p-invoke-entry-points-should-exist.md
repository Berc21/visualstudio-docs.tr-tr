---
title: "CA1400: P-Invoke giriş noktaları bulunmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1400
- PInvokeEntryPointsShouldExist
helpviewer_keywords:
- PInvokeEntryPointsShouldExist
- CA1400
ms.assetid: 1d64e470-7b2f-4cca-8fb0-ac92829e6332
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 95e4b0841cfed5ae5ba2428a9a38da2ab43b8527
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1400-pinvoke-entry-points-should-exist"></a>CA1400: P/Invoke giriş noktaları bulunmalıdır
|||  
|-|-|  
|TypeName|PInvokeEntryPointsShouldExist|  
|CheckId|CA1400|  
|Kategori|Microsoft.Interoperability|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Genel veya korumalı bir yöntem ile işaretlenmiş <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. Yönetilmeyen kitaplık bulunamadı ya da yöntem için bir işlev kitaplığında eşleştirilemedi. Tam olarak belirlenen yöntem adı kural bulamazsanız, ANSI veya joker karakter sürümlerini yöntemi için yöntem adı '' veya 'W' suffixing tarafından görünüyor. Eşleşme bulunamazsa, kural __stdcall ad biçimi kullanarak bir işlev bulmaya çalışır (_MyMethod@12, 12 bağımsız değişkenler uzunluğunu temsil ettiği). Eşleşme ve yöntem adı '#' ile başlayan, kural işlevi için bir ad başvuru yerine sıralı bir başvuru olarak arar.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Derleme zamanı Denetimsiz emin olmak kullanılabilir işaretlenir yöntemleri <xref:System.Runtime.InteropServices.DllImportAttribute> başvurulan yönetilmeyen DLL'de bulunur. Ortak Dil Çalışma Zamanı Kitaplığı'nda belirtilen ada sahip bir işlev yok veya yöntemi için bağımsız işlev bağımsız değişkenleri eşleşmiyor, bir özel durum oluşturur.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için sahip yöntemi düzeltmek <xref:System.Runtime.InteropServices.DllImportAttribute> özniteliği. Yönetilmeyen kitaplığı varolduğundan ve yöntemi içeren derlemenin aynı dizinde olduğundan emin olun. Kitaplık bulunmalı ve düzgün başvurulan ise, yöntem adı, dönüş türü ve bağımsız değişkeni imza kitaplığı işlevi eşleştiğini doğrulayın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Yönetilmeyen kitaplığı başvurduğu yönetilen derleme ile aynı dizinde olduğunda bir uyarı bu kuraldan bastırmak değil. Bir yere yönetilmeyen kitaplığı bulunamadı durumda bu kuraldan gizlemek güvenli olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir. Adlı bir işlev `DoSomethingUnmanaged` kernel32.dll modülünde oluşur.  
  
 [!code-csharp[FxCop.Interoperability.DLLExists#1](../code-quality/codesnippet/CSharp/ca1400-p-invoke-entry-points-should-exist_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>