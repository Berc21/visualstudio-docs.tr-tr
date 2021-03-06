---
title: "Nasıl yapılır: bir temel Lambert gölgelendirici oluşturun | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec5c10fb-9600-4240-8280-d59451ea1d68
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6c383337c97197daba7b434d4c678bd5d565c10d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-basic-lambert-shader"></a>Nasıl Yapılır: Temel Lambert Gölgelendiricisi Oluşturma
Bu belgede gölgelendirici Tasarımcısı ve yönlendirilmiş grafik gölgelendirici dili (DGSL) Klasik Lambert aydınlatma modeli uygulayan aydınlatma gölgelendirici oluşturmak için nasıl kullanılacağı gösterilmektedir.  
  
 Bu belgede, bu etkinlikler gösterir:  
  
-   Gölgelendirici grafiğe düğüm ekleme  
  
-   Düğümleri bağlantısı kesiliyor  
  
-   Düğümlerini bağlayan  
  
## <a name="the-lambert-lighting-model"></a>Lambert aydınlatma modeli  
 Ortam ve yön aydınlatma 3B Sahne içinde gölge nesnelere Lambert aydınlatma modeli içerir. Ortam bileşenleri aydınlatma 3B Sahne olarak temel seviyede sağlar. Tek yönlü bileşenleri tek yönlü (Şimdiye kadar koyma) açık kaynaklardan ek aydınlatma sağlar. Ortam aydınlatma Sahne içindeki tüm yüzeyleri eşit, bağımsız olarak kendi yönlendirmesini etkiler. Belirli bir yüzey için ortam yüzey ve rengini renk ve Sahne ortam aydınlatma yoğunluğunu bir üründür. Tek yönlü ışık ışık kaynağının yönüne göre yüzeyini yönünü göre Sahne her yüzey farklı şekilde etkiler. Bu ürün dağıtma renk ve yüzey ve rengi, yoğunluğu ve açık kaynakları yönünü yönünü olur. En fazla katkısı doğrudan ışık kaynağının doğru yüz yüzeyleri alabilir ve doğrudan hemen yüz yüzeyleri hiçbir katkı alırsınız. Lambert aydınlatma modeli altında her nesne noktası toplam dağıtma renk katkı belirlemek için ortam bileşeni ve bir veya daha çok yönlü bileşenleri birleştirilir.  
  
 Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.  
  
#### <a name="to-create-a-lambert-shader"></a>Lambert gölgelendirici oluşturmak için  
  
1.  Çalışmak için DGSL gölgelendirici oluşturun. Başlarken bölümünde DGSL gölgelendirici projenize ekleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md).  
  
2.  Bağlantı kesme **nokta rengi** düğümden **son renk** düğümü. Seçin **RGB** , terminal **nokta rengi** düğümünü ve ardından **bölün bağlantılar**. Bırakın **alfa** terminal bağlı.  
  
3.  Ekleme bir **Lambert** grafiğe düğüm. İçinde **araç**altında **yardımcı programı**seçin **Lambert** ve tasarım yüzeyine taşıyın. Lambert düğüm ortam ve dağıtma aydınlatma parametrelerine göre piksel, toplam dağıtma renk payını hesaplar.  
  
4.  Bağlantı **nokta rengi** düğüme **Lambert** düğümü. İçinde **seçin** modu, taşıma **RGB** , terminal **nokta rengi** düğüme **Dağıt renk** , terminal **Lambert**  düğüm. Bu bağlantı piksel Ara değerli dağıtma rengini lambert düğümle sağlar.  
  
5.  Hesaplanan renk değeri son renk bağlayın. Taşıma **çıkış** , terminal **Lambert** düğüme **RGB** , terminal **son renk** düğümü.  
  
 Aşağıdaki çizimde, grafik ve teapot modeline uygulanan gölgelendirici önizlemesini tamamlanmış gölgelendirici gösterir.  
  
> [!NOTE]
>  Bu çizimde gölgelendirici etkisini daha iyi göstermek için turuncu bir renk kullanarak belirtilmiş **MaterialDiffuse** Gölgelendirici parametresi. Oyun veya uygulama bu parametre her nesne için bir benzersiz renk değeri sağlamak için kullanabilirsiniz. Önizleme gölgelendiriciler bölümünde malzeme parametreleri hakkında daha fazla bilgi için bkz [gölgelendirici Tasarımcısı](../designers/shader-designer.md).  
  
 ![Gölgelendirici grafik ve etkisini önizlemesini. ] (../designers/media/digit-lambert-effect-graph.png "Lambert etkisi grafik basamak")  
  
 Belirli şekillerin daha iyi önizlemeleri için bazı gölgelendiriciler sağlayabilir. Önizleme gölgelendiriciler bölümünde gölgelendirici Tasarımcısı'nda gölgelendiriciler önizleme hakkında daha fazla bilgi için bkz [gölgelendirici Tasarımcısı](../designers/shader-designer.md).  
  
 Aşağıdaki çizimde, 3-b modeline uygulanan bu belgede açıklanan gölgelendirici gösterir.  
  
 ![Lambert aydınlatma bir modele uygulanır. ] (../designers/media/digit-lambert-effect-result.png "Lambert etkisi sonucu basamak")  
  
 3B modele gölgelendirici uygulama hakkında daha fazla bilgi için bkz: [nasıl yapılır: Gölgelendirici uygulama 3B modele](../designers/how-to-apply-a-shader-to-a-3-d-model.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir 3B modele gölgelendirici uygulama](../designers/how-to-apply-a-shader-to-a-3-d-model.md)   
 [Nasıl yapılır: bir gölgelendirici dışarı aktarma](../designers/how-to-export-a-shader.md)   
 [Nasıl yapılır: bir temel Phong gölgelendirici oluşturma](../designers/how-to-create-a-basic-phong-shader.md)   
 [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)   
 [Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)