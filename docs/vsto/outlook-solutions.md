---
title: "Outlook çözümleri | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], Outlook
- Office projects [Office development in Visual Studio], Outlook
- Office solutions [Office development in Visual Studio], Outlook
- templates [Office development in Visual Studio], Outlook
- projects [Office development in Visual Studio], Outlook
- Outlook [Office development in Visual Studio]
- e-mail [Office development in Visual Studio], Outlook solutions
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c2ee35159e978150e7b63bacac127d5f7b8236c5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="outlook-solutions"></a>Outlook Çözümleri
  Visual Studio Proje şablonları, Microsoft Office Outlook için VSTO eklentileri oluşturma için kullanabileceğiniz sağlar. VSTO eklentileri Outlook otomatikleştirmek, Outlook özelliklerini genişletmek veya Outlook kullanıcı arabirimi (UI) özelleştirmek için kullanabilirsiniz. VSTO eklentileri hakkında daha fazla bilgi için bkz: [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
## <a name="creating-an-outlook-vsto-add-in-project"></a>Bir Outlook VSTO eklenti projesindeki oluşturma  
 Outlook projeleri kullanarak oluşturma **Outlook eklentisi** proje şablonu **yeni proje** iletişim kutusu. Bu şablon gerekli derleme başvurularını ve proje dosyalarını içerir.  
  
 Bir VSTO eklenti projesi oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md). Proje şablonları hakkında daha fazla bilgi için bkz: [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md).  
  
## <a name="outlook-vsto-add-in-programming-model"></a>Outlook VSTO eklenti programlama modeli  
 Outlook VSTO eklenti projesindeki oluşturduğunuzda, Visual Studio adlı bir sınıf oluşturur `ThisAddIn`, çözümünüzün temeli. Bu sınıf, kodunuzu yazmak için bir başlangıç noktası sağlar ve Outlook için VSTO eklentinizi nesne modelini de sunar.  
  
 Hakkında daha fazla bilgi için `ThisAddIn` sınıfı ve bir VSTO eklenti, kullanabileceğiniz diğer özellikler bkz [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
## <a name="automating-outlook-by-using-the-outlook-object-model"></a>Outlook nesne modeli kullanarak Outlook otomatikleştirme  
 Outlook nesne modeli Outlook otomatikleştirmek için kullanabileceğiniz birçok türü ortaya çıkarır. Bu tür ortak görevleri gerçekleştirmek için kod yazmayı etkinleştir:  
  
-   Program aracılığıyla oluşturma ve e-posta iletileri gönderme.  
  
-   Yeni toplantı istekleri gönderme.  
  
-   Outlook klasörleri öğeleri arayın.  
  
 Daha fazla bilgi için bkz: [Outlook nesne modeline genel bakış](../vsto/outlook-object-model-overview.md).  
  
## <a name="customizing-the-user-interface-of-an-outlook-application"></a>Outlook uygulamasını kullanıcı arabirimini özelleştirme  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Outlook Inspector Şerite özel sekmeler ekleme|[Şeride Genel Bakış](../vsto/ribbon-overview.md)|  
|Outlook Inspector yerleşik bir sekmede özel gruplar ekleyin.|[Nasıl Yapılır: Yerleşik Bir Sekmeyi Özelleştirme](../vsto/how-to-customize-a-built-in-tab.md)|  
|Outlook Denetçisi'nde görüntülenen özel görev bölmesi ekleme|[Özel görev bölmeleri](../vsto/custom-task-panes.md).|  
|Genişletir veya varolan Outlook formlarını değiştiren bir form bölgesi ekleme.|[Outlook Form Bölgeleri Oluşturma](../vsto/creating-outlook-form-regions.md)|  
  
 Outlook UI ve diğer Microsoft Office uygulamaları özelleştirme hakkında daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Outlook Nesne Modeline Genel Bakış](../vsto/outlook-object-model-overview.md)|Outlook nesne modeli tarafından sağlanan nesneler genel bir bakış sağlar.|  
|[Outlook Form Bölgeleri Oluşturma](../vsto/creating-outlook-form-regions.md)|Tasarlama, geliştirme ve form bölgeleri hata ayıklama kolaylaştıracak Visual Studio tarafından sağlanan araçları açıklanmaktadır.|  
|[İnceleme: Outlook için İlk VSTO Eklentinizi Oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)|Microsoft Office Outlook için VSTO eklentisi oluşturulacağı gösterilmektedir.|  
|[Outlook 2010 Office geliştirme](http://go.microsoft.com/fwlink/?LinkId=199013)|MSDN burada makaleleri bulmaya ve başvuru (Visual Studio kullanarak Office geliştirmeye özgü olmayan) Outlook çözümleri geliştirme hakkında belgeleri kitaplığı alanı.|  
  
  