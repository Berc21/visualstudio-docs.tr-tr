---
title: "Liste ayrıştırılmış komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- debug.listdisassembly
helpviewer_keywords:
- Debug.ListDisassembly command
- list disassembly command
ms.assetid: eb363e35-e86a-4121-966f-991210c27e2a
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c6a704ac783f4efc300de26c2a5e987f82fc2e9c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="list-disassembly-command"></a>Ayrıştırılmış Kodu Listele Komutu
Hata ayıklama işlemi başlar ve hataların nasıl işleneceğini belirtmenizi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListDisassembly [/count:number] [/endaddress:expression]  
[/codebytes:yes|no] [/source:yes|no] [/symbolnames:yes|no]  
[/linenumbers:yes|no]  
```  
  
## <a name="switches"></a>Anahtarlar  
 Her anahtar, formun tamamını veya bir kısa süreli kullanılarak çağrılabilir.  
  
 / count: `number` [veya] / c: `number` [veya] /length: `number` [veya] / l:`number`  
 İsteğe bağlı. Görüntülenecek yönergeleri sayısı. Varsayılan değer 8'dir.  
  
 /endaddress: `expression` [veya] / e:`expression`  
 İsteğe bağlı. Ayrıştırılmış durdurmak hangi adresi.  
  
 /codebytes:`yes`&#124;`no` [veya] /bytes:`yes`&#124;`no` [veya] / b:`yes`&#124;`no`  
 İsteğe bağlı. Kod bayt sayısının görüntülenip görüntülenmeyeceğini belirtir. Varsayılan değer `no`.  
  
 / source:`yes`&#124;`no` [veya] / s:`yes`&#124;`no`  
 İsteğe bağlı. Kaynak kodu görüntülenip görüntülenmeyeceğini gösterir. Varsayılan değer `no`.  
  
 /symbolnames:`yes`&#124;`no` [veya] /names:`yes`&#124;`no` [veya] / n:`yes`&#124;`no`  
 İsteğe bağlı. Simgeler adları görüntülenip görüntülenmeyeceğini gösterir. Varsayılan değer `yes`.  
  
 [/ lınenumbers:`yes`&#124;`no`]  
 İsteğe bağlı. Kaynak koduyla ilişkili satır numaralarını görüntülemesini sağlar. / Source anahtar değeri olmalıdır `yes` /linenumbers anahtarı kullanacak.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.ListDisassembly  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağrı yığınını Listele komutu](../../ide/reference/list-call-stack-command.md)   
 [İş parçacıklarını Listele komutu](../../ide/reference/list-threads-command.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)