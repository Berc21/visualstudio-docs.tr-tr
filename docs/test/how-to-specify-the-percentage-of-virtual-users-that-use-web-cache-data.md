---
title: "Sanal kullanım Web önbellek verilerini Yük için Visual Studio'da Test kullanıcı yüzdesi belirtin | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, virtual users
ms.assetid: f66d5d43-4121-4487-b27f-d0a0baaf7601
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: c1aa64c0ecee9f214d1bd892c62ba79090d2ce15
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-specify-the-percentage-of-virtual-users-that-use-web-cache-data"></a>Nasıl yapılır: Web Önbellek Verilerini Kullanan Sanal Kullanıcıların Yüzdesini Belirtme

Yük testi ile oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, senaryoları özelliklerini kullanarak test gereksinimlerini ve hedeflerinizi karşılayacak şekilde değiştirebilirsiniz **Yük Testi Düzenleyicisi**. Yük testi senaryosu özellikleri ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

**Yeni kullanıcı yüzdesi** özelliği Özellikler penceresinde ayarlanır. Yük Testi Düzenleyicisi'nde yük testi senaryosu özellikleri düzenleyin.

**Yeni kullanıcı yüzdesi** özelliği, bir Web tarayıcısı tarafından gerçekleştirilen yük testi benzetim önbelleğe alma biçimini etkiler. Varsayılan olarak, **yeni kullanıcı yüzdesi** özelliğini % 0'a ayarlayın. Varsa değeri **yeni kullanıcı yüzdesi** özelliğini % 100'e ayarlayın, bir yük testinde çalışan her Web performans testi içeriklerin Web sitesinden kendi previ tarayıcı önbelleğinden olmayan Web sitesi için ilk kullanıcı gibi kabul edilir OU'lar ziyaret eder. Bu nedenle, Web testinde görüntüleri gibi tüm bağımlı istekleri dahil olmak üzere tüm istekler indirilir.

> [!NOTE]
> Aynı alınabilir kaynak birden çok kez web testinde istendiğinde, istekler indirilmez.

Çok sayıda görüntülerine sahip büyük bir olasılıkla dönüş kullanıcılar bir Web sitesi test yük varsa ve bu diğer alınabilir yerel olarak ardından bir ayar için % 100 oranında önbelleğe alınmış içeriği **yeni kullanıcı yüzdesi** özelliği daha üretir Gerçek kullanımını oluşacak fazla indirme istek. Bu durumda, kullanıcılar ilk kez web sitesinin ve ayarlama ziyaretleriniz Web sitenize yüzdesini tahmin **yeni kullanıcı yüzdesi** özelliği uygun şekilde.

## <a name="to-specify-the-agents-to-use-for-a-scenario"></a>Bir senaryo için kullanılacak aracıları belirtmek için

1.  Bir yük testi açın.

     **Yük Testi Düzenleyicisi** görüntülenir. Yük testi ağacı görüntülenir.

2.  Ağaçları yük testi **senaryoları** klasörü için kullanılacak aracıları belirtmek istediğiniz senaryo düğümünü seçin.

3.  Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Senaryonun kategoriler ve Özellikler Özellikler penceresinde görüntülenir.

4.  Değeri ayarlanamıyor **yeni kullanıcı yüzdesi** yeni kullanıcı yüzdesi için bir sayı girerek özelliği.

5.  Özelliği değiştirmeyi bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından yeni kullanarak yük testlerini çalıştırabilirsiniz **yeni kullanıcı yüzdesi** değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [İzlenecek yol: Oluşturma ve bir yük testi çalıştırma](../test/walkthrough-create-and-run-a-load-test.md)
- [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)
- [Sanal kullanıcı etkinlikleri modellemek için yük desenlerini düzenleme](../test/edit-load-patterns-to-model-virtual-user-activities.md)