---
title: "Visual Studio'da SharePoint araçları genişletme | Microsoft Docs"
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
- Visual Studio, extending tools
- extensibility [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, extending tools
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: db0afa41641cd9d5ae04cfe6d391dbf0fe814f0f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="extending-the-sharepoint-tools-in-visual-studio"></a>SharePoint Araçlarını Visual Studio'da Genişletme
  Visual Studio'da SharePoint araçları birçok uygulama geliştirme senaryoları gereksinimlerini karşılamak. Ancak, bunlar burada, veya diğer geliştiriciler gerektiren işlevselliği sağlamaz durumlarda fark edebilirsiniz. Bu durumlarda, ihtiyacınız olan işlevselliği oluşturmak için SharePoint araçları genişletebilirsiniz.  
  
## <a name="how-to-extend-the-sharepoint-tools"></a>SharePoint araçları genişletme  
 SharePoint Proje sisteminin genişletebilirsiniz ve **SharePoint bağlantıları** düğümünde **Sunucu Gezgini** penceresi.  
  
### <a name="extending-the-sharepoint-project-system"></a>SharePoint Proje Sistemini Genişletme  
 Visual Studio Proje şablonları ve SharePoint çözümleri oluşturmak için kullanabileceğiniz öğe şablonları kümesini içerir. Örneğin, Olay alıcıları, liste tanımları, iş akışları ve Web bölümleri için şablonlar vardır. Ancak, kendi tür alanları veya özel eylemler gibi SharePoint bileşenlerini oluşturmak için SharePoint Proje öğeleri tanımlayabilirsiniz. SharePoint projeleri için Uzantılar oluşturabilir ve Visual Studio yüklü olan SharePoint proje öğesi türleri için uzantıları de oluşturabilirsiniz.  
  
 Daha fazla bilgi için bkz: [SharePoint Proje sistemini genişletme](../sharepoint/extending-the-sharepoint-project-system.md).  
  
### <a name="extending-the-sharepoint-connections-node-in-server-explorer"></a>Sunucu Gezgininde SharePoint Bağlantılarını Genişletme  
 Visual Studio'da kullandığınız **SharePoint bağlantıları** düğümünde**Sunucu Gezgini** bir hiyerarşik ağaç görünümünde birçok bileşenlerin bir veya daha fazla yerel SharePoint siteleri için pencere. Ayrıca genişletebilirsiniz **SharePoint bağlantıları** aşağıdaki yollarla düğümü:  
  
-   Kendi düğüm ekleyerek. Bu, varsayılan olarak görüntülenmez SharePoint siteleri bileşenlerinin görüntülemek istiyorsanız kullanışlıdır.  
  
-   Varolan düğümleri genişleterek. Örneğin, varolan bir düğümü yeni bir alt düğüm ekleyebilir veya bir düğüme bir kısayol menü öğesi ekleme ve bir geliştirici menü öğesini tıkladığında görevleri gerçekleştirin.  
  
 Daha fazla bilgi için bkz: [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).  
  
## <a name="development-computer-requirements"></a>Geliştirme bilgisayar gereksinimleri  
 SharePoint araçları için Uzantılar oluşturmak için geliştirme bilgisayarınızda Visual Studio'da SharePoint çözümleri oluşturmak için aynı gereksinimleri karşılamalıdır. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
 Ayrıca, yüklemenizi öneririz [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]. SDK proje şablonları ve Visual Studio genişletmek için kullanabileceğiniz araçlar içerir. Özellikle, SDK kolayca bir Visual Studio Uzantısı (VSIX) paketi oluşturmak için kullanabileceğiniz bir proje şablonu içerir. VSIX paket Visual Studio'da Visual Studio uzantılarını dağıtmak için tercih edilen yöntemdir. Tüm SharePoint araç uzantıları VSIX paket kullanılarak dağıtılmalıdır. İzlenecek yollar bu belgedeki tüm sahip olduğunuzu varsaymaktadır [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)] yüklü.  
  
 Visual Studio SDK'sını yüklemek için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md). Visual Studio uzantıları hakkında daha fazla bilgi için bkz: [geliştirmek Visual Studio uzantıları başlangıç](../extensibility/starting-to-develop-visual-studio-extensions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzantıları araç SharePoint programlama modeline genel bakış](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)   
 [SharePoint Proje sistemini genişletme](../sharepoint/extending-the-sharepoint-project-system.md)   
 [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [SharePoint araç uzantıları için programlama kavramları ve Özellikler](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)   
 [Başvuru &#40; SharePoint araçları genişletilebilirliği &#41;](../sharepoint/reference-sharepoint-tools-extensibility.md)   
 [Visual Studio'da SharePoint araçları için hata ayıklama uzantıları](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md)   
 [Visual Studio'da SharePoint Araçları için Hata Ayıklama Uzantıları](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  