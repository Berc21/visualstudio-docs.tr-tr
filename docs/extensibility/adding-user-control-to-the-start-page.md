---
title: "Başlangıç sayfasına kullanıcı denetimi ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- start page dll
- custom start page
- start page assembly
ms.assetid: 5b7997db-af6f-4fa9-a128-bceb42bddaf1
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 448eba0d13a9501c328da79fa31fa66f4376d5df
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-user-control-to-the-start-page"></a>Kullanıcı denetimi için başlangıç sayfası ekleme
Bu kılavuz, özel bir başlangıç sayfası DLL başvuru eklemek gösterilmiştir. Örnek bir kullanıcı denetimi çözüme kullanıcı denetimi oluşturur ve ardından başlangıç sayfası .xaml dosyasından yerleşik bütünleştirilmiş koduna başvuruyor ekler. Yeni bir sekme temel bir Web tarayıcısı olarak işlev kullanıcı Denetim barındırır.  
  
 Aynı işlem .xaml dosyasından çağrılabilir derleme eklemek için kullanabilirsiniz.  
  
## <a name="adding-a-wpf-user-control-to-the-solution"></a>WPF kullanıcı denetimi çözüme ekleniyor  
 İlk olarak, bir Windows Presentation Foundation (WPF) kullanıcı denetimi başlangıç sayfası çözüme ekleyin.  
  
1.  Bir başlangıç sayfası oluşturma kullanarak içinde oluşturduğumuz [bir özel başlangıç sayfası oluşturma](../extensibility/creating-a-custom-start-page.md).  
  
2.  İçinde **Çözüm Gezgini**, çözüme sağ tıklayın, **Ekle**ve ardından **yeni proje**.  
  
3.  Sol bölmesinde **yeni proje** iletişim kutusunda, genişletin **Visual Basic** veya **Visual C#** düğümü ve tıklatın **Windows**. Orta bölmede seçin **WPF kullanıcı denetimi Kitaplığı**.  
  
4.  Denetim adı `WebUserControl` ve ardından **Tamam**.  
  
## <a name="implementing-the-user-control"></a>Kullanıcı denetimini uygulama  
 WPF kullanıcı denetimi için XAML kullanıcı arabiriminde (UI) oluşturun ve ardından arka plan kodu olayları C# veya başka bir .NET dil yazın.  
  
#### <a name="to-write-the-xaml-for-the-user-control"></a>XAML kullanıcı denetimi için yazmak için  
  
1.  Kullanıcı denetimi için XAML dosyasını açın. İçinde \<kılavuz > öğesi, aşağıdaki satırı tanımları denetimine ekleyin.  
  
    ```vb  
    <Grid.RowDefinitions>  
        <RowDefinition Height="Auto"/>  
        <RowDefinition Height="*" />  
    </Grid.RowDefinitions>  
  
    ```  
  
2.  Ana `Grid` öğesi, aşağıdaki yeni ekleyin `Grid` yeni adresini ayarlamak için bir düğmeyi ve Web adresleri yazmak için bir metin kutusu içeren öğe.  
  
    ```xml  
    <Grid Grid.Row="0">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="*" />  
            <ColumnDefinition Width="Auto" />  
        </Grid.ColumnDefinitions>  
        <TextBox x:Name="UserSource" Grid.Column="0" />  
        <Button Grid.Column="1" x:Name="SetButton" Content="Set Address" Click="SetButton_Click" />  
    </Grid>  
    ```  
  
3.  Aşağıdaki çerçevesi için üst düzey ekleme `Grid` öğesi hemen sonra `Grid` düğmesi ve metin kutusu içeren öğe.  
  
    ```vb  
    <Frame Grid.Row="1" x:Name="WebFrame" Source="http://www.bing.com" Navigated="WebFrame_Navigated" />  
    ```  
  
4.  Aşağıdaki örnekte kullanıcı denetimi tamamlanmış XAML gösterir.  
  
    ```xml  
    <UserControl x:Class="WebUserControl.UserControl1"  
                 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
                 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
                 xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
                 xmlns:d="http://schemas.microsoft.com/expression/blend/2008"   
                 mc:Ignorable="d"   
                 d:DesignHeight="300" d:DesignWidth="300">  
        <Grid>  
            <Grid.RowDefinitions>  
                <RowDefinition Height="Auto"/>  
                <RowDefinition Height="*" />  
            </Grid.RowDefinitions>  
            <Grid Grid.Row="0">  
                <Grid.ColumnDefinitions>  
                    <ColumnDefinition Width="*" />  
                    <ColumnDefinition Width="Auto" />  
                </Grid.ColumnDefinitions>  
                <TextBox x:Name="UserSource" Grid.Column="0" />  
                <Button Grid.Column="1" x:Name="SetButton" Content="Set Address" Click="SetButton_Click" />  
            </Grid>  
            <Frame Grid.Row="1" x:Name="WebFrame" Source="http://www.bing.com" Navigated="WebFrame_Navigated" />  
        </Grid>  
    </UserControl>  
  
    ```  
  
#### <a name="to-write-the-code-behind-events-for-the-user-control"></a>Kullanıcı denetimi için arka plan kodu olayları yazmak için  
  
1.  XAML Tasarımcısı'nda çift **adresi kümesinin** düğme denetimine eklendi.  
  
     UserControl1.cs dosyası Kod Düzenleyicisi'nde açar.  
  
2.  SetButton_Click olay işleyicisini aşağıdaki gibi doldurun.  
  
    ```csharp  
    private void SetButton_Click(object sender, RoutedEventArgs e)  
    {  
        try  
        {  
            this.WebFrame.Source = new Uri(this.UserSource.Text, UriKind.Absolute);  
        }  
        catch (Exception error)  
        {  
            MessageBox.Show(error.Message);  
        }  
    }  
    ```  
  
     Bu kod, Web tarayıcısı için hedef olarak metin kutusuna yazdığınız Web adresini ayarlar. Adresi geçerli değil, kodu bir hata oluşturur.  
  
3.  Ayrıca WebFrame_Navigated olay işlemesi gerekir:  
  
    ```csharp  
    private void WebFrame_Navigated(object sender, EventArgs e)  
    { }  
    ```  
  
4.  Çözümü oluşturun.  
  
## <a name="adding-the-user-control-to-the-start-page"></a>Kullanıcı denetimi için başlangıç sayfası ekleme  
 Bu denetim başlangıç sayfası proje dosyasında başlangıç sayfası proje kullanılabilir hale getirmek için yeni denetim kitaplığına bir başvuru ekleyin. Daha sonra Başlat Sayfası XAML biçimlendirme denetimi ekleyebilirsiniz.  
  
1.  İçinde **Çözüm Gezgini**, başlangıç sayfası projeye sağ tıklayın **başvuruları** ve ardından **Başvuru Ekle**.  
  
2.  Üzerinde **projeleri** sekmesine **WebUserControl** ve ardından **Tamam**.  
  
3.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     Çözümü derledikten kullanıcı denetimi için IntelliSense çözümdeki diğer dosyalar için kullanılabilmesini sağlar.  
  
 Başlangıç sayfası XAML işaretleme denetim eklemek için derleme ad alanı referansı ekleyin, sonra denetimi sayfasına yerleştirin.  
  
#### <a name="to-add-the-control-to-the-markup"></a>Biçimlendirme denetim eklemek için  
  
1.  İçinde **Çözüm Gezgini**, başlangıç sayfası .xaml dosyasını açın.  
  
2.  İçinde **XAML** bölmesinde, aşağıdaki ad alanı bildirimi için üst düzey ekleyin <xref:System.Windows.Controls.Grid> öğesi.  
  
    ```xml  
    xmlns:vsc="clr-namespace:WebUserControl;assembly=WebUserControl"  
    ```  
  
3.  İçinde **XAML** bölmesinde, kaydırın \<kılavuz > bölümü.  
  
     Bölüm içeren bir <xref:System.Windows.Controls.TabControl> öğesinde bir <xref:System.Windows.Controls.Grid> öğesi.  
  
4.  Ekleme bir \<TabControl > öğesi içeren bir \<TabItem >, kullanıcı denetimi için bir başvuru içeriyor.  
  
    ```xml  
  
    <TabItem Header="Web" Height="Auto">  
        <vsc:UserControl1 />  
    </TabItem>  
  
    ```  
  
 Artık denetimi test edebilirsiniz.  
  
## <a name="testing-a-manually-created-custom-start-page"></a>El ile oluşturulan özel bir başlangıç sayfası test etme  
  
1.  XAML dosyanızı ve destekleyici metin dosyaları veya işaretleme dosyaları, çok kopya **%USERPROFILE%\My Documents\Visual Studio 2015\StartPages\\**  klasör.  
  
2.  Başlangıç sayfanızı herhangi bir denetimleri veya Visual Studio tarafından yüklenmemiş derlemelerindeki başvuruyorsa, derlemeler kopyalayıp sonra bunları *Visual Studio yükleme klasörü***\Common7\IDE\ PrivateAssemblies\\**.  
  
3.  Bir Visual Studio komut isteminde **devenv /rootsuffix Exp** Visual Studio deneysel örneği açın.  
  
4.  Deneysel örneğinde Git **Araçlar / Seçenekler / ortamı / başlangıç** sayfasında ve XAML dosyanızdan seçin **başlangıç sayfasını özelleştirme** açılır.  
  
5.  Üzerinde **Görünüm** menüsünde tıklatın **başlangıç sayfası**.  
  
     Özel başlangıç sayfanızı görüntülenmesi gerekir. Tüm dosyaları değiştirmek istiyorsanız, gerekir deneysel örneği kapatın, değişiklik, kopyalamak ve değişen dosyaları yapıştırın ve değişiklikleri görmek için deneysel örneği yeniden açın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF kapsayıcı denetimleri](http://msdn.microsoft.com/en-us/a0177167-d7db-4205-9607-8ae316952566)   
 [İzlenecek Yol: Başlangıç Sayfasına Özel XAML Ekleme](../extensibility/walkthrough-adding-custom-xaml-to-the-start-page.md)