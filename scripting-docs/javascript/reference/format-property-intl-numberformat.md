---
title: "format özelliği (INTL.numberformat) | Microsoft Docs"
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
ms.assetid: 68c3223a-023c-4fa0-aa99-d049a7a0e26a
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be40f8e94220ad7504dd3b9736e71b3416bb3d2a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="format-property-intlnumberformat"></a>format Özelliği (Intl.NumberFormat)
Belirtilen sayı biçimlendirici ayarları kullanarak bir yerel ayarlara özgü sayıyı biçimlendirir bir işlev döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
numberFormatObj.format  
```  
  
#### <a name="parameters"></a>Parametreler  
 `numberFormatObj`  
 Gerekli. Adını `NumberFormat` bir biçimlendirici kullanılacak nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından döndürülen işlevi `format` özelliği alır tek bir bağımsız değişken `value`ve belirtilen seçenekleri kullanarak yerelleştirilmiş sayıyı temsil eden bir dize döndürür `NumberFormat` nesnesi. Varsa `value` işlevi döndürür sağlanmamışsa `NaN` (sayı değil).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanan bir `NumberFormat` yerelleştirilmiş birkaç oluşturulacak nesne.  
  
```JavaScript  
var nf = new Intl.NumberFormat(["en-US"], {  
    style: "currency",  
    currency: "CNY",  
    currencyDisplay: "symbol",  
    maximumFractionDigit: 1  
})  
  
if (console && console.log) {  
    console.log(nf.format(100)); // "¥100.00"  
}  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [INTL.numberformat nesnesi](../../javascript/reference/intl-numberformat-object-javascript.md)