---
title: "Durum etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.State.UI
ms.assetid: 9455ab37-93a0-4c46-9eb8-b6611ca23167
caps.latest.revision: "5"
ms.author: sdanie
manager: erikre
ms.openlocfilehash: 22e9e9c6f31923eb097b34eab19e61762fb2956b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="state-activity-designer"></a>Durum etkinlik Tasarımcısı
A <xref:System.Activities.Statements.State> içinde Durum makinesi olabilen içinde bir durumu temsil eder.  
  
## <a name="using-the-state-activity-designer"></a>Durum etkinlik Tasarımcısı'nı kullanarak  
 Eklemek için bir <xref:System.Activities.Statements.State> bir iş akışına sürükleyin **durumu** etkinlik Tasarımcısı'ndan **Durum makinesi** bölümünü **araç** ve oturum bırakın bir <xref:System.Activities.Statements.StateMachine> faaliyete [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] yüzeyini. A <xref:System.Activities.Statements.State> etkinlik bırakılan üzerine bir <xref:System.Activities.Statements.StateMachine> ve geçişleri eklenen daha sonra; veya bir geçiş olarak oluşturulabilir <xref:System.Activities.Statements.State> etkinlik bırakıldı. Eklemek için bir <xref:System.Activities.Statements.State> etkinliği ve bir geçiş tek bir adımda Sürükle oluşturmak bir **durumu** etkinliğinden **Durum makinesi** bölümünü **araç** ve başka getirin İş Akışı Tasarımcısı'nda durumu. Zaman sürüklenen <xref:System.Activities.Statements.State> başka bir <xref:System.Activities.Statements.State>, dört üçgenler diğer görünür <xref:System.Activities.Statements.State>. Varsa <xref:System.Activities.Statements.State> bırakılır dört üçgenler birini için durum makinesinin eklenir ve bir geçiş kaynak sunucudan oluşturulan <xref:System.Activities.Statements.State> bırakılan hedefe <xref:System.Activities.Statements.State>. Daha fazla bilgi için bkz: [geçiş](../workflow-designer/transition-activity-designer.md).  
  
### <a name="state-activity-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda durum etkinlik özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.State> Tasarımcısı'nda nasıl kullanıldığını açıklar ve iş akışı Tasarımcısı'nı kullanarak ayarlanabilir özellikleri. Bu özelliklerden bazıları özellik kılavuzunda düzenlenebilir ve bazı Tasarımcı yüzeyine düzenlenebilir.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.State.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.State> etkinlik Tasarımcısı'nda başlığı. Varsayılan değer **durumu**. Değeri, özellik kılavuzu veya etkinlik Tasarımcısı başlığındaki doğrudan düzenlenebilir. <xref:System.Activities.Statements.State.DisplayName%2A> İş akışı Tasarımcısı'nı üstünde görüntülenen içerik haritası Gezinti kullanılır.<br /><br /> Ancak <xref:System.Activities.Statements.State.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.State.Entry%2A>|False|Bu durum için geçirildiğinde uygulanacak eylemi belirtir. Zaman <xref:System.Activities.Statements.State> etkinlik genişletildiğinde, bu değer bir etkinlikten sürükleyerek ayarlanabilir **araç** ve üzerine bırakmadan **girişi** bölüm durumu.|  
|<xref:System.Activities.Statements.State.Exit%2A>|False|Bu durum merkezden geçirildiğinde uygulanacak eylemi belirtir. Zaman <xref:System.Activities.Statements.State> etkinlik genişletildiğinde, bu değer bir etkinlikten sürükleyerek ayarlanabilir **araç** ve üzerine bırakmadan **çıkış** bölüm durumu.|  
|<xref:System.Activities.Statements.State.Transitions%2A>|False|Kaynaklanan olası geçişler listeler <xref:System.Activities.Statements.State>. Listedeki her öğeye ilişkili bir bağlantı vardır <xref:System.Activities.Statements.Transition> ve hedef <xref:System.Activities.Statements.State>. Bağlantı tıklatıldığında değiştirmek Tasarımcısı için genişletilmiş görünümünü <xref:System.Activities.Statements.Transition> veya <xref:System.Activities.Statements.State>.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Durum makinesi](../workflow-designer/statemachine-activity-designer.md)   
 [Son durum](../workflow-designer/finalstate-activity-designer.md)   
 [Geçiş](../workflow-designer/transition-activity-designer.md)