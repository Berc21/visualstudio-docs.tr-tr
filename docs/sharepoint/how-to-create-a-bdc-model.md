---
title: "Nasıl yapılır: bir BDC modeli oluşturma | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], creating a model
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6b4e01a61ac3802edc2dc6e5f6ab3680d39e7704
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-a-bdc-model"></a>Nasıl yapılır: BDC Modeli Oluşturma
  Bu tür bir öğe için şablon kullanılarak ve sonra herhangi bir SharePoint projesine model ekleyerek bir iş verileri bağlantı (BDC) modeli oluşturabilirsiniz. Daha fazla bilgi için bkz: [iş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md). Model tasarlama hakkında daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-create-a-bdc-project"></a>BDC projesi oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
    > [!NOTE]  
    >  Visual Basic geliştirme ayarlarını kullanmak için IDE'yi ayarlarsanız seçin **dosya**, **yeni proje**.  
  
     **Yeni proje** iletişim kutusu açılır.  
  
2.  Ya da altında **Visual Basic** veya **Visual C#**, seçin **Office/SharePoint**, **SharePoint çözümlerini**.  
  
3.  İçinde **şablonları** bölmesinde seçin **SharePoint 2013 - boş proje** öğesini ve ardından **Tamam** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** açar.  
  
4.  Üzerinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** sayfasında, yerel bilgisayarda bir SharePoint sitesinin URL'sini belirtin, **Grup çözümü olarak dağıtma** seçeneği düğmesine ve ardından **Son** düğmesi.  
  
     Belirtilen SharePoint sitesindeki modeli test edeceğiz.  
  
    > [!IMPORTANT]  
    >  BDC modeli yalnızca küme çözümleri desteklemediğinden proje Grup çözümü dağıtmanız gerekir.  
  
     Boş bir SharePoint projesi oluşturulur.  
  
5.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle**.  
  
6.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **Office/SharePoint** düğümü.  
  
7.  SharePoint şablonları listesinden seçip **iş verileri bağlantı modeli (yalnızca Grup çözüm)**.  
  
8.  İçinde **adı** kutusunda BDC modeli için bir ad belirtin ve ardından **Ekle** düğmesi.  
  
     A **iş verileri bağlantı modeli** öğe projeye eklenmiş. Varsayılan olarak, model BDC Tasarımcısı'nda görünür. Daha fazla bilgi için bkz: [iş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [Nasıl yapılır: bir SharePoint projesine mevcut bir BDC modeli dosyası ekleme](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [Nasıl yapılır: yerelleştirilmiş adlar, özellikler ve izinleri belirtmek için kaynak dosyası kullanın](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [Nasıl yapılır: bir BDC özelliğine özel bir derlemeyi dahil etme](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)   
 [İş Verilerini SharePoint ile Tümleştirme](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  