---
title: "T4 metin şablonuna ilişkin hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text templates, troubleshooting
- text templates, debugging
ms.assetid: 0877fdf2-20bf-42da-b3cc-4c5856b80821
caps.latest.revision: "28"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: d60acd7d0d992ced0235d5d1e1c768f146bf4acd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="debugging-a-t4-text-template"></a>Bir T4 Metin Şablonuna İlişkin Hata Ayıklama
Metin şablonlarında kesme noktaları ayarlayabilirsiniz. Tasarım zamanı metin şablonu hata ayıklamak için metin şablonu dosyasını kaydedin ve ardından **hata ayıklama T4 şablon** Çözüm Gezgini'nde dosyasının kısayol menüsünde. Çalışma zamanı metin şablonu hata ayıklamak için basitçe ait olduğu uygulama hata ayıklama.  
  
 Metin şablonu hata ayıklamak için şablonu dönüştürme süreci adımları anlamanız gerekir. İçinde her adımı çeşitli hatalar oluşabilir. Adımlar aşağıdaki gibidir.  
  
|Adım|Tasarım zamanı şablonu: ne zaman olur|Çalışma zamanı şablonu: ne zaman olur|  
|----------|--------------------------------------------|-----------------------------------------|  
|Metin şablonundan kodu oluşturulur.<br /><br /> Yönergeleri, hatalar veya eşleşmeyen veya disordered `<#...#>` etiketler.|Olduğunda şablonu kaydetmek veya metin dönüştürmeyi çağırma.|Olduğunda şablonu kaydetmek veya metin dönüştürmeyi çağırma.|  
|Oluşturulan kod derlenir.<br /><br /> Derleme hataları şablon kodunuzda.|Hemen önceki adımdan sonra.|Uygulama kodunuz yanı sıra.|  
|Kod çalışır.<br /><br /> Şablon kodunuzda çalışma zamanı hataları.|Hemen önceki adımdan sonra.|Olduğunda, uygulamanızın çalışır ve şablonu kodu çağırır.|  
  
 Çoğu durumda, hata raporunda şablonu kodu satır numaralarını verilir. Hata raporu için geçici bir dosya adı başvurduğunda normal metin şablonu kodda eşleşmeyen köşeli ayraç nedenidir.  
  
 Metin şablonlarında kesme noktalarını ayarlayın ve her zamanki gibi hata ayıklama.  
  
## <a name="common-errors-and-fixes"></a>Yaygın hatalar ve düzeltmeler  
 Aşağıdaki tabloda, en yaygın hataları ve bunların düzeltmeleri listeler.  
  
|Hata İletisi|Açıklama|Çözüm|  
|-------------------|-----------------|--------------|  
|'{0}' temel sınıfı hangi dönüştürme sınıfının devraldığı yüklenemedi.|Belirtilen taban sınıfı bulamazsa oluşur `inherits` şablon yönergesi parametresi. İleti şablon yönergesi satır sayısını sağlar.|Belirtilen sınıf var ve içinde var. derleme bir derleme yönergesi belirtildiğinden emin olun.|  
|Çözümlenemedi file:{0 metni içeren}|Dahil edilen bir şablonu bulunamıyor oluşur. İleti istenen içeren dosyanın adı sağlar.|Dosya yolu özgün şablonu yolu göreli olduğunu veya konak ile kayıtlı bir konumda dosya olduğunu ya da dosyanın tam yolunu olduğunu unutmayın.|  
|Hatalar dönüştürme nesnesi başlatılırken oluşturuldu. Dönüştürme çalışmaz.|Dönüştürme sınıfı 'Initialize()' başarısız oldu veya yanlış döndürülen oluşur.|Belirtilen temel dönüştürme sınıfı Initialize() işlevi kodda geldiği \<#@template#> yönerge işlemcileri yönerge ve. Initialize büyük olasılıkla başarısız olmasına neden olan hata hata listesinde yer alıyor. Neden başarısız araştırın. Bir şablon hata ayıklamak için yordamları izleyerek Initialize() için gerçek oluşturulan kod bakabilirsiniz.|  
|'{0}' derlemesi yönerge işlemcisi '{1}' için FullTrust izni verilmedi. Yalnızca güvenilir derlemeler yönerge işlemcileri sağlamak için izin verilir. Bu yönerge işlemcisi yüklü değil.|Sistem yönerge işlemcisi içeren bir derleme için FullTrust izinlerini verin değil oluşur. İleti derlemenin adını ve yönerge işlemcisi adını sağlar.|Yalnızca yerel makinede güvenilir derlemeler, kullandığınızdan emin olun.|  
|'{0}' yolu, bu bilgisayar için yerel ya da güvenilen bölgesinin bir parçası olması gerekir.|Yönergesi veya derleme yönergesi yerel makinenizde değil ya da, ağınızın güvenilir bölgeye bir dosyaya başvuruda bulunan oluşur.|Yönergesi veya derleme yönergeleri bulunduğu dizin, güvenilen bir bölgede olduğundan emin olun. Ağ dizinine güvenilen bölgenizi Internet Explorer aracılığıyla ekleyebilirsiniz.|  
|"Geçersiz belirteç ' catch'" veya "bir ad alanı doğrudan üye içeremez" gibi birden çok sözdizimi hataları|Şablon kodunuzda çok fazla kapanış köşeli parantez. Derleyici, standart nesil koduyla kafa karıştırıcı değil.|Kaşlı ayraçlar kod sınırlayıcıları içinde kapatma sayısını denetleyin.|  
|Döngüler veya koşulları değil derlenmiş veya doğru bir şekilde yürütüldü. Örneğin: `<#if (i>10)#> Number is: <#= i #>`.<br /><br /> Bu kodu her zaman değeri çıkarır ediyorum. Yalnızca "sayıdır:" koşullu değil.|C# ' ta her zaman küme ayraçları denetim deyimlerinde katıştırılmış metin blokları surround için kullanın.|Küme parantezleri Ekle: `<#if (i>10) { #>    Number is: <#= i #><# } #>`.|  
|"İfade çok karmaşık" olduğunda bir tasarım zamanı şablon işleme veya bir çalışma zamanı (önceden işlenmiş) şablonu derleme.<br /><br /> [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]çalışma zamanı şablon tarafından oluşturulan kodu incelemek çalışırken çalışmayı durdurur.|Metin bloğu çok uzun. T4 metin blokları her şablon satır için değişmez değer bir dize içeren bir dize birleştirme ifadesi dönüştürür. Çok uzun metin blokları derleyicinin boyutu sınırları overstep.|Gibi bir ifade bloğu ile uzun metin bloğu bölmeniz:<br /><br /> `<#= "" #>`|  
  
## <a name="warning-descriptions-and-fixes"></a>Uyarı açıklamaları ve düzeltmeler  
 Aşağıdaki tabloda, varsa en yaygın uyarılar düzeltmeleri, ile birlikte listeler.  
  
|Uyarı iletisi|Açıklama|Çözüm|  
|---------------------|-----------------|--------------|  
|İçerme dosyası '{0}' yüklenirken null veya boş bir dize döndürdü.|Dahil edilen metin şablon dosyası boş olduğunda oluşur. İleti dahil dosyasının dosya adı sağlar.|INCLUDE yönergesi kaldırın ya da dosyanın bazı içerikler sahip olduğundan emin olun.|  
|Dönüştürme derleme:|Tüm hatalar veya uyarılar dönüştürme derlediğinde derleyiciden kaynaklanan bu dizeye başına. Bu dize derleyici bir hata veya uyarı oluşturdu anlamına gelir.|DLL bulma bir sorun varsa, DLL GAC içinde ise tam yol veya tam bir güçlü ad sağlamanız gerekebilir.|  
|'{0}' parametresi yönergesinde zaten var. Yinelenen parametre yoksayılacak.|Parametre birden çok kez bir yönergesinde belirtilen oluşur. İleti adı parametresi ve yönergesi satır sayısını sağlar.|Yinelenen parametre belirtimini kaldırın.|  
|İçerme dosyası '{0}' yüklenirken bir hata oluştu. INCLUDE yönergesi yoksayılacak.|Belirtilen bir dosyayı bulamıyor oluşur bir `include` yönergesi. İleti dosyasının adını ve yönergesi satır sayısını sağlar.|Özgün metin şablon dosyası ile aynı dizinde veya konak ile kayıtlı içerme dizinleri birinde içerme dosyası var olduğundan emin olun.|  
|Geçersiz bir temel sınıf dönüştürme sınıfı için belirtildi. Taban sınıf Microsoft.VisualStudio.TextTemplating.TextTransformation türetilmelidir.|Oluşur zaman `inherits` şablon yönergesi parametresinde belirtir öğesinden devralmıyor bir sınıf `TextTransformation`. İleti şablon yönergesi satır sayısını sağlar.|Türetilen bir sınıfı belirtin `TextTransformation`.|  
|Geçersiz bir kültür 'template' yönergesinde belirtildi. Kültür "xx-XX" biçiminde olmalıdır. Sabit kültür kullanılır.|Bir şablon yönergesi kültür parametresinde yanlış belirtilen oluşur. İleti şablon yönergesi satır sayısını sağlar.|Kültür parametresi "xx-XX" biçiminde geçerli bir kültür değiştirin.|  
|Bir geçersiz hata ayıklama değeri '{0}' şablon yönergesinde belirtildi. Hata ayıklama değer "true" veya "false" olmalıdır. Varsayılan değer "false" olan kullanılır.|Oluşur zaman `debug` şablon yönergesi parametresinde yanlış belirtildi. İleti şablon yönergesi satır sayısını sağlar.|Hata ayıklama parametresi "true" veya "false" olarak ayarlayın.|  
|Geçersiz bir HostSpecific değeri '{0}' şablon yönergesinde belirtildi. HostSpecific değer "true" veya "false" olmalıdır. Varsayılan değer "false" olan kullanılır.|Oluşur olduğunda ana bilgisayara özgü parametresinde bir `template` yönergesi yanlış belirtildi. İleti şablon yönergesi satır sayısını sağlar.|Ana bilgisayara özgü parametreyi "true" veya "false" ayarlayın.|  
|Geçersiz bir dil '{0}' 'template' yönergesinde belirtilmedi. Dil "C#" veya "VB" olmalıdır. "C#" varsayılan değeri kullanılacak.|Desteklenmeyen bir dil belirtilen oluşur `template` yönergesi. Yalnızca "C#" veya "VB" izin verilir (büyük küçük harfe duyarlı). İleti şablon yönergesi satır sayısını sağlar.|Ayarlama `language` şablon yönergesi "C#" veya "VB" parametresi.|  
|Birden çok çıktı yönergeleri şablonda bulunamadı. Birinci dışındaki tüm yoksayılacak.|Oluşur, birden çok `output` yönergeleri, bir şablon dosyasında belirtilir. İleti yinelenen çıkış yönergesi satır sayısını sağlar.|Yinelenen kaldırma `output` yönergeleri.|  
|Birden çok şablon yönergeleri şablonda bulunamadı. Birinci dışındaki tüm yoksayılacak. Birden çok parametre şablon yönergesi için bir şablon yönergesi içinde belirtilmesi gerekir.|Birden çok belirlerseniz oluşur `template` yönergeleri (eklenen dosyalar dahil) bir metin şablon dosyası içinde. İleti yinelenen şablon yönergesi satır sayısını sağlar.|Farklı bir araya `template` tek yönergeleri `template` yönergesi.|  
|'{0}' adlı bir yönerge için hiçbir işlemci belirtildi. Yönergesi yoksayılacak.|Belirttiğiniz saptanmışsa bir `custom` yönergesi, ancak sağlıyor mu bir `processor` özniteliği. İleti adını yönergesi ve satır numarası sağlar.|Sağlayan bir `processor` adını taşıyan öznitelik `directive` yönergesi için işlemci.|  
|'{0}' adlı bir işlemci '{1}' adlı yönergesi için bulunamadı. Yönergesi yoksayılacak.|Sistem bulamıyor oluşur `directive` işlemci içinde belirtilen bir `custom` yönergesi. İleti yönerge adı, işlemci adı ve yönergesi satır sayısını sağlar.|Ayarlama `processor` yönerge işlemcisi adına yönergesi özniteliği.|  
|'{0}' '{1}' yönergesi için gerekli bir parametre bulunamadı. Yönergesi yoksayılacak.|Sistem gerekli yönerge parametre sağlamaz oluşur. İleti eksik parametre adı, yönerge adı ve satır numarası sağlar.|Eksik parametre sağlayın.|  
|'{0}' adlı İşlemci '{1}' adlı yönergesi desteklemez. Yönergesi yoksayılacak.|Bir yönerge işlemcisi bir yönerge desteklemiyor oluşur. İleti yönerge işlemcisi adını birlikte sorunlu yönergesi adı ve satır sayısını sağlar.|Yönergesi adını düzeltin.|  
|'{0}' dosyası için bir içerme yönergesi sonsuz bir döngüye neden olur.|Döngüsel yönergeleri eklerseniz görüntülenen belirtilir (örneğin, dosya A Dosya A içeren dosya B içerir).|Döngüsel belirtmeyin yönergeleri içerir.|  
|Dönüştürme çalıştırma:|Tüm hatalar veya dönüştürme çalıştırılırken oluşturulan uyarılar için bu dizeyi başına.|Yok.|  
|Beklenmeyen bir başlangıç veya bitiş etiketi bloğu içinde bulunamadı. Bir başlangıç veya bitiş etiketi yanlış yazmadınız ve şablonda herhangi iç içe geçmiş bir bloğu yoksa emin olun.|Beklenmeyen bir olduğunda görüntülenen \<# veya #>. Diğer bir deyişle, varsa bir \<# kapalı başka bir açık etiketinden sonra veya sahip bir #> önceki kapatılmamış bir açma etiketi yok olduğunda. İleti eşleşmeyen etiketi satır sayısını sağlar.|Eşleşmeyen başlangıç veya bitiş etiketi Kaldır ya da bir kaçış karakteri kullanın.|  
|Bir yönerge biçimi yanlış belirtildi. Yönergesi yoksayılacak. Lütfen yönergesi biçiminde belirtin`<#@ name [parametername="parametervalue"]*  #>`|Bir yönerge doğru biçimde belirtilmezse ayrıştırıcı tarafından görüntülenir. İleti hatalı yönergesi satır sayısını sağlar.|Tüm yönergeleri biçiminde olduğundan emin olmanız `<#@ name [parametername="parametervalue"]*  #>`. Daha fazla bilgi için bkz: [T4 metin şablonu yönergeleri](../modeling/t4-text-template-directives.md).|  
|Kayıtlı yönerge işlemcisi '{1}' için '{0}' derlemesi yüklenemedi<br /><br /> {2}|Bir yönerge işlemcisi ana bilgisayar tarafından yüklenemedi oluşur. İleti yönerge işlemcisi ve yönerge işlemcisi ad için sağlanan derleme tanımlar.|Yönerge işlemcisi doğru şekilde kaydedildiğini ve derleme var olduğundan emin olun.|  
|'{0}' türünün '{1}' derlemesinde kayıtlı yönerge işlemcisi '{2}' bulunamadı.<br /><br /> {3}|Bir yönerge işlemcisi türü, Derleme yüklenemedi oluşur. İleti türü, derleme ve yönerge işlemcisi adı sağlar.|Vshost yönerge işlemcisi bilgileri (adı, derleme ve türü) kayıt defterinde bulur. Yönerge işlemcisi doğru şekilde kaydedildiğini ve türü derlemede var olduğundan emin olun.|  
|'{0}' derlemesi yüklenirken bir sorun oluştu|Bir derlemesi yüklenirken bir sorun olduğunda oluşur. İleti derlemenin adını sağlar.|İçinde yüklenecek derlemeler belirtebilirsiniz \<@# assembly #> yönergeleri ve yönerge işlemcileri tarafından. Bu dize aşağıdaki hata iletisini daha fazla veri derleme yük neden başarısız sağlamalıdır.|  
|Oluşturma ve '{1}' adlı bir yönerge işlemcisi başlatılırken bir sorun oluştu. {0} işlemci türde değil. Yönergesi yoksayılacak.|Sistem oluşturamadı veya bir yönerge işlemcisi başlatma oluşur. Message yönergesi adı ve satır sayısı ve işlemci türü sağlar.|Doğru yönerge işlemcisi kullanın ve yönerge işlemcisi ortak varsayılan bir oluşturucu sahip olduğundan emin olun. Aksi takdirde yönerge işlemcisi önce Initialize() yöntemini neden başarısız çıkışı bulmak için hata ayıklama seçeneklerini kullanın. Daha fazla bilgi için bkz: [sorun giderme metin şablonları](../modeling/debugging-a-t4-text-template.md).|  
|'{0}' adlı bir yönerge işlenirken bir özel durum.|Bir yönerge işlemcisi bir yönerge işlenirken bir özel durum oluşturduğunda gerçekleşir.|Yönerge işlemcisi parametrelerinin doğru olduğundan emin olun.|  
|Ana derleme başvurusu '{0}' çözümlemeye çalışırken özel durum oluşturdu.|Konak bir derleme başvurusu çözümlemeye çalışırken bir özel durum oluşturduğunda gerçekleşir. Derleme ileti sağlar başvuru dize.|Derleme başvuruları gelen \<@# assembly #> yönergeleri ve yönerge işlemcileri. Derleme parametrede sağlanan 'name' parametresiyle doğru olduğundan emin olun.|  
|Desteklenmeyen {1} değeri '{0}' yönergesi {2} belirleme girişimi|RequiresProvidesDirectiveProcessor (tüm bizim oluşturulan yönerge işlemcileri ondan türetilen), oluşur sağladığınız desteklenmeyen gerektirir veya bağımsız değişkeni sağlar.|Name = adlarında 'de sağlanan çiftleri değeri' emin olması gerekir ve parametreleri doğru sağlar.|