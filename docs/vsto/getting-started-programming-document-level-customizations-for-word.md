---
title: "Word için belge düzeyi özelleştirme programlamasına başlama | Microsoft Docs"
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
- Word solutions in Visual Studio
- Word projects [Office development in Visual Studio], getting started
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8ad9195a0ef0274400b4c7c69d23a7f1f94d838d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="getting-started-programming-document-level-customizations-for-word"></a>Word'de Belge Düzeyinde Özelleştirme Programlamasına Başlama
  Yalnızca Visual Studio kullanarak Microsoft Office Word için belge düzeyi özelleştirmeleri oluşturma başlıyorsanız, işte bilmeniz gerekir.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
## <a name="understanding-how-document-level-customizations-for-word-work"></a>Word iş için belge düzeyi özelleştirmeleri anlama  
 Oluşturduğunuz her Word özelleştirmesi tek bir belge çevresinde temel alır. Özelleştirmeyi kullanmaya başlamak için son kullanıcı belgeyi açar veya belge Word şablonu oluşturur. Örneğin belirli alanlara imleci taşıma veya menü öğeleri ve düğmelere belgedeki olaylar olay işleme yöntemleri derlemede çağırabilir. Word'de özelleştirme tarafından sağlanan özellikler artık belge kapalı olduğunda kullanılabilir.  
  
 Daha fazla bilgi için bkz: [belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md).  
  
## <a name="creating-document-level-projects-for-word"></a>Word için belge düzeyi projelerine oluşturma  
 Word için belge düzeyi özelleştirme oluşturmak için Word belgesi veya Word Şablonu proje şablonu kullanın **yeni proje** iletişim kutusu. Bu şablonlar gerekli derleme başvurularını ve proje dosyalarını içerir.  
  
 Word için belge düzeyi projesi oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md). Proje şablonları hakkında daha fazla bilgi için bkz: [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md).  
  
## <a name="programming-word-documents-by-using-host-items-host-controls"></a>Konak öğeleri ana bilgisayar denetimleri kullanarak Word belgelerini programlama  
 *Konak öğelerini* ve *konak denetimlerini* için belge düzeyi özelleştirmelerini programlama modeli sağlar sınıflarıdır.  
  
 Konak öğeleri kodunuz için giriş noktası sağlar ve bunlar da ana bilgisayar denetimleri ve Windows Forms denetimleri için kapsayıcılar olarak çalışabilir. Word için belge düzeyi projelerinde konak öğesi tarafından temsil edilen `ThisDocument` sınıfı.  
  
 Konak denetimleri içerik denetimleri, yer işaretleri ve XML düğümlerini gibi yerel Word nesneleri temel alır. Konak denetimleri için yerel Word nesnelerine benzer işlevsellik sağlasa da, bunlar yeni olaylar, tasarımcı desteği ve veri bağlama yetenekleri de vardır. Proje kodunuzda ve Word nesne modeli gitmek zorunda kalmadan, doğrudan kodunuzda belirli nesnelere başvurma kolaylaştırır IntelliSense birinci sınıf nesneler olarak görünürler.  
  
 Daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Belge Düzeyi Özelleştirmelerini Programlama](../vsto/programming-document-level-customizations.md)  
  
-   [Genişletilmiş Nesneleri Kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)  
  
-   [Konak Öğelerine ve Denetimlerine Genel Bakış](../vsto/host-items-and-host-controls-overview.md)  
  
## <a name="customizing-the-user-interface-of-word"></a>Word kullanıcı arabirimini özelleştirme  
 Microsoft Office çözümlerinin çoğu kullanıcı arabirimi (UI) çözümü ile etkileşim kullanıcılar için herhangi bir şekilde sağlamak için Office uygulamasının değiştirin. Belge düzeyi özelleştirme kullanarak UI Word'ün değişiklik yapabilirsiniz birçok yolu vardır. Örneğin, Şerit denetimlerini ekleyebilirsiniz ve Eylemler bölmesinde görüntüleyebilirsiniz. Daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
 Projeniz Visual Studio'da doğrudan ilişkilendirilmiş belge da açabilirsiniz. Belge Visual Studio'da açıkken Word kullanıcı arabirimini kullanarak belgeyi değiştirebilirsiniz. Denetimleri sürükleyin olanak tanıyan bir tasarım yüzeyi olarak belge de kullanabilirsiniz. Daha fazla bilgi için bkz: [Visual Studio ortamında Office projeleri](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
## <a name="binding-controls-to-data"></a>Denetimlere veri bağlama  
 İçerik denetimleri ve <xref:Microsoft.Office.Tools.Word.Bookmark> denetimi olan'ndan sürükleyebilirsiniz denetimleri listesinde **veri kaynakları** penceresi. İçerik denetimleri ve bu yolla yer işaret ekleyerek bunları penceresini kullanarak ayarladığınız veri kaynağına bağlar. Herhangi bir kod yazmak zorunda kalmadan, veritabanları, hizmetleri ve iş nesneleri verilerini görüntüleyebilir. Daha fazla bilgi için bkz: [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Word için belge düzeyi özelleştirme oluşturmayı öğrenmek için bkz: [izlenecek yol: oluşturma bilgisayarınızı ilk belge düzeyi özelleştirme için Word](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md). Bu kılavuzda Office geliştirme araçlarını Visual Studio ve Word belge düzeyi özelleştirmelerini programlama modeli sunar.  
  
 Word projeleri ortak görevlerin bazıları size yol konuların listesi için bkz: [Office programlama ortak görevlerin](../vsto/common-tasks-in-office-programming.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Word çözümleri](../vsto/word-solutions.md)   
 [İzlenecek yol: Word için ilk belge düzeyi özelleştirmeyi oluşturma](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)   
 [Word kullanımında izlenecek yollar](../vsto/walkthroughs-using-word.md)   
 [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md)   
 [Office Çözümlerinde Kod Yazma](../vsto/writing-code-in-office-solutions.md)  
  
  