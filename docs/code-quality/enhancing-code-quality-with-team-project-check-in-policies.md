---
title: "İade takım projesi ilkeleriyle kod kalitesini arttırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code quality, using check-in policies
- team-based development, enhancing code quality
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c82bc929fa7633719c06569cb3dded5df651a349
ms.sourcegitcommit: e5bd950df79175a96fe62b3d4b17a3ef536ec4c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2018
---
# <a name="enhancing-code-quality-with-team-project-check-in-policies"></a>Takım Projesi İade İlkeleriyle Kod Kalitesini Arttırma

Team Foundation sürüm denetimi (TFVC'yi) kullandığınızda, takım projeleriniz için iade ilkeleri oluşturabilirsiniz. zorlamak için daha iyi bir kod ve daha verimli grup geliştirme bu sağlama yöntemleri. İade ilkeleri, takım projesi düzeyinde ayarlamak ve kod iade edilmesi için izin verilmeden önce Geliştirici bilgisayarlarda zorlanan kurallardır.

Bu takım projesi iade ilkeleri belirtebilirsiniz:

- **Derlemeler**: derleme sırasında oluşturulan yapı sonları yeni iade önce düzeltilmesi gereken gerektirir.

- **Değişiklik kümesi açıklamalarını**: kullanıcıların değişiklikler iade edilirken açıklamaları sağlaması gerekir.

- **Kod çözümleme**: Kod Analizi iade önce çalıştırmanızı gerektirir.

- **İş öğeleri**: iş öğelerinin biri veya daha fazla onay-ilişkilendirilmiş olmasını gerektirir.

> [!IMPORTANT]
> İade ilkelerini kullanmak için bağlanmanız gerekir [!INCLUDE[vststfsLong](../code-quality/includes/vststfslong_md.md)].

## <a name="common-tasks"></a>Ortak Görevler

|Görev|Destekleyici İçerik|
|----------|------------------------|
|**Oluşturma ve kod çözümleme iade ilkelerini kullanma:** standart kod çözümleme kurallarını kümesinden seçebilir veya özel bir grup oluşturabilirsiniz.|[Kod Çözümleme İade İlkeleri Oluşturma ve Kullanma](../code-quality/creating-and-using-code-analysis-check-in-policies.md)|

## <a name="related-tasks"></a>İlgili görevleri

|Görev|Destekleyici İçerik|
|----------|------------------------|
|**Kod çözümleme geliştirme işlemde kullanın:** takım üyeleri geliştirme bilgisayarlarında Kod Analizi çalıştırın. Visual Studio'da geliştiriciler yapılandırmak ve kod projeleri için kod çözümleme çalıştırır çalıştırmak, görüntülemek ve sorunları çözümlemek çalıştırır tarafından bulunan ve Uyarılar için iş öğelerini oluşturabilir.|[Uygulama Kalitesini Analiz Etme](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)|
|**Birim testleri oluşturma ve çalıştırma:** birim testleri, C#, Visual Basic ve C++ projelerine sınıfların yöntemler mantık hataları aramak için hızlı bir şekilde geliştiriciler ve sınayıcılar verin. Birim testi bir kez oluşturulabilir ve hiçbir hata sunulan emin olmak için her kaynak kodda değiştiğinde çalıştırın.|[Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)|
|**İş öğeleri ve hataları izleme:** iş öğelerini izlemek ve iş ve bilgi takım projenizin hakkında yönetmek için kullanabilirsiniz. Bir iş öğesi bir veritabanı olduğundan bu kayıt [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] atama ve iş ilerlemesini izlemek için kullanır. Farklı türlerde iş öğeleri çalışma, müşteri gereksinimleri, ürün hataları ve geliştirme görevleri gibi farklı türlerde izlemek için kullanabilirsiniz.|[İş öğeleri (VSTS)](/vsts/work/work-items/index)|

## <a name="external-resources"></a>Dış kaynaklar

[Visual Studio 2012 - bölüm 2 ile sürekli teslimat için test etme: birim testi: iç test etme](http://go.microsoft.com/fwlink/?LinkID=255188)