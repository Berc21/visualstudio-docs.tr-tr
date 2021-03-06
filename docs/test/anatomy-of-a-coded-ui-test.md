---
title: "Visual Studio'da kodlanmış UI testinin anatomisi | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- coded UI tests
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 71e513978eb8d84ef2b8ac5ebea4105382808222
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="anatomy-of-a-coded-ui-test"></a>Kodlanmış UI testinin anatomisi

Kodlanmış UI test projesinde Kodlanmış bir UI testi oluşturduğunuzda, birkaç dosyaları çözüme eklenir. Bu makalede dosyaları hakkında bilgi sağlar.

## <a name="contents-of-a-coded-ui-test"></a>Kodlanmış UI testi içeriğini

Kodlanmış bir UI testi, oluşturduğunuzda **kodlanmış UI Test oluşturucusunu** test ve ayrıca test yöntemleri, parametreleri ve altındaki tüm testler için onayların kullanıcı arabiriminin bir harita oluşturur. Ayrıca, her test için bir sınıf dosyası oluşturur.

|Dosya|İçindekiler|Düzenlenebilir mi?|
|----------|--------------|---------------|
|[UIMap.Designer.cs](#UIMapDesignerFile)|[Bildirimler bölümü](#UIMapDesignerFile)<br /><br /> [UIMap sınıfı](#UIMapClass) (kısmi, otomatik olarak oluşturulan)<br /><br /> [Yöntemler](#UIMapMethods)<br /><br /> [Özellikler](#UIMapProperties)|Hayır|
|[UIMap.cs](#UIMapCS)|[UIMap sınıfı](#UIMapCS) (kısmi)|Evet|
|[CodedUITest1.cs](#CodedUITestCS)|[Codeduıtest1 sınıfı](#CodedUITestCS)<br /><br /> [Yöntemler](#CodedUITestMethods)<br /><br /> [Özellikler](#CodedUITestProperties)|Evet|
|[UIMap.uitest](#UIMapuitest)|UI testi için XML eşlemesi.|Hayır|

###  <a name="UIMapDesignerFile"></a> UIMap.Designer.cs
 Bu dosya tarafından otomatik olarak oluşturulan kodu içerir **kodlanmış UI Test oluşturucusunu** test oluşturulduğunda. Bu dosya Ekle veya Değiştir kodu bir dosya olmaması test değişiklikler, her zaman yeniden oluşturulur.

#### <a name="declarations-section"></a>Bildirimler bölümü
 Bu bölüm aşağıdaki bildirimler için bir Windows kullanıcı arabirimini içerir.

```csharp
using System;
using System.CodeDom.Compiler;
using System.Collections.Generic;
using System.Drawing;
using System.Text.RegularExpressions;
using System.Windows.Input;
using Microsoft.VisualStudio.TestTools.UITest.Extension;
using Microsoft.VisualStudio.TestTools.UITesting;
using Microsoft.VisualStudio.TestTools.UITesting.WinControls;
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Keyboard = Microsoft.VisualStudio.TestTools.UITesting.Keyboard;
using Mouse = Microsoft.VisualStudio.TestTools.UITesting.Mouse;
using MouseButtons = System.Windows.Forms.MouseButtons;
```

 <xref:Microsoft.VisualStudio.TestTools.UITesting.WinControls> Ad alanı, bir Windows kullanıcı arabirimini (UI) eklenir. Bir Web sayfası kullanıcı Arabirimi için ad alanı olacaktır <xref:Microsoft.VisualStudio.TestTools.UITesting.HtmlControls>; bir Windows Presentation Foundation Arabirimi için ad alanı olacaktır <xref:Microsoft.VisualStudio.TestTools.UITesting.WpfControls>.

####  <a name="UIMapClass"></a> UIMap sınıfı
 Sonraki bölüm dosyasının <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> sınıfı.

```csharp
[GeneratedCode("Coded UITest Builder", "10.0.21221.0")]
public partial class UIMap
```

Sınıf kodu ile başlayan bir <xref:System.CodeDom.Compiler.GeneratedCodeAttribute> kısmi bir sınıf olarak bildirilmiş sınıfa uygulanan öznitelik. Bu dosyadaki her sınıfa öznitelik de geçerli dikkat edin. Bu sınıf için daha fazla içerebilecek dosya `UIMap.cs`, hangi ele alınmıştır daha sonra.

Oluşturulan `UIMap` sınıfı, her yöntem test zaman kaydedildiği belirtilen için kod içerir.

```csharp
public void LaunchCalculator()
public void AddItems()
public void VerifyTotal()
public void CleanUp()
```

Bu bölümü <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> sınıfı yöntemleri için gereken her bir özellik için oluşturulan kodu da içerir.

```csharp
public virtual LaunchCalculatorParams LaunchCalculatorParams
public virtual AddItemsParams AddItemsParams
public virtual VerifyTotalExpectedValues VerifyTotalExpectedValues
public virtual CalculateItemsParams CalculateItemsParams
public virtual VerifyMathAppTotalExpectedValues
    VerifyMathAppTotalExpectedValues
public UIStartMenuWindow UIStartMenuWindow
public UIRunWindow UIRunWindow
public UICalculatorWindow UICalculatorWindow
public UIStartWindow UIStartWindow
public UIMathApplicationWindow UIMathApplicationWindow
```

#####  <a name="UIMapMethods"></a> UIMap yöntemleri
 Her yöntem benzer bir yapıya sahip `AddItems()` yöntemi. Bu kodu daha anlaşılır olması eklemek için satır sonları ile birlikte sunulan altında daha ayrıntılı açıklanmıştır.

```csharp
/// <summary>
/// AddItems - Use 'AddItemsParams' to pass parameters into this method.
/// </summary>
public void AddItems()
{
    #region Variable Declarations
    WinControl uICalculatorDialog =
        this.UICalculatorWindow.UICalculatorDialog;
    WinEdit uIItemEdit =
        this.UICalculatorWindow.UIItemWindow.UIItemEdit;
    #endregion

    // Type '{NumPad7}' in 'Calculator' Dialog
    Keyboard.SendKeys(uICalculatorDialog,
        this.AddItemsParams.UICalculatorDialogSendKeys,
        ModifierKeys.None);

    // Type '{Add}{NumPad2}{Enter}' in 'Unknown Name' text box
    Keyboard.SendKeys(uIItemEdit,
        this.AddItemsParams.UIItemEditSendKeys,
        ModifierKeys.None);
}
```

Her bir yöntemin tanımı için Özet açıklama hangi sınıfın bu yöntem için parametre değerleri için kullanılacağını söyler. Bu durumda olan `AddItemsParams` daha sonra dosyasında tanımlanan sınıfı `UIMap.cs` dosya ve ayrıca tarafından döndürülen değer türü olduğu `AddItemsParams` özelliği.

 Kodu yöntemi en üstte bir `Variable Declarations` yerel değişkenler için kullanıcı arabirimini tanımlar bölge nesneleri yöntemi tarafından kullanılır.

 Bu yöntemde her ikisi de `UIItemWindow` ve `UIItemEdit` kullanılarak erişilen özellikleri `UICalculatorWindow` daha sonra dosyasında tanımlanan sınıfı `UIMap.cs` dosya.

 Sonraki özelliklerini kullanarak metin klavyeden hesaplayıcı uygulamaya gönder satırları olan `AddItemsParams` nesnesi.

 `VerifyTotal()` Yöntemi benzer bir yapıya sahiptir ve aşağıdaki onay kodunu içerir:

```csharp
// Verify that 'Unknown Name' text box's property 'Text' equals '9. '
Assert.AreEqual(
    this.VerifyTotalExpectedValues.UIItemEditText,
    uIItemEdit.Text);
```

 Windows hesap makinesi uygulama geliştiricisi denetimi için genel kullanıma açık bir ad sağlamadığından metin kutusu adı bilinmeyen olarak listelenir. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A?displayProperty=fullName> Yöntem gerçek değer testin başarısız olmasına neden olacağından beklenen değer ile eşit olmadığında başarısız olur. Ayrıca, beklenen değer boşluk bırakarak bir Ondalık ayırıcının içerdiğine dikkat edin. Bu belirli test işlevlerini değiştirmek amacıyla varsa, ondalık ayırıcıdan ve boşluğa izin vermesi gerekir.

#####  <a name="UIMapProperties"></a> UIMap özellikleri
 Her bir özellik için de sınıfı standart kodudur. Aşağıdaki kod `AddItemsParams` özelliği kullanılıyor `AddItems()` yöntemi.

```csharp
public virtual AddItemsParams AddItemsParams
{
    get
    {
        if ((this.mAddItemsParams == null))
        {
            this.mAddItemsParams = new AddItemsParams();
        }
        return this.mAddItemsParams;
    }
}
```

 Özellik adlı özel bir yerel değişken kullanıyor bildirimi `mAddItemsParams` döndürmeden önce değeri tutmak için. Özellik adı ve döndürdüğü nesnesi için sınıf adı aynıdır. Sınıf daha sonra tanımlanan `UIMap.cs` dosya.

 Bir özellik tarafından döndürülen her sınıf benzer şekilde yapılandırılmıştır. Aşağıdaki `AddItemsParams` sınıfı:

```csharp
/// <summary>
/// Parameters to be passed into 'AddItems'
/// </summary>
[GeneratedCode("Coded UITest Builder", "10.0.21221.0")]
public class AddItemsParams
{
    #region Fields
    /// <summary>
    /// Type '{NumPad7}' in 'Calculator' Dialog
    /// </summary>
    public string UICalculatorDialogSendKeys = "{NumPad7}";

    /// <summary>
    /// Type '{Add}{NumPad2}{Enter}' in 'Unknown Name' text box
    /// </summary>
    public string UIItemEditSendKeys = "{Add}{NumPad2}{Enter}";
    #endregion
}
```

Tüm sınıflarda olduğu gibi `UIMap.cs` dosyası, bu sınıf ile başlayan <xref:System.CodeDom.Compiler.GeneratedCodeAttribute>. Bu küçük sınıf bir `Fields` parametreleri olarak kullanılmak üzere dize tanımlayan bölge <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard.SendKeys%2A?displayProperty=fullName> kullanılır yöntemi `UIMap.AddItems()` daha önce bahsedilen yöntemi. Bu parametreleri kullanılan yöntemi çağrılmadan önce bu dize alanlarındaki değerleri değiştirmek üzere kod yazabilirsiniz.

###  <a name="UIMapCS"></a> UIMap.cs
 Varsayılan olarak, bu dosyayı bir kısmi içeren `UIMap` yöntemleri ya da özellikleri olan sınıfı.

#### <a name="uimap-class"></a>UIMap sınıfı
 İşlevlerini genişletmek için özel kod oluşturabileceğiniz budur <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> sınıfı. Bu dosyada oluşturduğunuz kod tarafından geçersiz kılınmaz **kodlanmış UI Test oluşturucusunu** test değiştiren her zaman.

 Tüm parçalarını <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> yöntemleri ve diğer herhangi bir kısmını özelliklerinden kullanabilirsiniz <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> sınıfı.

###  <a name="CodedUITestCS"></a> Codeduıtest1.cs
 Bu dosya tarafından oluşturulan **kodlanmış UI Test oluşturucusunu**, ancak bu dosya kodda değiştirebilmek için test değiştirildiğinde, her zaman yeniden oluşturulmaz. Dosyanın adını oluşturduğunuz zaman, test için belirttiğiniz addan üretilir.

#### <a name="codeduitest1-class"></a>Codeduıtest1 sınıfı

Varsayılan olarak, bu dosya yalnızca bir sınıf için tanım içeriyor.

```csharp
[CodedUITest]
public class CodedUITest1
```

<xref:Microsoft.VisualStudio.TestTools.UITesting.CodedUITestAttribute> Otomatik olarak bir test uzantısı olarak tanımak test çerçevesi sağlar sınıfı uygulanır. Ayrıca bu bir parçalı sınıf olmadığına dikkat edin. Tüm sınıf kodu bu dosyada yer alır.

#####  <a name="CodedUITestProperties"></a> Codeduıtest1 özellikleri

Sınıfı dosyanın sonunda bulunan iki varsayılan özelliklerini içerir. Bunları değiştirmeyin.

```csharp
/// <summary>
/// Gets or sets the test context which provides
/// information about and functionality for the current test run.
///</summary>
public TestContext TestContext
public UIMap UIMap
```

#####  <a name="CodedUITestMethods"></a> Codeduıtest1 yöntemleri
 Varsayılan olarak, sınıfı tek yöntemi içerir.

```csharp
public void CodedUITestMethod1()
```

 Bu yöntem her çağırır `UIMap` üzerinde bölümünde açıklanan testinizi kaydettiğiniz zaman belirtilen yöntemi [UIMap sınıfı](#UIMapClass).

 Adlandırılmış bir bölge `Additional test attributes`, kaldırılmamışsa, isteğe bağlı iki yöntem içerir.

```csharp
// Use TestInitialize to run code before running each test
[TestInitialize()]
public void MyTestInitialize()
{
    // To generate code for this test, select "Generate Code for Coded
    // UI Test" from the shortcut menu and select one of the menu items.
    // For more information on generated code, see
    // http://go.microsoft.com/fwlink/?LinkId=179463

    // You could move this line from the CodedUITestMethod1() method
    this.UIMap.LaunchCalculator();
}

// Use TestCleanup to run code after each test has run
[TestCleanup()]
public void MyTestCleanup()
{
    // To generate code for this test, select "Generate Code for Coded
    // UI Test" from the shortcut menu and select one of the menu items.
    // For more information on generated code, see
    // http://go.microsoft.com/fwlink/?LinkId=179463

    // You could move this line from the CodedUITestMethod1() method
    this.UIMap.CloseCalculator();
}
```

 `MyTestInitialize()` Yöntemi sahip <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestInitializeAttribute> , herhangi bir test yöntem önce bu yöntemi çağırmak için test çerçevesi söyler uygulanır. Benzer şekilde, `MyTestCleanup()` yöntemi sahip <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCleanupAttribute> uygulanan, bu yöntem tüm diğer test yöntemleri çağırmak için test çerçevesi söyleyen çağrılıp çağrılmadığını. Bu yöntemlerin kullanımı isteğe bağlıdır. Bu test için `UIMap.LaunchCalculator()` yöntemi konumundan çağrılabilir `MyTestInitialize()` ve `UIMap.CloseCalculator()` yöntemi konumundan çağrılabilir `MyTestCleanup()` yerine gelen `CodedUITest1Method1()`.

 Kullanarak daha fazla yöntem bu sınıfa eklerseniz <xref:Microsoft.VisualStudio.TestTools.UITesting.CodedUITestAttribute>, test çerçevesi testin bir parçası her bir yöntemi çağırır.

###  <a name="UIMapuitest"></a> UIMap.uitest
 Temsil kaydı yapısı kodlanmış UI test XML dosyasını ve tüm bölümleri budur. Bunlar, eylemleri ve sınıfları yöntemleri ve bu sınıfların özelliklerine ek olarak içerir. [UIMap.Designer.cs](#UIMapDesignerFile) dosya kodlanmış UI test yapısı oluşturmaya oluşturucusu tarafından oluşturulur ve test çerçevesi bağlantısı sağlayan kodunu içerir.

 `UIMap.uitest` Dosyası doğrudan düzenlenebilir değil. Ancak, otomatik olarak değiştirir testi değiştirmek için kodlanmış UI Oluşturucusu kullanabilirsiniz `UIMap.uitest` dosya ve [UIMap.Designer.cs](#UIMapDesignerFile) dosya.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>
- <xref:Microsoft.VisualStudio.TestTools.UITesting.WinControls>
- <xref:Microsoft.VisualStudio.TestTools.UITesting.HtmlControls>
- <xref:Microsoft.VisualStudio.TestTools.UITesting.WpfControls>
- <xref:System.CodeDom.Compiler.GeneratedCodeAttribute>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard.SendKeys%2A?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UITesting.CodedUITestAttribute>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestInitializeAttribute>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCleanupAttribute>
- [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI Testleri için En İyi Yöntemler](../test/best-practices-for-coded-ui-tests.md)
- [Birden Çok UI Eşlemesi Bulunan Büyük Uygulamaları Sınama](../test/testing-a-large-application-with-multiple-ui-maps.md)
- [Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)