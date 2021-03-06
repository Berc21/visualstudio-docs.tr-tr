---
title: "Visual Studio yükleme testi çalıştırma ayarlarını komut satırından ayarlama | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, command line
- load tests, run settings, selecting
ms.assetid: 175d1d58-f09a-4449-b132-a29a394a7c8e
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: e7a9a7dec6fffdb51cf71ff5a45a2841c616f8c0
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-select-a-load-test-run-setting-to-use-from-the-command-line"></a>Nasıl yapılır: Komut Satırından Kullanmak için Bir Yük Testi Çalışma Ayarı Seçme

Bir yük testi bir veya daha fazla içerebilir *çalışma ayarları*, bir yük testi çalışma biçimini etkileyen özellikler kümesi olduğu. Çalıştırma Ayarları Özellikleri penceresinde kategoriler halinde düzenlenir. Bir yük testi çalıştırdığınızda, şu anda etkin olarak ayarlanmış çalışma ayarı kullanır.

 Yük testi çalışma ayarı yalnızca bir içeriyorsa, her zaman etkin düğüm olur. Yük testi birden çok çalışma ayarları düğümü içeriyorsa, komut satırı ile bir yük testi çalıştırdığınızda kullanmak için birini seçebilirsiniz. Bkz: [nasıl yapılır: bir yük testine ek çalışma ayarları ekleme](../test/how-to-add-additional-run-settings-to-a-load-test.md).

## <a name="to-change-the-run-setting-from-the-command-line"></a>Komut satırından çalıştırma ayarını değiştirmek için

1.  Bağlam parametresi stratejisi yararlanmak için komut satırından farklı çalışma ayarları kullanmak istiyorsanız, aşağıdaki komutu kullanın:

    `Set Test.UseRunSetting= CorporateStagingWebServer`

2.  Mstest'i kullanarak yük testi çalıştırın:

    `mstest /testcontainer:loadtest1.loadtest`

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)
- [Yük testindeki bilgisayarlar için sayaç kümelerini ve eşik kurallarını belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Nasıl yapılır: bir yük testine ek çalışma ayarları ekleme](../test/how-to-add-additional-run-settings-to-a-load-test.md)
- [Nasıl yapılır: yük testi için etkin çalışma ayarını seçin](../test/how-to-select-the-active-run-setting-for-a-load-test.md)