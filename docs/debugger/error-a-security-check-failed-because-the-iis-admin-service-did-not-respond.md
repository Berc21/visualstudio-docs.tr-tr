---
title: "Hata: Güvenlik denetimi başarısız IIS Yönetici Hizmeti yanıt vermediğinden | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.iis_not_responding
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 85b96d9e1396933519da71e93bac075ee51af001
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-a-security-check-failed-because-the-iis-admin-service-did-not-respond"></a>Hata: IIS Yönetici Hizmeti Yanıt Vermediğinden Güvenlik Denetimi Başarısız
IIS Yönetici Hizmeti yanıt vermiyor bu hata oluşur. Bu, genellikle IIS yükleme ile ilgili bir sorun olduğunu gösterir. İlk olarak, hizmet kullanarak çalıştığını doğrulayın **Hizmetleri** öğesinden aracı **Yönetimsel Araçlar**.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Kullanarak IIS'yi yeniden **Program Ekle veya Kaldır** Denetim Masası.  
  
-   veya  
  
-   IIS, Program Ekle veya Kaldır Denetim Masası'nı kullanarak makinenizden kaldırın. IIS kaldırdınız ve hala sorunları varsa, kayıt defterini denetleyin ve bu anahtar artık var olduğundan emin olun:  
  
    ```  
    HKEY_CLASSES_ROOT\CLSID\{A9E69610-B80D-11D0-B9B9-00A0C922E750}  
    ```  
  
     veya  
  
-   Yönetimsel Araçlar Denetim Masası'nı kullanarak IIS Yönetim hizmeti devre dışı bırakın. Bu IIS makinenizde devre dışı bırakır.  
  
     Bu üç adımı birini gerçekleştirdikten sonra bilgisayarınızı yeniden başlatın.  
  
     Ek bilgi için IIS belgelerine bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Web uygulamalarında hata ayıklama: Hatalar ve sorun giderme](../debugger/debugging-web-applications-errors-and-troubleshooting.md)