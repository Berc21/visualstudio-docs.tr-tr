---
title: Idiasymbol::get_thunkordinal | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_thunkOrdinal method
ms.assetid: 4b28d78a-1974-4d8a-8bb7-781bf630f2f4
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d9eb23f90ea960f927ab8561ff215968134bc30e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetthunkordinal"></a>IDiaSymbol::get_thunkOrdinal
Bir işlevin dönüştürücü türü alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_thunkOrdinal (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Arasında bir değer döndürür [THUNK_ORDINAL numaralandırması](../../debugger/debug-interface-access/thunk-ordinal.md) bir işlev dönüştürücü türünü belirtir numaralandırması.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliğin simge için kullanılabilir olup olmadığı anlamına gelir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellik geçerli yalnızca simgesi olarak bir [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerini `SymTagThunk`.  
  
 "Dönüştürücü" (bölümlenmiş adres alanı olarak da bilinir) bir 16 bit adres alanı ile bir 32 bit bellek adres alanı (düz adres alanı olarak da bilinir) arasındaki dönüştürür kod parçasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Thunk_ordınal numaralandırması](../../debugger/debug-interface-access/thunk-ordinal.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)