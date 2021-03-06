---
title: Seçenekler ve ayarlar Python için | Microsoft Docs
description: Visual Studio'da Python kodu ve projeler ile ilgili çeşitli ayarlar için bir başvuru.
ms.custom: ''
ms.date: 03/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Python_Tools
- VS.ToolsOptionsPages.Python_Tools.General
- VS.ToolsOptionsPages.Python_Tools.Debugging
- VS.ToolsOptionsPages.Python_Tools.Diagnostics
- VS.ToolsOptionsPages.Python_Tools.Experimental
- VS.ToolsOptionsPages.Python_Tools.Interactive_Windows
- VS.ToolsOptionsPages.Text_Editor.Python.Advanced
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 71c6e3424d93af2b3696f19193498ed6940cbc7a
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="options-for-python-in-visual-studio"></a>Visual Studio'da Python için seçenekleri

Python seçenekleri görüntülemek için kullanın **Araçlar > Seçenekler** menü komutu, emin olun **tüm ayarları göster** seçilir ve ardından gidin **Python Araçları**:

![Python Seçenekleri iletişim kutusu, Genel sekmesi](media/options-general.png)

Vardır ayrıca Python özgü ek seçenekler **metin düzenleyicisi > Python > Gelişmiş** sekmesinde ve **ortam > yazı tiplerini ve renkleri** "metin düzenleyici" grubu sekmede.

> [!Note]
> **Experimental** grubu özellikleri hala geliştirilmektedir ve burada belgelenmemiş seçenekleri içerir. Bunlar genellikle gönderilerde üzerinde ele alınan [Microsoft blogu Python mühendislik](https://blogs.msdn.microsoft.com/pythonengineering/).

## <a name="general-options"></a>Genel seçenekleri

(**Araçlar > Seçenekler > Python** sekmesi.)

| Seçenek | Varsayılan | Açıklama |
| --- | --- | --- |
| Sanal ortamlar oluştururken çıktı penceresini göster| Açık | Çıktı penceresi görünmesini engellemek için işaretini kaldırın. |
| Çıkış yüklerken veya paketlerini kaldırma penceresini göster | Açık | Çıktı penceresi görünmesini engellemek için işaretini kaldırın. |
| Her zaman PIP yönetici olarak çalıştır | Kapalı | Her zaman yükseltir `pip install` işlemleri tüm ortamlar için. Ortam korumalı bir dosya sistemi bölümünde gibi bulunuyorsa paketleri yüklerken, Visual Studio için yönetici ayrıcalıkları ister `c:\Program Files`. Her zaman yükseltmesine seçebilirsiniz, istemindeki `pip install` bir bu ortam için. Bkz: [Paketleri sekmesi](python-environments-window-tab-reference.md#packages-tab). |
| Tamamlama DB ilk kullanımında otomatik olarak oluştur | Açık | *Visual Studio 2017 sürüm 15,5 ve önceki ve sonraki sürümler için IntelliSense veritabanı kullanıldığında geçerlidir.* Bunu kullanan kodu yazarken bir kitaplık veritabanı tamamlama öncelik olarak belirler. Daha fazla bilgi için bkz: [ortamları penceresi başvuru - IntelliSense sekmesini](python-environments-window-tab-reference.md). |
| Sistem genelinde PYTHONPATH değişkenleri yoksay | Açık | Visual Studio ortamları ve projeleri arama yolları belirtmek için daha doğrudan bir yol sağladığından PYTHONPATH varsayılan olarak sayılır. Bkz: [arama yolları](search-paths.md) Ayrıntılar için. |
| Bağlantılı dosyaları eklerken güncelleştirme arama yolları | Açık | Ayarlanırsa, ekleme, bir [bağlı dosya](managing-python-projects-in-visual-studio.md#linked-files) projeye güncelleştirmeleri [arama yolları](search-paths.md) böylece IntelliSense tamamlanma veritabanında bulunan bağlantılı dosyanın klasörünün içeriğini içerebilir. Bu tür içeriği tamamlama veritabanından dışlamak için bu seçeneği temizleyin. |
| Modülü bulunamıyor aktarıldığında uyar | Açık | Temizle içeri aktarılan modül bildiğinizde uyarıları gizlemek için bu seçeneği şu anda kullanılabilir değil ancak Aksi halde kodu işlemi etkilemez. |
| Rapor tutarsız girinti olarak | Uyarılar | Python yorumlayıcı kapsamını belirlemek için uygun girinti yoğun bir şekilde bağlı olduğundan, varsayılan olarak Visual Studio kodlama hataları gösterebilir tutarsız girintileri algıladığında uyarılar verir. Kümesine *hataları* daha katı olması için bu gibi durumlarda çıkmak program neden olur. Bu davranış tamamen devre dışı bırakmak için seçin *yok*. |
| Anket/haber denetle | Haftada bir | Ayarlar Visual Studio izin sıklığı varsa bir web sayfası Python ilgili anketler ve haber öğeleri içeren bir pencere açabilirsiniz. Seçenekler *hiçbir zaman*, *günde bir kez*, *haftada bir kez*, ve *ayda bir kez*. |
| Tüm kalıcı olarak gizli iletişim kutuları (düğme) Sıfırla | yok | Farklı iletişim kutularının sağlamak seçenekleri gibi **bunu bir daha gösterme**. Bu seçenekler temizleyin ve yeniden açmak için iletişim kutularını neden için bu düğmeyi kullanın. |

![Python Seçenekleri iletişim kutusu, Genel sekmesi](media/options-general.png)

## <a name="debugging-options"></a>Hata ayıklama seçenekleri

(**Araçlar > Seçenekler > Python > hata ayıklama** sekmesi.)

| Seçenek | Varsayılan | Açıklama |
| --- | --- | --- |
| Hataları mevcut olduğunda çalıştırmadan önce sor | Açık | Ne zaman, ister hataları içeren kodu çalıştırmak istediğinizi onaylamak için ayarlayın. Uyarıyı devre dışı bırakmak için bu seçeneği temizleyin. |
| İşlemi anormal olarak çıktığında giriş bekle<br/><br/>İşlemi normal olarak çıktığında giriş bekle | Üzerinde (her ikisi için de) | Visual Studio'dan başlatılan Python programı kendi konsol penceresinde çalışır. Varsayılan olarak, programın nasıl çıkar bağımsız olarak kapatmadan önce herhangi bir tuşa basın için pencereyi bekler. Bu istemi kaldırmak ve penceresi otomatik olarak kapatmak için ya da bu seçeneklerin ikisi de temizleyin. |
| Hata ayıklama çıktı penceresine program çıktısı t | Açık | Program çıktısı, hem ayrı konsol penceresi hem de Visual Studio çıktı penceresinde görüntüler. Çıktı yalnızca ayrı konsol penceresinde göstermek için bu seçeneği temizleyin. |
| SystemExit özel sıfır çıkış kodu ile bölün | Kapalı | Varsa ayarlayın, bu özel durum hata ayıklayıcı durdurur. Açık olduğunda, hata ayıklayıcı olmadan sonu çıkar. |
| Python standart kitaplığı hata ayıklamayı etkinleştir | Kapalı | Bu adıma standart kitaplığı kaynak kodunda hata ayıklama sırasında mümkün hale getirir, ancak başlatmak hata ayıklayıcı için geçen süreyi artırır.|

![Python Seçenekleri iletişim kutusu, hata ayıklama sekmesi](media/options-debugging.png)

## <a name="diagnostics-options"></a>Tanılama seçenekleri

(**Araçlar > Seçenekler > Python > tanılama** sekmesi.)

| Seçenek | Varsayılan | Açıklama |
| --- | --- | --- |
| Analiz günlüklerini içerir | Açık | Tanılama için Dosya kaydedilirken yüklü Python ortamları analiz için ilgili veya düğmeleri kullanarak Panoya kopyalama ayrıntılı günlükleri içerir. Bu seçenek, oluşturulan dosya boyutunu önemli ölçüde artırabilir, ancak genellikle IntelliSense sorunlarını tanılamak için gereklidir. |
| Tanılama (düğme) dosyaya kaydet | yok | İçin bir dosya adı ister ve sonra günlüğe bir metin dosyasına kaydeder. |
| Tanılama (düğme) Panoya Kopyala | yok | Günlük tamamen panoya yerleştirir; Bu işlem günlüğü boyutuna bağlı olarak biraz zaman alabilir. |

![Python Seçenekleri iletişim kutusu, Tanılama sekmesi](media/options-diagnostics.png)

## <a name="interactive-windows-options"></a>Etkileşimli Windows seçenekleri

(**Araçlar > Seçenekler > Python > Etkileşimli Windows** sekmesi.)

| Seçenek | Varsayılan | Açıklama |
| --- | --- | --- |
| Komut dosyaları | yok | Tüm ortamlar için etkileşimli windows uygulamak başlatma komut dosyaları için genel bir klasörü belirtir. Bkz: [başlatma komut dosyaları](python-environments-window-tab-reference.md#startup-scripts). Ancak, bu özellik şu anda çalışmıyor unutmayın. |
| Geçmiş okları yukarı/aşağı gidin | Açık | Etkileşimli pencere geçmişinde gezinmek için ok tuşlarını kullanır. Bunun yerine etkileşimli pencerenin çıktısı gezinmek için ok tuşlarını kullanmak için bu ayarı temizleyin. |
| Tamamlanma modu | İşlev çağrıları olmadan ifadeleri yalnızca değerlendir | Bir ifade etkileşimli penceresinde kullanılabilir üyeler belirleme işlemi yan etkileri veya birden çok kez çağrılan işlevleri neden olabilecek geçerli tamamlanmamış ifade değerlendirme gerektirebilir. Varsayılan ayar *yalnızca işlev çağrılarını olmadan ifadeleri değerlendirme* bir işlevi çağırmak için görünür, ancak diğer ifadeler değerlendirir ifadeleri dışlar. Örneğin, değerlendirir `a.b` ama `a().b`.  *Hiçbir zaman ifadeleri değerlendirme* tüm yan önerileri için yalnızca normal IntelliSense altyapısını kullanarak etkileri, engeller. *Tüm ifadeler değerlendirmek* yan etkileri bakılmaksızın önerileri almak için tam ifadeyi hesaplar. |
| Statik çözümleme önerileri Gizle | Kapalı | Ayarlandığında, ifadesinin hesaplanmasıyla elde edilen yalnızca önerileri görüntüler. Tamamlanma modu ile birleştirildiğinde *hiçbir zaman ifadeleri değerlendirme*, hiçbir yararlı tamamlamalar etkileşimli penceresinde görünür. |

![Python Seçenekleri iletişim kutusu, etkileşimli Windows sekmesi](media/options-interactive-windows.png)

## <a name="advanced-python-editor-options"></a>Gelişmiş Python Düzenleyici Seçenekleri

(**Araçlar > Seçenekler > Metin Düzenleyicisi > Python > Gelişmiş** sekmesi.)

### <a name="completion-results"></a>Tamamlama sonuçları

| Seçenek | Varsayılan | Açıklama |
| --- | --- | --- |
| Üye tamamlama üyeleri kesişimi görüntüler | Kapalı | Ayarlandığında, tüm olası türleri tarafından desteklenen tek tamamlamalar gösterir. |
| Arama dizesine dayalı filtre listesi | Açık | Siz yazarken tamamlama önerileri filtrelerini uygular (varsayılan işaretli). |
| Otomatik olarak tüm tanımlayıcılar için tamamlamalar Göster | Açık | Hem Düzenleyici hem de etkileşimli windows tamamlamalar devre dışı bırakmak için bu seçeneği temizleyin. |

### <a name="selection-in-completion-list"></a>Tamamlama listesindeki seçimi

| Seçenek | Varsayılan | Açıklama |
| --- | --- | --- |
| Şu karakterleri yazarak yürütüldü | `{}[]().,:;+-*/%&&#124;^~=<>#@\` | Bu karakterler tipik olarak bir karakter yazarak tamamlama yürütmek için uygun olacak şekilde, bir tamamlama listeden seçebilirsiniz tanımlayıcı izleyin. Özel karakterler istendiği listesine ekleyebilir veya kaldırabilirsiniz.  |
| İşlemeleri geçerli tamamlama girin | Açık | Ayarlandığında, Enter tuşuna seçer ve şu anda seçili tamamlama karakterlerle gibi yukarıdaki uygular (ancak doğal olarak, hiç Enter karakteri bu listeye doğrudan Git uygulanamadı şekilde!). |
| Yeni Satır Ekle üzerinde tam olarak yazılan word sonunda girin | Kapalı | Varsayılan olarak, görüntülenen tüm Word'ün tamamlama açılan kutuya yazın ve Enter tuşuna basın, tamamlama uygulayın. Tanımlayıcı yazdıktan sonra Enter yeni bir satır ekler, bu seçeneği ayarlayarak, etkili bir şekilde tamamlamalar yürüttükten. |

### <a name="miscellaneous-options"></a>Çeşitli seçenekleri

| Seçenek | Varsayılan | Açıklama |
| --- | --- | --- |
| Anahat modu dosyalarını açtığınızda girin | Açık | Otomatik olarak Visual Studio'nun anahat özelliğini Düzenleyicisi'nde bir Python kodu dosyasını açarken açın. |
| REPL istemleri Yapıştır kaldırıldı | Açık | Kaldırır >>> ve etkileşimli penceresinden kod düzenleyicisine Kolay Aktarım izin vererek... yapıştırılan metni. Başka kaynaklardan yapıştırılırken bu karakterleri silmemeniz gerekiyorsa bu seçeneği temizleyin. |
| Renk adları türlerine göre | Açık | Python kodu renklendirme sözdizimi sağlar. |

![Gelişmiş sekmesi, Python Düzenleyici Seçenekleri iletişim](media/options-editor-advanced.png)

## <a name="fonts-and-colors-options"></a>Yazı tipleri ve renkler seçenekleri

(**Ortam > yazı tiplerini ve renkleri** "metin düzenleyici" grubu sekmede.)

Python seçenekleri adlarını tüm "Python ile" öneki ve kendinden açıklamalıdır. Tüm Visual Studio renk temaları varsayılan yazı tipini 10nk Consolas normal olduğundan (kalın değil). Varsayılan renkler tema göre farklılık gösterir. Varsayılan ayarlarla metninin okunması zor bulursanız, tipik olarak, bir yazı tipi veya renk değiştirin.

![Python yazı tipi ve renk seçenekleri](media/options-fonts-and-colors.png)