---
title: "Nasıl yapılır: Visual Studio'da bir yük testi sonuçları deposunu seçme | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
f1_keywords:
- vs.test.load.dialog.connectstringmissing
- vs.test.load.dialog.databaseconnectstring
helpviewer_keywords:
- load tests, results repository
- results, load test
- load test results, repository
- Load Test Results Repository
- SQL, Load Test Results Store
ms.assetid: fa0c4dd9-612f-4a57-b8eb-458f129d9cda
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: a85606196b701f98e8fb65b4e92b3896ef7a6b2c
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-select-a-load-test-results-repository"></a>Nasıl yapılır: Yük Testi Sonuçları Deposunu Seçme

Bir yerel sonuçları deposu sınırlı değildir. Genellikle, yük testleri Aracı bilgisayarların uzaktan kümesine göre çalıştırılır. Bir denetleyici birlikte aracıları tek bir bilgisayardan daha fazla benzetilmiş yük oluşturabilir. Daha fazla bilgi için bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).

Test sonuçlarından aracılarınızı veya yerel bilgisayarınıza bir yük testi sonuçları deposu oluşturmuş olduğunuz herhangi bir SQL sunucusuna kaydedilebilir. Her iki durumda da Test Denetleyicilerini Yönetme penceresini kullanarak yük testi sonuçlarını depolamak istediğiniz tanımlamanız gerekir.

Aracıları hakkında daha fazla bilgi için bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).

## <a name="identify-a-results-store-for-load-test-data"></a>Yük testi verileri için bir sonuç deposu tanımlayın

1.  İçinde **Çözüm Gezgini**, yük testi dosyasını açın.

2.  Gelen **yük testi** araç seçin **Test Denetleyicilerini Yönet**. Test denetleyicisi Yönet iletişim kutusu görüntülenir. Aracıyı uzaktan kullanıyorsanız, bir denetleyici seçmelisiniz.

     ![Yük testi sonuçları deposunu bağlantı özelliklerini](../test/media/loadtestconnectionproperties.png "LoadTestConnectionProperties") yük testi sonuçları deposunu bağlantı özellikleri

3.  İçinde **Yük Testi Sonuçları Deposu**, (...) görüntülemek için tıklatın **bağlantı özelliklerini** iletişim kutusu.

4.  İçinde **sunucu adı**, çalıştırdığınız sunucunun adını yazın `LoadTest` komut dosyaları.

    > [!TIP]
    > Yük testi deposu için yerel makinenizde SQL Express kullanıyorsanız girin \<bilgisayaradı > \sqlexpress (örneğin, **MyComputer\sqlexpress**).

5.  Altında **sunucuda oturum açın**, seçebileceğiniz **Windows kimlik doğrulamasını kullan**. Kullanıcı adı ve parola belirtebilirsiniz, ancak bunu yaparsanız, seçeneğini belirlemeniz **parolamı Kaydet**.

6.  Altında **veritabanına bağlan**, seçin **seçin veya bir veritabanı adı girin**. Seçin **LoadTest** aşağı açılan liste kutusundan.

7.  Seçin **Tamam**. Seçerek bağlantıyı test edebilirsiniz **Bağlantıyı Sına**.

8.  Seçin **Kapat** içinde **yönetmek Test denetleyicisi** iletişim kutusu.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçları havuzu yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md)