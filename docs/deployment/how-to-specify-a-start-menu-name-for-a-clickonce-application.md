---
title: "Nasıl yapılır: ClickOnce uygulaması için Başlat menüsü adı belirtme | Microsoft Docs"
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
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
caps.latest.revision: "17"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: b27cf6d67cef1098a54277d4857b75d3fba0ff65
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulaması için Başlat Menüsü Adı Belirtme
Zaman bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamanın yüklü çevrimiçi ve çevrimdışı kullanım için bir giriş eklenen **Başlat** menü ve **Program Ekle veya Kaldır** listesi. Varsayılan olarak, görünen adı uygulama derlemesinin adını aynıdır, ancak ayarlayarak görünen adı değiştirebilirsiniz **ürün adı** içinde **Yayımla Seçenekleri** iletişim kutusu.  
  
 **Ürün adı** görüntülenir publish.htm sayfasında; yüklü çevrimdışı bir uygulama için giriş adı olacaktır **Başlat** menü ve bu da olacak gösterir adı **ekleme veya kaldırma Programları**.  
  
 **Yayımcı adı** yukarıdaki publish.htm sayfasında görünecek **ürün adı**, ve yüklü çevrimdışı bir uygulama için uygulamanın simgesini içeren klasörün adını olacaktır **Başlat**  menüsü.  
  
 Ayarlayabileceğiniz **ürün adı** ve **Yayımcı adı** özelliklerinde **Yayımla Seçenekleri** iletişim kutusu, kullanılabilir **Yayımla** sayfası **Proje Tasarımcısı**.  
  
### <a name="to-specify-a-start-menu-name"></a>Başlat menüsü adı belirtmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **seçenekleri** açmak için düğmeye **Yayımla Seçenekleri** iletişim kutusu.  
  
4.  Tıklatın **açıklama**.  
  
5.  İçinde **Yayımla Seçenekleri** iletişim kutusunda, görüntülemek için bir ad girin **ürün adı**.  
  
6.  İsteğe bağlı olarak, bir yayımcı adını girebilirsiniz **Yayımcı adı**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)