---
title: "CvReleaseMarkerSeries işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cvmarkers/CvReleaseMarkerSeries
helpviewer_keywords:
- CvReleaseMarkerSeries method
ms.assetid: 3b4711ee-e534-411d-9128-f69cd7932a48
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3251db736e42d0b5e49d92b17720605c507d2184
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="cvreleasemarkerseries-function"></a>CvReleaseMarkerSeries İşlevi
İşaretçi serisi serbest bırakır. Aksi takdirde uygulamanızı yayınlama çökebilir sonra işaret serisi nesne kullanmayın. İşaretçi serisi yayımlamayı hatası bellek sızıntısı neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CvReleaseMarkerSeries(  
   _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pMarkerSeries`  
 Sağlayıcı nesne değişkeni adresidir. Adres boş olamaz, değişkeni herhangi bir değer olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşaret serisi başarıyla yayınlandığı veya tüm hatalar oluştu. hata kodu var. durumda olduğunda S_OK. Hata koşulu denetlemek için başarılı/başarısız makroları kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)