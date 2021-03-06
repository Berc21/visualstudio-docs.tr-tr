---
title: "Performans Rapor Görünümü Filtresi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools, Profiler Report view filter
- Profiler Report View filter, profiling tools
ms.assetid: 35f89d86-4683-4db1-aa0c-ae0ce65fa524
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 587e76a0108f3636d851b299c30506e0d8d55d9a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="performance-report-view-filter"></a>Performans Rapor Görünümü Filtresi
Profil Oluşturucusu Rapor Görünümü Filtresi penceresi performans raporu penceresinin en üstünde yer alır. Göremiyorsanız, tıklatın **Göster filtre** düğmesi.  
  
 Sonuçlarınızı daraltmak için her filtre yan tümcesi değiştirebilirsiniz. Aşağıdaki sütunlar filtresi Oluşturucu'da kullanılabilir.  
  
|Filtre öğesi|Açıklama|  
|-----------------|-----------------|  
|Ve/veya|Seçin **ve** bir sonuç eşleşiyorsa bu yan tümce sonraki yan tümcesi hem de girintili için olmalıdır. Seçin **veya** bir sonuç eşleşiyorsa bu yan tümcesi veya sonraki yan tümcesi girintili olabilir.|  
|Alan|Alanın filtre yan tümcesi geçerli rapor dosyasında kullanılabilir veri alanları listesinden kullanmak için seçin.|  
|İşleç|Alan ve değer arasında istediğiniz ilişkiyi belirten işleci seçin.<br /><br /> = Eşittir<br /><br /> <> Eşit değildir<br /><br /> < Küçüktür<br /><br /> > Büyüktür<br /><br /> < = küçüktür veya eşittir<br /><br /> > = büyüktür veya eşittir|  
|Değer|Aranacak bir değer girin veya seçin. Bazı alanları alan için kullanılabilir değerleri listeler.|  
  
 Filtre en iyi sonuçlar verir düşündüğünüz kadar filtre yan tümcesi ekleyebilirsiniz. Tıklatın **yürütme filtre** veri dosyasına filtre uygulamak için.  
  
 Gelen **işaretleri** rapor görünümü, verileri iki işaretleri arasında toplanan veriler için rapor görünümlerini sınırlandırmak için filtre yan tümcesi oluşturabilir. Başlangıç ve bitiş verileri, sonra sağ tıklatın ve seçin raporu istediğiniz işaretleri seçin **işaretleri üzerinde filtre Ekle** veya **zaman damgaları üzerinde filtre Ekle**. Her iki süzgeçleri aynı aralığa geçerli veri dosyasındaki verilerin sınırlar; **İşaretleri üzerinde filtre Ekle** diğer .vsp dosyalara uygulanabilir.  
  
 Filtre kaydetmek için tıklatın **verme filtresi** performans raporu araç çubuğunda ve .vspf dosyanın konumu ve dosya adını belirtin. Daha önce kaydedilen bir filtreyi yüklemek için tıklayın **alma filtresi** ve kaydedilmiş filtre dosyasını bulun. Filtre dosyalar, veri dosyalarını bağımsız profil oluşturma araçları yüklü olan bilgisayarlarda filtre uygulamak için de kullanılabilir. Daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araçları verilerini performansını analiz etme](../profiling/analyzing-performance-tools-data.md)   
 [VSPerfReport](../profiling/vsperfreport.md)