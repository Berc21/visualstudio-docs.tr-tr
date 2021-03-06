---
title: "ScriptEngine işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ScriptEngine
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ScriptEngine function
ms.assetid: 65674b2b-d2c2-4493-99b3-f0d20fda8249
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d441fcce065677f7b673a9979acff9cf9aa2ce90
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="scriptengine-function-javascript"></a>ScriptEngine İşlevi (JavaScript)
Komut dosyası dili adını kullanımda alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ScriptEngine()  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `ScriptEngine` İşlevi döndürür belirten "JScript" [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] geçerli komut dosyası motoru.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `ScriptEngine` işlevi:  
  
```JavaScript  
if (window.ScriptEngine) {  
    console.log(window.ScriptEngine());  
}  
  
// Output: JScript  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ScriptEngineBuildVersion işlevi](../../javascript/reference/scriptenginebuildversion-function-javascript.md)   
 [ScriptEngineMajorVersion işlevi](../../javascript/reference/scriptenginemajorversion-function-javascript.md)   
 [ScriptEngineMinorVersion işlevi](../../javascript/reference/scriptengineminorversion-function-javascript.md)