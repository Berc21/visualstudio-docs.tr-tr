---
title: "Nasıl yapılır: performans veri dosyası adlandırma seçeneklerini ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7a8d6b9-ab23-46fb-98ed-774781157860
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 07aecd8c21c97fd84ea7c286abade06b3e9de84e
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="how-to-set-performance-data-file-name-options"></a>Nasıl yapılır: performans veri dosyası adlandırma seçeneklerini ayarlama

Varsayılan olarak, aşağıdaki sözdizimini kullanarak bir profil oluşturma verileri (.vsp) dosyasını kaydedin:

*Path\VSP-File\YYMMDD(N)* **.vsp**

Herhangi bir adlandırma parametre Özellikleri iletişim kutusu, genel sayfasında performans oturumu için değiştirebilirsiniz.

|||
|-|-|
|*Yol*|Raporda dizin. Varsayılan konum çözüm klasör ya da kullanıcının projeler ve çözümler için varsayılan konum değil.|
|*VSP-File*|Profil oluşturma veri dosyası adı. Çözüm adı varsayılan addır veya yürütülebilir, profili.|
|*YYAAGG*|Yıl, ay ve profil oluşturma verileri toplanan gün gösterir ve tarih damgası.|
|*(N)*|Birden fazla profil oluşturma veri dosyası zaten varsa, ayraçlar arasında dosya adı artan bir sayı eklenir.|

## <a name="to-change-the-naming-syntax-of-the-profiling-data-files-of-a-performance-session"></a>Profil oluşturma veri dosyaları bir performans oturumu adlandırma sözdizimi değiştirmek için

1. İçinde **performans Gezgini**, performans oturumunu adına sağ tıklayın ve ardından **özellikleri**.

2. Tıklatın **genel**.

3. Altında **rapor**, aşağıdaki ayarlardan birini değiştirin:

    |||
    |-|-|
    |**Rapor konumu**|Profil oluşturma veri dosyaları depolamak için bir dizin belirtin.|
    |**Rapor adı**|Dosyalar için bir veritabanı adı belirtin.|
    |**Yeni raporlar oturuma otomatik olarak Ekle**|Otomatik olarak veri dosyası performans oturumuna eklemek için bu onay kutusunu seçin.|
    |**Bir artacak numarası oluşturulan raporlar ekleme**|Aynı ada sahip birden fazla dosya varsa, dosya adına bir artacak numarası eklemek için bu onay kutusunu seçin. Varolan dosyanın üzerine yazmak için bu onay kutusunu temizleyin.|
    |**Bir zaman damgası numarasını kullanın**|Dosya adına bir tarih damgası eklemek için bu onay kutusunu seçin.|