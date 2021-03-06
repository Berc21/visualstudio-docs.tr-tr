---
title: "Yük testleri Visual Studio'da veri ve tanılama eklerini görüntüleme | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, data and diagnostics attachments
ms.assetid: 73309bdd-437a-4eb0-88c8-702c3e24b9b0
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 5d955412195a32a69e069ccac2b40456a9ffb986
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-view-data-and-diagnostic-attachments-using-the-load-test-analyzer"></a>Nasıl yapılır: Yük Testi Çözümleyicisi Kullanarak Verileri ve Tanılama Eklerini Görüntüleme

Bir yük çalıştırılmadan önce test, kullanmak istediğiniz tanılama ve veri bağdaştırıcılarını belirten bir test ayarını seçebilirsiniz. Yük testi tamamlandıktan sonra sonuçlarını analiz ederken bu tanılama ve veri bağdaştırıcıları ayrıntılarını görüntülemek için Yük Testi Çözümleyicisi'ni kullanın. Veri ve tanılama bağdaştırıcısı ayrıntılarını görüntülemek için seçin **görünüm verileri ve tanılama eklerini** Yük Testi Çözümleyicisinin araç çubuğunda. Örneğin, yük testi test ortamında yapılandırılmış bir sistem bilgileri bağdaştırıcısına sahipse, yük testi çalıştırdığınızda, kullanılan makinenin sistem bilgileri görüntüleyebilirsiniz.

![Tanılama veri bağdaştırıcısı ek iletişim seçme](../test/media/load_adapterdialog.png "Load_AdapterDialog")

Test ayarında IntelliTrace bağdaştırıcısı içeren yük testi başka bir örnektir. IntelliTrace bağdaştırıcısı IntelliTrace Özet sayfasını açmanızı sağlar.

![IntelliTrace Özet](../test/media/load_intellitrace.png "Load_IntelliTrace")

Daha fazla bilgi için bkz: [toplamak tanılama bilgileri Test ayarlarını kullanarak](../test/collect-diagnostic-information-using-test-settings.md) ve [toplamak IntelliTrace verilerini](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md).

## <a name="to-view-data-and-diagnostic-attachments-in-a-load-test-from-the-load-test-analyzer"></a>Yük Testi Çözümleyicisi öğesinden bir yük testi verileri ve tanılama eklerini görüntülemek için

1.  Bir yük testi tamamlandıktan sonra veya bir yük testi sonuç Yük Testi Çözümleyicisi'nin araç çubuğunda açtıktan sonra Seç **görünüm verileri ve tanılama eklerini**.

     **Seçin tanılama veri bağdaştırıcısı** iletişim kutusu görüntülenir.

2.  Analiz edin ve ardından istediğiniz tanılama veri bağdaştırıcısı eki seçin **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)