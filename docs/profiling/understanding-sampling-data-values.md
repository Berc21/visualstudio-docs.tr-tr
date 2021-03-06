---
title: "Örnekleme veri değerlerini anlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sampling profiling method
- Profiling Tools, sampling
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5793fea089bd5efa53bdb356597fd7f176aa4ba0
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="understanding-sampling-data-values"></a>Örnekleme Veri Değerlerini Anlama

*Örnekleme* profili oluşturma yöntemi, profil oluşturma Visual Studio Araçları Bilgisayar işlemcisi belirlenen aralıklarla keser ve işlev çağrı yığını toplar. A *çağrı yığını* işlemci yürütülen işlevler hakkında bilgi depolar dinamik bir yapıdır.

Profil Oluşturucu analiz işlemci hedef işleminde kod yürütmek olup olmadığını belirler. İşlemci kod hedef işleminde yürütülmüyor, örnek atılır.

İşlemci hedef kod yürütüyor, profil oluşturucu çağrı yığınında her işlevi örnek sayısını artırır. Örnek alındıktan aynı anda yalnızca bir işlevi çağrı yığınında kodu yürütülüyor. Diğer yığında döndürmek bunların alt öğeleri için bekleyen işlev çağrılarını hiyerarşideki üst işlevlerdir.

Profil Oluşturucu artışlarla örnek olayı için *özel* örnek kendi yönergeleri yürütülmekte işlevi sayısı. Özel bir örnek de toplam parçası olduğundan (*dahil*) örnekleri işlevinin, şu anda etkin işlevi (bunlar dahil) örnek sayısı da artar.

 Profil Oluşturucu diğer işlevleri çağrı yığınında kapsayıcı örnek sayısını artırır.

## <a name="inclusive-samples"></a>Kapsayıcı örnekleri

Hedef işlevi yürütülmesi sırasında toplanan örnek toplam sayısı.

Bu işlev kodu doğrudan yürütülmesi sırasında toplanan örnekleri ve hedef işlev tarafından çağrılan alt işlevleri yürütülmesi sırasında toplanan örnekleri içerir.

## <a name="exclusive-samples"></a>Özel örnekleri

Hedef işlevi yönergeleri doğrudan yürütülmesi sırasında toplanan örnek sayısı.

Özel örnekleri hedef işlev tarafından çağrılan işlevleri yürütülmesi sırasında toplanan örnekleri dahil etmeyin.

## <a name="inclusive-percent"></a>Kapsayıcı yüzde

Toplam işlevi veya veri aralığının her ikisi de dahil örnekleri olan profil çalıştırın (bunlar dahil) örnek sayısını yüzdesi.

## <a name="exclusive-percent"></a>Özel yüzde

Toplam işlevi veya veri aralığı özel örnekleri olan çalıştırmak Profil özel örnek sayısını yüzdesi.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Koleksiyon yöntemleri seçme](../profiling/how-to-choose-collection-methods.md)  
[Araçları verilerini performansını analiz etme](../profiling/analyzing-performance-tools-data.md)