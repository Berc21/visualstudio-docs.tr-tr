---
title: DEBUG_ADDRESS_UNION | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEBUG_ADDRESS_UNION
helpviewer_keywords:
- DEBUG_ADDRESS_UNION union
ms.assetid: e3d11aab-de0d-4109-b5dc-11e07e64382d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: fc4e5c4bf075c69f4549e34185d407ba9fb95cd5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugaddressunion"></a>DEBUG_ADDRESS_UNION
Adresleri farklı türleri açıklanmaktadır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _tagDEBUG_ADDRESS_UNION {  
   ADDRESS_KIND dwKind;  
   union {  
      NATIVE_ADDRESS                  addrNative;  
      UNMANAGED_ADDRESS_THIS_RELATIVE addrThisRel;  
      UNMANAGED_ADDRESS_PHYSICAL      addrUPhysical;  
      METADATA_ADDRESS_METHOD         addrMethod;  
      METADATA_ADDRESS_FIELD          addrField;  
      METADATA_ADDRESS_LOCAL          addrLocal;  
      METADATA_ADDRESS_PARAM          addrParam;  
      METADATA_ADDRESS_ARRAYELEM      addrArrayElem;  
      METADATA_ADDRESS_RETVAL         addrRetVal;  
      DWORD                           unused;  
   } addr;  
} DEBUG_ADDRESS_UNION;  
```  
  
```csharp  
public struct DEBUG_ADDRESS_UNION {  
   public ADDRESS_KIND dwKind;  
   public IntPtr       unionmember;  
}  
```  
  
## <a name="terms"></a>Koşulları  
 dwKind  
 Arasında bir değer [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) belirterek birleşimi yorumlama numaralandırması.  
  
 addr.addrNative  
 [Yalnızca C++] İçeren [NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md) , yapı `dwKind` ADDRESS_KIND_NATIVE =.  
  
 addr.addrThisRel  
 [Yalnızca C++] İçeren[UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md) , yapı `dwKind` ADDRESS_KIND_UNMANAGED_THIS_RELATIVE =.  
  
 addr.addUPhysical  
 [Yalnızca C++] İçeren[UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md) , yapı `dwKind` ADDRESS_KIND_UNMANAGED_PHYSICAL =.  
  
 addr.addrMethod  
 [Yalnızca C++] İçeren[METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md) , yapı `dwKind` ADDRESS_KIND_METHOD =.  
  
 addr.addrField  
 [Yalnızca C++] İçeren[METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md) , yapı `dwKind` ADDRESS_KIND_FIELD =.  
  
 addr.addrLocal  
 [Yalnızca C++] İçeren[METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md) , yapı `dwKind` ADDRESS_KIND_LOCAL =.  
  
 addr.addrParam  
 [Yalnızca C++] İçeren[METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md) , yapı `dwKind` ADDRESS_KIND_PARAM =.  
  
 addr.addrArrayElem  
 [Yalnızca C++] İçeren[METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md) , yapı `dwKind` ADDRESS_KIND_ARRAYELEM =.  
  
 addr.addrRetVal  
 [Yalnızca C++] İçeren[METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md) , yapı `dwKind` ADDRESS_KIND_RETVAL =.  
  
 addr.Unused  
 [C++ yalnızca] doldurma.  
  
 Adr  
 [Yalnızca C++] UNION adı.  
  
 unionmember  
 [Sadece C#] Bu değer göre uygun bir yapı türüne sıralanması gerekiyor `dwKind`. Açıklamalar arasındaki ilişkiyi bkz `dwKind` ve UNION yorumu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı parçası olan [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) yapısı ve adresleri farklı türde bir dizi birini temsil eder ( `DEBUG_ADDRESS` yapısı doldurulur çağrısıyla [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) yöntemi).  
  
 [Sadece C#] Aşağıdaki tabloda yorumlama gösterilmektedir `unionmember` adresi her türdeki üye. Bu örnek, bu adresi bir tür için nasıl yapıldığını gösterir.  
  
|`dwKind`|`unionmember`yorumlanan|  
|--------------|----------------------------------|  
|`ADDRESS_KIND_NATIVE`|[NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md)|  
|`ADDRESS_KIND_UNMANAGED_THIS_RELATIVE`|[UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md)|  
|`ADDRESS_KIND_UNMANAGED_PHYSICAL`|[UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md)|  
|`ADDRESS_KIND_METHOD`|[METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md)|  
|`ADDRESS_KIND_FIELD`|[METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md)|  
|`ADDRESS_KIND_LOCAL`|[METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md)|  
|`ADDRESS_KIND_PARAM`|[METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md)|  
|`ADDRESS_KIND_ARRAYELEM`|[METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md)|  
|`ADDRESS_KIND_RETVAL`|[METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md)|  
  
## <a name="example"></a>Örnek  
 Bu örnek, bir tür adres yorumlama gösterir (`METADATA_ADDRESS_ARRAYELEM`), `DEBUG_ADDRESS_UNION` C# yapısı. Kalan öğeleri tam olarak aynı şekilde yorumlanabilir.  
  
```csharp  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(DEBUG_ADDRESS_UNION dau)  
        {  
            if (dau.dwKind == (uint)enum_ADDRESS_KIND.ADDRESS_KIND_METADATA_ARRAYELEM)  
            {  
                 METADATA_ADDRESS_ARRAYELEM arrayElem =  
                     (METADATA_ADDRESS_ARRAYELEM)Marshal.PtrToStructure(dau.unionmember,  
                                 typeof(METADATA_ADDRESS_ARRAYELEM));  
            }  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)