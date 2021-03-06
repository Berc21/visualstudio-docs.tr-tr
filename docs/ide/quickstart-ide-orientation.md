---
title: Visual Studio IDE turu | Microsoft Docs
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 66ff5933a1a3e2623df706f0f3e7446e750f173b
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="quickstart-first-look-at-the-visual-studio-ide"></a>Hızlı Başlangıç: Visual Studio IDE ilk bakış

Bu 5-10 dakikalık bir giriş Visual Studio tümleşik geliştirme ortamı (IDE), biz bazı windows, menüleri ve diğer kullanıcı Arabirimi özelliklerini gezin.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) ücretsiz yüklemek için sayfa.

## <a name="start-page"></a>Başlangıç Sayfası

Visual Studio'yu başlattıktan sonra göreceğiniz ilk büyük olasılıkla başlangıç sayfası şeydir. Başlangıç sayfası, proje dosyalarını daha hızlı gerekir ve komutları bulmanıza yardımcı olmak için "hub" olarak tasarlanmıştır. **Son** bölümünde projeleri ve klasörleri, çalıştığınız üzerinde yakın zamanda görüntülenir. Altında **yeni proje**, yeni proje iletişim kutusu çağrılırken veya altında bir bağlantıyı tıklatabilirsiniz **açmak**, varolan bir projeyi veya kod klasörünü açın. Sağ tarafta bir akış son geliştirici Haberler ' dir.

![VS başlangıç sayfası](media/quickstart-IDE-start-page.png)

Başlangıç sayfası ve yeniden görmek isterseniz kapatırsanız, ondan yeniden açabilirsiniz **dosya** menüsü.

![Dosya menüsü](media/quickstart-IDE-file-menu-large.png)

IDE keşfetmeye devam etmek için yeni bir proje oluşturalım.

1. Üzerinde **başlangıç sayfası**, arama kutusuna altında **yeni proje**, girin `console` proje türleri listesini filtrelemek için. Bir C# veya VB seçin **konsol uygulaması (.NET Framework)**. (C++, Javascript veya diğer dil Geliştirici varsa, alternatif olarak, bu dillerden birinde bir proje oluşturmak çekinmeyin. Biz bakarak UI tüm diller için benzer.)

1. İçinde **yeni proje** iletişim kutusunda, varsayılan proje adı kabul edin ve seçin **Tamam**.

   Proje oluşturulur ve bir dosya adlı **Program.cs** veya **Program.vb** açılır **Düzenleyicisi** penceresi. Düzenleyici dosyaların içeriğini gösterir ve kodlama çalışmanızı Visual Studio'da çoğunu burada gerçekleştirirsiniz.

## <a name="solution-explorer"></a>Çözüm Gezgini

Çözüm Gezgini proje, çözüm veya kod klasörü içinde dosya ve klasörleri hiyerarşisini grafik gösterimi gösterir. Hiyerarşi göz atın ve Çözüm Gezgini'nde bir dosyaya gidin.

![Çözüm Gezgini](media/quickstart-IDE-solution-explorer.png)

## <a name="menus"></a>Menüler

Menü çubuğu üstünde IDE komutları kategoriler halinde gruplandırır. Örneğin, **proje** menüsü içinde çalışırken projeyle ilgili komutları içerir. Üzerinde **Araçları** menüsünde seçerek IDE özelleştirebilirsiniz **seçenekleri**, veya özelliklerini seçerek yüklemenize ekleyin **alma araçları ve özelliklerinin...** .

![Menü çubuğu](media/quickstart-IDE-menu-bar.png)

Hata Listesi penceresini seçerek açalım **Görünüm** menüsünde ve ardından **hata listesi**.

## <a name="error-list"></a>Hata Listesi

Hata listesi hataları, uyarı ve kodunuzu geçerli durumu ile ilgili iletileri gösterir. Dosyanızda veya herhangi bir projenizdeki hataları (örneğin, bir sözdizimi yazım hatası) varsa, burada listelenir.

![Hata Listesi](media/quickstart-IDE-error-list.png)

## <a name="output-window"></a>Çıktı penceresi

Derleme ve kaynak denetimi iletileri çıktı çıkış penceresi şunu gösterir.

Şimdi bazı çıktı günlüğünü görmek için projeyi oluşturun. Gelen **yapı** menüsünde seçin **yapı çözümü**. Çıktı penceresi otomatik olarak odağı alır ve başarılı yapı iletisini görüntüler.

![Çıktı Penceresi](media/quickstart-IDE-output.png)

## <a name="quick-launch"></a>Hızlı Başlat

Hızlı Başlatma kutusu kadar her şeyi IDE pretty için hızlı ve kolay bir yoludur. Yapmak istediğiniz ilgili bazı metinleri girin ve onu metne ait seçeneklerin bir listesini göstereceğiz. Örneğin, hakkında tam olarak yapı yaptığını ek günlük bilgileri görüntülemek için yapı çıkış ayrıntı düzeyini artırmak istiyoruz varsayalım:

1. Girin `verbosity` içine **hızlı başlatma** kutusuna ve ardından **projeler ve çözümler oluşturma ve çalıştırma ->** altında **seçenekleri** kategorisi.

   ![Hızlı Başlatma kutusu](media/quickstart-IDE-quick-launch.png)

   **Seçenekleri** iletişim kutusu açılır **derleme ve çalıştırma** seçenekler sayfası.

1. Altında **MSBuild Proje yapı çıktı ayrıntı**, seçin **Normal**ve ardından **Tamam**.

1. Biz projeyi yeniden üzerinde sağ tıklayarak oluşturmak artık **ConsoleApp1** proje **Çözüm Gezgini**ve seçme **yeniden** ve bağlam menüsünden.

   Bu zaman hangi dosyaları dahil olmak üzere where kopyalanan çıktı penceresi oluşturma işleminden daha ayrıntılı günlük kaydını gösterir.

## <a name="send-feedback-menu"></a>Geri bildirim menü Gönder

Herhangi bir sorun, Visual Studio kullanıyorsanız ya da ürünü geliştirmemize ilgili öneriler varsa, kullanabileceğiniz karşılaşmamanız gerekir **geri bildirim gönder** hızlı başlatma kutusunun yanında IDE üstündeki menü.

![Geri bildirim menü Gönder](media/quickstart-IDE-send-feedback.png)

## <a name="next-steps"></a>Sonraki adımlar

İnceledik kullanıcı arabirimiyle tanıyalım için Visual Studio IDE özelliklerinin birkaçı. Daha fazlasını keşfetmek için:

- Windows hakkında daha fazla derinliği gibi girmeyeceğini VS belgelerine genel kullanıcı arabirimi öğeleri bölümünü Gözat [hata listesi](../ide/reference/error-list-window.md), [çıktı penceresi](../ide/reference/output-window.md), [Özellikler penceresini](../ide/reference/properties-window.md), ve [Seçenekler iletişim kutusu](../ide/reference/options-dialog-box-visual-studio.md)

- Daha ayrıntılı IDE gezin ve hatta hata ayıklama, buna dabble [Visual Studio IDE genel bakış](../ide/visual-studio-ide.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Hızlı Başlangıç: IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md)
- [Hızlı Başlangıç: düzenleyicide kodlama](../ide/quickstart-editor.md)
- [Hızlı Başlangıç: Projeler ve çözümler](../ide/quickstart-projects-solutions.md)
