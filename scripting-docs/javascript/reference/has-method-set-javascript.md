---
title: "has yöntemi (küme) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: fb80f2e0-fc5e-4508-af14-1c3b3b833636
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9690e3d091e8ae0f9670fd737a29590524834c9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="has-method-set-javascript"></a>has Yöntemi (Küme) (JavaScript)
Döndürür `true` kümesi belirtilen öğeyi içeriyorsa.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
setObj.has(value)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `setObj`  
 Gerekli. A `Set` nesnesi.  
  
 `value`  
 Gerekli. Test edilecek öğe.  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 `true`belirlenen belirtilen öğeyi içeriyorsa.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, üye eklemek gösterilmiştir bir `Set` ve kümesi belirli bir üyeye sahip olup olmadığını denetleyin.  
  
```JavaScript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
  
document.write(s.has(1776));  
document.write(s.has("1776"));  
  
// Output:  
// true  
// false  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]