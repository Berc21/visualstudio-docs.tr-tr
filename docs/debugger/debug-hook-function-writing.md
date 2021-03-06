---
title: "Hata ayıklama kanca işlevi yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], CRT debug support
- debug hook functions
- hooks, debug
- hooks
- debugging [CRT], debug hook functions
ms.assetid: 5510635f-cf69-4907-b72d-ae27af1f19af
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b5071e2fd7c8114cb13697eef4a4ddfa32d95718
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debug-hook-function-writing"></a>Hata Ayıklama Kanca İşlevi Yazma
Bu bölümde, hata ayıklayıcı'nın normal işlem içindeki önceden tanımlanmış bazı noktaları kodunuzu eklemeye izin veren, yazabilirsiniz özel hata ayıklama kanca işlevleri açıklanmaktadır.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [İstemci blok kanca işlevleri](../debugger/client-block-hook-functions.md)  
 Kılavuz ve prototip doğrulamak veya _clıent_block bloklarında depolanan verileri içeriğini raporun işlevler yazma için sağlar.  
  
 [Atama kanca işlevleri](../debugger/allocation-hook-functions.md)  
 Bir ayırma kanca işlevini tanımlar, farklı kullanımları, kısıtlamalar, çıkış noktaları inceler ve prototip sağlar.  
  
 [Ayırma kancaları ve CRT bellek ayırma](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)  
 Kısıtlama açıkça yoksayılıyor, atama kanca işlevleri açıklanır `_CRT_BLOCK` iç bellek C çalışma zamanı kitaplığı işlevleri yapılan her çağrı yaparsanız engeller. Atama kanca değil yoksayarsanız Bu konu ayrıca sonuçları listeler `_CRT_BLOCK` bloklarla (örnekler) ve varsayılan yerleşimi değiştirmek nasıl kanca işlevini **CrtDefaultAllocHook**.  
  
 [Kanca işlevlerini raporlama](../debugger/report-hook-functions.md)  
 Ele `_CrtSetReportHook`, filtre uygulamak için kullanabileceğiniz raporları ayırmaları belirli türlerdeki odaklanmak için. Bu konu aynı zamanda bir prototip sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [CRT hata ayıklama teknikleri](../debugger/crt-debugging-techniques.md)  
 CRT hata ayıklama kitaplığı, raporlama, makroları kullanma dahil olmak üzere C çalışma zamanı kitaplığı için ayıklama teknikleri bağlantılar arasındaki farklılıklar `malloc` ve `_malloc_dbg`, hata ayıklama kanca işlevleri ve CRT hata ayıklama yığınını yazma.