---
title: IDebugDocumentPositionOffset2::GetRange | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugDocumentPositionOffset2::GetRange
ms.assetid: 27da7130-0932-4f97-abde-05e6fb018606
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 09b415e01b6c768f471bdf9ad2e595d1a910d582
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentpositionoffset2getrange"></a>IDebugDocumentPositionOffset2::GetRange
Geçerli belge konumu için aralığını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetRange(  
   DWORD* pdwBegOffset,  
   DWORD* pdwEndOffset  
);  
```  
  
```csharp  
public int GetRange(  
   ref uint pdwBegOffset,  
   ref uint pdwEndOffset  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdwBegOffset`  
 [içinde out] Aralık için başlangıç konumu uzaklığı. Bu bilgileri gerekmiyorsa bu parametre null bir değere ayarlayın.  
  
 `pdwEndOffset`  
 [içinde out] Aralığın bitiş konumu için uzaklık. Bu bilgileri gerekmiyorsa bu parametre null bir değere ayarlayın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Belge konumda bir konum kesme noktası için belirtilen aralık, önceden gerçekte kod katkıda bulunan bir deyim için arama yapmak (DE) hata ayıklama altyapısı tarafından kullanılır. Örneğin, aşağıdaki kodu göz önünde bulundurun:  
  
```  
Line 5: // comment  
Line 6: x = 1;  
```  
  
 Satır 5 ayıklanacak programa kod katkıda bulunur. 5. satırda kesme ayarlar hata ayıklayıcı DE belirli bir miktar kod katkıda bulunan ilk satırı için ileriye doğru arama yapmak isterse, hata ayıklayıcı nereye bir kesme noktası düzgün yerleştirilmesi ek adayı satırları içeren bir aralığı belirtirsiniz. Bir kesme noktası kabul edebilecek bir satır bulunamadı kadar DE sonra İleri bu satırlar arama.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDocumentPositionOffset2](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2.md)   
 [GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)