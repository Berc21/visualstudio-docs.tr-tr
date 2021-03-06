---
title: "Visual Studio için R araçları değişken Explorer'da | Microsoft Docs"
description: "Visual Studio'da değişken Gezgini tüm değişkenleri belirli bir kapsamda geçerli R oturumda gösterir."
ms.custom: 
ms.date: 01/24/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
dev_langs:
- R
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 41dab5fa99f4f725ef3aadc76b2b2441cb2c4abb
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="variable-explorer"></a>Değişken Gezgini

**Değişken Explorer** kullanılarak açılır pencere, **R Araçlar > Windows > değişken Explorer** (veya Ctrl +, kullandıysanız 8 **R Araçlar > veri bilimi ayarları**), tüm gösterir belirli bir kapsamda geçerli R oturumdaki değişkenleri. Örneğin, değişken Explorer açılan ve aşağıdaki satırları girerseniz [etkileşimli pencere](interactive-repl-for-r-in-visual-studio.md):

```R
x <- 42
y <- 43
n <- c(1,2,3,5,8,13)
```

Değişken Gezgini penceresi sonra şu şekilde görünür:

![Visual Studio'da değişken Gezgini penceresi](media/variable-explorer-window.png)

Oturumda tanımlanan daha karmaşık bir R veri çerçevesi varsa, verileri gidebilirsiniz. Örneğin, çalıştırdıktan sonra `cars <- mtcars` değişken Explorer'da farklı düğümleri genişleterek dataset içinde gidebilirsiniz:

![Genişletilmiş Görünüm değişken Gezgini](media/variable-explorer-expanded-results.png)

Değişkenleri silmek için sağ tıklatın ve seçin **silmek**, değişkeni seçin veya Delete tuşuna basın.

Ayrıca bir gözlem artımlı arama özelliğini kullanarak bir veri çerçevesinde arayabilirsiniz. İlk olarak, arama yapmak istediğiniz veri çerçevesinde düğümleri genişletin, sonra arama kutusuna arama terimlerini girin.

## <a name="details-table-view"></a>Ayrıntılarına bakın (tablo)

Veri genellikle tablo olduğundan, herhangi bir karmaşık veri türü ayrı bir tablo Büyüteç simgesini seçerek veya sağ tıklayıp seçerek görüntüleyebileceğiniz **ayrıntıları göster**.

![Değişken Explorer Tablo görünümü](media/variable-explorer-table-view.png)

Bir sütun başlığını tıklatarak veriler (artan veya azalan arasında değişen) sütuna göre sıralanır. Shift tuşunu basılı tutarak ve ek sütunlarda tıklatarak da sıralama için bu sütunları ekler. Bir sütun Shift olmadan tek sütun sıralama için döndürür.

Sütun başlıklarını tıklatın dizisi sıralama gerçekleştirildiği sırasını belirler. Örneğin, SHIFT tuşunu **cyl** sütun sonra Shift tuşunu **mpg** sütunu iki kez silindir artan veya azalan galon başına mil liste sıralar:

![İki sütuna göre sıralama verilerinin Tablo görünümü.](media/variable-explorer-table-view-sorting.png)

Değişken Gezgini ve tablo görünümlerini ayrı Visual Studio windows olduğundan, yan yana iş için istiyor ancak bunları düzenleyebilirsiniz. Bkz: [Visual Studio'da pencere düzenlerini özelleştirme](../ide/customizing-window-layouts-in-visual-studio.md) genel yönergeler için.

## <a name="open-in-excel-or-other-csv-capable-application"></a>Excel'de Aç (veya başka CSV özellikli bir uygulama)

Daha fazla işleme ve analizi için sık sık oturum değişkenleri CSV'ye dışarı aktarmak yararlıdır. Dışarı aktarma küçük Excel simge ile yapılır (![Excel dışarı aktarma simgesine](media/variable-explorer-excel-icon.png)) her düğüme değişken Gezgini'nde veya öğeyi sağ tıklatıp seçerek yanındaki **CSV uygulamasında açık**. Simgesini seçerek Yazar verileri yeni bir CSV dosyasına `%userprofile%\Documents\RTVS_CSV_Exports` klasörünü ve ardından başlatır ne olursa olsun uygulamada açılır bu dosyayı ilişkili olduğu `.csv` uzantısı.

## <a name="scopes"></a>Kapsamları

Varsayılan olarak, genel kapsam değişken Gezgini'ni açar. Pencerenin üstündeki açılan bir paket seçerek bir paket kapsamına geçiş yapabilirsiniz.

![Bir paket kapsamı gösteren değişken Gezgini](media/variable-explorer-package-scopes.png)

Hata ayıklayıcı (değişken Explorer otomatik olarak ayıklanacak kod işlevi kapsamını geçiş yapmaz unutmayın) bir kesme noktasında durduğunda işlevi kapsama geçebilirsiniz:

![Hata ayıklama sırasında veri çerçevesi gösteren değişken Gezgini](media/variable-explorer-as-locals-window.png)

Yerel değişkenler bir işlevde gösteren ayıklayıcısında kod adım adım olarak değişken Explorer işlev kapsamı otomatik olarak değişir.

## <a name="importing-data-into-variable-explorer"></a>Değişken Explorer'a veri alma

İki komutları değişken Explorer araç çubuğunda, ayrıca aracılığıyla kullanılabilen **R Araçlar > veri** menüsünde alma dış CSV kümelerine R oturumunuz: **Web URL'si R oturumundan içeri aktarma kümesine** ve **alma Dataset R oturumuna metin dosyasından**. 

İçeri aktarmak için CSV dosyası tanımladıktan sonra Visual Studio görüntüler bir **alma Dataset** o veri dosyasını nasıl ayrıştırılır denetlemek için seçenekleri sahip iletişim (diğer bir deyişle, alan ayırıcı nedir ve tırnak işaretleri nasıl ele alınacağını). Aynı zamanda içeri aktarılan veri çerçevesi ve özgün veri dosyası önizlemesini görebilirsiniz:

![İçeri aktarma dataset iletişim kutusu](media/variable-explorer-import-dataset-dialog.png)
