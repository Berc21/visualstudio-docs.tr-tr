---
title: "&lt;fileAssociation&gt; öğesi (ClickOnce uygulaması) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <fileAssociation> element [ClickOnce application manifest]
- manifests [ClickOnce], fileAssociation element
ms.assetid: 8f951b4f-54f9-412e-a9e5-af4e379fcf08
caps.latest.revision: "8"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: bd5d7ed1a37923cefc4a6b7975610b6016fd0ae6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltfileassociationgt-element-clickonce-application"></a>&lt;fileAssociation&gt; öğesi (ClickOnce uygulaması)
Uygulamayla ilişkilendirilecek bir dosya uzantısı tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<fileAssociation  
    xmlns="urn:schemas-microsoft-com:clickonce.v1"  
    extension  
    description  
    progid  
    defaultIcon  
/>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `fileAssociation` Öğesidir isteğe bağlıdır. Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`extension`|Gerekli. Uygulamayla ilişkilendirilecek dosya uzantısı.|  
|`description`|Gerekli. Kabuk tarafından kullanım için dosya türü açıklaması.|  
|`progid`|Gerekli. Dosya türü benzersiz olarak tanımlayan bir ad.|  
|`defaultIcon`|Gerekli. Bu uzantılı dosyalar için kullanılacak simgeyi belirtir. Simge dosyası kullanarak belirtilmelidir [ \<Dosya > öğesi](../deployment/file-element-clickonce-application.md) içinde [ \<derleme > öğesi](../deployment/assembly-element-clickonce-application.md) bu öğe içeriyor.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu öğe bir XML ad alanı referansı içermelidir "urn: şemaları-microsoft-com:clickonce.v1". Varsa `<fileAssociation>` öğesi kullanılırsa, sonra gelmelidir `<application>` , üst öğedeki [ \<derleme > öğesi](../deployment/assembly-element-clickonce-application.md).  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]dosya ilişkilendirmeleri üzerine yazmaz. Ancak, bir ClickOnce uygulamasını yalnızca geçerli kullanıcı için dosya uzantısı geçersiz kılabilirsiniz. Bu ClickOnce Uygulama kaldırıldıktan sonra dosya ilişkilendirme kullanıcı için ClickOnce siler ve makine başına ilişkilendirme yeniden etkindir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği gösterilmektedir `fileAssociation` bildiriminde bir uygulamada kullanılarak dağıtılan bir metin düzenleyici uygulaması için [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Bu kod örneği de içeren [ \<Dosya > öğesi](../deployment/file-element-clickonce-application.md) gerektirdiği `defaultIcon` özniteliği.  
  
```  
<file name="text.ico" size="4286">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>0joAqhmfeBb93ZneZv/oTMP2brY=</dsig:DigestValue>  
  </hash>  
</file>  
<file name="writing.ico" size="9662">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>2cL2U7cm13nG40v9MQdxYKazIwI=</dsig:DigestValue>  
  </hash>  
</file>  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".text" description="Text  Document (ClickOnce)" progid="Text.Document" defaultIcon="text.ico" />  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".writing" description="Writings (ClickOnce)" progid="Writing.Document" defaultIcon="writing.ico" />  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulama Bildirimi](../deployment/clickonce-application-manifest.md)