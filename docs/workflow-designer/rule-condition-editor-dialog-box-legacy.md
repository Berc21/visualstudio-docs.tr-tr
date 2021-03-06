---
title: "Kural Koşulu Düzenleyicisi iletişim kutusu (eski) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Workflow.Activities.Rules.Design.RuleConditionDialog.UI
helpviewer_keywords:
- Rule Condition dialog box
ms.assetid: c7ca8be9-de31-4a64-939c-4d53a50d5e29
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1e3e4c54dff4bded0bcc07fb5e8891162cc12ea8
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="rule-condition-editor-dialog-box-legacy"></a>Kural Koşulu Düzenleyicisi iletişim kutusu (eski)

Bu konuda açıklanmaktadır kullanma **Kural Koşulu Düzenleyicisi** eski Windows iş akışı Tasarımcısı'nda iletişim kutusu. Eski kullanmak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ya da hedeflemek gerektiğinde [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

Oluşturma ve bildirim temelli kural koşulları kullanarak değiştirme **Kural Koşulu Düzenleyicisi** iletişim kutusu. Bu kural koşulları, aşağıdaki Windows Workflow Foundation out-of-box etkinliklerin özellikleri olarak sunulur:

-   [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)

-   [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)

-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)

-   [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)

-   [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)

-   [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)

Size erişim **Kural Koşulu Düzenleyicisi** iletişim kutusunu kullanarak [koşulu iletişim kutusunu (eski)](../workflow-designer/select-condition-dialog-box-legacy.md).

Kullanıcı Arabirimi (UI) öğelerini aşağıdaki tabloda açıklanmaktadır **Kural Koşulu Düzenleyicisi** iletişim kutusu.

|Arabirim Öğesi|Açıklama|
|----------------|-----------------|
|**Koşul:**|Kural koşulu için ifade girin.|
|**TAMAM**|Kural koşulu kaydetmek için tıklatın.|

## <a name="entering-condition-expressions"></a>Koşul ifadeleri girme

Koşul ifadeleri metin olarak girilir. Yazabilirsiniz **bu.** düzenleyicisine alanları, özellikleri ve yöntemleri iş akışı içinde kullanılan başvurmak için IntelliSense benzeri menüsünü kullanarak. Veya doğrudan bir iş akışı üye adı yazın. AND, OR gibi koşul mantıksal işleçler ekleyebilirsiniz ve değil. Koşulları de ekleyebilirsiniz. Bir koşul, ikili işleç ve iki işlenen ' dir. Desteklenen ikili işleçler  **==** ,  **>** ,  **\<** ,  **>=** , ve  **<=** . Desteklenen işlenenler sabit değer, aritmetik işlevi ve kapsamlı Genel Üyeler ' dir.

Karşılaştırma için türünü belirtebilirsiniz ve'karşılaştırabilirsiniz **null** ya da boş bir dize. Örneğin, bir karmaşık tür içeren bir değişken iç içe geçmiş çağrıları üyelerine yapabileceğiniz `this.Address.State == "WA"`.

Kural Koşulu Düzenleyicisi aşağıdaki işleçleri destekler:

-   İlişkisel işleçleri: ==, =,! =

-   Karşılaştırma işleçleri: <, \<=, >, > =

-   Aritmetik işleçler: +, -, \*, /, MOD

-   Mantıksal işleçler: ve, & &, OR &#124; &#124;değil,!

-   Bitwise operators: &, &#124;

İfade İşleç önceliği C# işleci öncelik kuralları izler.

Kural Koşulu Düzenleyicisi aşağıdaki sayısal ifadeler destekler:

this.i == 1 D (çözümler 1.0 için)

this.i 1E1 == (10.0 için çözümler)

this.i == 1 M (çözümler bir uzun olarak)

this.i == 1 M (çözümler bir ondalık olarak)

this.i 1F == (tek bir çözümler)

this.i 1U == (imzalanmamış int çözümler)

Koşullar hakkında daha fazla bilgi için bkz: [kullanan koşulları iş akışlarında](http://go.microsoft.com/fwlink?LinkID=65009).

## <a name="see-also"></a>Ayrıca bkz.

- [IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033)
- [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)
- [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)
- [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)
- [Koşul Seç İletişim Kutusu (Eski)](../workflow-designer/select-condition-dialog-box-legacy.md)
- [İş akışlarında koşullar kullanma](http://go.microsoft.com/fwlink?LinkID=65009)
- [Windows Workflow Foundation Kullanıcı Arabirimi Yardımı için Eski Tasarımcı](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)