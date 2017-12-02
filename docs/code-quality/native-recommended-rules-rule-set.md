---
title: "Yerel önerilen kurallar kural kümesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d845b5a-1b75-4e9d-861a-7c59cb7752af
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3063f1a65035018df9c9d6a034ef11b5e9732a30
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="native-recommended-rules-rule-set"></a>Yerel Önerilen Kurallar kural kümesi
Yerel önerilen kurallar olası güvenlik açıklarını ve uygulama çökme (Crash) dahil olmak üzere, yerel kodunuzda en kritik ve ortak sorunları odaklanır.  Yerel projeleriniz için oluşturduğunuz herhangi bir özel kural kümesi içinde bu kural kümesi içermelidir.  Bu ruleset Visual Studio Professional edition ile ve daha yüksek çalışmak üzere tasarlanmıştır.  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[C6001](../code-quality/c6001.md)|Başlatılmamış bellek kullanma|  
|[C6011](../code-quality/c6011.md)|Null işaretçinin başvurusunun kaldırılmasının|  
|[C6029](../code-quality/c6029.md)|Unchecked değeri kullanımı|  
|[C6031](../code-quality/c6031.md)|Göz ardı dönüş değeri|  
|[C6053](../code-quality/c6053.md)|Çağrısından sıfır sonlandırma|  
|[C6054](../code-quality/c6054.md)|Sonlandırma eksik sıfır|  
|[C6059](../code-quality/c6059.md)|Hatalı birleştirme|  
|[C6063](../code-quality/c6063.md)|İşlev biçimlendirmek için dize bağımsız değişkeni eksik|  
|[C6064](../code-quality/c6064.md)|İşlev biçimlendirmek için tamsayı bağımsız değişkeni eksik|  
|[C6066](../code-quality/c6066.md)|İşlev biçimlendirmek için işaretçi bağımsız değişkeni eksik|  
|[C6067](../code-quality/c6067.md)|İşlev biçimlendirmek için dize işaretçi bağımsız değişkeni eksik|  
|[C6101](../code-quality/c6101.md)|Başlatılmamış bellek döndürme|  
|[C6200](../code-quality/c6200.md)|Dizin arabellek üst sınırını aşıyor|  
|[C6201](../code-quality/c6201.md)|Dizin yığını arabellek üst sınırını aşıyor|  
|[C6214](../code-quality/c6214.md)|BOOL HRESULT geçersiz yayın|  
|[C6215](../code-quality/c6215.md)|Geçersiz yayın HRESULT BOOL|  
|[C6216](../code-quality/c6216.md)|Geçersiz derleyici eklenen yayın HRESULT BOOL|  
|[C6217](../code-quality/c6217.md)|Geçersiz HRESULT testiyle değil|  
|[C6220](../code-quality/c6220.md)|Geçersiz HRESULT karşılaştırma-1|  
|[C6226](../code-quality/c6226.md)|Geçersiz HRESULT atama-1|  
|[C6230](../code-quality/c6230.md)|Boole değeri olarak geçersiz HRESULT kullanın|  
|[C6235](../code-quality/c6235.md)|Sıfır olmayan sabit mantıksal ile- veya|  
|[C6236](../code-quality/c6236.md)|Mantıksal- ya da sıfır sabiti|  
|[C6237](../code-quality/c6237.md)|Mantıksal sıfır- ve yan etkileri kaybeder|  
|[C6242](../code-quality/c6242.md)|Zorlanan yerel geriye doğru izleme|  
|[C6248](../code-quality/c6248.md)|Null DACL oluşturma|  
|[C6250](../code-quality/c6250.md)|Yayımlanmamış adresi tanımlayıcıları|  
|[C6255](../code-quality/c6255.md)|Alloca korumasız kullanımı|  
|[C6258](../code-quality/c6258.md)|İş parçacığı sonlandırma kullanma|  
|[C6259](../code-quality/c6259.md)|Kullanılmayan Bitsel kod- veya sınırlı anahtar|  
|[C6260](../code-quality/c6260.md)|Bayt aritmetik kullanımı|  
|[C6262](../code-quality/c6262.md)|Aşırı yığın kullanımı|  
|[C6263](../code-quality/c6263.md)|Alloca Döngüdeki kullanma|  
|[C6268](../code-quality/c6268.md)|Cast parantezlerde eksik|  
|[C6269](../code-quality/c6269.md)|İşaretçi başvuru kaldırma göz ardı|  
|[C6270](../code-quality/c6270.md)|İşlev biçimlendirmek için Float bağımsız değişkeni eksik|  
|[C6271](../code-quality/c6271.md)|İşlev biçimlendirmek için ek bağımsız değişken|  
|[C6272](../code-quality/c6272.md)|İşlev biçimlendirmek için bağımsız değişken Float|  
|[C6273](../code-quality/c6273.md)|Tamsayı olmayan Argumen işlevi biçimlendirmek için|  
|[C6274](../code-quality/c6274.md)|İşlev biçimlendirmek için karakter olmayan bağımsız değişken|  
|[C6276](../code-quality/c6276.md)|Geçersiz dize atama|  
|[C6277](../code-quality/c6277.md)|Geçersiz CreateProcess arama|  
|[C6278](../code-quality/c6278.md)|Dizi yeni skaler silme uyuşmazlığı|  
|[C6279](../code-quality/c6279.md)|Skaler yeni dizi-Delete uyuşmazlığı|  
|[C6280](../code-quality/c6280.md)|Bellek ayırma kaldırma uyuşmazlığı|  
|[C6281](../code-quality/c6281.md)|Bit düzeyinde ilişkisi önceliği|  
|[C6282](../code-quality/c6282.md)|Test atama değiştirir|  
|[C6283](../code-quality/c6283.md)|Basit dizi yeni skaler silme uyuşmazlığı|  
|[C6284](../code-quality/c6284.md)|İşlev biçimlendirmek için geçersiz nesne değişkeni|  
|[C6285](../code-quality/c6285.md)|Mantıksal- veya sabitleri|  
|[C6286](../code-quality/c6286.md)|Sıfır olmayan mantıksal- veya yan etkileri kaybetme|  
|[C6287](../code-quality/c6287.md)|Yedek Test|  
|[C6288](../code-quality/c6288.md)|Mantıksal üzerinden karşılıklı içerme- ve False ise|  
|[C6289](../code-quality/c6289.md)|Karşılıklı dışlama mantıksal üzerinden- ya da geçerlidir|  
|[C6290](../code-quality/c6290.md)|Bitwise Not mantıksal- ve önceliği|  
|[C6291](../code-quality/c6291.md)|Bitwise Not mantıksal- veya önceliği|  
|[C6292](../code-quality/c6292.md)|En büyük gelen yukarı döngü sayar|  
|[C6293](../code-quality/c6293.md)|Döngü Minimum sayıları|  
|[C6294](../code-quality/c6294.md)|Hiçbir zaman yürütülen döngü gövdesine|  
|[C6295](../code-quality/c6295.md)|Sonsuz bir döngü|  
|[C6296](../code-quality/c6296.md)|Yalnızca bir kere yürütülmesi döngüsü|  
|[C6297](../code-quality/c6297.md)|Shift sonucunu Cast daha büyük boyutu|  
|[C6299](../code-quality/c6299.md)|Bit alanını bir Boolean karşılaştırması|  
|[C6302](../code-quality/c6302.md)|İşlev biçimlendirmek için geçersiz bir karakter dizesi bağımsız değişkeni|  
|[C6303](../code-quality/c6303.md)|İşlev biçimlendirmek için geçersiz geniş karakter dizesi bağımsız değişkeni|  
|[C6305](../code-quality/c6305.md)|Eşleşmeyen boyutunu ve sayısını kullan|  
|[C6306](../code-quality/c6306.md)|Yanlış değişken bağımsız değişken işlev çağrısı|  
|[C6308](../code-quality/c6308.md)|Realloc sızıntısı|  
|[C6310](../code-quality/c6310.md)|Geçersiz özel durum filtresi sabiti|  
|[C6312](../code-quality/c6312.md)|Özel durum yürütme döngü devam|  
|[C6314](../code-quality/c6314.md)|Bit düzeyinde- veya önceliği|  
|[C6317](../code-quality/c6317.md)|Değil değil tamamlama|  
|[C6318](../code-quality/c6318.md)|Özel durum arama devam|  
|[C6319](../code-quality/c6319.md)|Virgül ile yoksayıldı|  
|[C6324](../code-quality/c6324.md)|Dize karşılaştırma yerine dize kopyalama|  
|[C6328](../code-quality/c6328.md)|Olası bağımsız değişkeni tür uyuşmazlığı|  
|[C6331](../code-quality/c6331.md)|VirtualFree geçersiz bayrakları|  
|[C6332](../code-quality/c6332.md)|VirtualFree geçersiz parametre|  
|[C6333](../code-quality/c6333.md)|VirtualFree geçersiz boyutu|  
|[C6335](../code-quality/c6335.md)|İşlem tanıtıcısı sızıntısı|  
|[C6381](../code-quality/c6381.md)|Kapatma bilgileri eksik|  
|[C6383](../code-quality/c6383.md)|Öğe sayısını bayt-sayısı arabellek taşması|  
|[C6384](../code-quality/c6384.md)|İşaretçi boyutu bölme|  
|[C6385](../code-quality/c6385.md)|Okuma taşması|  
|[C6386](../code-quality/c6386.md)|Taşma yazma|  
|[C6387](../code-quality/c6387.md)|Geçersiz parametre değeri|  
|[C6388](../code-quality/c6388.md)|Geçersiz parametre değeri|  
|[C6500](../code-quality/c6500.md)|Geçersiz öznitelik özelliği|  
|[C6501](../code-quality/c6501.md)|Çakışan öznitelik özellik değerleri|  
|[C6503](../code-quality/c6503.md)|Başvuruları Null olamaz|  
|[C6504](../code-quality/c6504.md)|İşaretçi null|  
|[C6505](../code-quality/c6505.md)|Void üzerinde Pages'in|  
|[C6506](../code-quality/c6506.md)|İşaretçi olmayan veya dizi arabellek boyutu|  
|[C6507](http://msdn.microsoft.com/en-us/18f88cd1-d035-4403-a6a4-12dd0affcf21)|Konumundaki null uyuşmazlığı sıfır başvuru|  
|[C6508](../code-quality/c6508.md)|Yazma erişimi sabiti|  
|[C6509](../code-quality/c6509.md)|Önkoşul üzerinde kullanılan dönüş|  
|[C6510](../code-quality/c6510.md)|Null işaretçinin olmayan üzerinde sonlandırıldı|  
|[C6511](../code-quality/c6511.md)|Pages'in olmalıdır Evet veya Hayır|  
|[C6513](../code-quality/c6513.md)|Arabellek boyutu olmadan öğesi boyutu|  
|[C6514](../code-quality/c6514.md)|Dizi boyutu arabellek boyutunu aşıyor|  
|[C6515](../code-quality/c6515.md)|İşaretçi olmayan arabellek boyutu|  
|[C6516](../code-quality/c6516.md)|Hiçbir öznitelik özellikleri|  
|[C6517](../code-quality/c6517.md)|Okunabilir olmayan arabellek geçerli boyutu|  
|[C6518](../code-quality/c6518.md)|Yazılabilir olmayan arabellek yazılabilir boyutu|  
|[C6519](http://msdn.microsoft.com/en-us/2b6326b0-0539-4d26-8fb1-720114933232)|Geçersiz ek açıklama: 'NeedsRelease' özelliğinin değeri olmalıdır Evet veya Hayır|  
|[C6521](http://msdn.microsoft.com/en-us/e98d0ae3-6f13-47b2-9a15-15d4055af9ef)|Boyutu geçersiz dize başvuru|  
|[C6522](../code-quality/c6522.md)|Boyutu geçersiz dize türü|  
|[C6523](http://msdn.microsoft.com/en-us/11397a31-b224-46b0-afb7-d49ca576a3bb)|Geçersiz boyutu dizesi parametresi|  
|[C6525](../code-quality/c6525.md)|Boyutu geçersiz dize ulaşılamaz konumu|  
|[C6526](http://msdn.microsoft.com/en-us/59c590c7-0098-4166-a1ac-87f324596002)|Boyutu geçersiz dize arabellek türü|  
|[C6527](../code-quality/c6527.md)|Geçersiz ek açıklama: 'NeedsRelease' özelliğinin türü void değerlerine kullanılamaz|  
|[C6530](../code-quality/c6530.md)|Tanınmayan biçim dizesi stili|  
|[C6540](../code-quality/c6540.md)|Bu işlev özniteliği ek açıklamalarını kullanımını tüm mevcut __declspec açıklamalarıyla geçersiz kılar|  
|[C6551](../code-quality/c6551.md)|Geçersiz boyut belirtimi: ifadesi değil parsable|  
|[C6552](../code-quality/c6552.md)|Geçersiz Deref = veya Notref =: ifadesi değil parsable|  
|[C6701](../code-quality/c6701.md)|Değer geçerli bir Evet/Hayır/olabilir değeri değil|  
|[C6702](../code-quality/c6702.md)|Değer bir dize değeri değil|  
|[C6703](../code-quality/c6703.md)|Değer bir sayı değil|  
|[C6704](../code-quality/c6704.md)|Beklenmeyen ek açıklama ifade hatası|  
|[C6705](../code-quality/c6705.md)|Beklenen sayıda bağımsız değişken ek açıklama için gerçek ek açıklama için bağımsız değişken sayısı eşleşmiyor|  
|[C6706](../code-quality/c6706.md)|Ek açıklama için beklenmeyen bir ek açıklamanın hata|  
|[C6995](../code-quality/c6995.md)|XML günlük dosyası kaydedilemedi|  
|[C26100](../code-quality/c26100.md)|Yarış durumu|  
|[C26101](../code-quality/c26101.md)|Interlocked işlemi düzgün bir şekilde kullanmak için başarısız|  
|[C26110](../code-quality/c26110.md)|Arayan kilit tutacak başarısız|  
|[C26111](../code-quality/c26111.md)|Arayan kilidi başarısız|  
|[C26112](../code-quality/c26112.md)|Arayan herhangi kilit tutun olamaz|  
|[C26115](../code-quality/c26115.md)|Kilidi başarısız|  
|[C26116](../code-quality/c26116.md)|Başarısız olan edinmeye veya kilidi tutmak için|  
|[C26117](../code-quality/c26117.md)|Unheld kilidi serbest bırakma|  
|[C26140](../code-quality/c26140.md)|Eşzamanlılık SAL ek açıklama hata|  
|[C28020](../code-quality/c28020.md)|İfade bu çağrısı doğru değil|  
|[C28021](../code-quality/c28021.md)|Açıklama parametresi bir işaretçi olmalıdır|  
|[C28022](../code-quality/c28022.md)|Bu işlev üzerinde işlevi sınıfları, tanımlamak için kullanılan typedef üzerinde işlevi sınıfları eşleşmiyor.|  
|[C28023](../code-quality/c28023.md)|Atanan veya geçirilen işlevi bir _Function_class olmalıdır\_ sınıfları en az biri için ek açıklaması|  
|[C28024](../code-quality/c28024.md)|Atanmasına işlev işaretçisi işlev sınıfları listesinde bulunmayan işlevi sınıfıyla işaretiyle gösterilir.|  
|[C28039](../code-quality/c28039.md)|Gerçek parametrenin türü türü tam olarak eşleşmelidir|  
|[C28112](../code-quality/c28112.md)|Interlocked işlevi erişilen değişken her zaman bir Interlocked işlevi erişilmesi gerekir.|  
|[C28113](../code-quality/c28113.md)|Interlocked işlevi aracılığıyla yerel değişkene erişme|  
|[C28125](../code-quality/c28125.md)|İşlev çağrılmalıdır deneyin içinde / bloğu dışında|  
|[C28137](../code-quality/c28137.md)|Değişken bağımsız değişken yerine (değişmez değer) sabiti olmalıdır|  
|[C28138](../code-quality/c28138.md)|Sabit bağımsız değişkeni yerine olmalıdır|  
|[C28159](../code-quality/c28159.md)|Başka bir işlevi yerine kullanmayı düşünün.|  
|[C28160](../code-quality/c28160.md)|Hata ek açıklaması|  
|[C28163](../code-quality/c28163.md)|İşlev hiçbir zaman gelen çağrılmalıdır deneyin içinde / bloğu dışında|  
|[C28164](../code-quality/c28164.md)|Bir işaretçi bir nesneye (işaretçisi değil bir işaretçi) beklediği bir işleve bağımsız değişkeni geçirilmiş|  
|[C28182](../code-quality/c28182.md)|BOŞ işaretçi başvurusunun kaldırılmasının. Başka bir işaretçi yaptığınız gibi bir işaretçi aynı NULL değer içeriyor.|  
|[C28183](../code-quality/c28183.md)|Bağımsız değişkeni bir değer olabilir ve değeri bir kopyasını işaretçinin bulundu|  
|[C28193](../code-quality/c28193.md)|Değişkeni incelenmesi gereken bir değer tutar|  
|[C28196](../code-quality/c28196.md)|Gereksinim gerçekleşmedi. (İfade true olarak değerlendirmez.)|  
|[C28202](../code-quality/c28202.md)|Statik olmayan üye geçersiz başvuru|  
|[C28203](../code-quality/c28203.md)|Sınıf üyesine başvuru belirsiz.|  
|[C28205](../code-quality/c28205.md)|_Success\_ veya _On_failure\_ geçersiz bir bağlamda kullanılır|  
|[C28206](../code-quality/c28206.md)|İşlenen noktaları için yapı sol, Kullan '->'|  
|[C28207](../code-quality/c28207.md)|Sol işleneni yapı, kullanın '.'|  
|[C28209](../code-quality/c28209.md)|Sembol bildirimi çakışan bir bildirime sahip|  
|[C28210](../code-quality/c28210.md)|Ek açıklamalar __on_failure bağlamının açık öncesi bağlamda olmamalıdır|  
|[C28211](../code-quality/c28211.md)|Statik içerik adı SAL_context için bekleniyor|  
|[C28212](../code-quality/c28212.md)|İşaretçi ifade eklenti için bekleniyor|  
|[C28213](../code-quality/c28213.md)|_Use_decl_annotations\_ ek açıklama, başvuru, değişiklik yapmadan önce bir bildirim için kullanılmalıdır.|  
|[C28214](../code-quality/c28214.md)|Öznitelik parametre adları p1... olmalıdır p9|  
|[C28215](../code-quality/c28215.md)|Typefix bir typefix zaten olan bir parametre için uygulanamaz|  
|[C28216](../code-quality/c28216.md)|CheckReturn ek açıklama yalnızca Sonkoşullar belirli bir işlev parametresi için geçerlidir.|  
|[C28217](../code-quality/c28217.md)|İşlevi için dosya bulunan ek açıklama için parametre sayısı eşleşmiyor|  
|[C28218](../code-quality/c28218.md)|İşlev paramteer için dosya bulunan ek açıklamanın parametresi eşleşmiyor|  
|[C28219](../code-quality/c28219.md)|Numaralandırma üyesi için ek açıklama ek açıklamanın parametresinde bekleniyordu.|  
|[C28220](../code-quality/c28220.md)|Tamsayı ifade eklenti için ek açıklama parametresinde bekleniyordu.|  
|[C28221](../code-quality/c28221.md)|Ek açıklamanın parametresinin beklenen dize ifadesi|  
|[C28222](../code-quality/c28222.md)|__yes, \__hayır, veya \__maybe eklenti için bekleniyor|  
|[C28223](../code-quality/c28223.md)|Beklenen belirteç/tanımlayıcı ek bilgi için bulamadı parametresi|  
|[C28224](../code-quality/c28224.md)|Ek açıklama parametreleri gerektirir|  
|[C28225](../code-quality/c28225.md)|Gerekli Parametreler doğru sayıda açıklama içinde bulunamadı|  
|[C28226](../code-quality/c28226.md)|Ek açıklama ayrıca PrimOp (bildiriminde geçerli) olamaz|  
|[C28227](../code-quality/c28227.md)|Ek açıklama bir PrimOp da olamaz (önceki bildirimi bakın)|  
|[C28228](../code-quality/c28228.md)|Ek açıklama parametresi: türü ek açıklamalar kullanamaz|  
|[C28229](../code-quality/c28229.md)|Ek açıklama parametreleri desteklemez|  
|[C28230](../code-quality/c28230.md)|Parametre hiç üye türü.|  
|[C28231](../code-quality/c28231.md)|Ek açıklama yalnızca dizisinde geçerlidir|  
|[C28232](../code-quality/c28232.md)|önceden, post veya hiçbir ek açıklama uygulanmamış deref|  
|[C28233](../code-quality/c28233.md)|önceden, gönderme veya bir blok uygulanan deref|  
|[C28234](../code-quality/c28234.md)|ifade __at geçerli işlevi için geçerli değildir|  
|[C28235](../code-quality/c28235.md)|İşlev açıklamanın tek başına olamaz|  
|[C28236](../code-quality/c28236.md)|Ek açıklamanın bir ifadede kullanılamaz|  
|[C28237](../code-quality/c28237.md)|Ek açıklamayı parametresi artık desteklenmiyor|  
|[C28238](../code-quality/c28238.md)|Ek açıklamanın parametresi üzerinde birden fazla değer, stringValue ve LongDeğer sahip. Paramn kullanmak xxx =|  
|[C28239](../code-quality/c28239.md)|Ek açıklamanın parametresi üzerinde hem değer, stringValue veya LongDeğer sahiptir; ve paramn = xxx. Yalnızca paramn kullanmak xxx =|  
|[C28240](../code-quality/c28240.md)|Ek açıklamanın parametresindeki param2 ancak hiçbir param1 sahiptir|  
|[C28241](../code-quality/c28241.md)|Ek açıklamanın parametresindeki işlevi için tanınmıyor|  
|[C28243](../code-quality/c28243.md)|İşlev parametresi üzerinde daha gerektirir açıklama gerçek tür izin verdiğinden ek açıklamanın dereferences|  
|[C28244](../code-quality/c28244.md)|Ek açıklamanın işlevi için ayrıştırılamayan parametre/dış açıklamanın sahip|  
|[C28245](../code-quality/c28245.md)|Ek açıklamanın işlevi için bir üye-işlev olmayan üzerinde 'this' açıklama ekler|  
|[C28246](../code-quality/c28246.md)|İşlevi için parametre ek açıklama parametresinin türü eşleşmiyor.|  
|[C28250](../code-quality/c28250.md)|İşlevi için tutarsız ek açıklama: önceki örneği hatalı.|  
|[C28251](../code-quality/c28251.md)|İşlevi için tutarsız ek açıklama: Bu örnek bir hata vardır.|  
|[C28252](../code-quality/c28252.md)|İşlevi için tutarsız ek açıklama: Bu örneğinde parametresine sahip başka bir ek açıklamaları.|  
|[C28253](../code-quality/c28253.md)|İşlevi için tutarsız ek açıklama: Bu örneğinde parametresine sahip başka bir ek açıklamaları.|  
|[C28254](../code-quality/c28254.md)|Ek açıklamalar dynamic_cast <> (') desteklenmiyor|  
|[C28262](../code-quality/c28262.md)|Ek açıklamanın bir sözdizimi hatası ek açıklama için işlevi bulundu|  
|[C28263](../code-quality/c28263.md)|İç eklenti için koşullu bir ek açıklamanın bir sözdizimi hatası bulundu|  
|[C28264](http://msdn.microsoft.com/en-us/bf6ea983-a06e-4752-a042-747a7dbf338c)|Sonuç listeleri değerleri olmalıdır.|  
|[C28267](../code-quality/c28267.md)|Ek açıklamalar bir sözdizimi hatası ek açıklama işlevinde bulunamadı.|  
|[C28272](../code-quality/c28272.md)|Ek açıklamanın işlevi için incelerken parametresi işlev bildirimi ile tutarsız|  
|[C28273](../code-quality/c28273.md)|İşlevi için ipuçları işlevi bildirimi ile tutarsız|  
|[C28275](../code-quality/c28275.md)|_Macro_value parametresi\_ null|  
|[C28279](../code-quality/c28279.md)|Simge için bir 'başlamak' bir eşleşen 'end ' bulundu|  
|[C28280](../code-quality/c28280.md)|Simge için bir 'end' bir eşleşen olmadan 'başlamak' bulundu|  
|[C28282](../code-quality/c28282.md)|Biçim dizeleri önkoşulları içinde olmalıdır|  
|[C28285](../code-quality/c28285.md)|İşlev, parametre sözdizimi hatası|  
|[C28286](../code-quality/c28286.md)|İşlev, son yakınında sözdizimi hatası|  
|[C28287](../code-quality/c28287.md)|İşlev, söz dizimi hatası sürü_müne\_() ek açıklama (tanınmayan parametre adı)|  
|[C28288](../code-quality/c28288.md)|İşlev, söz dizimi hatası sürü_müne\_() ek açıklama (geçersiz parametre adı)|  
|[C28289](../code-quality/c28289.md)|İşlevi için: ReadableTo veya WritableTo bir parametre olarak bir sınırı spec yoktu|  
|[C28290](../code-quality/c28290.md)|ek açıklamanın işlevi için parametre gerçek sayısından daha fazla Externals içerir|  
|[C28291](../code-quality/c28291.md)|POST null/notnull adresindeki deref düzeyi 0'dır işlevi için anlamsız.|  
|[C28300](../code-quality/c28300.md)|Uyumsuz türlerin operatöre ifade işlenenleri|  
|[C28301](../code-quality/c28301.md)|İşlevin ilk bildirimi için hiçbir ek açıklamalar.|  
|[C28302](../code-quality/c28302.md)|Bir ek _Deref\_ işleci ek açıklamayı bulundu.|  
|[C28303](../code-quality/c28303.md)|Belirsiz _Deref\_ işleci ek açıklamayı bulundu.|  
|[C28304](../code-quality/c28304.md)|Yanlış yerleştirilmiş _Notref\_ işleci belirtecine uygulanan bulundu.|  
|[C28305](../code-quality/c28305.md)|Bir belirteç ayrıştırılırken bir hata bulundu.|  
|[C28306](../code-quality/c28306.md)|Ek açıklamanın parametresindeki obsolescent|  
|[C28307](../code-quality/c28307.md)|Ek açıklamanın parametresindeki obsolescent|  
|[C28350](../code-quality/c28350.md)|Ek açıklamanın koşullu kullanılamaz bir durumda açıklar.|  
|[C28351](../code-quality/c28351.md)|Ek açıklamanın dinamik bir değer (bir değişken) koşulunda burada kullanılamaz açıklar.|