---
title: IDebugProperty3::CreateObjectID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProperty3::CreateObjectID
helpviewer_keywords:
- IDebugProperty3::CreateObjectID
ms.assetid: f2fa81e7-822f-456e-8729-a96a18eea771
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 337e1a4025e71a637e73b258df41828b7ddf1f43
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugproperty3createobjectid"></a>IDebugProperty3::CreateObjectID
Diğer özellikler arasında benzersiz olduğundan emin olmak için bu özellik için benzersiz bir kimliği oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CreateObjectID(  
   void  
);  
```  
  
```csharp  
int CreateObjectID();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellik diğer özellikler arasında benzersiz şekilde tanımlanır emin olmak oturum hata ayıklama Yöneticisi istediği zaman bu yöntem çağrılır. Hata ayıklama altyapısı (DE) ile ilgilenir özellikleri zaten benzersiz şekilde tanımlanır sürece bu yöntem destekler. DE bu yöntemi desteklemiyor varsa, döndürür `E_NOTIMPL`.  
  
 Benzersiz bir kimliği ile oluşturulan `CreateObjectID` zaman yok [DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md) yöntemi çağrılır; bu da bu özellik benzersiz olarak tanımlamak için gereken sonuna işaret eder.  
  
> [!NOTE]
>  Bu benzersiz kimliği ne olursa olsun için benzersiz kimlikler istediği DE yapabilirsiniz almak için bir yöntem yoktur, `CreateObjectID` yöntemi çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md)