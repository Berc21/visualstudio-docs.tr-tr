---
title: Proje özelliği kullanıcı arabirimi | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- project properties [Visual Studio], user interface
- projects [Visual Studio SDK], properties UI
- project properties UI
ms.assetid: b6aec634-8533-476c-9ebd-36536a2288e2
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9355cd730d58b19dbae0840fa225032ca3ec1589
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="project-property-user-interface"></a>Proje özelliği kullanıcı arabirimi
Proje alt öğeleri projesinde kullanabilirsiniz **özellik sayfaları** iletişim kutusunda Temel Proje tarafından verdiği Gizle veya sağlanan salt okunur denetimler ve tüm sayfaları yapın veya Projealtözgüsayfalarıekleme**Özellik sayfaları** iletişim kutusu.

## <a name="extending-the-project-property-dialog-box"></a>Proje özellik iletişim kutusu genişletme
 Proje alt Otomasyon Extender'larının ve proje yapılandırma Gözat nesneleri uygular. Bu Extender'larının uygulamak <xref:EnvDTE.IFilterProperties> belirli özellikler gizli veya salt okunur hale getirmek için arabirim. **Özellik sayfaları** temel proje tarafından uygulanan temel projenin iletişim kutusu geliştirir Otomasyon Extender'larının tarafından gerçekleştirilen filtreleme.

 Genişletme işlemi bir **proje özelliği** iletişim kutusu aşağıda ana hatları verilmiştir:

-   Temel Proje Extender'larının proje alt türden uygulayarak alır <xref:EnvDTE80.IInternalExtenderProvider> arabirimi. Gözat, Proje Otomasyonu ve tüm temel projenin proje yapılandırma Gözat nesneleri bu arabirimi uygular.

-   Uygulaması <xref:EnvDTE80.IInternalExtenderProvider> proje Gözat nesnesi ve proje Otomasyon nesnesi için temsilci seçme için <xref:EnvDTE80.IInternalExtenderProvider> uygulaması proje alt Toplayıcısı'nın (diğer bir deyişle, bunlar `QueryInterface` için <xref:EnvDTE80.IInternalExtenderProvider> üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> Proje nesnesi).

-   Temel projeyi yapılandırma Gözat nesnesi de uygulayan <xref:EnvDTE80.IInternalExtenderProvider> proje alt yapılandırma nesnesinden Otomasyon genişletici içinde doğrudan kablo. Kendi uygulama temsilci için <xref:EnvDTE80.IInternalExtenderProvider> proje alt toplayıcısı tarafından uygulanan arabirimi.

-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetProjectItem%2A>, proje Gözat, yapılandırma nesnesi tarafından döndürür uygulanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> nesnesi.

-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetCfg%2A>, aynı zamanda proje Gözat, yapılandırma nesnesi tarafından döndürür uygulanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg> nesnesi.

-   Proje alt çalışma zamanında temel projenin çeşitli Genişletilebilir nesneler için uygun CATIDs aşağıdaki alarak belirleyebilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> değerler:

    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>

    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>

    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>

Proje kapsamı CATIDs belirlemek için yukarıdaki özelliklerini proje alt alır [VSITEMID. Kök](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>) gelen `VSITEMID typedef`. Proje alt Ayrıca hangi denetlemek isteyebilirsiniz **özellik sayfaları** iletişim kutusu sayfaları proje için görüntülenen hem yapılandırma bağımlı hem bağımsız yapılandırma. Bazı proje subtypes yerleşik sayfaları kaldırmak ve proje alt belirli sayfalara eklemek gerekebilir. Bu, yönetilen istemci projesi çağrıları etkinleştirmek için <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> yöntemi aşağıdaki özellikler için:

-   `VSHPROPID_PropertyPagesCLSIDList` — Yapılandırma bağımsız özellik sayfaları CLSID noktalı virgülle ayrılmış listesi.

-   `VSHPROPID_CfgPropertyPagesCLSIDList —` yapılandırmaya bağlı özellik sayfaları CLSID noktalı virgülle ayrılmış listesi.

Proje alt tür çünkü toplamalar <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> nesnesi, hangi denetlemek için bu özellikleri tanımı geçersiz **özellik sayfaları** iletişim kutuları görüntülenir. Proje alt bu özellikleri iç temel projeden alın ve ardından ekleyebilir veya CLSID gerektiği şekilde kaldırabilirsiniz.

Proje alt tarafından eklenen yeni özellik sayfaları bir proje yapılandırma Gözat nesnesi temel proje uygulamasından verilir. Bu proje yapılandırma Gözat nesnesi Otomasyon Extender'larının destekler. AutomationExtenders hakkında daha fazla bilgi için bkz: [uygulanması ve Otomasyon Extender'larının](http://msdn.microsoft.com/Library/0d5c218c-f412-4b28-ab0c-33a611f62356). Proje alt çağrı tarafından uygulanan özellik sayfaları <xref:EnvDTE.Project.Extender%2A> temel projeyi yapılandırma Gözat nesnesini genişletir kendi proje alt yapılandırma Gözat nesnesini almak için.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:EnvDTE.IFilterProperties>
- [Özellik sayfaları iletişim kutusu](http://msdn.microsoft.com/en-us/4a3d34ac-ed03-45e8-ae60-a0e1aad300e4)