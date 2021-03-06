---
title: "&lt;formRegions&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- formRegions element
- <formRegions> element
- application manifests [Office development in Visual Studio], <formRegions> element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: eb7008f86dd552eac2b8a6ba9b227884270c8694
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="ltformregionsgt-element-office-development-in-visual-studio"></a>&lt;formRegions&gt; öğesi (Visual Studio'da Office Geliştirme)
  `formRegions` Öğesinin `vstov4` ad alanı, VSTO eklenti ile ilişkili Microsoft Office Outlook form bölgeleri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<formRegions>  
  <formRegion>  
  </formRegion>  
</formRegions>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `formRegions` Öğesinin `vstov4` ad alanı içeren tüm `formRegion` bir Outlook VSTO eklenti için öğeleri. Yalnızca Outlook VSTO form bölgeleri içeren eklentileri için gereklidir.  
  
 Yalnızca bir olabilir `formRegions` uygulama bildiriminde tanımlanan öğe.  
  
 `formRegions` Öğesi özniteliklere sahip değildir.  
  
 `formRegions` Öğesinin öğesi yok.  
  
### <a name="formregion"></a>formRegion  
 Outlook VSTO form bölgeleri içeren eklentileri için gereklidir. `formRegion` Öğesi tanımlanmış [&#60; formRegion &#62; Öğe &#40; Office geliştirme Visual Studio &#41; ](../vsto/formregion-element-office-development-in-visual-studio.md).  
  
## <a name="vsto-add-in-example"></a>VSTO eklentileri örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir bir `formRegions` kullanarak dağıtılmış uygulama düzeyi Office çözümü için bir uygulama bildirimi öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```  
<vstov4:formRegions>  
  <vstov4:formRegion  
      name="OutlookAddIn1.FormRegion1">  
    <vstov4:messageClass name="IPM.Note" />  
    <vstov4:messageClass name="IPM.Contact" />  
    <vstov4:messageClass name="IPM.Appointment" />  
  </vstov4:formRegion>  
</vstov4:formRegions>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  