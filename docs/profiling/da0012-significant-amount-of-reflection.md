---
title: "DA0012: Önemli miktarda yansıma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DAReflection
- vs.performance.12
- vs.performance.rules.DA0012
- vs.performance.DA0011
ms.assetid: c92a1d76-21fa-426e-8b1b-a3c08e9bcbca
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 203de647342affb9d81f0a57d0bcd44ac983f307
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="da0012-significant-amount-of-reflection"></a>DA0012: Önemli miktarda Yansıma
|||  
|-|-|  
|Kural Kimliği|DA0012|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemleri|Örnekleme|  
|İleti|Yansıma aşırı kullanıyor olabilir. Bu pahalı bir işlemdir.|  
|Kural türü|Uyarı|  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma verileri önemli bir kısmının çağrıları InvokeMember ve GetMember gibi System.Reflection yöntemleri veya MemberInvoke gibi türü yöntemleri için aynıdır. Mümkün olduğunda, bu yöntemleri bağımlı derlemeleri yöntemleri için erken bağlama değiştirerek göz önünde bulundurun.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Yansıma, uygulamanızın bağımlı bir çalışma zamanı derleme geç bağlama gerçekleştirmek ya da oluşturmak ve yeni türleri çalışma zamanı sırasında dinamik olarak çalıştırmak için kullanılan .NET Framework'ün esnek bir özelliğidir. Ancak, sık kullanılan veya sıkı Döngülerde adlı bu teknikler performansı düşürebilir.  
  
 Daha fazla bilgi için bkz: [yansıma ve geç bağlama](http://go.microsoft.com/fwlink/?LinkId=177826) bölüm 5 bölümünü — geliştirme yönetilen kod performans Microsoft Patterns and Practices geliştirme .NET uygulama performansı ve ölçeklenebilirliği hacmi MSDN Kitaplığı.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gitmek için Hata Listesi penceresi iletisinde çift [işlev Ayrıntıları görünümü](../profiling/function-details-view.md) profil oluşturma veri. İşlevleri çağırma .NET yansıma API'lerini en sık rastlanan kullanılmasını sağlamak program bölümlerini bulmak için System.Type veya System.Reflection yönteminin inceleyin. Meta veri döndüren yöntemler kullanmaktan kaçının. Uygulamanızın performansını önemli olduğunda geç bağlama ve çalışma zamanında dinamik olarak türleri oluşturma kullanmaktan kaçının gerekebilir.