---
title: "Dize uzunluğu kısıtlamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, restrictions on string lengths
ms.assetid: 877173d2-ca27-43b3-b1f4-8379f7c5e268
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 99144288a4da2a27956a9dc065ba5f5fba03fdcb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="restrictions-on-string-lengths"></a>Dize uzunluğu kısıtlamalar
Kaynak Denetim eklentisi API çeşitli işlevlerde kullanılan dizeleri uzunlukları sınırlar.  
  
## <a name="string-length-values"></a>Dize uzunluğu değerleri  
  
|Sabit|Değer|  
|--------------|-----------|  
|`SCC_NAME_LEN`|31|  
|`SCC_AUXLABEL_LEN`|31|  
|`SCC_USER_LEN`|31|  
|`SCC_PRJPATH_LEN`|300|  
  
> [!NOTE]
>  Uzunluk sonlandırma içermez `null`. Diğer sabitleri "_LEN" yerine "_SIZE" soneki sonlandırma için boşluk `null`.  
  
|Sabit|Değer|  
|--------------|-----------|  
|SCC_NAME_SIZE|32|  
|SCC_AUXLABEL_SIZE|32|  
|SCC_USER_SIZE|32|  
|SCC_PRJPATH_SIZE|301|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentileri](../extensibility/source-control-plug-ins.md)