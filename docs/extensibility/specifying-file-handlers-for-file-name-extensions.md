---
title: "Dosya adı uzantıları için dosya işleyicisi belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- file extensions, specifying file handlers
ms.assetid: e3de4730-a95c-465a-b3b2-92ca85364ad7
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d5db7a218a718e27f584abbf350b49907b56fb17
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="specifying-file-handlers-for-file-name-extensions"></a>Dosya adı uzantıları için dosya işleyicisi belirtme
Bir belirli bir uzantıya sahip bir dosya işler uygulamayı belirlemek için çeşitli yöntemler vardır. OpenWithList ve OpenWithProgids fiilleri dosya uzantısı için kayıt defteri girdisinin altındaki dosya işleyicisi belirtmek için iki yollarıdır.  
  
## <a name="openwithlist-verb"></a>OpenWithList fiil  
 Windows Gezgini'nde bir dosyaya sağ tıklayın, gördüğünüz **açık** komutu. Birden fazla ürün uzantı ile ilişkili ise, gördüğünüz bir **birlikte Aç** alt.  
  
 Uzantı HKEY_CLASSES_ROOT içinde dosya uzantısı için OpenWithList anahtarını ayarlayarak açmak için farklı uygulamaları kaydedebilir. Bir dosya uzantısı için bu anahtarı altında listelenen uygulamaları altında göründüğünü **önerilen program** içinde başlık **birlikte Aç** iletişim kutusu. Aşağıdaki örnek .vcproj dosya uzantısı açmak için kaydedilmiş uygulamaları gösterir.  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)="VisualStudio.vcproj.14.0"  
      OpenWithList\  
         devenv.exe  
```  
  
> [!NOTE]
>  HKEY_CLASSES_ROOT\Applications altındaki listeden uygulamalar belirtme anahtarları şunlardır.  
  
 Bir OpenWithList anahtarı ekleyerek aittir uzantısı'nın başka bir uygulama olsa bile, uygulamanızın bir dosya uzantısı desteklediğini bildirin. Bu, uygulamanızın veya başka bir uygulama gelecek bir sürümünde olabilir.  
  
## <a name="openwithprogids"></a>OpenWithProgIDs  
 Programsal tanımlayıcıları (ProgID) bir uygulama veya COM nesnesi sürümünü tanımlamak ClassID kolay sürümleridir. Birlikte creatable her nesne kendi ProgID olması gerekir. Örneğin, VisualStudio.DTE.10.0 başlatılırken VisualStudio.DTE.7.1 Visual Studio .NET 2003 başlar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Bir proje veya proje öğesi türü sahibi olarak, dosya uzantısı için sürüme özgü ProgID oluşturmanız gerekir. Aynı uygulamayı birden fazla ProgID başlayabilir, bu ProgID gereksiz olabilir. Daha fazla bilgi için bkz: [dosya adı uzantıları için kaydetme fiillere](../extensibility/registering-verbs-for-file-name-extensions.md).  
  
 Aşağıdaki adlandırma kuralını sürümlü dosya ProgID diğer satıcılardan kayıt ile yinelemesinden kaçınmak için kullanın:  
  
|Dosya uzantısı|Sürümü tutulan ProgID|  
|--------------------|----------------------|  
|.Extension|ProductName. extension.versionMajor.versionMinor|  
  
 Belirli dosya uzantısı sürümlü ProgID değeri olarak HKEY_CLASSES_ROOT ekleyerek açabilmelisiniz farklı uygulamaları kaydedebilir\\*\<uzantısı >*\OpenWithProgids anahtarı. Bu kayıt defteri anahtarı dosya uzantısı ile ilişkili diğer ProgID listesini içerir. Listelenen ProgID ile ilişkili uygulamaları görünür **birlikte Aç***ürün adı* alt. İkisi de aynı uygulama belirtilirse `OpenWithList` ve `OpenWithProgids` anahtarları, işletim sistemi çoğaltmaların birleştirir.  
  
> [!NOTE]
>  `OpenWithProgids` Anahtarı yalnızca Windows XP'de desteklenir. Bu anahtar diğer işletim sistemlerinin yoksay çünkü dosya işleyicileri için yalnızca kayıt olarak kullanmayın. Windows XP'de daha iyi bir kullanıcı deneyimi sağlamak için bu anahtarı kullanın.  
  
 İstenen ProgID REG_NONE türü değerleri ekleyin. Aşağıdaki kodu bir dosya uzantısı için ProgID kaydetme örneğidir (. *ext*).  
  
```  
HKEY_CLASSES_ROOT\  
   .ext\  
      (default)="MyProduct.ext.14.0"  
      OpenWithProgids  
         progid        REG_NONE (zero-length binary value)  
         otherprogid   REG_NONE (zero-length binary value)  
```  
  
 Varsayılan değer dosya uzantısı için varsayılan dosya işleyici olarak belirtilen ProgID. Önceki bir sürümü ile birlikte gelen bir dosya uzantısı için ProgID değiştirirseniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] veya diğer uygulamalar tarafından devralınırsa alınabilmesini ardından kaydetmeniz gerekir `OpenWithProgids` dosya uzantısı için anahtarı ve birlikte listesinde yeni ProgID belirtin desteklediğiniz eski ProgID. Örneğin:  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)="VisualStudio.vcproj.14.0"  
      OpenWithProgids  
         vcprojfile              //old progid  
         VisualStudio.vcproj.12.0 //old progid  
         VisualStudio.vcproj.14.0 //new progid  
```  
  
 Eski ProgID ilişkili fiiller sahip sonra bu eylemler de altında görünür **birlikte Aç** *ürün adı* kısayol menüsünde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya adı uzantıları hakkında](../extensibility/about-file-name-extensions.md)   
 [Dosya Adı Uzantıları için Fiil Kaydetme](../extensibility/registering-verbs-for-file-name-extensions.md)