---
title: "&lt;Güncelleştirme&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
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
- update element
- <update> element
- application manifests [Office development in Visual Studio], <update> element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 72caa5e93b311430f4416946b6ec0bdc9fda5031
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="ltupdategt-element-office-development-in-visual-studio"></a>&lt;Güncelleştirme&gt; öğesi (Visual Studio'da Office Geliştirme)
  `update` Öğesi çözüm denetleyecek güncelleştirmelere yönelik aralığı belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<update  
  enabled>  
  <expiration  
    maximumAge  
    unit  
  />  
</update>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `update` Öğesi gereklidir ve yer `vstav3` ad alanı.  
  
 `update` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`enabled`|Gerekli. Aşağıdaki değerlerden biri için etkinleştirilmiş ayarlayın:<br /><br /> -   **doğru** güncelleştirmeleri denetlemek için.<br />-   **yanlış** güncelleştirmeleri denetleniyor önlemek için.|  
  
 `update` Öğe aşağıdaki alt öğeleri vardır.  
  
### <a name="expiration"></a>süre sonu  
 `expiration` Öğesi gereklidir ve yer `vstav3` ad alanı. Bu öğe, çözüm denetler aralığını güncelleştirmeleri belirtir.  
  
 `expiration` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`maximumAge`|-Gerekli. Bu, bir tamsayıya eşit ayarlayın.|  
|`unit`|Gerekli. Ayarlama `unit` aşağıdaki değerlerden birine:<br /><br /> -   **saatleri**<br />-   **gün**<br />-   **Hafta**|  
  
## <a name="example-of-always-checking-for-updates"></a>Her zaman güncelleştirmeleri denetleniyor örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir bir `update` her zaman Office çözümlerinde güncelleştirmeleri denetlemek için ayarlanmış öğesi.  
  
### <a name="code"></a>Kod  
  
```  
<vstav3:update enabled="true" />  
```  
  
## <a name="example-of-setting-a-default-update-interval"></a>Bir varsayılan güncelleştirme aralığı ayarlama örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir bir `update` Office çözümleri için uygulama bildiriminde öğesi. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```  
<vstav3:update enabled="true">  
    <vstav3:expiration maximumAge="7" unit="days" />  
</vstav3:update>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  