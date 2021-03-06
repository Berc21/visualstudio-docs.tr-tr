---
title: "Çıktı penceresi tanılama iletileri gönderme | Microsoft Docs"
ms.custom: 
ms.date: 04/25/2017
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
helpviewer_keywords:
- diagnostic messages [C#]
- System.Diagnostics.Debug class, Output window
- messages, diagnostic
- Debug.Print replacements
- diagnosis
- Output window, diagnostic messages
- System.Diagnostics.Trace class, Output window
- Trace class, diagnostic messages
- diagnostics
- debugger, Output window
- debugging [Visual Studio], diagnostic messages in Output window
- Debug class
ms.assetid: 386e9524-be17-4573-83fb-4f7c5cae0be0
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: df071834a6ae36da0156c527284f6ffbfcee0e4e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="send-diagnostic-messages-to-the-output-window"></a>Çıktı penceresi tanılama iletileri gönder
Çalışma zamanı iletileri yazma **çıkış** penceresini kullanarak `Debug` sınıfı veya `Trace` parçasıdır sınıfı, <xref:System.Diagnostics> sınıf kitaplığı. Hata ayıklama sınıfı programınızın hata ayıklama sürümü yalnızca çıktı kullanın. Hata ayıklama ve yayın sürümleri çıktısında istiyorsanız, izleme sınıfı kullanın.  
  
## <a name="output-methods"></a>Çıktı yöntemleri  
 <xref:System.Diagnostics.Trace> Ve <xref:System.Diagnostics.Debug> sınıfları aşağıdaki çıktı yöntemlerini sağlar:  
  
-   Çeşitli `Write` yürütme bozmadan bilgileri çıkış yöntemleri. Bu yöntem Değiştir `Debug.Print` Visual Basic önceki sürümlerinde kullanılan yöntem.  
  
-   <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>ve <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> belirtilen bir koşul başarısız olursa, yürütme ve çıkışları bilgileri bölün yöntemleri. Varsayılan olarak, `Assert` yöntemi, bir iletişim kutusu bilgileri görüntüler. Daha fazla bilgi için bkz: [yönetilen koddaki onaylar](../debugger/assertions-in-managed-code.md).  
  
-   <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> Ve <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName> her zaman yürütme keser ve bilgi çıkaran yöntemleri. Varsayılan olarak, `Fail` yöntemleri bir iletişim kutusu bilgileri görüntüler.  
  
 Ek olarak, uygulamanızın programdan **çıkış** penceresi hakkında bilgileri görüntüleyebilirsiniz:  
  
-   Modülleri hata ayıklayıcı yüklenen veya yüklenmemiş.  
  
-   Oluşturulan özel durumlar.  
  
-   Çıkış işlemleri.  
  
-   Exit iş parçacıkları.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Çıktı penceresi](../ide/reference/output-window.md)   
 [İzleme ve İşaretleme Uygulamaları](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)  
 [C#, F # ve Visual Basic proje türleri](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)