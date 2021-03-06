---
title: "İç içe geçmiş projeleri için filtreleme addItem iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filtering, nested projects
- nested projects, AddItem dialog box filtering
ms.assetid: 5b3e352e-7f18-4f66-be16-b0ad55637ce5
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e1f5fc7695df028330d0e53faebefc178f499da1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="filtering-the-additem-dialog-box-for-nested-projects"></a>İç içe geçmiş projeleri için filtreleme addItem iletişim kutusu
Görüntülediğinizde bir **addItem** ana proje iç içe geçmiş bir proje için iletişim kutusu, hangi öğeler iletişim kutusunda görüntülenen denetleyebilirsiniz.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> Arabirimi olacak düğümleri filtreleme olanak tanır bir **addItem** iletişim kutusu. Alt proje görüntülendiğinde **addItem** iletişim kutusu, üst uygulayabilirsiniz `IVsFilterAddProjectItemDlg` çocuğun projesinde görüntülenmesi arabirimi ve filtre öğeleri.  
  
 Projeleri belirli üst projeleri altında işleve göre gruplandırılır olduğunda uygulayabileceğiniz `IVsFilterAddProjectItemDlg` kullanıcı seçtiğinde **proje öğesi Ekle** iç içe proje kısayol menüsünde. Uygulama `IvsFilterAddProjectItemDlg displays` yalnızca proje öğelerini ya da bu gruba belirli dosyaları. Aynı dizinde depolanır olsa bile diğer grupları için proje öğeleri iletişim kutusu dışında filtrelenir.  
  
 Kullanıcı açtığında **addItem** alt, üst projenin uygulaması için iletişim kutusu `IVsFilterAddProjectItemDlg` arabirimi çağrılır.  
  
 `IVsFilterAddProjectItemDlg` Arabirimi, kategoriye göre filtreleme de uygulayabilirsiniz. Daha fazla bilgi için bkz: [ekleme yeni öğe iletişim kutuları için öğe eklemeyi](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md) ve [kaydetme proje ve öğe şablonlarını](../../extensibility/internals/registering-project-and-item-templates.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Öğeler ekleme yeni öğe Ekle iletişim kutuları](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Proje ve öğe şablonları kaydediliyor](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Projeleri İç İçe Geçirme](../../extensibility/internals/nesting-projects.md)