---
title: "Extensiondataıtem öğesi | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ExtensionDataItem element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 65911101f7484b5e97d63df713c3e580c6964fe7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="extensiondataitem-element"></a>ExtensionDataItem Öğesi
  SharePoint proje öğesi anahtar/değer biçimi ile ilişkili bir özel veri öğesini temsil eder. Anahtar ve değer dize olmalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ExtensionDataItem Key = "Key of the data item"  
    Value = "Value of the data item" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**Key**|Gerekli **xs: String** özniteliği.<br /><br /> Depolamak ve veri öğesi almak için kullanılan anahtar.|  
|**Değer**|Gerekli **xs: String** özniteliği.<br /><br /> Veri öğesinin değeri.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[ExtensionData](../sharepoint/extensiondata-element.md)|SharePoint proje öğesi ile ilişkili olan özel veri öğeleri koleksiyonunu temsil eder.|  
  
## <a name="remarks"></a>Açıklamalar  
 İlişkilendirdiğinizde özel verileri ile bir SharePoint proje öğesi kullanarak <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> özelliği bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> nesnesi, Visual Studio verileri yeni bir kaydeder **Extensiondataıtem** proje öğesi için .spdata dosyasındaki öğesi. Daha fazla bilgi için bkz: [SharePoint Proje sisteminin uzantılarında veri kaydetme](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
## <a name="element-information"></a>Öğe Bilgisi  
  
|||  
|-|-|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Şema adı**|SharePoint proje öğesi şeması|  
|**Dosya doğrulama**|ProjectItemModelSchema.xsd|  
|**Boş olamaz**|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Proje Öğesi Şema Başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  