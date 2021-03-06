---
title: "VSCT XML Şeması koşullu öznitelikler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, conditional attributes
- conditional attributes (VSCT XML schema)
ms.assetid: 754d4f32-319b-44c9-915f-f7c60e53222e
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 75b593110f68cd559717ae87920e898f39cdeb43
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="vsct-xml-schema-conditional-attributes"></a>VSCT XML Şeması koşullu öznitelikler
Koşullu öznitelikler tüm listeler ve öğeleri uygulanabilir. Mantıksal işleçler ve sembol genişletme ifadeler doğru veya yanlış olarak değerlendirin. TRUE ise, sonuçta elde edilen çıktı ilişkili liste veya öğesi içerir.  
  
 Belirteç genişletmeleri diğer belirteç genişletmeleri veya sabitleri karşı test edilmelidir. Defined() işlevi, hiçbir değer olsa bile belirli bir adı tanımlı olup olmadığını test etmek için kullanılır.  
  
 Bir koşul özniteliği bir listeye uygulandığında, koşul listesindeki her alt öğenin uygulanır. Bir alt öğesi koşul özniteliği içeriyorsa, koşul ve işlem tarafından üst ifade ile birleştirilir.  
  
 1, '1' ve 'true' değerlerini doğru olarak değerlendirilir ve 0, '0' ve 'false' yanlış olarak değerlendirilir.  
  
## <a name="operators"></a>İşleçler  
 Aşağıdaki işleçleri koşullu ifadeler değerlendirmek için kullanılabilir.  
  
|İşleç|Tanım|  
|--------------|----------------|  
|(,)|Gruplandırma|  
|!|Mantıksal değil|  
|\<, >, \<=, >=, ==, !=|İlişkisel ve eşitlik|  
|and|Boole değeri|  
|veya|Boole değeri|  
  
## <a name="examples"></a>Örnekler  
  
```  
<Menu Condition="Defined(DEBUG)" ...  
</Menu>  
  
<Menu Condition="%(SKU_MODE) = 'Demo'" ...  
</Menu>  
  
<Menus Condition="Defined(DEBUG)">  
    <Menu ...  
    </Menu>  
</Menus>  
  
<Menus Condition="Defined(DEMO_SKU)">  
    <Menus Condition="!Defined(DEBUG)">  
        <Menu ...  
        </Menu>  
    </Menus>  
  
    <Menu ...  
    </Menu>  
</Menus>  
  
<Menus Condition="(Defined(DEMO_SKU) or Defined(SAMPLE_SKU))   
and !Defined(DEBUG)">  
    <Menu ...  
    </Menu>  
</Menus>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)