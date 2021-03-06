---
title: "Nasıl yapılır: bir iş akışı etkinlik kitaplığı (eski) oluşturun | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, activity library projects
- workflow activity libraries
- projects, workflow activity libraries
ms.assetid: fb5aa940-2ae8-4b52-b52c-51c20861a7b4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 60d6fb1aebc6810a271eda8806fe6ac83060f73f
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-create-a-workflow-activity-library-legacy"></a>Nasıl yapılır: bir iş akışı etkinlik kitaplığı (eski) oluşturun

Eski Windows iş akışı tarafından sağlanan Tasarımcısı'nı kullanarak bir iş akışı etkinlik kitaplığı projesi oluşturmak için bu adımları [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]. Eski kullanmak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ya da hedeflemek gerektiğinde [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

### <a name="to-create-a-workflow-activity-library-project"></a>Bir iş akışı etkinlik kitaplığı projesi oluşturmak için

1.  Visual Studio'yu başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

     **Yeni proje** iletişim kutusu açılır.

3.  Şunlardan birini seçin **.NET Framework 3.0** seçeneği veya **.NET Framework 3.5** aşağı açılan listeden en üstündeki seçeneğinde **yeni proje** eski Tasarımcısı erişmek için penceresi.

    > [!NOTE]
    > Varsayılan seçenek [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] olan **.NET Framework 4**. Bu seçenek oluşturmak için kullanılan [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] hedefleyen uygulamalar [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] ve eski Tasarımcısı'nı kullanmaz.

4.  İçinde **proje türleri** bölmesinde, select Visual C# veya Visual Basic (altında **diğer diller**) ve ardından **iş akışı**.

5.  İçinde **şablonları** bölmesinde, **iş akışı etkinlik kütüphanesini**.

6.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.

7.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.

     Proje için oluşturulan bir çözüm dizin istiyorsanız seçin **çözüm için dizin oluştur** onay kutusunu işaretleyin ve bir ad girin **çözüm adı** kutusu.

8.  **Tamam**'ı tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışı Projeleri Oluşturma](../workflow-designer/creating-legacy-workflow-projects.md)
- [Eski Etkinlik Tasarımcısını Kullanma](../workflow-designer/using-the-legacy-activity-designer.md)
- [Eski İş Akışı Etkinlikleri ](../workflow-designer/legacy-workflow-activities.md)
- [İş akışı etkinliklerini geliştirme](http://msdn.microsoft.com/en-us/19876dfc-dfa5-4d52-b1f5-1d087474cc52)
- [Windows Workflow Foundation etkinlikleri](http://msdn.microsoft.com/en-us/192c4c1e-afb6-4f58-ab11-2b5bbbc2d2c0)