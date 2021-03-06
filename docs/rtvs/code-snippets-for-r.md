---
title: "Kod parçacıkları R araçları ile Visual Studio için | Microsoft Docs"
description: "Kod parçacıkları Visual Studio'da R için hızlı bir şekilde kod blokları benzer bir kod defalarca yeniden yazmaktan kaçınmanıza yardımcı olur, rastgele uzunlukta eklemek için kısayollar sağlar."
ms.custom: 
ms.date: 01/24/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
dev_langs:
- R
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: d8628b2712c52aae614223b702344bb0b548e306
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="code-snippets"></a>Kod parçacıkları

Visual Studio'da kod parçacıkları hızlı bir şekilde kod blokları benzer bir kod defalarca yeniden yazmaktan kaçınmanıza yardımcı olur, rastgele uzunlukta eklemek için kısayollar sağlar. R araçları için Visual Studio (RTVS) yararlı R parçacıkları düzinelerce Visual Studio'nun koleksiyonuna ekler.

Parçacık eklemek için kısaltılmış adını yazın (IntelliSense sağlanır) kod parçacığında, sonra SEKME tuşuna basın eklemek için.

Basit bazı örnekler:

- tür `=` sonra sekme ve RTVS şekilde genişletir `<-` atama işleci.
- tür `>` RTVS genişletir ve ardından sekme `%>%` dikey çizgi işleci.

Kod parçacıkları çok daha fazlasına karakter tamamlama karakter olabilir. İçeren bir CSV dosyası okumak için bir kod parçacığında `read.csv` işlevi, örneğin, hafifletmek, adlarını veya parametreleri anımsamak zorunda kalmaktan:

![Animasyon read.csv yapılan bir çağrı eklemek için bir kod parçacığı kullanma](media/code-snippet-expansion.gif)

Bu durumda, siz yazarken `readc`, IntelliSense tamamlanma listesini görüntüler. Bu tamamlama açılan seçip sekmesini seçer tuşuna basarak `readc`, ve yeniden SEKME tuşuna basarak kod parçacığını genişletir. ("Kod parçacığını yazın ve SEKME tuşuna iki kez basın gibi" Bu nedenle, kod parçacığında genişletme genellikle, düşünüldüğü). Çoğu durumda, ilk sekme IntelliSense seçimi tamamlar ve ikinci sekmesinde genişletme tetikler.

Tüm kullanılabilir parçacıkları görmek için açın **Araçlar > kod parçacıkları Yöneticisi...**  iletişim kutusunu (Ctrl + K, B) ve select **R** için **dil**. Gruplar'ı genişletin ve bir açıklama ve kısayol metni görmek için tek tek parçaları seçin:

![Kod parçacıkları iletişim kutusu r](media/code-snippet-dialog.png)

Özel kod parçacıkları, yönergeleri izleyerek oluşturmak için [izlenecek yol: kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md). Sonuç olarak, bir kod parçacığı yalnızca bir XML dosyasıdır. Örneğin, aşağıdaki kod parçacığını kanal işlemi için. (kısayol `>`):

```xml
<?xml version="1.0" encoding="utf-8" ?>
<CodeSnippets  xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
  <CodeSnippet Format="1.0.0">
    <Header>
      <Title>Dplyr pipe</Title>
      <Shortcut>&gt;</Shortcut>
      <Description>Code snippet for '%&gt;%' operator</Description>
      <Author>Microsoft Corporation</Author>
      <SnippetTypes>
        <SnippetType>Expansion</SnippetType>
       </SnippetTypes>
    </Header>
    <Snippet>
      <Code Language="R">
        <![CDATA[ %>% $end$]]>
      </Code>
    </Snippet>
  </CodeSnippet>
</CodeSnippets>
```

Tüm kod parçacıkları için XML dosyaları ile RTVS yüklenir; **konumu** alanındaki **kod parçacıkları Yöneticisi** yolunu sağlar. Altında github'da RTVS kaynak kodundaki de bulabilirsiniz [src/paket/Impl/parçacıkları](https://github.com/Microsoft/RTVS/tree/master/src/Package/Impl/Snippets).
