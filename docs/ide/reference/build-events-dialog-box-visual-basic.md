---
title: "Derleme olayları iletişim kutusu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- build events, specifying
- pre-build events
- Build Events dialog box
- post-build events
ms.assetid: 3a81a7c7-39f9-47a8-ba5a-b351227f380e
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: da28d0858784a8e71006c0ec072c3aea5110037e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="build-events-dialog-box-visual-basic"></a>Derleme Olayları İletişim Kutusu (Visual Basic)
Kullanım **yapı olayları** yapı yapılandırma yönergeleri belirtmek için iletişim kutusu. Ayrıca, tüm ön derleme veya derleme sonrası olayları çalıştığı koşulları belirtebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: belirtin Build Events (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).  
  
 **Derleme öncesi olay komut satırı**  
 Yapı başlamadan önce yürütülecek herhangi bir komut belirtir. Uzun komutları yazmak için tıklatın **düzen oluşturma öncesi** görüntülemek için [oluşturma öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).  
  
> [!NOTE]
>  Oluşturma öncesi olaylar proje güncel olduğundan ve hiçbir derleme tetiklenir çalıştırmayın.  
  
 **Derleme sonrası olay komut satırı**  
 Derleme sona erdikten sonra yürütmek için herhangi bir komut belirtir. Uzun komutları yazmak için tıklatın **düzen oluşturma sonrası** görüntülemek için **oluşturma öncesi olay/derleme sonrası olay komut satırı d**ialog kutusu.  
  
> [!NOTE]
>  Ekleme bir `call` .bat dosyaları çalıştıran tüm sonrası derleme komutları önce deyim. Örneğin, `call C:\MyFile.bat` veya `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Oluşturma sonrası olay çalıştırın**  
 Aşağıdaki tabloda gösterildiği gibi çalıştırmak, oluşturma sonrası olay koşulları belirtir.  
  
|Seçenek|Sonuç|  
|------------|------------|  
|**Her zaman**|Oluşturma sonrası olay oluşturma işlemi başarılı olup olmadığını bağımsız olarak çalışır.|  
|**Üzerinde başarılı derleme**|Oluşturma işlemi başarılı olursa oluşturma sonrası olay çalıştırın. Olay oluşturma işlemi başarılı olduğu sürece, güncel bile bir proje için çalışır. Varsayılan ayar budur.|  
|**Yapı proje çıktı zaman güncelleştirir**|Yalnızca önceki derleyici çıktı dosyasından derleyicinin çıktı dosyası (.exe veya .dll) farklı olduğu durumlarda oluşturma sonrası olay çalıştırın. Bir proje güncel ise oluşturma sonrası olay çalıştırılmaz.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derle sayfası, Proje Tasarımcısı (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Nasıl yapılır: derleme olayları belirtme (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Derleme öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)