---
title: "Nasıl yapılır: bir SharePoint Proje öğe uzantısına bir kısayol menü öğesi ekleme | Microsoft Docs"
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
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 26158159015a9d4e6b76845341903aa8c25af0e4
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension"></a>Nasıl yapılır: Bir SharePoint Proje Öğe Uzantısına bir Kısayol Menü Öğesi Ekleme
  Bir proje öğesi uzantısı kullanarak bir var olan bir SharePoint proje öğesi bir kısayol menü öğesi ekleyebilirsiniz. Bir kullanıcı proje öğeyi tıklattığında menü öğesi görünür **Çözüm Gezgini**.  
  
 Aşağıdaki adımlar, bir proje öğesi uzantısı zaten oluşturduğunuzu varsayalım. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje öğesi uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
### <a name="to-add-a-shortcut-menu-item-in-a-project-item-extension"></a>Bir proje öğe uzantısına bir kısayol menü öğesi eklemek için  
  
1.  İçinde <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> yöntemi, <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> uygulaması, tanıtıcı <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> olayı *projectItemType* parametresi.  
  
2.  Olay işleyicisi için <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> olay, yeni bir ekleme <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> nesnesini <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> veya <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> olay bağımsız değişken parametre koleksiyonu.  
  
3.  İçinde <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> yeni için olay işleyicisini <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> nesne, bir kullanıcı kısayol menü öğesi tıkladığında yürütmek istediğiniz görevleri gerçekleştirin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği için olay alıcı proje öğesi bir kısayol menü öğesi ekleme gösterilmiştir. Kullanıcı proje öğeyi tıklattığında **Çözüm Gezgini** ve **yazma iletisi çıkış penceresine** menü öğesi, Visual Studio içinde bir ileti görüntüler **çıkış**penceresi.  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemextensionmenu.vb#1)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemextensionmenu.cs#1)]  
  
 Bu örnek ileti yazmak için SharePoint Proje hizmeti kullanır **çıkış** penceresi. Daha fazla bilgi için bkz: [SharePoint Proje hizmetini kullanma](../sharepoint/using-the-sharepoint-project-service.md).  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek, bir sınıf kitaplığı projesi aşağıdaki derlemeler başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Uzantısını dağıtma  
 Uzantıyı dağıtmak için oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir SharePoint proje öğesi uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)   
 [Nasıl yapılır: bir SharePoint Proje öğe uzantısına özellik ekleme](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)   
 [SharePoint proje öğelerini genişletme](../sharepoint/extending-sharepoint-project-items.md)   
 [İzlenecek yol: Bir SharePoint Proje Öğesi Türünü Genişletme](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
  