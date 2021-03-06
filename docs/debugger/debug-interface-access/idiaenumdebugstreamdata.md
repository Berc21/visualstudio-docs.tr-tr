---
title: Idiaenumdebugstreamdata | Microsoft Docs
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
- IDiaEnumDebugStreamData interface
ms.assetid: e2023c32-4c05-4d0c-a0be-f016a230c788
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 31e7f3415a502d2bf7737a498f235fd38a75ec48
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumdebugstreamdata"></a>IDiaEnumDebugStreamData
Hata ayıklama veri akışı kayıtları erişim sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaEnumDebugStreamData : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaEnumDebugStreamData`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDiaEnumDebugStreamData::get__NewEnum](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-newenum.md)|Alır [IEnumVARIANT arabirimi](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) bu Sıralayıcı sürümü.|  
|[IDiaEnumDebugStreamData::get_Count](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md)|Hata ayıklama veri akışında kayıt sayısını alır.|  
|[IDiaEnumDebugStreamData::get_name](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-name.md)|Hata ayıklama veri akışı adını alır.|  
|[IDiaEnumDebugStreamData::Item](../../debugger/debug-interface-access/idiaenumdebugstreamdata-item.md)|Belirtilen kayıt alır.|  
|[IDiaEnumDebugStreamData::Next](../../debugger/debug-interface-access/idiaenumdebugstreamdata-next.md)|Belirtilen kayıt sayısı numaralandırılmış dizisinden alır.|  
|[IDiaEnumDebugStreamData::Skip](../../debugger/debug-interface-access/idiaenumdebugstreamdata-skip.md)|Numaralandırılmış dizisi kayıtlarında belirtilen sayıda atlar.|  
|[IDiaEnumDebugStreamData::Reset](../../debugger/debug-interface-access/idiaenumdebugstreamdata-reset.md)|Numaralandırılmış dizisi başına sıfırlar.|  
|[IDiaEnumDebugStreamData::Clone](../../debugger/debug-interface-access/idiaenumdebugstreamdata-clone.md)|Geçerli Numaralandırıcı aynı numaralandırılmış sırada içeren bir numaralandırıcı oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirimi hata ayıklama veri akışı kayıtlarının bir akış temsil eder. Boyut ve her kayıt yorumu kaydı geldiği veri akışı bağımlı. Bu arabirim etkili bir şekilde ham verileri bayt sembol dosyası olarak erişim sağlar.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [Idiaenumdebugstreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md) veya [Idiaenumdebugstreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md) almak için yöntemleri bir `IDiaEnumDebugStreamData` nesnesi.  
  
## <a name="example"></a>Örnek  
 Bu örnek bir tek veri akışı ve kayıtlarını nasıl erişileceği gösterir.  
  
```C++  
void PrintStreamData(IDiaEnumDebugStreamData* pStream)  
{  
    BSTR  wszName;  
    LONG  dwElem;  
    ULONG celt    = 0;  
    DWORD cbData;  
    DWORD cbTotal = 0;  
    BYTE  data[1024];  
  
    if(pStream->get_name(&wszName) != S_OK)  
    {  
        wprintf_s(L"ERROR - PrintStreamData() get_name\n");  
    }  
    else  
    {  
        wprintf_s(L"Stream: %s", wszName);  
        SysFreeString(wszName);  
    }  
    if(pStream->get_Count(&dwElem) != S_OK)  
    {  
        wprintf(L"ERROR - PrintStreamData() get_Count\n");  
    }  
    else  
    {  
        wprintf(L"(%d)\n", dwElem);  
    }  
    while(pStream->Next(1, sizeof(data), &cbData, (BYTE *)&data, &celt) == S_OK)  
    {  
        DWORD i;  
        for (i = 0; i < cbData; i++)  
        {  
            wprintf(L"%02X ", data[i]);  
            if(i && i % 8 == 7 && i+1 < cbData)  
            {  
                wprintf(L"- ");  
            }  
        }  
        wprintf(L"| ");  
        for(i = 0; i < cbData; i++)  
        {  
            wprintf(L"%c", iswprint(data[i]) ? data[i] : '.');  
        }  
        wprintf(L"\n");  
        cbTotal += cbData;  
    }  
    wprintf(L"Summary :\n\tSizeof(Elem) = %d\n\tNo of Elems = %d\n\n",  
            cbTotal/dwElem, dwElem);  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumdebugstreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)   
 [IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)