---
title: "Şema önbelleğinin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35a7fcad-f3bf-4a96-9008-4306e7276223
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9315fdeeb336ac262f59df31b941c05ca3101b3b
ms.sourcegitcommit: 5f436413bbb1e8aa18231eb5af210e7595401aa6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/08/2018
---
# <a name="schema-cache"></a>Şema önbelleği
XML Düzenleyicisi'ni %InstallRoot%\Xml\Schemas dizininde yer alan bir şema önbelleği sağlar. Şema önbelleği, bilgisayardaki tüm kullanıcılar için geneldir ve IntelliSense ve XML belge doğrulama için kullanılan standart XML şemaları içerir.  
  
 XML Düzenleyicisi'ni de çözümde bulunan şemaları bulabilir, şemalar belirtilen **şemaları** belgenin alan **özellikleri** penceresi ve şemalar tarafından tanımlanan `xsi:schemaLocation` ve `xsi:noNamespaceSchemaLocation`öznitelikleri.  
  
 Aşağıdaki tabloda XML Düzenleyicisi ile yüklenen şemaları açıklanmaktadır.  
  
|Dosya adı|Açıklama|  
|--------------|-----------------|  
|catalog.xsd|XML Düzenleyicisi şema katalog dosyaları için şema. Şema kataloglar hakkında daha fazla bilgi için aşağıya bakın.|  
|DotNetConfig.xsd|Web.Config dosyaları için şema "http://schemas.microsoft.com/.NETConfiguration/v2.0".|  
|MSBuild.xsd|MSBuild yapma dosyaları için şema "http://schemas.microsoft.com/developer/msbuild/2003".|  
|MSDATA.xsd|Tarafından eklenen XSD ek açıklamalar için şema <xref:System.Data.DataSet> sınıfı, "urn: şemaları-microsoft-com: xml-msdata".|  
|msxsl.xsd|Microsoft XSLT betik bloğu uzantıları, urn: şemaları için şema-microsoft-com:xslt.|  
|SnippetFormat.xsd|Kod parçacığı XML dosyaları için şema. % InstallDir%\VC#\Expansions örnekler için bkz.|  
|Soap1.1.xsd|Basit Nesne Erişim Protokolü (SOAP) 1.1 için şema, http://schemas.xmlsoap.org/soap/envelope/.|  
|Soap1.2.xsd|Basit Nesne erişim protokolü 1.2 için şema.|  
|SiteMapSchema.xsd|Şema ASP.NET site haritası XML dosyası için "http://schemas.microsoft.com/AspNet/SiteMap-File-1.0".|  
|WSDL.xsd|Web Service Description Language için şema http://schemas.xmlsoap.org/wsdl/.|  
|xenc.xsd|XML şifrelemesi için şema http://www.w3.org/2000/09/xmldsig#.|  
|XHTML.xsd|XHTML http://www.w3.org/1999/xhtml için şema.|  
|XLink.xsd|XLink1.0, şema http://www.w3.org/1999/xlink.|  
|XML.xsd|Şema açıklayan XML: Space ve XML: lang öznitelikleri, http://www.w3.org/XML/1998/namespace.|  
|xmlsig.xsd|XML dijital imzalar, şema http://www.w3.org/2000/09/xmldsig#.|  
|xsdschema.xsd|Açıklayan XSD şema kendisi, http://www.w3.org/2001/XMLSchema.|  
|XSLT.xsd|Http://www.w3.org/1999/XSL/Transform XML Şeması dönüştürür.|  
  
## <a name="updating-schemas-in-the-cache"></a>Önbellek şemalarda güncelleştiriliyor  
 XML Düzenleyicisi paket yüklenir ve çalışırken değişiklikleri izleyen Düzenleyicisi şema önbellek dizini yükler. Bir şema eklediyseniz bilinen şemalar bellek içi dizine otomatik olarak yüklenir. Bir şema kaldırdıysanız bellek içi dizinden otomatik olarak kaldırılır. Otomatik olarak bir şema güncelleştirildiyse, bu şemanın bellek içi önbellek geçersiz kılar.  
  
> [!NOTE]
>  Şema önbellek dizini bilgisayarınıza genel olduğundan, standart ve bilgisayarınızda oluşturulan tüm Visual Studio projeleri için yararlı olan şemaları burada yalnızca eklemeniz gerekir.  
  
 XML Düzenleyicisi'ni şema katalog dosyaları herhangi bir sayıda şema önbellek dizininde de destekler. Şema kataloglar diğer konumları hakkında bilgi edinmek için Düzenleyicisi her zaman istediğiniz şemaları için işaret edebilir. Catalog.xsd dosya katalog dosyası biçimini tanımlar ve şema önbellek dizininde bulunur. Varsayılan katalog catalog.xml dosyasıdır ve diğer şemalar % InstallDir % bağlantılar içerir. Bir örnekleme catalog.xml dosyasının verilmiştir:  
  
```xml
<SchemaCatalog xmlns="http://schemas.microsoft.com/xsd/catalog">  
  <Schema href="%InstallDir%/help/schemas/Favorites.xsd" targetNamespace="urn:Favorites-Schema"/>  
  <Schema href="%InstallDir%/help/schemas/Links.xsd" targetNamespace="urn:Links-Schema"/>  
  <Schema href="%InstallDir%/help/schemas/MyHelp.xsd" targetNamespace="urn:VSHelp-Schema"/>  
</SchemaCatalog>  
```
  
 `href` Özniteliği şemaya işaret eden bir dosya yolu veya http URL'si olabilir. Dosya yolu göreli katalog belge olabilir. Virgülle ayrılan aşağıdaki değişkenleri %% Düzenleyicisi tarafından tanınmıyor ve yolunda genişletilecek:  
  
-   InstallDir  
  
-   Sistem  
  
-   ProgramFiles  
  
-   Programlar  
  
-   CommonProgramFiles  
  
-   ApplicationData  
  
-   CommonApplicationData  
  
-   LCID  
  
Katalog belge içerebilir bir `Catalog` diğer katalog işaret öğesi. Kullanabileceğiniz `Catalog` takım veya şirket tarafından paylaşılan merkezi bir katalog veya iş ortaklarınızla paylaşılan çevrimiçi katalog işaret etmek için öğesi. `href` Diğer kataloglar dosya yolu veya http URL'si bir özniteliktir. Aşağıdaki örneğidir `Catalog` öğe:  
  
```xml
<Catalog href="file://c:/xcbl/xcblCatalog.xml"/>  
```
  
 Kataloğu, ayrıca nasıl şemaları özel kullanarak XML belgeleri ile ilişkili denetleyebilirsiniz `Association` öğesi. Bu öğe hiçbir hedef ad alanı XML Düzenleyicisi'ni olmayan şemaların herhangi otomatik ilişkilendirme yapmak için yararlı olabilecek belirli dosya uzantısına sahip olan şemaları ilişkilendiren bir `targetNamespace` özniteliği. Aşağıdaki örnekte `Association` öğesi ilişkilendirir dotNetConfig şema "yapılandırma" dosya uzantısına sahip tüm dosyaları:  
  
```xml
<Association extension="config" schema="%InstallDir%/xml/schemas/dotNetConfig.xsd"/>  
```
  
## <a name="localized-schemas"></a>Yerelleştirilmiş şemaları  
 Çoğu durumda, yerelleştirilmiş şemaları girişlerinde catalog.xml dosya içermiyor. Yerelleştirilmiş şema dizine işaret catalog.xml dosyası için ek girdiler ekleyebilirsiniz.  
  
 Aşağıdaki örnekte yeni bir `Schema` öğesi yerelleştirilmiş şemaya işaret edecek şekilde % LCID % değişkeni kullanan oluşturuldu.  
  
```xml
<Schema href="%InstallRoot%/Common7/IDE/Policy/Schemas/%LCID%/TDLSchema.xsd"  
  targetNamespace="http://www.microsoft.com/schema/EnterpriseTemplates/TDLSchema"/>  
```
  
## <a name="changing-the-location-of-the-schema-cache"></a>Şema önbelleğinin konumunu değiştirme  
 Şema önbelleğini kullanmak için konumun özelleştirebilirsiniz **çeşitli** seçenekler sayfası. Sık kullanılan şemaların bir dizin varsa, bu şemaları kullanmayı Düzenleyicisi yapılandırılabilir.  
  
> [!NOTE]
>  Bu değişiklik, yalnızca geçerli Visual Studio kullanıcı etkiler.  
  
#### <a name="to-change-the-schema-cache-location"></a>Şema önbellek konumunu değiştirmek için  
  
1.  Gelen **Araçları** menüsünde, select **seçenekleri**.  
  
2.  Genişletme **metin düzenleyici**, genişletin **XML**ve ardından **çeşitli**.  
  
3.  Tıklatın **Gözat** düğmesini **şemaları** alan.  
  
4.  Şema önbelleği klasörü seçin ve tıklatın **Tamam**.  
  
#### <a name="to-add-another-directory-of-common-schemas"></a>Ortak şema başka bir dizin eklemek için  
  
1.  XML Düzenleyicisi şema önbellek dizinindeki catalog.xml dosyasını düzenleyin.  
  
2.  Yeni bir ekleme `<Catalog href="..."/>` ek şema dizine işaret öğesi.  
  
3.  Değişikliklerinizi kaydedin.  
  
     Katalog otomatik olarak geri yüklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Düzenleyicisi](../xml-tools/xml-editor.md)