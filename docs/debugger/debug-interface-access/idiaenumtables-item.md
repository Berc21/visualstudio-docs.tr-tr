---
title: Idiaenumtables::Item | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Item method
ms.assetid: d65ab262-10c6-48ce-95a3-b5e4cb2c85af
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: fd0049e15f17d5dff58d35d4279bb0ab0673091e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumtablesitem"></a>IDiaEnumTables::Item
Bir dizin veya ad yoluyla bir tablo alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Item (   
   VARIANT     index,  
   IDiaTable** table  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `index`  
 [in] Adı veya dizin [Idiatable](../../debugger/debug-interface-access/idiatable.md) alınacak. Bir tamsayı değişken kullanılırsa, bu aralıktaki 0 olmalıdır `count`-1, burada `count` tarafından döndürülen gibi [Idiaenumtables::get_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md) yöntemi.  
  
 `table`  
 [out] Döndürür bir [Idiatable](../../debugger/debug-interface-access/idiatable.md) istenen tabloyu temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir dize değişken belirtilmezse, dizenin belirli bir tablo adları. Adı bir tablo adlarının tanımlandığı gibi olmalıdır [Sabitleri (hata ayıklama arabirimi Erişim SDK)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md).  
  
## <a name="example"></a>Örnek  
  
```C++  
VARIANT var;  
var.vt = VT_BSTR;  
var.bstrVal = SysAllocString(DiaTable_Symbols );  
IDiaTable* pTable;  
pEnumTables->Item( var, &pTable );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumtables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [Idiatable](../../debugger/debug-interface-access/idiatable.md)   
 [Idiaenumtables::get_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)   
 [Sabitler (Arabirim Erişimi SDK'sında Hata Ayıklama)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)