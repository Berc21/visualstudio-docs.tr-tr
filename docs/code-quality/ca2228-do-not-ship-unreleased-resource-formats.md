---
title: "CA2228: yayımlanmamış kaynak biçimlerini yollamayın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dcbd6627e17a4dfe179f485a2439aaf04c1a01ae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: Yayımlanmamış kaynak biçimlerini yollamayın
|||  
|-|-|  
|TypeName|DoNotShipUnreleasedResourceFormats|  
|CheckId|CA2228|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Kaynak dosyası bir sürümü kullanılarak oluşturuldu [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] , şu anda desteklenmiyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Yayın öncesi sürümleri kullanılarak oluşturulan kaynak dosyaların [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] .NET Framework'ün desteklenen sürümleri tarafından kullanılamayabilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için desteklenen bir sürümünü kullanarak kaynak yapı [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]k.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.