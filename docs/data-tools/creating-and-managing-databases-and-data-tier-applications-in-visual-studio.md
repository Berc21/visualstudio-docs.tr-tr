---
title: "Veritabanı projeleri, sunucu projeler ve Visual Studio projelerinde DAC | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing change, databases
- database features of Visual Studio, managing change
- databases, managing change
- managing change, database servers
ms.assetid: 40b51f5a-d52c-44ac-8f84-037a0917af33
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 8e599e1d309ab254c2b2d5a3a490c0cd912b8823
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="database-projects-and-data-tier-applications-in-visual-studio"></a>Veritabanı projeleri ve Visual Studio'da veri katmanı uygulamaları  
Veritabanı projeleri yeni veritabanları oluşturmak için kullanabileceğiniz yeni veri katmanı uygulamaları (Dac'ler) ve varolan veritabanları ve veri katmanı uygulamaları güncelleştirmek için. Hem veritabanı projeleri hem de DAC projeleri, sürüm denetimi ve proje yönetimi tekniklerini yönetilen veya özgün kod bu teknikler uygulamak benzer şekilde, veritabanı geliştirme çabalarınız uygulamak etkinleştirin. Geliştirme ekibiniz oluşturarak veritabanları ve veritabanı sunucuları için değişiklikleri yönetmenize yardımcı olabilir bir *DAC proje*, *veritabanı projesi*, veya bir *sunucu projesi* ve onu koyma Sürüm denetimi altında. Ekibinizin üyeleri sonra kontrol edebilirsiniz, yapı ve değişiklikleri test dosyalarını bir *yalıtılmış geliştirme ortamı*, veya ekiple paylaşımı önce korumalı alan,. Kod kalitesini sağlamaya yardımcı olmak için takımınızın tamamlayın ve üretime değişiklikleri dağıtmadan önce tüm değişiklikleri veritabanına belirli bir sürümü için bir hazırlama ortamında test.  
  
Veri katmanı uygulamaları tarafından desteklenen veritabanı özelliklerinin bir listesi için bkz: [desteklenen özellikler veri katmanlı uygulamalarda](http://go.microsoft.com/fwlink/?LinkId=164239) Microsoft web sitesinde. Veri katmanı uygulamaları tarafından desteklenmeyen özellikleri veritabanınızdaki kullanırsanız, değişiklikleri veritabanınızı yönetmek için bunun yerine veritabanı projesi kullanmanız gerekir.  
  
## <a name="common-high-level-tasks"></a>Ortak üst düzey görevler  
  
|Üst düzey görev|Destekleyici İçerik|  
|----------------------|------------------------|  
|**Veri katmanı uygulaması geliştirme Başlat:** A DAC olduğu ile sunulan yeni bir kavram [!INCLUDE[sskatmai_r2](../data-tools/includes/sskatmai_r2_md.md)] tanımını içeren bir [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] veritabanını ve destekleyen bir istemci-sunucu veya 3 katmanlı tarafından kullanılan nesneleri örneği uygulama. Bir DAC tabloları ve görünümleri, oturum açma bilgileri gibi örnek varlıkları birlikte gibi veritabanı nesnelerini içerir. Kullanabileceğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DAC projesi oluşturmak için DAC paket dosyası oluşturun ve o DAC paket dosyası örneği üzerine dağıtımı için veritabanı yöneticisi göndermek [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] veritabanı altyapısı.|-   [Veri katmanı uygulamaları oluşturma ve yönetme](http://go.microsoft.com/fwlink/?LinkId=160741) (Microsoft web sitesi)<br />-   [SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=227328)|  
|**Yinelemeli veritabanı geliştirme gerçekleştirme:** bir geliştirici veya bir tester ise, proje bölümlerini denetleyin ve bunları bir yalıtılmış geliştirme ortamında güncelleştirin. Bu ortam türünü kullanarak diğer takım üyeleri etkilemeden değişikliklerinizi test edebilirsiniz. Değişiklikler tamamlandıktan sonra burada diğer ekip üyelerinin değişikliklerinizi edinebilir ve yapı ve test sunucusuna dağıtmak geri sürüm denetimine, dosyalarını denetleyin.|-   [Sorgu ve metin düzenleyicileri (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327) (Microsoft web sitesi)<br />-   [Transact-SQL hata ayıklayıcı](http://go.microsoft.com/fwlink/?LinkId=227324) (Microsoft web sitesi)|  
|**Prototipi oluşturulurken, doğrulama test sonuçları, değiştirme veritabanı komut dosyalarında ve nesneleri:** kullanabileceğiniz [!INCLUDE[tsql](../data-tools/includes/tsql_md.md)] Düzenleyicisi'ni bu ortak görevleri herhangi birini gerçekleştirebilirsiniz.|-   [Sorgu ve metin düzenleyicileri (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327) (Microsoft web sitesi)|  
  
## <a name="see-also"></a>Ayrıca bkz.
[.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)
