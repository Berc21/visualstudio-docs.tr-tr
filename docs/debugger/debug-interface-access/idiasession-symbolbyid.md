---
title: "Idiasession::symbolbyıd | Microsoft Docs"
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
- IDiaSession::symbolById method
ms.assetid: 062e4b5a-9c4d-4703-88da-ec13102c2b66
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c6792f3271f09742d40b92691dee06854deea8f2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasessionsymbolbyid"></a>IDiaSession::symbolById
Bir simge benzersiz tanımlayıcısıyla alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT symbolById (   
   DWORD        id,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Benzersiz tanımlayıcı.  
  
 `ppSymbol`  
 [out] Döndürür bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) simgenin temsil eden nesnesi alınamadı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen tanımlayıcı tüm sembolleri benzersiz hale getirmek amacıyla DIA SDK'sı tarafından dahili olarak kullanılan benzersiz bir değerdir.  
  
 Bu yöntem, örneğin, başka bir simge türünü temsil eden simgeyi almak için kullanılabilir (örneğe bakın).  
  
## <a name="example"></a>Örnek  
 Bu örnek alır bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) temsil eden başka bir simge türü. Bu örnek nasıl kullanılacağını gösterir `symbolById` oturumunda yöntemi. Basit bir yaklaşım çağırmaktır [Idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md) tür simgesi doğrudan alma yöntemi.  
  
```C++  
IDiaSymbol *GetSymbolType(IDiaSymbol *pSymbol, IDiaSession *pSession)  
{  
    IDiaSymbol *pTypeSymbol = NULL;  
    if (pSymbol != NULL && pSession != NULL)  
    {  
        DWORD symbolTypeId;  
        pSymbol->get_typeId(&symbolTypeId);  
        pSession->symbolById(symbolTypeId, &pTypeSymbol);  
    }  
    return(pTypeSymbol);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)