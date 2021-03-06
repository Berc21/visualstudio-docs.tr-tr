---
title: "Hızlı Başlangıç: İlk Python web uygulamanızı oluşturmak için Visual Studio'yu kullanın. | Microsoft Docs"
description: Bu hızlı başlangıç bir Python Flask framework kullanarak basit bir web uygulamasını oluşturmak için Visual Studio kullanın.
ms.custom: mvc
ms.date: 03/21/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: quickstart
dev_langs:
- python
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 71501e113bc744f430c6935dbf20bfd2ec533758
ms.sourcegitcommit: 064f8678f4a918e1dce60285090a9803d37dc34b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/30/2018
---
# <a name="quickstart-use-visual-studio-to-create-your-first-python-web-app"></a>Hızlı Başlangıç: Kullanım ilk Python web uygulamanızı oluşturmak için Visual Studio

Bu 5-10 dakikalık bir giriş bir Python IDE olarak Visual Studio, Flask Framework'e dayalı basit bir Python web uygulaması oluşturun. Ayrık üzerinden proje oluşturma yardımcı adımları Visual Studio'nun temel özellikleri hakkında bilgi edinin.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) ücretsiz yüklemek için. Yükleyicisi'nde seçtiğinizden emin olun **Python geliştirme** iş yükü.

## <a name="create-the-project"></a>Projeyi oluşturma

Aşağıdaki adımları boş bir oluşturma *proje* , uygulama için bir kapsayıcı olarak görev yapar:

1. Visual Studio 2017'ni açın.

1. Üst menü çubuğundan seçin **Dosya > Yeni > Proje...** .

1. İçinde **yeni proje** iletişim kutusunda, üst sağ taraftaki arama alanı "Python Web projesi" girin, seçin **Web projesi** Orta listesinde, proje "HelloPython" gibi bir ad verin ve ardından **Tamam**.

    ![Python Web Seçili proje ile yeni proje iletişim kutusu](media/quickstart-python-00-web-project.png)

    İşyeri dışında Python proje şablonları görmüyorsanız, İptal **yeni proje** iletişim kutusuna ve üst menü çubuğundan seçin **Araçlar > alma araçları ve özelliklerinin...**  Visual Studio yükleyicisi açın. Seçin **Python geliştirme** iş yükü, ardından **Değiştir**.

    ![Visual Studio yükleyicisi Python geliştirme iş yükü](../python/media/installation-python-workload.png)

1. Yeni Proje açılır **Çözüm Gezgini** sağ bölmede. Proje, bu noktada, diğer bir dosyaları içerdiği için boştur.

    ![Yeni oluşturulan boş proje gösteren Çözüm Gezgini](media/quickstart-python-01-empty-project.png)

**Soru: Visual Studio için Python uygulama projesi oluşturma avantajı nedir?**

**Yanıt**: Python uygulamalar, yalnızca dosya ve klasörleri kullanılarak tipik olarak tanımlanır, ancak uygulamalar daha büyük hale ve belki de JavaScript web uygulamaları için otomatik olarak oluşturulan dosyaları içeren vb. gibi bu basit bir yapıya sıkıcı olabilir. Visual Studio projesi bu karışıklığı yönetmenize yardımcı olur. Proje (bir `.pyproj` dosyası) kaynak ve projenizi ile ilişkili içerik dosyalarını tanımlar, her dosya için yapı bilgileri içerir, kaynak denetimi sistemleriyle tümleştirmeyi bilgilerini korur ve uygulamanızı düzenlemenize yardımcı olur mantıksal bileşenlerine.

**Soru: "Çözüm" nedir Çözüm Gezgini'nde gösterilen?**

**Yanıt**: bir Visual Studio *çözüm* grup olarak bir veya daha fazla ilgili projelerde yönetmenize yardımcı olan bir kapsayıcı ve projeye özel olmayan yapılandırma ayarları depolar. Bir çözümde proje de birbirine başvurabilir, sağlayacak şekilde bir proje çalıştıran (Python uygulaması) otomatik olarak (örneğin, Python uygulamada kullanılan C++ uzantısı) ikinci bir proje oluşturur.

## <a name="install-the-flask-library"></a>Flask kitaplığını yükle

Web uygulamalarında Python neredeyse her zaman birçok kullanılabilir Python kitaplıklarından birini yönlendirme web isteklerini ve yanıtlarını şekillendirme gibi alt düzey ayrıntıların işlemek için kullanır. Bu amaç için Visual Studio çeşitli sağlayan *şablonları* web uygulamaları, bunlardan biri daha sonra bu hızlı başlangıcı kullanırsınız.

Burada, "Bu proje için Visual Studio kullanan varsayılan genel ortama" Flask Kitaplığı'nı yüklemek için aşağıdaki adımları kullanın.

1. Genişletme **Python ortamları** proje için varsayılan ortamı görmek için proje düğümünde.

    ![Varsayılan ortam gösteren Çözüm Gezgini](media/quickstart-python-02-default-environment.png)

1. Ortam sağ tıklatıp **Python paketini yükle...** . Bu komut açar **Python ortamları** penceresinde **paketleri** sekmesi.

1. Arama alanına "flask" girin ve **PIP flask Pypı yüklemek**. Sizden yönetici ayrıcalıkları kabul edin ve gözlemlemek **çıkış** ilerleme için Visual Studio penceresinde. (Bir istem genel ortam için paketler klasörü korumalı alanı içinde bulunduğu yükseltme gerçekleşir ister `c:\program files`.)

    ![Flask kitaplığı yükleme](media/quickstart-python-03-install-package.png)

1. Bir kez yüklendikten sonra ortamında kitaplık görünür **Çözüm Gezgini**, yapabileceğiniz anlamına bunu Python kodu kullanın.

    ![Yüklü flask kitaplığı](media/quickstart-python-04-package-installed.png)

> [!Note]
> Kitaplıkları genel ortamında yüklemek yerine, geliştiriciler genellikle "sanal ortam" belirli bir proje için kitaplıkları yükleneceği oluşturun. Visual Studio şablonları anlatıldığı gibi bu seçenek, genellikle teklif [hızlı başlangıç - bir şablonu kullanarak bir Python projesi oluşturma](../python/quickstart-02-python-in-visual-studio-project-from-template.md).

**Soru: Burada diğer kullanılabilir Python paketlerini hakkında daha fazla bilgi edinebilirim?**

**Yanıt**: ziyaret [Python paket dizini](https://pypi.python.org/pypi) (pypi.python.org).

## <a name="add-a-code-file"></a>Bir kod dosyası ekleme

Artık bir en az bir web uygulaması uygulamak için Python kodu biraz eklemek hazırsınız.

1. ' Nde projeye sağ **Çözüm Gezgini** seçip **Ekle > Yeni öğe...** .

1. Görüntülenen iletişim kutusunda, seçin **boş Python dosyası**, adlandırın `app.py`seçip **Ekle**. Visual Studio dosya Düzenleyicisi penceresinde otomatik olarak açılır.

1. Aşağıdaki kodu kopyalayın ve yapıştırın `app.py`:

    ```python
    from flask import Flask

    # Create an instance of the Flask class that is the WSGI application.
    # The first argument is the name of the application module or package,
    # typically __name__ when using a single module.
    app = Flask(__name__)

    # Flask route decorators map / and /hello to the hello function.
    # To add other resources, create functions that generate the page contents
    # and add decorators to define the appropriate resource locators for them.

    @app.route('/')
    @app.route('/hello')
    def hello():
        # Render the page
        return "Hello Python!"

    if __name__ == '__main__':
        # Run the app server on localhost:4449
        app.run('localhost', 4449)
    ```

1. Fark etmiş **Ekle > Yeni öğe...**  diğer türlerde dosyaları Python sınıfı, bir Python paket, Python birim testi, web.config dosyaları ve daha da dahil olmak üzere bir Python projesine Ekle iletişim kutusu görüntüler. Genel olarak, bunlar *öğe şablonlarını*adlı gibi hızlı bir şekilde yararlı Demirbaş kod ile dosyaları oluşturmak için harika bir yoludur.

**Soru: Burada Flask hakkında daha fazla bilgi edinebilirim?**

**Yanıt**: başlayarak Flask belgelerine başvurun [Flask Quickstart](https://flask.pocoo.org/docs/0.12/quickstart/) (flask.pocoo.org).

## <a name="run-the-application"></a>Uygulamayı çalıştırın

1. Sağ `app.py` içinde **Çözüm Gezgini** seçip **başlangıç dosyası olarak ayarlamak**. Bu komut, uygulama çalışırken Python içinde başlatmak için kod dosyası tanımlar.

    ![Çözüm Gezgini'nde proje için başlangıç dosyası ayarı](media/quickstart-python-05-set-as-startup-file.png)

1. ' Nde projeye sağ **Çözüm Gezgini** seçip **özellikleri**. Ardından **hata ayıklama** sekmesinde ve ayarlama **bağlantı noktası numarası** özelliğine `4449`. Bu adım, Visual Studio bir tarayıcı ile başlatır sağlar `localhost:4449` eşleşecek şekilde `app.run` kodu bağımsız değişkenler.

1. Seçin **hata ayıklama > hata ayıklama olmadan Başlat** (Ctrl + F5), dosyalarına değişiklikleri kaydeder ve uygulamayı çalıştırır.

1. İletinin bir komut penceresi görünür "* çalışan https://localhost:4449/", ve bir tarayıcı penceresi açın `localhost:4449` iletisini görürseniz burada "Hello, Python!" GET isteğini ayrıca 200 durumuyla komut penceresinde görünür.

    Bir tarayıcı otomatik olarak açılmazsa, tercih ettiğiniz tarayıcıyı başlatın ve gidin `localhost:4449`.

    Yalnızca Python etkileşimli Kabuk komut penceresinde görürseniz, bu pencereyi kısaca ekranda yanıp sönen varsa, ayarladığınız emin olun veya `app.py` yukarıdaki 1. adımda başlangıç dosyası olarak.

1. Gidin `localhost:4449/hello` , test etmek için oluşturma öğesi `/hello` kaynak de çalışır. Yeniden GET isteğini 200 durumuyla komut penceresinde görüntülenir. 404 durum kodları komut penceresinde Göster görmek için bazı diğer URL de denemek çekinmeyin.

1. Uygulama durdurmak için komut penceresini kapatın, sonra da tarayıcı penceresini kapatın.

**Soru: Hata ayıklama olmadan Başlat komutu ve hata ayıklamayı Başlat arasındaki fark nedir?**

**Yanıt**: kullandığınız **hata ayıklamayı Başlat** bağlamında uygulamayı çalıştırmak için [Visual Studio hata ayıklayıcısı](../python/debugging-python-in-visual-studio.md), kesme noktaları ayarlamanıza olanak veren, değişkenleri inceleyin ve adım kodunuzu satır. Uygulamalar, hata ayıklama mümkün kılar çeşitli kancaları nedeniyle hata ayıklayıcısı'ndaki daha yavaş çalışabilir. **Hata ayıklama olmadan Başlat**, buna karşılık, komut satırından hiçbir hata ayıklama bağlamına sahip çalıştırdıysanız gibi uygulama doğrudan çalışır ve aynı zamanda otomatik olarak bir tarayıcı ile Proje Özellikleri'nde belirtilen URL başlatarak  **Hata ayıklama** sekmesi.

## <a name="next-steps"></a>Sonraki adımlar

Hangi bir Python IDE Visual Studio kullanma hakkında biraz öğrendiğinize ilk Python uygulamanızı Visual Studio'dan içinde çalışan Tebrikler!

Bu hızlı başlangıcı ve ardından adımları oldukça genel olduğundan, bunlar olabilir ve otomatikleştirilmesi gereken büyük olasılıkla tahmin. Bu tür Otomasyon Visual Studio rolüdür *proje şablonlarını*. Bir web uygulaması, bu makalede, ancak daha az adım ile oluşturduğunuz bir benzer oluşturur bir örnek aşağıda düğmesini seçin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç - bir şablonu kullanarak bir Python projesi oluşturma](../python/quickstart-02-python-in-visual-studio-project-from-template.md)

Visual Studio'da etkileşimli penceresini kullanarak da dahil olmak üzere, veri görselleştirme, hata ayıklama ve Git ile çalışma, Python daha eksiksiz bir öğretici devam etmek için aşağıdaki düğmesini seçin.

> [!div class="nextstepaction"]
> [Öğretici: Visual Studio'da Python ile çalışmaya başlama](../python/tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

Visual Studio sunmak olan daha keşfetmek için aşağıdaki bağlantıları seçin.

- Hakkında bilgi edinin [Python web uygulaması şablonları Visual Studio'da](../python/python-web-application-project-templates.md).
- Hakkında bilgi edinin [Python hata ayıklama](../python/debugging-python-in-visual-studio.md)
- Daha fazla bilgi edinmek [Visual Studio IDE](../ide/visual-studio-ide.md) genel.
