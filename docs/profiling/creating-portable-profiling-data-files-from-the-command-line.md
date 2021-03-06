---
title: "Taşınabilir profil oluşturma veri dosyalarıyla komut satırından oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 95302666d8bd5c5738f93a2fb0a8ec698c5bb7d9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-portable-profiling-data-files-from-the-command-line"></a>Komut Satırından Taşınabilir Profil Oluşturma Veri Dosyaları Oluşturma
Profil oluşturma verilerini daha kolay paylaşımı yapmak için kullanabileceğiniz [VSPerfReport](../profiling/vsperfreport.md) profil .vsp dosyasına çalıştırmak için simgeleri eklemek için komut satırı aracı.  
  
 Daha küçüktür ve IDE içinde yüklemek daha hızlı bir şekilde önceden çözümlenen bir profil oluşturma veri (.vsps) dosyası da oluşturabilirsiniz.  
  
> [!NOTE]
>  Simge (.pdb) dosyaları için kullanılabilir olduğundan emin olun **VSPerfReport**. Daha fazla bilgi için bkz: [nasıl yapılır: simge dosyası konumlarını komut satırından belirtme](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
>   
>  Yolu hakkında bilgi için **VSReport**, bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Profil oluşturma verileri .vsps dosyasında filtrelenemez.  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Bir profil bir profil oluşturma veri (.vsp) dosyasına çalıştırmak için simgeleri eklemek için  
  
-   Bir komut istemi penceresinde, aşağıdaki komutu yazın:  
  
     \<Yolu >**VSPerfReport \<** VSP Dosya > **/PackSymbols**  
  
     Varsayılan olarak, .vsps dosya .vsp dosyasının temel adı ile adlandırılır. Kullanarak bir diğer ad belirtebilirsiniz **çıkış** seçeneği.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>Özet bir profil oluşturma veri dosyası oluşturmak için  
  
-   Bir komut istemi penceresinde, aşağıdaki komutu yazın:  
  
     \<Yolu >**VSPerfReport \<** VSP Dosya > **/SummaryFile** [**/çıktı:**\<dosya adı >]  
  
     Varsayılan olarak, .vsps dosya .vsp dosyasının temel adı ile adlandırılır. Kullanarak bir diğer ad belirtebilirsiniz **çıkış** seçeneği.