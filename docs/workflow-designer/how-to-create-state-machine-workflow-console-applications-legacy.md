---
title: "Nasıl yapılır: Durum makinesi iş akışı konsol uygulamaları (eski) oluşturma | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- console applications, state machine workflows
- state machine workflow console applications
- state machine workflows, console applicationa
ms.assetid: d6170b5d-5d4f-48e1-8257-c78604f27eac
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1d345afcddaae2e3a139fbf7861b78f57774ead6
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-create-state-machine-workflow-console-applications-legacy"></a>Nasıl yapılır: Durum makinesi iş akışı konsol uygulamaları (eski) oluşturma
Eski Windows iş akışı tarafından sağlanan Tasarımcısı'nı kullanarak bir Durum makinesi iş akışı konsol uygulaması projesi oluşturmak için bu adımları [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]. Eski kullanmak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ya da hedeflemek gerektiğinde [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

### <a name="to-create-a-state-machine-application-project"></a>Bir durum makine uygulama projesi oluşturmak için

1.  Visual Studio'yu başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

     **Yeni proje** iletişim kutusu açılır.

3.  Şunlardan birini seçin **.NET Framework 3.0** seçeneği veya **.NET Framework 3.5** aşağı açılan listeden en üstündeki seçeneğinde **yeni proje** eski Tasarımcısı erişmek için penceresi.

    > [!NOTE]
    > Varsayılan seçenek [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] olan **.NET Framework 4**. Bu seçenek oluşturmak için kullanılan [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] hedefleyen uygulamalar [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] ve eski Tasarımcısı'nı kullanmaz.

4.  İçinde **proje türleri** bölmesinde, select Visual C# veya Visual Basic (altında **diğer diller**) ve ardından **iş akışı**.

5.  İçinde **şablonları** bölmesinde, **Durum makinesi iş akışı konsol uygulaması**.

6.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.

7.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.

     Proje için oluşturulan bir çözüm dizin istiyorsanız seçin **çözüm için dizin oluştur** onay kutusunu işaretleyin ve bir ad girin **çözüm adı** kutusu.

8.  **Tamam**'ı tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışı Projeleri Oluşturma](../workflow-designer/creating-legacy-workflow-projects.md)
- [Nasıl yapılır: Durum Makinesi İş Akışı Kitaplığı Oluşturma (Eski)](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md)