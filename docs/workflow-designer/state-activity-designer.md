---
title: "Durum etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.State.UI
ms.assetid: 9455ab37-93a0-4c46-9eb8-b6611ca23167
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: c2942b8973dadd0d9f04b0bf9738661f4ec44703
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="state-activity-designer"></a>Durum etkinlik Tasarımcısı
A <xref:System.Activities.Statements.State> içinde Durum makinesi olabilen içinde bir durumu temsil eder.

## <a name="using-the-state-activity-designer"></a>Durum etkinlik Tasarımcısı'nı kullanarak
 Eklemek için bir <xref:System.Activities.Statements.State> bir iş akışına sürükleyin **durumu** etkinlik Tasarımcısı'ndan **Durum makinesi** bölümünü **araç** ve oturum bırakın bir <xref:System.Activities.Statements.StateMachine> Windows iş akışı Tasarımcısı yüzeyinde etkinliği. A <xref:System.Activities.Statements.State> etkinlik bırakılan üzerine bir <xref:System.Activities.Statements.StateMachine> ve geçişleri eklenen daha sonra; veya bir geçiş olarak oluşturulabilir <xref:System.Activities.Statements.State> etkinlik bırakıldı. Eklemek için bir <xref:System.Activities.Statements.State> etkinliği ve bir geçiş tek bir adımda Sürükle oluşturmak bir **durumu** etkinliğinden **Durum makinesi** bölümünü **araç** ve başka getirin İş Akışı Tasarımcısı'nda durumu. Zaman sürüklenen <xref:System.Activities.Statements.State> başka bir <xref:System.Activities.Statements.State>, dört üçgenler diğer görünür <xref:System.Activities.Statements.State>. Varsa <xref:System.Activities.Statements.State> bırakılır dört üçgenler birini için durum makinesinin eklenir ve bir geçiş kaynak sunucudan oluşturulan <xref:System.Activities.Statements.State> bırakılan hedefe <xref:System.Activities.Statements.State>. Daha fazla bilgi için bkz: [geçiş](../workflow-designer/transition-activity-designer.md).

### <a name="state-activity-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda durum etkinlik özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.State> Tasarımcısı'nda nasıl kullanıldığını açıklar ve iş akışı Tasarımcısı'nı kullanarak ayarlanabilir özellikleri. Bu özelliklerden bazıları özellik kılavuzunda düzenlenebilir ve bazı Tasarımcı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.State.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.State> etkinlik Tasarımcısı'nda başlığı. Varsayılan değer **durumu**. Değeri, özellik kılavuzu veya etkinlik Tasarımcısı başlığındaki doğrudan düzenlenebilir. <xref:System.Activities.Statements.State.DisplayName%2A> İş akışı Tasarımcısı'nı üstünde görüntülenen içerik haritası Gezinti kullanılır.<br /><br /> Ancak <xref:System.Activities.Statements.State.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.State.Entry%2A>|False|Bu durum için geçirildiğinde uygulanacak eylemi belirtir. Zaman <xref:System.Activities.Statements.State> etkinlik genişletildiğinde, bu değer bir etkinlikten sürükleyerek ayarlanabilir **araç** ve üzerine bırakmadan **girişi** bölüm durumu.|
|<xref:System.Activities.Statements.State.Exit%2A>|False|Bu durum merkezden geçirildiğinde uygulanacak eylemi belirtir. Zaman <xref:System.Activities.Statements.State> etkinlik genişletildiğinde, bu değer bir etkinlikten sürükleyerek ayarlanabilir **araç** ve üzerine bırakmadan **çıkış** bölüm durumu.|
|<xref:System.Activities.Statements.State.Transitions%2A>|False|Kaynaklanan olası geçişler listeler <xref:System.Activities.Statements.State>. Listedeki her öğeye ilişkili bir bağlantı vardır <xref:System.Activities.Statements.Transition> ve hedef <xref:System.Activities.Statements.State>. Bağlantı tıklatıldığında değiştirmek Tasarımcısı için genişletilmiş görünümünü <xref:System.Activities.Statements.Transition> veya <xref:System.Activities.Statements.State>.|

## <a name="see-also"></a>Ayrıca bkz.

- [StateMachine](../workflow-designer/statemachine-activity-designer.md)
- [Son durum](../workflow-designer/finalstate-activity-designer.md)
- [geçiş](../workflow-designer/transition-activity-designer.md)