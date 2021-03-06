---
title: "İşareti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d72cef3-bb09-4bbb-8864-6ea0ab623ff9
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8fb616cd9b938bb2624d762272f98ae2ad1f7fe9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="mark"></a>İşaret
VSPerfCmd.exe **işareti** seçeneği belirtilen bilgileri profil oluşturma veri dosyasına ekler. Profil Oluşturucu UI işareti rapor görünümü veya ayrı bir VSPerfReport raporlarında işareti listelenebilir. **İşareti** başlangıç ve bitiş noktalarını rapor ve Görünüm filtreleri belirtmek için kullanılır.  
  
 **İşareti** seçeneği, komut satırında belirtilen tek seçenek olmalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Mark:MarkID,[MarkName]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `MarkID`  
 Profil Oluşturucu görünümleri ve raporlarda işareti kimliği olarak listelenen bir kullanıcı tanımlı bir tamsayı. `MarkID`benzersiz olması gerekmez.  
  
 `MarkName`  
 (İsteğe bağlı) Profil Oluşturucu görünümler ve raporlar işareti adı olarak listelenen bir kullanıcı tarafından tanımlanan bir dize. Varsa `MarkName` belirtilmezse, işareti dökümün işareti adı alanı boş olur. Boşluk içeremez veya eğik tırnak işaretleri ("/") iletmek dizeleri alın.  
  
## <a name="example"></a>Örnek  
 Bu örnek 123 Kimliğine ve "TestMark" işareti adını işaretiyle ekler.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
VSPerfCmd.exe /Mark:123,TestMark  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)