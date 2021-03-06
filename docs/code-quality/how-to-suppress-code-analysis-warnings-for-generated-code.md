---
title: "Nasıl yapılır: üretilen kod için Kod Analizi uyarılarını bastırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bd917c8c9a3b66dc1fe34e089e14481c2b7df5a5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>Nasıl yapılır: Üretilen Kod İçin Kod Çözümleme Uyarılarını Bastırma
Yönetilen kod derleyicileri genellikle bir projeye hızlı kod geliştirme kolaylaştırmak için eklenen kod oluşturur. Ayrıca, geliştiriciler genellikle üçüncü taraf araçları uygulamaları çabucak geliştirmelerine yardımcı olması için kullanın. Bu araçları ayrıca projeye eklenen kodu oluşturur.  
  
 Kod çözümleme oluşturulan kodda bulur kural ihlallerinin görmek isteyebilirsiniz. Ancak, görüntülemek ve ihlalin içeren kodunu korumak görebileceği istemeyebilirsiniz.  
  
 **Bastırmak oluşturulan kod sonuçlarından** projenin Kod Analizi özellik sayfasında onay kutusunu üçüncü taraf aracı tarafından oluşturulan kodundan Kod Analizi uyarıları görmek istediğinizi seçin olanak sağlar.  
  
> [!NOTE]
>  Hataları ve Uyarıları formlar ve şablonlar görüntülendiğinde bu seçenek Kod Analizi hataları ve Uyarıları oluşturulan kodundan engelleme. Hem görüntülemek ve bir form veya şablon için kaynak kodunu sağlayabilirsiniz.  
  
### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>Projede üretilen kod için uyarıları gizlemek için  
  
1.  Çözüm Gezgini'nde projeye sağ tıklayın ve ardından **özellikleri**.  
  
2.  Tıklatın **kod çözümleme**.  
  
3.  Seçin **bastırmak oluşturulan kod sonuçlarından** onay kutusu.