---
title: "Satırlar görünümü - .NET bellek örnekleme verileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Lines view
ms.assetid: 6631ab87-0e62-4c76-a063-4ea7222b07da
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: a10c38ec29e9a149d6756bcbe5bbfa1e65fcbe24
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="lines-view---net-memory-sampling-data"></a>Satırlar görünümü - .NET bellek örnekleme verileri
Satırlar görünümü örnekleme yöntemini kullanan .NET bellek ayırma profil oluşturma verileri için profil oluşturma çalışması sırasında bellek tahsis deyimleri listeler. Sütunları ayırmaları sayısı ve boyutu da içerir.  
  
 Bir kaynak dosyasında bir deyim bir kaynak dosyasında birden fazla satırı kapsayabilir ve tek bir satıra birden fazla deyim içerebilir.  
  
 Bir deyim aşağıdaki tarafından tanımlanır:  
  
-   Function deyimi içeren kaynak dosyası.  
  
-   Deyimi içeren işlev.  
  
-   Deyim başlatan kaynak satırı.  
  
-   Deyim başlatan kaynak satırdaki karakter.  
  
-   Deyim erdiği kaynak satırı.  
  
-   Deyim erdiği kaynak satırdaki karakter.  
  
 Satır ad sütunu tanımlayıcısı verileri sıralanabilir bir birleşimini sağlar.  
  
 Tanımı gereği, diğer işlevleri bir deyim çağırmaz. Bu nedenle, yalnızca özel değerler listelenmektedir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**İşlem kimliği**|İşlemi çalıştırmak profil oluşturma kimliği (PID).|  
|**İşlem adı**|İşlemin adı.|  
|**Modül adı**|Deyim içeren modülü adı.|  
|**Modül yolu**|Deyim içeren modülü yolu.|  
|**Kaynak dosya**|Deyimi içeren kaynak dosya.|  
|**İşlev adı**|Deyimi içeren işlevin adı.|  
|**İşlev satır numarası**|Bu işlev kaynak dosyadaki başlangıç satır sayısı.|  
|**İşlev adresi**|İşlev başlangıç adresi.|  
|**Kaynak satırı başlangıç**|Ayırma gerçekleştiği kaynak dosyasında başlangıç satır numarası.|  
|**Kaynak satır sonu**|Ayırma gerçekleştiği kaynak dosyasında bitiş satır numarası.|  
|**Kaynak karakter başlangıç**|Ayırma gerçekleştiği kaynak dosyası satırı başlangıç karakteri uzaklığı.|  
|**Kaynak karakter ucu**|Ayırma gerçekleştiği kaynak dosya satırında bir bitiş karakteri uzaklığı.|  
|**Satırı adı**|Aşağıdaki söz dizimini içeren satırı profil oluşturucu ürettiği tanıtıcısı:`Source File`**; [**  `Line Number Start` **,**`Character Start`**] ->; [** `Line Number Start,Character Start`**]**|  
|**Özel ayırmaları**|Bu satırda oluşturulan nesneleri toplam sayısı.|  
|**Özel ayırmaları %**|Bu satırda ayrılan çalıştırmak profil oluşturulan tüm nesneler yüzdesi.|  
|**Özel bayt sayısı**|Bu satırda ayrılan tüm profil çalıştırmak ayrılan belleği bayt yüzdesi.|  
|**Özel bayt %**|Bu satırda ayrılan tüm profil çalıştırmak ayrılan belleği bayt yüzdesi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satırlar Görünümü](../profiling/lines-view-sampling-data.md)