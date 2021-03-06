---
title: "Nasıl yapılır: WPF ağacı Görselleştiricisini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- WPF, debugging
- debugging, WPF
ms.assetid: 2a1bf1cd-90f9-4d06-9fb4-1bfc925afef3
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 78806b2ace7872db06ff403bcae28bb6eff21cd2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-wpf-tree-visualizer"></a>Nasıl Yapılır: WPF Ağacı Görselleştiricisini Kullanma
WPF ağacı görselleştiricisini bir WPF nesnesinin görsel ağaç keşfetmek için ve o ağaç içinde bulunan nesneleri WPF bağımlılık özelliklerini görüntülemek için kullanabilirsiniz. Görsel ağaçlar hakkında daha fazla bilgi için bkz: [WPF ağaçlarında](/dotnet/framework/wpf/advanced/trees-in-wpf). Bağımlılık özellikleri hakkında daha fazla bilgi için bkz: [bağımlılık özelliklerine genel bakış](/dotnet/framework/wpf/advanced/dependency-properties-overview).  
  
 WPF ağacı görselleştiricisini açtığınızda, iki bölme görürsünüz: **görsel ağaç** soldaki ve **özelliklerini** *adı***:**  *Tür* sağdaki bölmesi. Herhangi bir nesne seçin **görsel ağaç** bölmesinde ve **özelliklerini** *adı***:***türü* bölmesi Bu nesne özelliklerini göstermek için otomatik olarak güncelleştirilir.  
  
### <a name="to-open-the-wpf-tree-visualizer"></a>WPF ağacı görselleştiricisini açmak için  
  
1.  Bir DataTip içinde **izleme** penceresinde **otomobiller** penceresinde veya **Yereller** WPF nesne adının yanındaki penceresi için büyüteç simgesini bitişik oka tıklayın.  
  
     Görselleştiriciler listesi görüntülenir.  
  
2.  Tıklatın **WPF ağacı Görselleştiricisini**.  
  
### <a name="to-search-the-visual-tree"></a>Görsel ağaç aramak için  
  
-   İçinde **görsel ağaç** bölmesinde, içinde arama yapmak istediğiniz dizeyi yazın **arama** kutusu.  
  
     WPF ağacı görselleştiricisini ilk nesne yazdığınız dizesiyle eşleşen görsel ağaçta hemen bulur. Daha doğru bir eşleşme bulmak için daha fazla karakterleri yazın.  
  
    -   Sonraki eşleşme görsel ağaç içinde gitmek için tıklatın **sonraki**.  
  
    -   Önceki eşleşmeye geri dönmek için tıklatın **önceki**.  
  
    -   Arama ölçütlerini temizlemek için tıklatın **temizleyin**.  
  
### <a name="to-search-the-properties-list"></a>Özellikler listesi aramak için  
  
-   İçinde **özelliklerini** *adı***:***türü* bölmesinde, içinde arama yapmak istediğiniz dizeyi yazın **filtre**kutusu.  
  
     WPF ağacı görselleştiricisini hemen yazdığınız dizeyi eşleştir özellikleri bulur; Şimdi, yalnızca yazdığınız dize eşleştirme özelliklerini görüntüler. Daha doğru bir eşleşme bulmak için daha fazla karakterleri yazın.  
  
    -   Arama ölçütlerini temizlemek için tıklatın **temizleyin**.  
  
### <a name="to-close-the-visualizer"></a>Görselleştirici kapatmak için  
  
-   Tıklatın **Kapat** iletişim kutusunun sağ üst köşedeki simgesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md)   
 [WPF ağaçlarında](/dotnet/framework/wpf/advanced/trees-in-wpf)   
 [Bağımlılık Özelliklerine Genel Bakış](/dotnet/framework/wpf/advanced/dependency-properties-overview)