---
title: "DA0030: Veritabanı projeleri için katman etkileşim ölçümleri toplamak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.DA0030
- vs.performance.rules.DA0030
- vs.performance.30
ms.assetid: 42b2f69d-0cfa-4854-82c4-589c3d8b4557
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a41357670b7f9c634de57f66bd292320d354dbc2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="da0030-gather-tier-interaction-measurements-for-database-projects"></a>DA0030: Veritabanı projeleri için Katman Etkileşim ölçümlerini topla
|||  
|-|-|  
|Kural Kimliği|DA0030|  
|Kategori|Profil oluşturma araçları kullanım|  
|Profil oluşturma yöntemi|Örnekleme|  
|İleti|Çok katmanlı uygulamalar için etkileşim ölçümleri toplama veritabanı kullanım desenlerini ve anahtar verileri anlamanıza yardım gecikmelerini erişecek. Uygulama yeniden katman etkileşim profil seçeneği etkin profil deneyin.|  
|Kural türü|Bilgiler|  
  
## <a name="cause"></a>Sebep  
 Çağrılar <xref:System.Data> yöntemleridir profil oluşturma verileri önemli bir kısmının ve Çalıştır profil katman etkileşim verileri toplanmadı. Yeniden profil oluşturmak ve katman etkileşim verileri ekleme göz önünde bulundurun.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Dahil olmak üzere System.Data ad alanlarında bulunan işlevlerinde önemli etkinlik olduğunda bu kural harekete <xref:System.Data.Linq> <xref:System.Data.Linq>.  
  
 Çok katmanlı uygulamalar için kendi sunu ve veri katmanlarını katmanlı Hizmetleri kullanın. Genellikle veri katmanı Microsoft Sql Server gibi bir veritabanı yönetim sistemine çalıştıran ayrı bir işlemdir. Veri katmanı bile ayrı bir makineye uygulama geri kalanından çalışıyor olabilir. Örnekleme profiller az fikirler işlevler ve işlem dışı çalışan hizmetler sağlamak veya uzaktan.  
  
 Profil Araçları ADO.NET hizmetleri zaman uyumsuz çağrıları kullanan bir Microsoft Sql Server veri katmanı ile etkileşim çok katmanlı uygulamalar için zamanlama bilgilerini toplayabilirsiniz. Katman etkileşim profil açıkça etkinleştirmelisiniz. Varsayılan olarak açık değildir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural, yalnızca bilgi amaçlıdır ve düzeltme eylemi gerektirmeyebilecek.  
  
 Visual Studio IDE'den veri profil oluşturma için katman etkileşim verileri ekleme hakkında daha fazla bilgi için bkz: [katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md). Komut satırından katman etkileşim verileri ekleme hakkında daha fazla bilgi için bkz: [katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md).