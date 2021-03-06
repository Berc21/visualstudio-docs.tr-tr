---
title: "Nasıl yapılır: Visual Studio'da bir ASP.NET Web uygulaması için kod analizini yapılandırma | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.asp
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- aspnet
ms.openlocfilehash: 075382db550fae1198b0eca239be8efd1bfadff6
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="how-to-configure-code-analysis-for-an-aspnet-web-application"></a>Nasıl yapılır: Bir ASP.NET Web Uygulaması İçin Kod Çözümlemesini Yapılandırma

Visual Studio'da Kod Analizi listesinden seçebilirsiniz *kural kümeleri* uygulamak için [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması. Varsayılan kural Microsoft Minimum önerilen kurallar kümesidir. Başka bir kural Web sitesine uygulamak için kümesini seçebilirsiniz.

1. Web sitesini seçin **Çözüm Gezgini**.

2. Üzerinde **Çözümle** menüsünde tıklatın **Web sitesi için Kod Analizi yapılandırma**.

3. Çözüm seçili birden çok proje çözümü vardır, derleme, yapılandırma ve hedef işletim sisteminden seçin ve **yapılandırma** ve **Platform** listeler.

4. Çözümdeki her projeye için tıklayarak **kural kümesi** sütun ve kuralın adını ayarlayın çalıştırmak için tıklatın.

5. Varsayılan olarak, Çözümdeki tüm projeleri üzerinde kod analizi çalıştırılır. Devre dışı bırakmak veya belirli bir projede için Kod Analizi etkinleştirmek için şu adımları izleyin:

    1. Proje adına sağ tıklayın ve ardından Özellikler'i tıklatın.

    2. Denetleyin veya temizleyin **etkinleştirmek Kod Analizi** onay kutusu. Ayrıca Kod Analizi el ile seçerek çalıştırabilirsiniz **çalıştırmak Kod Analizi Web sitesinde** gelen **Çözümle** menüsü.

6. İçinde **bu kural kümesini çalıştırmak** aşağı açılan listesinde, aşağıdaki adımları izleyin:

    - Kullanmak istediğiniz kural kümesini seçin.

    - Seçin  **\<Gözat >** var olan bir özel kural kümesini belirlemek için listede değil.

    - Tanımlayan bir [özel kural kümesi](../code-quality/how-to-create-a-custom-rule-set.md).