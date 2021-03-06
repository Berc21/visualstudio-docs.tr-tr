---
title: "Bir dil sunucusu Protokolü uzantısı ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/14/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52f12785-1c51-4c2c-8228-c8e10316cd83
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ea93ddee9c47f80322db2403aeecc0fb7dddb209
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="adding-a-language-server-protocol-extension"></a>Dil sunucu protokolü uzantısına ekleme

Dil sunucusu Protokolü (LSP) dil çeşitli kod düzenleyicileri hizmet özellikleri sağlamak için kullanılan JSON RPC v2.0 biçiminde ortak bir protokolle ' dir. Geliştiriciler protokolünü kullanarak dil IntelliSense, hata tanılama gibi hizmet özellikleri sağlamak için bulma tüm başvurular, vb. LSP destek çeşitli kod düzenleyiciler için tek bir dil sunucusunun yazabilirsiniz. Geleneksel olarak, Visual Studio'da dil Hizmetleri ya da eklenebilir temel işlevler söz dizimi vurgulama gibi ya da Visual Studio genişletilebilirlik API kümesini kullanarak özel dil Hizmetleri yazarak sağlamak üzere TextMate dilbilgisi dosyalarını kullanmak için daha zengin veri sağlar. Şimdi, LSP üçüncü bir seçenek sunar desteği.

![Visual Studio'da dil sunucusu Protokolü Hizmeti](media/lsp-service-in-VS.png)

## <a name="language-server-protocol"></a>Dil sunucusu Protokolü

Protokolün kendisi hakkında daha fazla bilgi için belgelere bakın [burada](https://github.com/Microsoft/language-server-protocol). Visual Studio'nun dil sunucusu protokolü önizlemede uygulamasıdır ve Destek Deneysel olarak düşünülmelidir. Önizleme sürümü uzantı biçimindedir ([dil sunucu Protokolü istemci Önizleme](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview)), **ancak bu uzantı yalnızca önizleme kanal, Visual Studio yüklenebilir**. Visual Studio daha sonraki bir sürümüne dil sunucu protokolü, aynı zamanda Önizleme bayrağı bırakılacak için yerleşik destek içerir. **Üretim için Önizleme kullanmamalısınız.**

Nasıl oluşturulacağı hakkında daha fazla bilgi için bir örnek dil sunucu ya da Visual Studio koda var olan bir dil sunucusu tümleştirme belgelerine bakın [burada](https://code.visualstudio.com/docs/extensions/example-language-server).

![Dil sunucu protokol uygulanması](media/lsp-implementation.png)

Bu makalede, bir dil LSP tabanlı sunucusu kullanan bir Visual Studio uzantısı oluşturmayı açıklar. Zaten bir dil LSP tabanlı sunucu geliştirilmiştir ve yalnızca Visual Studio'ya tümleştirmek istediğiniz varsayar.

Visual Studio içinde desteği için aşağıdaki mekanizmalar aracılığıyla (Visual Studio) istemci dil sunucuları iletişim kurabilir:

* Standart giriş/çıkış akışları
* Adlandırılmış Kanallar
* Yuva

Visual Studio'da bu için destek ve LSP amacı Visual Studio ürün parçası olmayan yerleşik dil Hizmetleri ' dir. Varolan dil hizmetler (C# ' ta) Visual Studio genişletmek için tasarlanmamıştır. Mevcut diller genişletmek için dil hizmetin genişletilebilirlik Kılavuzu'na bakın (örneğin, ["Roslyn".NET derleyici platformu](../extensibility/dotnet-compiler-platform-roslyn-extensibility.md)).

## <a name="language-server-protocol-features-supported"></a>Desteklenen dil sunucusu protokolü özellikleri

Aşağıdaki LSP özellikleri Visual Studio'da kadarki desteklenir:

İleti | Visual Studio'da desteğine sahip
--- | ---
başlatma | Evet
başlatıldı | Evet
kapatma | Evet
Çıkış | Evet
$/ cancelRequest | Evet
Pencere/showMessage | Evet
window/showMessageRequest | Evet
Pencere/logMessage | Evet
telemetri/olay |
İstemci/registerCapability |
İstemci/unregisterCapability |
workspace/didChangeConfiguration | Evet
workspace/didChangeWatchedFiles | Evet
Çalışma alanı/simgesi | Evet
workspace/executeCommand | Evet
workspace/applyEdit | Evet
textDocument/publishDiagnostics | Evet
textDocument/didOpen | Evet
textDocument/didChange | Evet
textDocument/willSave |
textDocument/willSaveWaitUntil |
textDocument/didSave | Evet
textDocument/didClose | Evet
textDocument/tamamlama | Evet
Tamamlama/Çöz | Evet
textDocument/vurgulu | Evet
textDocument/signatureHelp | Evet
textDocument/başvuruları | Evet
textDocument/documentHighlight |
textDocument/documentSymbol | Evet
textDocument ve biçimlendirme | Evet
textDocument/rangeFormatting | Evet
textDocument/onTypeFormatting |
textDocument/tanımı | Evet
textDocument/codeAction | Evet
textDocument/codeLens |
codeLens/resolve |
textDocument/documentLink |
documentLink/resolve |
textDocument/yeniden adlandır | Evet

## <a name="getting-started"></a>Başlarken

### <a name="create-a-vsix-project"></a>VSIX proje oluşturma

Bir dil LSP tabanlı sunucusu kullanarak bir dil hizmeti uzantı oluşturmak için ilk olarak olduğundan emin olun **Visual Studio uzantısı geliştirme** VS Örneğiniz için yüklü iş yükü.

Sonraki giderek yeni bir boş VSIXProject oluşturma **dosya** > **yeni proje** > **Visual C#**  >   **Genişletilebilirlik** > **VSIX proje**:

![create vsix project](media/lsp-vsix-project.png)

Önizleme sürümü için bir VSIX formunda LSP VS desteği olacaktır ([Microsoft.VisualStudio.LanguageServer.Client.Preview](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview)). LSP dil sunucuları kullanarak bir uzantı oluşturmak ister uzantısı geliştiriciler bu VSIX üzerinde bir bağımlılık almanız gerekir. Bu nedenle, bir dil sunucu uzantısını yüklemek isteyen müşteriler **dil sunucu Protokolü istemci Önizleme VSIX yüklemeniz gerekir.**

VSIX bağımlılık tanımlamak için VSIX için VSIX bildirim Tasarımcısı (projenizdeki source.extension.vsixmanifest dosyasını çift tıklatarak) açın ve gidin **bağımlılıkları**:

![Dil sunucu Protokolü İstemcisi başvuru ekleyin](media/lsp-reference-lsp-dependency.png)

Aşağıdaki gibi yeni bir bağımlılık oluşturun:

![Dil sunucu Protokolü istemci bağımlılık tanımlayın](media/lsp-define-lsp-dependency.png)

* **Kaynak**: el ile tanımlanmış
* **Ad**: dil sunucu Protokolü istemci Önizleme
* **Tanımlayıcı**: Microsoft.VisualStudio.LanguageServer.Client.Preview
* **Sürüm aralığı**: [1.0,2.0)
* **Çözümlenen bağımlılık nasıl yapıldığını**: kullanıcı tarafından yüklenen
* **Karşıdan yükleme URL'si**: [https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview)

> [!NOTE]
> **Yükleme URL'si** uzantınızı yükleyen kullanıcılar gerekli bağımlılık yükleme bilmesi doldurulması gerekir.

### <a name="language-server-and-runtime-installation"></a>Dil sunucu ve çalışma zamanı yükleme

Varsayılan olarak, Visual Studio'da LSP tabanlı dil sunucuları desteklemek için oluşturulmuş uzantıları dil sunucuları veya bunları yürütmek için gereken çalışma zamanları içermez. Uzantı geliştiricilerine dil sunucuları ve gerekli çalışma zamanları dağıtmaktan sorumludur. Bunu yapmak için birkaç yolu vardır:

* Dil sunucuları içerik dosyaları içinde VSIX içine katıştırılabilir.
* Dil sunucusunu yüklemek için bir MSI oluşturma ve/veya çalışma zamanları gerekli.
* Yönergeler Market bildiren kullanıcıların üzerinde çalışma zamanları ve dil sunucuları edinme sağlar.

### <a name="textmate-grammar-files"></a>TextMate dilbilgisi dosyaları

LSP diller için metin renklendirme sağlamak nasıl belirtimi içermez. Visual Studio'da diller için özel renklendirme sağlamak için Uzantı geliştiricilerine TextMate dilbilgisi dosyasını kullanabilirsiniz. Özel TextMate dilbilgisi veya tema dosyaları eklemek için aşağıdaki adımları izleyin:

1. Uzantınızı içinde "Aynı" adlı bir klasör oluşturun (veya seçtiğiniz herhangi bir ad olabilir).

2. "Aynı" klasörü içinde herhangi bir *.tmlanguage, *.plist, *.tmtheme veya istediğiniz özel renklendirme sağlar *.json dosyaları içerir.

3. Sağ tıklatın ve dosyaları **özellikleri**. Yapı eylemini **içerik** ve **Include in VSIX** özelliğinin true.

4. .Pkgdef dosyası oluşturun ve aşağıdakine benzer bir satır ekleyin:

  ```xml
  [$RootKey$\TextMate\Repositories]
  "MyLang"="$PackageFolder$\Grammars"
  ```

5. Sağ tıklatın ve dosyaları **özellikleri**. Yapı eylemini **içerik** ve **Include in VSIX** özelliğinin true.

Önceki adımları tamamladıktan sonra bir "Aynı" klasörü paket yüklemek için eklenen dizini depo kaynağı olarak adlandırılan 'MyLang' ('MyLang' Kesinleştirme için yalnızca bir ad ve benzersiz bir dize olabilir). Tüm aynı (.tmlanguage dosyaları) ve bu dizinde tema dosyaları (.tmtheme dosyaları) potentials toplanmış ve TextMate ile sağlanan yerleşik aynı yerini alır. Dilbilgisi dosyanın bildirilen uzantıları açılmakta dosya uzantısı eşleşiyorsa TextMate adım.

## <a name="creating-a-simple-language-client"></a>Basit bir dil istemci oluşturma

### <a name="main-interface---ilanguageclientdotnetapimicrosoftvisualstudiolanguageserverclientilanguageclientviewvisualstudiosdk-2017"></a>Ana arabirimi - [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)

VSIX projenizi oluşturduktan sonra aşağıdaki NuGet paketleri projenize ekleyin:

* [Microsoft.VisualStudio.LanguageServer.Client](https://www.nuget.org/packages/Microsoft.VisualStudio.LanguageServer.Client)

> [!NOTE]
> Yukarıdaki adımları tamamladıktan sonra NuGet paketi bir bağımlılık alırken Newtonsoft.Json ve StreamJsonRpc paketler, projenize eklenir. **Visual Studio sürümünde yeni sürümler yüklü emin olmadığınız sürece bu güncelleştirme paketleri değil, uzantısı hedeflerinizi**. Derlemeleri eklenmez, VSIX--bunun yerine, bunlar Visual Studio yükleme dizininden çekilmesi. Bir kullanıcının makinesinde uzantınızı yüklenenler değerinden daha yeni bir sürümü derlemeler başvuran varsa *çalışmaz*.

Daha sonra uygulayan yeni bir sınıf oluşturabilirsiniz [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017) arabirimi, bir dil LSP tabanlı sunucuya bağlanan dil istemciler için gerekli ana arabirim.

Bir örnek verilmiştir:

```csharp
namespace MockLanguageExtension
{
    [ContentType("bar")]
    [Export(typeof(ILanguageClient))]
    public class BarLanguageClient : ILanguageClient
    {
        public string Name => "Bar Language Extension";

        public IEnumerable<string> ConfigurationSections => null;

        public object InitializationOptions => null;

        public IEnumerable<string> FilesToWatch => null;

        public event AsyncEventHandler<EventArgs> StartAsync;
        public event AsyncEventHandler<EventArgs> StopAsync;

        public async Task<Connection> ActivateAsync(CancellationToken token)
        {
            await Task.Yield();

            ProcessStartInfo info = new ProcessStartInfo();
            info.FileName = Path.Combine(Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location), "Server", @"MockLanguageServer.exe");
            info.Arguments = "bar";
            info.RedirectStandardInput = true;
            info.RedirectStandardOutput = true;
            info.UseShellExecute = false;
            info.CreateNoWindow = true;

            Process process = new Process();
            process.StartInfo = info;

            if (process.Start())
            {
                return new Connection(process.StandardOutput.BaseStream, process.StandardInput.BaseStream);
            }

            return null;
        }

        public async Task OnLoadedAsync()
        {
            await StartAsync?.InvokeAsync(this, EventArgs.Empty);
        }

        public async Task OnServerInitializeFailedAsync(Exception e)
        {
            return Task.CompletedTask;
        }

        public async Task OnServerInitializedAsync()
        {
            return Task.CompletedTask;
        }
    }
}
```

Uygulanması gereken ana yöntemler şunlardır [OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017) ve [ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017). [OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017) Visual Studio uzantınızı yüklü ve dil sunucunuz başlatılması için hazır olduğunda çağrılır. Bu yöntemde, çağırabilirsiniz [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) hemen dil sunucunun başlatılması, veya ilave bir mantık yapın ve çağırma göstermek için temsilci [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) daha sonra. **Dil sunucunuzu etkinleştirmek için belirli bir noktada StartAsync çağırmanız gerekir.**

[ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017) sonunda çağırarak çağrılan yöntem [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) temsilci; dil sunucuyu başlatır ve bağlantı kurmak için mantığını içerir. Sunucuya yazma ve sunucudan okuma akışları içeren bir bağlantı nesnesi iade edilmesi gerekir. Burada oluşturulan tüm özel durumları yakalanan ve Visual Studio'da bir bilgi çubuğu iletisi yoluyla kullanıcıya görüntülenir.

### <a name="activation"></a>Etkinleştirme

Dil istemci sınıfınız uygulandıktan sonra onu nasıl Visual Studio'ya yüklenen ve etkinleştirilen tanımlamak iki öznitelik tanımlamak gerekir:

```csharp
  [Export(typeof(ILanguageClient))]
  [ContentType("bar")]
```

### <a name="mef"></a>MEF

Visual Studio kullanan [MEF](https://github.com/Microsoft/vs-mef/blob/master/doc/index.md) (Genişletilebilirlik Çerçevesi genişletilebilirlik noktaları yönetmek için yönetilen). [Verme](https://msdn.microsoft.com/library/system.componentmodel.composition.exportattribute(v=vs.110).aspx) öznitelik, Visual Studio için bu sınıf uzantısı noktası olarak toplanmış ve gerekir uygun zamanda yüklü olduğunu gösterir.

MEF kullanmak için VSIX bildiriminde bir varlık olarak MEF tanımlamalısınız.

VSIX bildirim Tasarımcısı'nı açın ve gidin **varlıklar** sekmesi:

![MEF varlık ekleme](media/lsp-add-asset.png)

Yeni bir varlık oluşturmak için Yeni'yi tıklatın:

![MEF varlık tanımlayın](media/lsp-define-asset.png)

* **Type**: Microsoft.VisualStudio.MefComponent
* **Kaynak**: geçerli çözümdeki bir proje ile
* **Proje**: [projenizi]

### <a name="content-type-definition"></a>İçerik türü tanımı

Şu anda LSP tabanlı dil sunucu uzantısı yüklemek için tek dosya içerik türüne göre yoludur. Diğer bir deyişle, dil istemci sınıfınız tanımlarken (hangi uygulayan [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)), türlerini tanımlamak gerekir, dosyaları açılır, uzantınızı yüklemek neden olur. Ardından, tanımlanmış içerik türüyle eşleşen hiçbir dosya açıldıysa, uzantınızı yüklenmeyecek.

Bu, bir veya daha fazla ContentTypeDefinition sınıfları tanımlama üzerinden yapılır:

```csharp
namespace MockLanguageExtension
{
    public class BarContentDefinition
    {
        [Export]
        [Name("bar")]
        [BaseDefinition(CodeRemoteContentDefinition.CodeRemoteContentTypeName)]
        internal static ContentTypeDefinition BarContentTypeDefinition;


        [Export]
        [FileExtension(".bar")]
        [ContentType("bar")]
        internal static FileExtensionToContentTypeDefinition BarFileExtensionDefinition;
    }
}
```

Önceki örnekte, bir içerik türü tanımı içinde sona dosyaları için oluşturulan `.bar` dosya uzantısı. İçerik türü tanımı "çubuğu" adı verilir ve **gerekir** öğesinden türetilen [CodeRemoteContentTypeName](/dotnet/api/microsoft.visualstudio.languageserver.client.coderemotecontentdefinition.coderemotecontenttypename?view=visualstudiosdk-2017).

Bir içerik türü tanımı eklendikten sonra daha sonra dil istemci sınıfı dil İstemci uzantı yüklemek ne zaman tanımlayabilirsiniz:

```csharp
    [ContentType("bar")]
    [Export(typeof(ILanguageClient))]
    public class BarLanguageClient : ILanguageClient
    {
    }
```

LSP dil sunucuları desteği eklemek için Visual Studio'da kendi proje sistem uygulamaktır gerektirmez. Müşterilerin, tek bir dosya veya klasör dil hizmetinizi kullanmaya başlamak için Visual Studio'da açabilirsiniz. LSP dil sunucuları tasarlanmıştır yalnızca açık klasör/dosya senaryolarda çalışmaya aslında desteği. Özel proje sistem uygulanmışsa (ayarlar gibi) bazı özellikler çalışmaz.

## <a name="advanced-features"></a>Gelişmiş Özellikler

### <a name="settings"></a>Ayarlar

Özel dil sunucusuna özel ayarları LSP destek Visual Studio'da Önizleme sürümü için kullanılabilir, ancak hala geliştirilen sürecinde desteği. Ayarları ne dil sunucunun destekler ve genellikle nasıl dil sunucunun veri yayar denetlemek için özeldir. Örneğin, bir dil sunucu rapor edilen hata sayısı için bir ayar olabilir. Uzantı yazarlar belirli projeler için kullanıcılar tarafından değiştirilebilir bir varsayılan değer tanımlayın.

LSP dil hizmeti uzantınızı ayarları desteği eklemek için bu adımları izleyin:

1. Bir JSON dosyası (örneğin, "MockLanguageExtensionSettings.json"), ayarlarını ve varsayılan değerlerini içeren projenize ekleyin. Örneğin:

  ```json
  {
    "foo.maxNumberOfProblems": -1
  }
  ```
2. JSON dosyasını sağ tıklatın ve seçin **özellikleri**. Değişiklik **yapı** eylem "İçerik" ve "VSIX Ekle ' özelliğini true.

3. Uygulama ConfigurationSections ve JSON dosyasında tanımlanan ayarları için önekleri listesini döndürmek (Visual Studio kod, bu eşleştirme package.json yapılandırma bölümü adına):

  ```csharp
  public IEnumerable<string> ConfigurationSections
  {
      get
      {
          yield return "foo";
      }
  }
  ```
4. Bir .pkgdef dosyası projeye ekleyin (yeni metin dosyası ekleyin ve .pkgdef için dosya uzantısı değiştirme). Pkgdef dosyası bu bilgileri içermelidir:

  ```xml
    [$RootKey$\OpenFolder\Settings\VSWorkspaceSettings\[settings-name]]
    @="$PackageFolder$\[settings-file-name].json"
  ```

5. .Pkgdef dosyasını sağ tıklatın ve seçin **özellikleri**. Değişiklik **yapı** eylem "İçerik" ve "VSIX de dahil" özelliğini true.

6. Açık `source.extension.vsixmanifest` dosyası ve bir varlığı Ekle **varlık** sekmesi:

  ![VSPackage varlık Düzenle](media/lsp-add-vspackage-asset.png)

  * **Type**: Microsoft.VisualStudio.VsPackage
  * **Kaynak**: dosya sistemi üzerindeki dosya
  * **Yol**: [pkgdef dosyanızın yolu]

### <a name="user-editing-of-settings-for-a-workspace"></a>Kullanıcı bir çalışma alanı ayarlarını düzenleme

1. Kullanıcı, sunucunun sahip olduğu dosyaları içeren bir çalışma alanı açılır.
2. Kullanıcı bir dosyayı "VSWorkspaceSettings.json" adlı ".vs" klasöründe ekler.
3. Kullanıcı VSWorkspaceSettings.json dosya sunucunun sağladığı bir ayar için bir satır ekler. Örneğin:

  ```json
  {
    "foo.maxNumberOfProblems": 10
  }
  ```
### <a name="enabling-diagnostics-tracing"></a>Tanılama izlemeyi etkinleştirme
Tanılama izleme istemci ve sorunları hata ayıklarken yararlı olabilir sunucusu arasındaki tüm iletileri çıktısını almak için etkinleştirilebilir.  Tanılama izleme etkinleştirmek için aşağıdakileri yapın:

1. "VSWorkspaceSettings.json" çalışma alanı ayarları dosyası oluşturun veya açın ("Çalışma alanı ayarlarını düzenleme kullanıcı" bakın).
2. Ayarları json dosyasında aşağıdaki satırı ekleyin:

```json
{
    "foo.server.trace": "Off"
}
```

İzleme ayrıntı için üç olası değerler şunlardır:
* "Kapalı": tamamen devre dışı izleme
* "İletileri": izleme açıldığında ancak tek yöntem adı ve yanıt kimliği izlenen.
* "Ayrıntılı": açık; izleme izlenen tüm rpc iletisi.

İzleme içerik zaman açık olduğundan, "% temp%\VisualStudio\LSP" dizinindeki bir dosyaya yazılır.  Günlük adlandırma biçimdedir `[LanguageClientName]-[Datetime Stamp].log`.  Şu anda, izleme yalnızca klasör Aç senaryoları için etkinleştirilebilir.  Bir dil Sunucusu'nu etkinleştirmek için tek bir dosyayı açma Tanılama izleme desteği yok.

### <a name="custom-messages"></a>Özel iletileri

Geçirme iletileri ve standart dil sunucusu protokolü parçası olmayan alıcı iletileri dil sunucusundan kolaylaştırmak için API'ler yerinde vardır. Özel iletileri işlemek için uygulama [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) dil istemci sınıfınız arabiriminde. [VS-StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md) kitaplığı dil istemci ve dil sunucu arasında özel iletileri iletmek için kullanılır. LSP dil istemci uzantısı yalnızca herhangi diğer Visual Studio uzantısı gibi olduğundan, (LSP tarafından desteklenmez) ek özellikleri eklemek Visual Studio'ya (diğer Visual Studio API kullanarak), uzantı özel iletileri üzerinden karar verebilirsiniz.

#### <a name="receiving-custom-messages"></a>Özel ileti alma

Dil sunucusundan özel iletileri almak için uygulama [CustomMessageTarget](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.custommessagetarget?view=visualstudiosdk-2017) özelliği [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) ve özel iletilerinizi nasıl ele alınacağını bildiği bir nesne döndürür . Aşağıdaki örnek:

```csharp
internal class MockCustomLanguageClient : MockLanguageClient, ILanguageClientCustomMessage
{
    private JsonRpc customMessageRpc;

    public MockCustomLanguageClient() : base()
    {
        CustomMessageTarget = new CustomTarget();
    }

    public object CustomMessageTarget
    {
        get;
        set;
    }

    public class CustomTarget
    {
        public void OnCustomNotification(JToken arg)
        {
            // Provide logic on what happens OnCustomNotification is called from the language server
        }

        public string OnCustomRequest(string test)
        {
            // Provide logic on what happens OnCustomRequest is called from the language server
        }
    }
}
```

#### <a name="sending-custom-messages"></a>Özel ileti gönderme

Dil sunucuya özel iletileri göndermek için uygulama [AttachForCustomMessageAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.attachforcustommessageasync?view=visualstudiosdk-2017) yöntemi [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017). Dil sunucunuz başlatılan ve iletileri almaya hazır olduğunda bu yöntem çağrılır. A [JsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/src/StreamJsonRpc/JsonRpc.cs) nesne dilini kullanarak sunucu ileti göndermek için sonra koruyabilirsiniz bir parametre olarak geçirilen [VS StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md) API'leri. Aşağıdaki örnek:

```csharp
internal class MockCustomLanguageClient : MockLanguageClient, ILanguageClientCustomMessage
{
    private JsonRpc customMessageRpc;

    public MockCustomLanguageClient() : base()
    {
        CustomMessageTarget = new CustomTarget();
    }

    public async Task AttachForCustomMessageAsync(JsonRpc rpc)
    {
        await Task.Yield();

        this.customMessageRpc = rpc;
    }

    public async Task SendServerCustomNotification(object arg)
    {
        await this.customMessageRpc.NotifyWithParameterObjectAsync("OnCustomNotification", arg);
    }

    public async Task<string> SendServerCustomMessage(string test)
    {
        return await this.customMessageRpc.InvokeAsync<string>("OnCustomRequest", test);
    }
}
```

### <a name="middle-layer"></a>Orta katman

Bazen bir uzantı Geliştirici gönderilen ve dil sunucudan alınan LSP iletileri izlemesine isteyebilirsiniz. Örneğin, bir uzantı Geliştirici belirli bir LSP iletiyi gönderilen ileti parametre değiştirmek istediğiniz, veya bir LSP özelliği (örneğin tamamlamalar) dil sunucusundan döndürülen sonuçlar değiştirin. Bu gerekli olduğunda, Uzantı geliştiricilerine LSP iletileri izlemesine MiddleLayer API'yi kullanabilirsiniz.

Her LSP ileti kişiler tarafından ele için kendi orta katman arabirimine sahiptir. Belirli bir iletiyi engellemek için bu iletiyi orta katman arabirimini uygulayan bir sınıf oluşturun. Ardından, uygulama [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) arabirim dil istemci sınıfınızda ve, nesne örneği döndürür [MiddleLayer](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.middlelayer?view=visualstudiosdk-2017) özelliği. Aşağıdaki örnek:

```csharp
public class MockLanguageClient: ILanguageClient, ILanguageClientCustomMessage
{
    public object MiddleLayer => MiddleLayerProvider.Instance;

    private class MiddleLayerProvider : ILanguageClientWorkspaceSymbolProvider
    {
        internal readonly static MiddleLayerProvider Instance = new MiddleLayerProvider();

        private MiddleLayerProvider()
        {
        }

        public async Task<SymbolInformation[]> RequestWorkspaceSymbols(WorkspaceSymbolParams param, Func<WorkspaceSymbolParams, Task<SymbolInformation[]>> sendRequest)
        {
            // Send along the request as given
            SymbolInformation[] symbols = await sendRequest(param);

            // Only return symbols that are "files"
            return symbols.Where(sym => string.Equals(new Uri(sym.Location.Uri).Scheme, "file", StringComparison.OrdinalIgnoreCase)).ToArray();
        }
    }
}
```

Orta katman halen geliştirilme ve henüz kapsamlı özelliğidir.

## <a name="sample-lsp-language-server-extension"></a>Örnek LSP dil server uzantısı

Visual Studio'da LSP İstemcisi API kullanarak bir örnek uzantısı kaynak kodunu görmek için VSSDK genişletilebilirliği örnekleri bkz [LSP örnek](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/LanguageServerProtocol).

## <a name="faq"></a>SSS

**Visual Studio'da daha zengin özellik desteği sağlamak üzere LSP dil sunucum desteklemek için özel Proje sistem oluşturmak ister misiniz nasıl ı gidin, bunu hakkında?**

Visual Studio'da dil LSP tabanlı sunucular için destek kullanır [Klasör Aç özelliği](https://blogs.msdn.microsoft.com/visualstudio/2016/04/12/open-any-folder-with-visual-studio-15-preview/) ve özel Proje sistem gerektirmeyecek şekilde özel olarak tasarlanmıştır. Yönergeleri izleyerek kendi özel Proje sistem oluşturabilirsiniz [burada](https://github.com/Microsoft/VSProjectSystem), ancak ayarları gibi bazı özellikler çalışmayabilir. Varsayılan başlatma mantığı LSP dil sunucuları için özel Proje sistemi kullanıyorsanız, özel mantık dil sunucu can emin olmak için başlatma sırasında sağlamanız gerekebilir için şu anda açılmakta klasörünün kök klasör konumunu geçirmektir düzgün şekilde başlatın.

**Hata ayıklayıcı desteği nasıl eklenir?**

Biz desteği sağlayacağı [ortak protokolü hata ayıklama](https://code.visualstudio.com/docs/extensionAPI/api-debugging) gelecek bir sürümde.

**Bir VS desteklenen dil hizmeti yüklenmiş (örneğin, JavaScript) ise, hala (linting gibi) ek özellikler sunar LSP dil sunucu uzantısı yükleyebilirim?**

Evet, ancak tüm özellikleri düzgün çalışacaktır. Ultimate LSP dil sunucu uzantıları için Visual Studio tarafından yerel olarak desteklenen dil hizmetlerini etkinleştirmek için belirtilir. Ek destek LSP dil sunucuları kullanarak uzantıları oluşturabilirsiniz, ancak bazı özellikler (örneğin, IntelliSense) sorunsuz bir deneyim olmaz. Genel olarak, LSP dil sunucu uzantıları var olanları genişletme değil, yeni dil deneyimleri sağlamak için kullanılması önerilir.

**Tamamlanan LSP dil sunucum VSIX burada yayımlanacak?**

Market yönergelere bakın [burada](walkthrough-publishing-a-visual-studio-extension.md).
