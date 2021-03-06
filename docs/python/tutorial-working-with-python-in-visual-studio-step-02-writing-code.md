---
title: Yazma ve çalıştırma kodu 2. adım, Python ile çalışma | Microsoft Docs
description: Adım 2 Python düzenleyin ve ardında, Visual Studio'nun düzenleme ve IntelliSense özellikleri gösteren daha ilginç koduyla basit bir Hello World program çalıştırma kapsayan Visual Studio içinde çalışmak için bir çekirdek öğretici olması gerekir.
ms.custom: mvc
ms.date: 01/16/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 6045b385754eebfe7b754b9d213f860a199b1824
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="step-2-writing-and-running-code"></a>2. adım: Yazma ve kodu çalıştırma

**Önceki adımda: [yeni bir Python projesi oluşturma](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)**

Çözüm Gezgini proje dosyalarını yöneteceğiniz olsa *Düzenleyicisi* penceredir genellikle birlikte çalıştığınız *içeriği* gibi kaynak kodu dosyaları. Düzenleyici bağlam düzenlediğiniz, programlama dili (dosya uzantısına göre) dahil olmak üzere dosyanın türü farkındadır ve teklifleri özellikleri uygun söz dizimi renklendirme ve otomatik tamamlama gibi o dil için IntelliSense kullanma.

1. Yeni bir "Python uygulama" projesi oluşturduktan sonra varsayılan boş adlı dosya `PythonApplication1.py` Visual Studio düzenleyicisinde açıktır.

1. Düzenleyicide yazmaya başlayın `print("Hello, Visual Studio")` ve Visual Studio IntelliSense otomatik tamamlama seçenekleri yol boyunca nasıl görüntülendiğine dikkat edin. Anahatları belirlenmiş aşağı açılan listesinde SEKME tuşuna bastığınızda, kullanılan varsayılan tamamlama seçenektir. Tamamlamalar en uzun deyimleri veya tanımlayıcıları söz konusu olduğunda faydalıdır.

    ![IntelliSense otomatik tamamlama açılır](media/vs-getting-started-python-04-IntelliSense1b.png)

1. IntelliSense, kullanmakta olduğunuz deyimi, aradığınız işlevi ve benzeri bağlı olarak farklı bilgiler gösterir. İle `print` işlev, yazarak `(` sonra `print` çağrısı bir işlev belirtmek için bu işlevi tam kullanım bilgilerini görüntüler. Açılır IntelliSense, geçerli bağımsız değişkeni de kalın olarak gösterilir. (**değeri** aşağıda gösterildiği gibi):

    ![Bir işlev için IntelliSense otomatik tamamlama açılır](media/vs-getting-started-python-05-IntelliSense2b.png)

1. Aşağıdaki eşleşecek şekilde deyimi tamamlayın:

    ```python
    print("Hello, Visual Studio")
    ```

1. Deyim ayıran sözdizimi coloration fark `print` bağımsız gelen `"Hello Visual Studio"`. Ayrıca, geçici olarak son silme `"` dize ve bildirim sözdizimi hataları içeren nasıl Visual Studio kırmızı bir alt çizgi kod için gösterir. Yerine `"` kodu düzeltmek için.

    ![IntelliSense söz dizimi renklendirme ve hata vurgulama](media/vs-getting-started-python-06-IntelliSense3b.png)

    > [!Tip]
    > Birinin geliştirme ortamı çok kişisel sağlasa da olduğundan, Visual Studio, Visual Studio'nun görünümü ve davranışı üzerinde tam denetim sağlar. Seçin **Araçlar > Seçenekleri** menü komut ve ayarları altında keşfetme **ortam** ve **metin düzenleyici** sekmeleri. Varsayılan olarak, yalnızca sınırlı sayıda seçenek görürsünüz; her programlama dili için her seçeneği görmek için seçin **tüm ayarları göster** iletişim kutusunun altındaki. 

1. Yazılan bu noktada Ctrl + F5 tuşuna basarak veya seçerek kodu çalıştırma **hata ayıklama > hata ayıklama olmadan Başlat** menü öğesi. Visual Studio, kodunuzda hataları hala olup olmadığını sizi uyarır.

1. Çalıştırdığınızda program sonuçlarını görüntüleyen bir konsol penceresi görünür bir Python yorumlayıcısı ile Çalıştır sanki `PythonApplication1.py` komut satırından. Pencereyi kapatmak ve Visual Studio Düzenleyicisi'ne dönmek için bir tuşa basın.

    ![Program ilk çalışması için çıktı](media/vs-getting-started-python-07-output.png)

1. İfadeler ve işlevleri için tamamlamalar yanı sıra, IntelliSense sağlamak tamamlamalar Python için `import` ve `from` deyimleri. Bu tamamlamalar hangi modüllerin ortamınıza ve bu modüller üyeleri kullanılabilen kolay bulmasına yardımcı olur. Düzenleyicisi'nde silin `print` satır ve yazmaya başlayın `import `. Alanı yazdığınızda modüller listesi görüntülenir:

    ![İçeri aktarma deyimi için kullanılabilir modülleri gösteren IntellSense](media/vs-getting-started-python-08-import1.png)

1. Yazarak veya seçerek satır tamamlamak `sys`.

1. Sonraki satıra yazın `from` yeniden modüllerin listesini görmek için:

    ![Kullanılabilir modülleri için gösteren IntellSense bir deyim gelen](media/vs-getting-started-python-09-import2.png)

1. Seçin veya yazın `math`, boşlukla yazmaya devam ve `import`, modül üyeleri görüntüler:

    ![IntellSense gösteren modülü üyeleri](media/vs-getting-started-python-10-import3.png)

1. Son içeri aktararak `sin`, `cos`, ve `radians` otomatik-tamamlamalar kullanılabilir her biri için haberiniz bile üyeleri. İşiniz bittiğinde, kodunuzu aşağıdaki gibi görünmelidir:

    ```python
    import sys
    from math import cos, radians
    ```

    > [!Tip]
    > Sözcükler, harf sözcükleri başındaki bölümlerini eşleşen yazın ve hatta karakter atlandı tamamlamalar alt dizeler ile çalışır. Bkz: [kod - tamamlamalar düzenleme](editing-python-code-in-visual-studio.md#completions) Ayrıntılar için.

1. 360 derece kosinüsünü değerlerini yazdırmak için biraz daha fazla kodu ekleyin:

    ```python
    for i in range(360):
        print(cos(radians(i)))
    ```

1. Ctrl + F5'e programı yeniden çalıştırın veya **hata ayıklama > hata ayıklama olmadan Başlat**. İşiniz bittiğinde çıktı penceresini kapatın.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Etkileşimli REPL penceresini kullanma](tutorial-working-with-python-in-visual-studio-step-03-interactive-repl.md)

## <a name="going-deeper"></a>Daha derin gitme

- [Kodu düzenleme](editing-python-code-in-visual-studio.md)
- [Kodu biçimlendirme](formatting-python-code.md)
- [Kodu yeniden düzenleme](refactoring-python-code.md)
- [PyLint Kullanma](linting-python-code.md)
