---
title: T4 Çıkış yönergesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: dc226af7afb14d180dfdc823e293365df2a7a9ca
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="t4-output-directive"></a>T4 Çıkış Yönergesi
İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] metin şablonları `output` yönergesi dosya adı uzantısı ve dönüştürülen dosyanın kodlamasını tanımlamak için kullanılır.  
  
 Örneğin, varsa, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje içeriyor adlı bir şablon dosyası **MyTemplate.tt** aşağıdaki yönergesi içerir:  
  
 `<#@output extension=".cs"#>`  
  
 ardından [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] adlı bir dosya oluşturur **MyTemplate.cs**  
  
 `output` Bir çalışma zamanı (önceden işlenmiş) metin şablonu yönerge gerekli değildir. Bunun yerine, uygulamanızı çağrılarak oluşturulan dize edinir `TextTransform()`. Daha fazla bilgi için bkz: [T4 metin şablonları ile çalışma zamanı metin oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
## <a name="using-the-output-directive"></a>Çıktı yönergesi kullanma  
  
```  
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>  
```  
  
 Olmamalıdır birden fazla `output` her metin şablonu yönerge.  
  
## <a name="extension-attribute"></a>Uzantı özniteliği  
 Oluşturulan metin çıkış dosyasının dosya adı uzantısını belirtir.  
  
 Varsayılan değer **.cs**  
  
 Örnekler:  
 `<#@ output extension=".txt" #>`  
  
 `<#@ output extension=".htm" #>`  
  
 `<#@ output extension=".cs" #>`  
  
 `<#@ output extension=".vb" #>`  
  
 Kabul edilebilir değerler:  
 Tüm geçerli dosya adı uzantısı.  
  
## <a name="encoding-attribute"></a>kodlama özniteliği  
 Çıktı dosyası oluşturulduğunda kullanılacak kodlama belirtir. Örneğin:  
  
 `<#@ output encoding="utf-8"#>`  
  
 Kodlama metin şablonu dosya tarafından kullanılan varsayılan değerdir.  
  
 Kabul edilebilir değerler:  
 `us-ascii`  
  
 `utf-16BE`  
  
 `utf-16`  
  
 `utf-8`  
  
 `utf-7`  
  
 `utf-32`  
  
 `0` (Sistem varsayılan)  
  
 Genel olarak, Web adı dize veya kod sayfası sayısı tarafından döndürülen Kodlamalar birini kullanabilirsiniz <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=fullName>.