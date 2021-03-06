---
title: "Eski iş akışı Tasarımcısı'nı kullanarak | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Visual Studio 2005 Extensions for Windows Workflow Foundation, about
ms.assetid: 7af53077-afd7-465f-9c1d-b387e9d4f216
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a042d98019b7f618792f7a9104d262362a4e6e3d
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="using-the-legacy-workflow-designer"></a>Eski iş akışı Tasarımcısı'nı kullanarak
Eski [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] tarafından sağlanan [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] kullanılabilir hedef [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 Ya da seçilerek erişilir **.NET Framework 3.0** seçeneği veya **.NET Framework 3.5** aşağı açılan listeden en üstündeki seçeneğinde **yeni proje** penceresi. Varsayılan seçenek [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] olan **.NET Framework 4** oluşturmak için kullanılan [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] hedefleyen uygulamalar [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)].

 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Grafik oluşturmak için bir yol sağlar [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] bilinen kullanan uygulamalar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kullanıcı arabirimi. [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] uygulamaları etkinlikler olarak adlandırılan iş akışı işlem adımlarından oluşur. Bir iş akışı oluşturmak için kendi ilgili etkinlik tasarımcıları gelen sürükleyerek tasarım yüzeyine etkinliklerini oluşturan **araç** tasarım yüzeyine.

 Aşağıdaki tabloda temel özellikleri listeler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Windows Workflow Foundation için.

|Özellik|Açıklama|
|-------------|-----------------|
|Etkinlik sürükleme ve bırakma|Sürükleme etkinliklerden **araç** bir iş akışı oluşturmak için tasarım yüzeyine.|
|Özellik Tarayıcısı|Standart **özellikleri** penceresinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir etkinlik özelliklerini yapılandırmak için kullanılır.|
|Yakınlaştır|Dürbün **yakınlaştırma düzeyini** simgesi tasarım yüzeyine sağ tarafında dikey kaydırma çubuğunun altında bulunur. Dürbün tıklatın ve yakınlaştırmak veya uzaklaştırmak için iş akışı grafiği neden yakınlaştırma yüzdesini seçin. Aynı zamanda **Pan** yakınlaştırma ve uzaklaştırma simge Büyüteç imleç seçenekleri.|
|Kaydır|**Pan** simgesi, dört yönde çapraz dört oklar içeren bir daire dürbün Yakınlaştır simgesi hemen altındaki tasarım yüzeyi sağ taraftaki dikey kaydırma çubuğunun altında bulunur. Pan simgesine tıklayın, açılır menü aşağıdaki imleç seçenekleri sunar:<br /><br /> - **Yakınlaştır** Büyüteç imleç tasarım yüzeyine tıklayarak yakınlaştırmak olanak sağlar.<br />- **Uzaklaştır** Büyüteç imleç tasarım yüzeyine tıklayarak Uzaklaştır olanak sağlar.<br />- **Gezinti aracı** el imleç "alın" ve bir iş akışında tasarım yüzeyine görünümünü shift olanak sağlar.<br />- **Varsayılan** ok imleç varsayılan ok imleci diğer imleçler geçiş olanak sağlar.|
|Otomatik kaydırma|Büyük bir iş akışı varsa, bir etkinlik tasarım yüzey alanını görünür görüntüsünü ötesinde yerleştirmek isteyebilirsiniz. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir etkinlik etkinlik yerleştirmek istediğiniz yere yakın tasarım yüzeyi kenarına doğru sürükleyin olanak sağlar. Tasarım yüzeyi görünümü bu yönde otomatik olarak kayar.|
|Akıllı etiketler|Tamamen yapılandırılmış veya geçerli bir şekilde yapılandırılan etkinlikleri bir ünlem simgesiyle işaretlenir. Simgesine tıklayın ve açılan listesini mevcut yapılandırma gereksinimlerini faaliyete bakın. Daha sonra kullanabilirsiniz **özellikleri** penceresi etkinlik uygun şekilde yapılandırın. Tüm özellikleri etkinliği için geçerli olduğunda ünlem işareti simge kaybolur.|

## <a name="see-also"></a>Ayrıca bkz.

- [İş akışları geliştirme](http://go.microsoft.com/fwlink?LinkID=65010)