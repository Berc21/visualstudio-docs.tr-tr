---
title: "SccGetVersion işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccGetVersion
helpviewer_keywords:
- SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2aef7ed21124c2e3555442819461f1989388ab22
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="sccgetversion-function"></a>SccGetVersion işlevi
Bu işlev, kaynak denetim eklentisi kaynak denetimi eklentisi tarafından desteklenen API sürümü sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
LONG SccGetVersion(void);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="return-value"></a>Dönüş Değeri  
 A `LONG` desteklenen kaynak denetim eklentisi API'si sürüm numarasını içeren veri türü:  
  
|WORD|Açıklama|  
|----------|-----------------|  
|HIWORD|Ana sürüm|  
|LOWORD|Alt sürümü|  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin, kaynak denetim eklentisi sürüm 1.3 kaynak denetim eklentisi API destekliyorsa, bu işlev 0x0103 döndürecektir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API İşlevleri](../extensibility/source-control-plug-in-api-functions.md)