---
title: "DA0503: Ortalama çalışma kümesinin profili oluşturuluyor işlem için bayt cinsinden | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.503
- vs.performance.DA0503
- vs.performance.rules.DA0503
ms.assetid: 9047a494-eaaf-4679-b422-c64e8bde77a4
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3c5333a6ce2ddfa5e3d627030e71466a8c9ae0c1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="da0503-average-working-set-in-bytes-for-the-process-being-profiled"></a>DA0503: İşlem için Bayt Cinsinden Ortalama Çalışma Kümesinin profili oluşturuluyor
|||  
|-|-|  
|Kural Kimliği|DA0503|  
|Kategori|Kaynak İzleme|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|Bu bilgiler yalnızca bilgi toplandı. İşlem çalışma kümesi sayaç profil işlem tarafından fiziksel bellek kullanımını ölçer. Tüm ölçüm aralıklarında ortalama hesaplanan değer bildirdi.|  
|Kural türü|Bilgiler|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu ileti ortalama işlem şu anda bayt (çalışma kümesi) kullanarak fiziksel bellek miktarını raporlar. İşlem çalışma kümesi şu anda fiziksel bellekte bulunan işlem adres alanından sayfaları temsil eder.  
  
 Bildirilen değer işlemi başvurmuş paylaşılan bellek kesimleri yerleşik sayfalarından içerir. İşlem başvuruları sayılan paylaşılan bellek segmentlerinde bulunan paylaşılan dll dosyaları. İşlem çalışma kümesi değerini paylaşılan bellek kesimler nedeniyle işlemin ayırdığı sanal bellek miktarından daha yüksek olabilir.  
  
 Bildirilen ortalama profili oluşturuluyor işlem etkin olan tüm ölçüm aralıklarında değerdir.  
  
 İşlemin çalışma kümesi boyutu işlem etkin olarak kullanan ne kadar sanal bellek yansıtır. Fiziksel bellek (veya RAM) miktarı etkilenir uygulama ve fiziksel belleğin için Çekişme diğer çalışan işlemlerini çalıştırmak kullanılabilir. Fiziksel bellek kısıtlı, işlem çalışma kümesini bellek kullanımı etkin işlemler boyunca düzenli aralıklarla işlem çalışma kümeleri oldukça etkin olmayan sayfalarından kırpma tarafından dengelemek için çalıştığında işletim sistemleri olarak büyük ölçüde farklılık apt değeri.  
  
 İşlem çalışma kümeleri hakkında daha fazla bilgi için bkz: [çalışma kümesi](http://go.microsoft.com/fwlink/?LinkId=177830) MSDN Windows bellek yönetimi belgelerinde.  
  
## <a name="how-to-use-rule-data"></a>Kural verileri kullanma  
 Farklı sürümlerini performansını veya programın derlemeleri karşılaştırmak ya da farklı profil oluşturma senaryoları altında uygulamanın performansını anlamak için kuralı değeri kullanın.  
  
 Gitmek için Hata Listesi penceresi iletisinde çift [işaretleri Görünüm](../profiling/marks-view.md) profil oluşturma verileri görünümü. Bul **Process\Working ayarlamak** ve **Bellek\Sayfa/sn** sütun. İki sütun karşılaştırın ve artan sayfalama g/ç etkinliği ile ilişkili olarak görünen belirli program yürütme aşamaları olup olmadığını belirleyin.