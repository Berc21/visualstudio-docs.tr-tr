---
title: "Karışık mod hata ayıklaması yalnızca desteklenen Microsoft .NET Framework 2.0 veya 3.0 kullanırken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.error.interop_unsupported_to_old
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: f607af6f-57fe-472a-a32e-b6202067aa96
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: c521592ed6ede141727d2ac9b40c7c350d72053b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="mixed-mode-debugging-is-only-supported-when-using-microsoft-net-framework-20-or-30"></a>Karışık Modda Hata Ayıklama Yalnızca Microsoft .NET Framework 2.0 veya 3.0 Sürümü Kullanılırken Desteklenir
Daha önce Microsoft .NET Framework sürümleri 2.0, destek 64 bit işlemleri karışık modda hata ayıklama için sağlamaz. Bu hata ayıklarken, yerel koda yönetilen koddan ya da yerel koddan yönetilen koda adım edilemez olduğunu anlamına gelir.  
  
 Bu sorunu gidermek için şunları yapabilirsiniz:  
  
-   Microsoft .NET Framework 2.0 veya 3.0 kullanmak için projenizin güncelleştirin.  
  
-   Yönetilen ve yerel kod hata ayıklama ayrı hata ayıklama oturumu.  
  
-   Aşağıdaki yordamlarda açıklandığı gibi karma kodunuzu bir 32 bitlik işlem olarak hata ayıklama.  
  
### <a name="to-change-the-operating-system-to-32-bit-visual-basic-or-c"></a>İşletim sisteminin 32-bit (Visual Basic veya C#) değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından **özellikleri** kısayol menüsünde.  
  
2.  Özellik sayfaları tıklatın **derleme** veya **hata ayıklama** sekmesi.  
  
3.  Tıklatın **Platform**ve ardından **x86** platformları listesinden.  
  
     Varsayılan olarak, Visual Basic ve C# Derleyicileri herhangi bir CPU'da çalıştırmak için kod oluşturur. Bir 64-bit bilgisayarda 64 bit işlemleri olarak bu ikili dosyaları çalıştırın. Bir 32 bitlik işlem olarak çalıştırmak için seçmelisiniz **Win32**değil **AnyCPU**.  
  
### <a name="to-change-the-operating-system-to-32-bit-cc"></a>İşletim sisteminin 32-bit (C/C++) değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından **özellikleri** kısayol menüsünde.  
  
     Özellik sayfaları tıklatın **Platform**ve ardından **Win32** platformları listesinden.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Bkz: [SQL hata ayıklama Kurulumu ayarı](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [64 Bit uygulamalarda hata ayıklama](../debugger/debug-64-bit-applications.md)