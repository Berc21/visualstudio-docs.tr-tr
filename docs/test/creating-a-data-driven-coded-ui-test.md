---
title: "Kodlanmış UI testi Visual Studio'da veri güdümlü oluşturma | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- coded UI tests, data-driven
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b9c5d03810a4a45e95c1742eab8e652997c91ab6
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="creating-a-data-driven-coded-ui-test"></a>Verilerle Çalışan Kodlanmış UI Testi Oluşturma

Farklı koşullarda test etmek için farklı parametre değerleri ile birden çok kez testleri çalıştırabilirsiniz. Veri tabanlı kodlanmış UI testleri bunu yapmak için uygun bir yöntemdir. Kodlanmış UI Test yineleme veri kaynağındaki her satır olduğundan ve bir veri kaynağı, parametre değerleri tanımlayın. Genel test sonucu, tüm yinelemeleri sonucunu dayalı olacak. Örneğin, bir test yineleme başarısız olursa genel test sonucu başarısız olur.

 **Gereksinimler**

-   Visual Studio Enterprise

## <a name="create-a-data-driven-coded-ui-test"></a>Veri tabanlı kodlanmış UI testi oluşturma
 Bu örnek Windows hesap makinesi uygulamanın çalıştığı kodlanmış bir UI testi oluşturur. İki sayıyı toplar ve toplamı doğru olduğunu doğrulamak için onayı ifade kullanır. Ardından, onaylama ve iki sayının parametre değerlerini verilere ve depolanan bir virgülle ayrılmış değer (.csv) dosyası olmasını kodlanmıştır.

#### <a name="step-1---create-a-coded-ui-test"></a>1. adım - kodlanmış UI testi oluşturma

1.  Bir proje oluşturun.

     ![Kodlanmış UI testi projesi oluşturma](../test/media/cuit_datadriven_.png "CUIT_dataDriven_")

2.  Eylemleri kaydetmek seçin.

     ![Eylemleri kaydetmek seçin](../test/media/cuit_datadriven_generatecodedialog.png "CUIT_dataDriven_GenerateCodeDialog")

3.  Hesaplayıcı uygulamasını açın ve test kaydı başlatın.

     ![Kayıt Eylemler](../test/media/cuit_datadriven_cuitbuilder.png "CUIT_dataDriven_CUITBuilder")

4.  1 ve 2 ekleyin, kaydedici duraklatma ve test yöntemi oluşturun. Daha sonra bir veri dosyasından gelen değerlerle Biz bu kullanıcı girişi değerlerini değiştirirsiniz.

     ![Genetate test yöntemi](../test/media/cuit_datadriven_cuitbuildergencode.png "CUIT_dataDriven_CUITBuilderGenCode")

     Test Oluşturucusu'nu kapatın. Yöntemi, test eklenir:

    ```csharp
    [TestMethod]
    public void CodedUITestMethod1()
    {
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.AddNumbers();
    }
    ```

5.  Kullanım `AddNumbers()` test çalıştığını doğrulamak için yöntem. Yukarıda gösterilen test yöntemi imleci yerleştirin, bağlam menüsünü açın ve seçin **Testleri Çalıştır**. (Klavye kısayolu: Ctrl + R, T).

     Test geçirilen ya da başarısız olmuşsa gösterir test sonucu Test Gezgini penceresinde görüntülenir. Gelen Test Gezgini penceresi açmak için **Test** menüsünde seçin **Windows** ve ardından **Test Gezgini**.

6.  Bir veri kaynağı onaylama parametre değerleri için de kullanılabilir olmadığından — kullanılan test tarafından beklenen değerler doğrulamak için — iki sayının toplamını doğru olduğunu doğrulamak için onayı ifade ekleyelim. Yukarıda gösterilen test yöntemi imleci yerleştirin, bağlam menüsünü açın ve seçin **kodlanmış UI testi için kod üret**ve ardından **kullanım kodlanmış UI Test oluşturucusunu**.

     Sum görüntüler hesaplayıcı metin denetiminde eşleyin.

     ![UI metin denetimini eşleme](../test/media/cuit_datadriven_addassertion.png "CUIT_dataDriven_AddAssertion")

7.  Toplam değeri doğru olduğunu doğrulayan bir onaylama ekleyin. Seçin **görüntü metni** değerine sahip özellik **3** ve ardından **onay Ekle**. Kullanım **AreEqual** karşılaştırıcı ve karşılaştırma değeri olduğundan emin olun **3**.

     ![Onaylama işlemi yapılandırma](../test/media/cuit_datadriven_builderaddassertion2.png "CUIT_dataDriven_BuilderAddAssertion2")

8.  Onaylama işlemi yapılandırdıktan sonra kodu yeniden Oluşturucu oluşturur. Bu doğrulama için yeni bir yöntem oluşturur.

     ![Onaylama işlemi yöntemi oluşturmak](../test/media/cuit_datadriven_assertiongencode.png "CUIT_dataDriven_AssertionGenCode")

     Çünkü `ValidateSum` yöntemi doğrulama sonuçlarını `AddNumbers` yöntemi, kod bloğunun altına taşıyın.

    ```csharp
    public void CodedUITestMethod1()
    {

        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.AddNumbers();
        this.UIMap.ValidateSum();

    }
    ```

9. Test kullanarak çalıştığını doğrulamanız `ValidateSum()` yöntemi. Yukarıda gösterilen test yöntemi imleci yerleştirin, bağlam menüsünü açın ve seçin **Testleri Çalıştır**. (Kısayol: Ctrl + R, T klavye).

     Bu noktada, tüm parametre değerleri kendi yöntemlerini sabitleri tanımlanır. Ardından, veri güdümlü bizim test yapmak için bir veri kümesi oluşturalım.

#### <a name="step-2---create-a-data-set"></a>2. adım - bir veri kümesi oluşturma

1.  Bir metin dosyası adlı dataDrivenSample projeye ekleyin `data.csv`.

     ![Bir virgülle ayrılmış değer dosyası projeye ekleyin](../test/media/cuit_datadriven_addcsvfile.png "CUIT_dataDriven_AddCSVFile")

2.  Aşağıdaki verilerle .csv dosyasını doldurmak:

    |Num1|Num2|TOPLA|
    |----------|----------|---------|
    |3|4|7|
    |5|6|11|
    |6|8|14|

     Veri eklendikten sonra dosyanın aşağıdaki gibi görünmelidir:

     ![Doldurur. Veri içeren CSV dosyası](../test/media/cuit_datadriven_adddatatocsvfile.png "CUIT_dataDriven_AddDataToCSVFile")

3.  Doğru kodlama kullanılarak .csv dosyasını kaydetmek önemlidir. Üzerinde **dosya** menüsünde seçin **Gelişmiş kaydetme seçenekleri** ve **Unicode (UTF-8 imza olmadan) - Codepage 65001** kodlama olarak.

4.  Çıktı dizinine .csv dosyasını kopyaladığınız veya test çalışamaz. Kopyalamak için Özellikler penceresini kullanın.

     ![Dağıtın. CSV dosyası](../test/media/cuit_datadriven_deploycsvfile.png "CUIT_dataDriven_DeployCSVFile")

     Şimdi biz oluşturulan veri kümesi sahip olduğunuza göre verileri test bağlayın.

#### <a name="step-3---add-data-source-binding"></a>3. adım - veri kaynağına bağlama ekleme

1.  Veri kaynağı bağlamak için add bir `DataSource` varolan içinde öznitelik `[TestMethod]` hemen test yöntemi bir öznitelik.

    ```csharp
    [DataSource("Microsoft.VisualStudio.TestTools.DataSource.CSV", "|DataDirectory|\\data.csv", "data#csv", DataAccessMethod.Sequential), DeploymentItem("data.csv"), TestMethod]
    public void CodedUITestMethod1()
    {

        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.AddNumbers();
        this.UIMap.ValidateSum();

    }
    ```

     Veri kaynağı artık bu test yöntemi kullanmak kullanılabilir.

    > [!TIP]
    > Bkz: [veri kaynağı özniteliği örnekleri](#CreateDataDrivenCUIT_QA_DataSourceAttributes) soru-cevap XML, SQL Express ve Excel gibi diğer veri kaynağı türleri kullanma örnekleri için bir bölüm.

2.  Testi çalıştırın.

     Üç yineleme ile test çalışmaları dikkat edin. Bağlanan veri kaynağı üç veri satırı içermesidir. Ancak, test yine sabit parametre değerlerini kullanarak ve her zaman 1 + 2 3 toplamı ile ekleyerek de görürsünüz.

     Ardından, veri kaynağı dosyasında değerleri kullanmak için test yapılandıracağız.

#### <a name="step-4---use-the-data-in-the-coded-ui-test"></a>4. adım - kodlanmış UI testi verileri kullanma

1.  Ekleme `using Microsoft.VisualStudio.TestTools.UITesting.WinControls` CodedUITest.cs dosyanın en üstüne için:

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Text.RegularExpressions;
    using System.Windows.Input;
    using System.Windows.Forms;
    using System.Drawing;
    using Microsoft.VisualStudio.TestTools.UITesting;
    using Microsoft.VisualStudio.TestTools.UnitTesting;
    using Microsoft.VisualStudio.TestTools.UITest.Extension;
    using Keyboard = Microsoft.VisualStudio.TestTools.UITesting.Keyboard;
    using Microsoft.VisualStudio.TestTools.UITesting.WinControls;
    ```

2.  Ekleme `TestContext.DataRow[]` içinde `CodedUITestMethod1()` değerleri veri kaynağından uygulanacak yöntemi. Veri kaynağı değerlerini denetimlerini kullanarak UIMap denetimlere atanan sabitleri geçersiz kılma `SearchProperties`:

    ```csharp
    public void CodedUITestMethod1()
    {

        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.UICalculatorWindow.UIItemWindow.UIItem1Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num1"].ToString();this.UIMap.UICalculatorWindow.UIItemWindow21.UIItem2Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num2"].ToString();
        this.UIMap.AddNumbers();
        this.UIMap.ValidateSumExpectedValues.UIItem2TextDisplayText = TestContext.DataRow["Sum"].ToString();
        this.UIMap.ValidateSum();

    }
    ```

     Verileri kodlamak için hangi arama özelliklerinin tahmin için kodlanmış UI Test Düzenleyicisi'ni kullanın.

    -   UIMap.uitest dosyasını açın.

         ![Kodlanmış UI Test Düzenleyicisi'ni açmak](../test/media/cuit_datadriven_opentesteditor.png "CUIT_dataDriven_OpenTestEditor")

    -   UI eylem seçin ve ilgili kullanıcı Arabirimi denetim eşleme gözlemleyin. Nasıl eşleme koduna, örneğin, karşılık gelen fark `this.UIMap.UICalculatorWindow.UIItemWindow.UIItem1Button`.

         ![Koduyla yardımcı olmak için kodlanmış UI Test Düzenleyicisi'ni kullanın](../test/media/cuit_datadriven_testeditor.png "CUIT_dataDriven_TestEditor")

    -   Özellikler penceresini açmak **arama özellikleri**. Arama özellikleri **adı** değerdir'ın veri kaynağını kullanarak kod içinde ne yönetilebilir. Örneğin, `SearchProperties` her veri satırının ilk sütununu değerler atanır: `UIItem1Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num1"].ToString();`. Üç yineleme için bu sınama değiştirir **adı** 3, ardından 5 ve son olarak 6 arama özelliği için değer.

         ![Kodlama yardımcı olmak için arama özelliklerini kullanın](../test/media/cuit_datadriven_searchproperties.png "CUIT_dataDriven_SearchProperties")

3.  Çözüm kaydedin.

#### <a name="step-5---run-the-data-driven-test"></a>Adım 5 - verilere test çalıştırma

1.  Test şimdi test yeniden çalıştırarak veri tabanlı olduğundan emin olun.

     .Csv dosyasında değerleri kullanarak üç yineleme aracılığıyla testi görmeniz gerekir. Doğrulama de çalışması gerekir ve test Test Explorer'ın geçti olarak görüntülenmelidir.

 **Kılavuz**

 Ek bilgi için bkz: [Visual Studio 2012 - bölüm 2 ile sürekli teslimat için test etme: birim testi: İç sınama](http://go.microsoft.com/fwlink/?LinkID=255188) ve [Visual Studio 2012 - bölüm 5 ile sürekli teslimat için test etme: Sistem testlerini otomatikleştirme](http://go.microsoft.com/fwlink/?LinkID=255196)

## <a name="q--a"></a>Soru - Yanıt

###  <a name="CreateDataDrivenCUIT_QA_DataSourceAttributes"></a> SQL Express veya XML gibi diğer veri kaynağı türleri için veri kaynağı öznitelikleri nelerdir?
 Kodunuza kopyalayarak ve gereken özelleştirmeleri yaparak, aşağıdaki tabloda örnek veri kaynağı dizeleri kullanabilirsiniz.

 **Veri kaynağı türleri ve öznitelikleri**

-   CSV

     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.CSV", "|DataDirectory|\\data.csv", "data#csv", DataAccessMethod.Sequential), DeploymentItem("data.csv"), TestMethod]`

-   Excel

     `DataSource("System.Data.Odbc", "Dsn=ExcelFiles;Driver={Microsoft Excel Driver (*.xls)};dbq=|DataDirectory|\\Data.xls;defaultdir=.;driverid=790;maxbuffersize=2048;pagetimeout=5;readonly=true", "Sheet1$", DataAccessMethod.Sequential), DeploymentItem("Sheet1.xls"), TestMethod]`

-   Team Foundation Server'da test durumu

     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.TestCase", "http://vlm13261329:8080/tfs/DefaultCollection;Agile", "30", DataAccessMethod.Sequential), TestMethod]`

-   XML

     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.XML", "|DataDirectory|\\data.xml", "Iterations", DataAccessMethod.Sequential), DeploymentItem("data.xml"), TestMethod]`

-   SQL Express

     `[DataSource("System.Data.SqlClient", "Data Source=.\\sqlexpress;Initial Catalog=tempdb;Integrated Security=True", "Data", DataAccessMethod.Sequential), TestMethod]`

### <a name="q-can-i-use-data-driven-tests-on-my-windows-phone-app"></a>S: Windows Phone Uygulamam verilere testleri kullanabilir miyim?
 **Y:** Evet. Windows Phone için veri tabanlı kodlanmış UI testleri, bir test yöntemi DataRow özniteliği kullanılarak tanımlanır. Aşağıdaki örnek, x ve y değerleri 1 ve 2 ilk yinelemeyi ve -1 -2 testinin ikinci yineleme için için kullanın.

```csharp
[DataRow(1, 2, DisplayName = "Add positive numbers")]
[DataRow(-1, -2, DisplayName = "Add negative numbers")]
[TestMethod]
public void DataDrivingDemo_MyTestMethod(int x, int y)
```

Daha fazla bilgi için bkz: [kullanım veri tabanlı kodlanmış UI testleri Windows Phone uygulamalarını](../test/test-windows-phone-8-1-apps-with-coded-ui-tests.md#TestingPhoneAppsCodedUI_DataDriven).

### <a name="q-why-cant-i-modify-the-code-in-the-uimapdesigner-file"></a>S: neden UIMap.Designer dosyasındaki kodu değiştirilemez?
 **Y:** UIMap - Kodlanmış UI Test derleyicisini kullanarak kod oluşturma her zaman UIMapDesigner.cs dosyasında yaptığınız herhangi bir kod değişikliğinin üzerine yazılır. Bu örnekte ve çoğu durumda, bir veri kaynağı kullanmak bir test etkinleştirmek için gereken kod değişikliği testin kaynak kodu dosyasına (diğer bir deyişle, Codeduıtest1.cs) yapılabilir.

Kayıtlı bir yöntemi değiştirmeniz gerekiyorsa, yöntemi UIMap.cs dosyasına kopyalayıp yeniden adlandırmanız gerekir. UIMap.cs dosyası, UIMapDesigner.cs dosyasındaki yöntemleri ve özellikleri geçersiz kılmak için kullanılabilir. Kodlanmış UITest.cs dosyasındaki orijinal yönteme başvuruyu kaldırıp yeniden adlandırılan yöntem adıyla değiştirmelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>
- [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI Testleri için En İyi Yöntemler](../test/best-practices-for-coded-ui-tests.md)
- [Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)