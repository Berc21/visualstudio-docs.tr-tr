---
title: "Office çözümlerinin işbirlikçi geliştirme | Microsoft Docs"
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
- Office applications [Office development in Visual Studio], collaborative development
- Office development in Visual Studio, collaboration
- source control [Office development in Visual Studio]
- collaborative development [Office development in Visual Studio]
ms.assetid: c493354b-17d3-4e50-85f0-968b104bc978
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 94313e1e7cb8d6f36c5c8bfb505d280f4e235a3b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="collaborative-development-of-office-solutions"></a>Office Çözümlerinin İşbirlikçi Geliştirmesi
  Birden çok geliştiricilerin Office projesinde, diğer Visual Studio projelerinde birlikte aynı şekilde çalışabilir. Office farklı konumlarda yüklü olsa bile visual Studio Microsoft Office yüklemesini her bilgisayarda doğru bulur. Ancak, farkında olmanız gereken bazı önemli noktalar vardır.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="debug-properties-are-not-shared"></a>Hata ayıklama özellikleri paylaşılmayan  
 Hata ayıklama özellikleri paylaşılamaz kaynak denetimi altında birden çok kullanıcı. Visual Basic ve Visual C# projeleri, kullanıcıya özel dosyada hata ayıklama özelliklerini depolar (*ProjectName*. vbproj.user veya *ProjectName*. csproj.user), ve bu dosya kaynak denetimi altında değil. Birden çok kişi hata ayıklama, her kişi hata ayıklama özelliklerini el ile girmeniz gerekir.  
  
 Proje kaynak denetiminde yerine ağ paylaşımında barındırılıyorsa çözümü açın ve derleme sınamak birlikte çalışan geliştiricilerin etkinleştirmek için bazı ek adımlar izlenmelidir.  
  
## <a name="source-control-requires-checking-out-all-files"></a>Kaynak Denetimi tüm dosyaları kullanıma alma gerektirir  
 Projeler için kaynak denetimi kullanırsanız, bir kod dosyasında altındaki tüm dosyaların kullanıma **Çözüm Gezgini** (ThisDocument, ThisWorkbook veya ThisAddIn kod dosyaları gibi) kod dosyası her değiştirdiğinizde bile Varsayılan olarak gizli dosyalar. Yalnızca üst düzey kod dosyasını kullanıma işaretlerseniz, yaptığınız değişiklikler kaybolabilir.  
  
 Yaptığınız değişiklikleri yaptıktan sonra tüm dosyalar geri denetleyin. Projelerdeki gizli kod dosyaları hakkında daha fazla bilgi için bkz: [Visual Studio ortamında Office projeleri](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
## <a name="security-for-informal-collaboration-on-a-network"></a>Bir ağ üzerinde resmi olmayan işbirliği için güvenlik  
 Bir ağ konumundaki tüm belge düzeyi çözümleri (gibi \\ \\ *Servername*\\*Sharename*), tam konum eklenmelidir birlikte çalıştığınız Microsoft Office uygulamasında güvenilir klasör listesi. Ana klasörü altında alt dizinleri içerir veya özel olarak hata ayıklama ekleyin ve yapı klasörlerini güvenilir klasör listesine seçeneğini seçin. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [belgelere güven verme](../vsto/granting-trust-to-documents.md).  
  
 Derleme zamanında otomatik olarak oluşturulan geçici sertifikalar parolalarla değil. Sertifikalar geliştiricinin oturum açma adı ve diğer kişisel bilgileri içerir. Geçici sertifikalar tarafından imzalanan özelleştirmeler dağıtıyorsanız, diğerlerinin bu bilgilere erişmek olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office çözümleri oluşturma](../vsto/building-office-solutions.md)  
  
  