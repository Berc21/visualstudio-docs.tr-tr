---
title: "Toplama atama işleci (+=) (JavaScript) | Microsoft Docs"
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
- +=
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- addition assignment operator (+=)
- += operator
- assignment operators, JavaScript
ms.assetid: 8517d05c-38b0-4107-bea4-253eb420f438
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 38d86c537dda90dd7f44923b97384b3609dad5ba
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="addition-assignment-operator--javascript"></a>Toplama Atama İşleci (+=) (JavaScript)
Bir ifadenin değerini bir değişkenin değerine ekler ve sonucu değişkenine atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result += expression   
```  
  
## <a name="parameters"></a>Parametreler  
 `result`  
 Herhangi bir değişken.  
  
 `expression`  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlecini kullanarak tam olarak aynı olup belirtme: `result = result + expression`.  
  
 İki ifade türleri davranışını belirlemek `+=` işleci.  
  
|Eğer|Ardından|  
|--------|----------|  
|Her iki ifade sayısal veya Boolean|Ekle|  
|Her iki ifade dizeler şunlardır:|Birleştirme|  
|Bir ifade sayısal ve diğer bir dizedir|Birleştirme|  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Toplama işleci (+)](../../javascript/reference/addition-operator-decrement-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)