---
title: "Özel durumdan sonra yürütmeye devam etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- managed exceptions, continuing execution after
- exceptions, continuing execution after
- debugger, exceptions
- managed code, exception handling
- exception handling, continuing execution after
- execution, continuing after an exception
- program execution
- threading [Visual Studio], continuing execution after exceptions
- Exceptions dialog box
- programs, executing
ms.assetid: 6fe97aac-2131-4615-bd92-d3afee741558
caps.latest.revision: "25"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 84ade967c00e33390402e16a1b2980277f89ed5a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="continuing-execution-after-an-exception"></a>Özel Durumdan Sonra Yürütmeye Devam Etme
Hata ayıklayıcı bir özel durum nedeniyle yürütme böldüğünde göreceğiniz **özel durum Yardımcısı**, varsayılan olarak. Devre dışı bıraktıysanız **özel durum Yardımcısı** içinde **seçenekleri** iletişim kutusu görürsünüz: **özel durum Yardımcısı** (C# veya Visual Basic) veya **özel durumu**  iletişim kutusu (C++).  
  
 Zaman **özel durum Yardımcısı** görüntülenirse, özel duruma neden olan sorunu gidermek deneyebilirsiniz.
  
## <a name="managed-and-native-code"></a>Yönetilen ve yerel kodu  
 Yönetilen ve yerel kodu yürütme iş parçacığı içinde işlenmeyen bir özel durumdan sonra devam edebilirsiniz. **Özel durum Yardımcısı** yeri özel durum noktasına çağrı yığını unwinds.
  
## <a name="mixed-code"></a>Karışık kod  
 Karışık yerel ve yönetilen kodda hata ayıklama sırasında işlenmeyen bir özel durum isabet ise, işletim sistemi kısıtlamaları çağrı yığını geriye doğru izleme engeller. Hata ayıklayıcı işlenmeyen bir bırakma olamaz kısayol menüsünü kullanarak çağrı yığını geri sarma çalışırsanız, bir hata iletisi açıklanmaktadır dışındaki karma kodda hata ayıklama sırasında.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durumları hata ayıklayıcısı ile yönetme](../debugger/managing-exceptions-with-the-debugger.md)