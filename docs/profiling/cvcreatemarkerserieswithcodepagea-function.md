---
title: "CvCreateMarkerSeriesWithCodePageA işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cvmakers/CvCreateMarkerSeriesWithCodePageA
helpviewer_keywords:
- CvCreateMarkerSeriesWithCodePageA method
ms.assetid: 3d7ed601-2222-4be9-a557-f217db008753
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d40f895133ce4fc36a40292d7931c47dd166e8e4
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="cvcreatemarkerserieswithcodepagea-function"></a>CvCreateMarkerSeriesWithCodePageA İşlevi
Belirtilen sağlayıcı ve belirtilen kod sayfası için işaret serisi oluşturur. Bu işlev, açıkça işaret API ANSI işlevleri tarafından yazılan metin kod sayfası belirlemek için kullanılabilir. İzleme yakalanan ve daha sonra farklı yerel ayarlara/dilleri ile farklı makinelerde analiz durumda kod sayfası ayarı yararlı olabilir. Varsayılan olarak GetACP() işlevi tarafından döndürülen kod sayfası kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CvCreateMarkerSeriesWithCodePageA(  
   _In_ PCV_PROVIDER pProvider,  
   _In_ LPCSTR pSeriesName,  
   _In_ UINT nTextCodePage,  
   _Out_ PCV_MARKERSERIES* ppMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pProvider`  
 Cvınitprovider tarafından daha önce başlatılmış sağlayıcı nesnesi. NULL olamaz.  
  
 `pSeriesName`  
 İşaretçi seri adı. BOŞ olamaz, ancak boş dize izin verilir.  
  
 `nTextCodePage`  
 Geçerli kod sayfası.  
  
 `ppMarkerSeries`  
 İşaretçi serisi bağlam depolayan bir çıkış değişkeninin adresi. NULL olamaz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşaretçi serisi başarıyla oluşturulduğunda veya tüm hatalar oluştu. hata kodu var. durumda S_OK. Hata koşulu denetlemek için başarılı/başarısız makroları kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)