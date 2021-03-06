---
title: Genel Windows Formları ve Web formları için kültüre özgü sınıflar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- globalization [Windows Forms], classes
- Web applications [.NET Framework], globalization
- culture, culture-specific classes
- numbers, international
- localization [Windows Forms], classes
- globalization [Visual Studio], culture-specific classes
- Windows Forms, localization
- international applications [Visual Studio], data formats
- time [Visual Studio], international
- dates [Visual Studio], international
- culture
- international characters
- currency formats
- ASP.NET, globalization
- classes [Visual Studio], culture-specific
- localization [Visual Studio], culture-specific classes
ms.assetid: 0d06a0a4-f887-4f7c-bde7-1d543c06f803
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 3e7982b11ffba3cc48cd47488cf2258978168452
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="culture-specific-classes-for-global-windows-forms-and-web-forms"></a>Genel Windows Formları ve Web Formları İçin Kültüre Özgü Sınıflar

Her kültür tarih, saat, sayılar, para birimi ve diğer bilgileri görüntülemek için farklı kurallara sahiptir. <xref:System.Globalization> Ad alanı kültüre özgü değerlerini değiştirmek için kullanılan sınıfları içerir, gibi görüntülenen <xref:System.Globalization.DateTimeFormatInfo>, **Takvim**, ve <xref:System.Globalization.NumberFormatInfo>.

## <a name="using-the-culture-setting"></a>Kültür ayarı kullanma

Uygulama veya depolanan kültür ayarı kullanmak **Bölgesel Seçenekler** otomatik olarak çalışma zamanında kültüre kuralları belirlemek ve bilgileri buna göre biçimlendirmek için Denetim Masası'nı tıklatın,. Kültürü ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: ASP.NET Web sayfası Genelleştirme için UI kültürü ve kültür ayarlamak](http://msdn.microsoft.com/Library/76091f86-f967-4687-a40f-de87bd8cc9a0). Kültür ayarı göre bilgi otomatik olarak Biçimlendir sınıfları kültüre özgü denir. Bazı kültüre özgü yöntemler <xref:System.IFormattable.ToString%2A?displayProperty=fullName>, <xref:System.Console.WriteLine%2A?displayProperty=fullName>, ve <xref:System.String.Format%2A?displayProperty=fullName>. Bazı kültüre özgü işlevleri (Visual Basic dilindeki) `MonthName` ve `WeekDayName`.

Örneğin, aşağıdaki kod nasıl kullanabileceğinizi gösterir <xref:System.IFormattable.ToString%2A> biçimi para birimi bir yönteme geçerli kültür için:

```vb
' Put the Imports statements at the beginning of the code module  
Imports System.Threading  
Imports System.Globalization  
' Display a number with the culture-specific currency formatting  
Dim MyInt As Integer = 100  
Console.WriteLine(MyInt.ToString("C", Thread.CurrentThread.CurrentCulture))
```

```csharp
// Put the using statements at the beginning of the code module  
using System.Threading;  
using System.Globalization;  
// Display a number with the culture-specific currency formatting  
int myInt = 100;  
Console.WriteLine(myInt.ToString("C", Thread.CurrentThread.CurrentCulture));  
```

Kültür "fr-FR" olarak ayarlanırsa, bu çıktı penceresinde görürsünüz:  

`100,00`

Kültür "en-US" olarak ayarlanırsa, bu çıktı penceresinde görürsünüz:  

`$100.00`

## <a name="see-also"></a>Ayrıca bkz.

<xref:System.IFormattable.ToString%2A?displayProperty=fullName>   
<xref:System.Globalization.DateTimeFormatInfo>   
<xref:System.Globalization.NumberFormatInfo>   
<xref:System.Globalization.Calendar>   
<xref:System.Console.WriteLine%2A?displayProperty=fullName>   
<xref:System.String.Format%2A?displayProperty=fullName>   
[Uygulamaları Genelleştirme ve Yerelleştirme](../ide/globalizing-and-localizing-applications.md)