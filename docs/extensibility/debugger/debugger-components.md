---
title: "Bileşenleri hata ayıklayıcı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Visual Studio], components
- components [Visual Studio SDK], debugging
- debugging [Debugging SDK], components
ms.assetid: 8b8ab77f-a134-495c-be42-3bc51aa62dfb
caps.latest.revision: "30"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1137c8c5c6041b41e8cbdc0e13d43b6188bd1b1b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugger-components"></a>Hata ayıklayıcı bileşenleri
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Hata ayıklayıcı VSPackage uygulanır ve tüm hata ayıklama oturumu yönetir. Hata ayıklama oturumu aşağıdaki öğeleri içerir:  
  
-   **Hata ayıklama paketi:** [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklayıcı ne ayıklanacak olsun aynı kullanıcı arabirimi sağlar.  
  
-   **Oturum hata ayıklama Yöneticisi (SDM):** tutarlı bir programlama arabirimi sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklayıcısı hata ayıklama motorları çeşitli yönetimi. Tarafından uygulanan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   **İşlem Hata Ayıklama Yöneticisi'ni (PDM):** yönetir, tüm çalışan örneklerinde için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], olabilir veya ayıklanacak tüm programların listesini. Tarafından uygulanan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   **Altyapısı (DE) hata ayıklama:** ayıklanacak, bir program izlemekten sorumludur SDM ve PDM çalışan programın durumunu iletişim ve gerçek zamanlı analizini sağlamak için ifade değerlendiricisi ve sembol sağlayıcısı ile etkileşim kurma bir programın bellek ve değişkenleri durumu. Tarafından uygulanan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (için desteklenen dilleri) ve kendi çalıştırma desteklemek istediğiniz üçüncü taraf satıcılar.  
  
-   **İfade değerlendirici (EE):** değişkenleri ve belirli bir noktada bir programı durdurulduğunda kullanıcı tarafından sağlanan ifadeleri dinamik olarak değerlendirmek için destek sağlar. Tarafından uygulanan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (için desteklenen dilleri) ve kendi dilleri desteklemek isteyen üçüncü taraf satıcılar.  
  
-   **Sembol sağlayıcısı (SP):** olarak da bilinir bir simge işleyici eşlemeleri bir programın hata ayıklama simgeleri program çalışan bir örneğini böylece anlamlı bilgiler (kaynak kodu düzeyi hata ayıklama ve ifade değerlendirmesi gibi) sağlanabilir. Tarafından uygulanan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (ortak dil çalışma zamanı için [CLR] sembolleri ve [PDB] Program veritabanı dosya biçimi sembol) ve hata ayıklama bilgilerini depolamak, kendi özel yöntemi olan üçüncü taraf satıcılar tarafından.  
  
 Aşağıdaki diyagramda, Visual Studio hata ayıklayıcısı bu öğeleri arasındaki ilişkiyi gösterir.  
  
 ![Hata ayıklama bileşenlerine genel bakış](../../extensibility/debugger/media/dbugcompovrview.gif "DBugCompOvrview")  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Paket Hatalarını Ayıklama](../../extensibility/debugger/debug-package.md)  
 Çalışan hata ayıklama paket anlatılmaktadır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kabuk ve tüm UI işler.  
  
 [İşlem Hata Ayıklama Yöneticisi](../../extensibility/debugger/process-debug-manager.md)  
 Hata ayıklaması yapılabilir işlemler yöneticisi PDM özelliklerine genel bakış sağlar.  
  
 [Oturum Hata Ayıklama Yöneticisi](../../extensibility/debugger/session-debug-manager.md)  
 Hata ayıklama oturumu birleşik bir görünümünü sağlar IDE SDM tanımlar. SDM DE yönetir.  
  
 [Hata Ayıklama Altyapısı](../../extensibility/debugger/debug-engine.md)  
 DE sağladığı hata ayıklama Hizmetleri belgeleri.  
  
 [Çalışma Modları](../../extensibility/debugger/operational-modes.md)  
 IDE çalışabilir üç modu genel bir bakış sağlar: Tasarım modunda, çalışma modunda ve kesme modu. Geçiş mekanizmaları da ele alınmıştır.  
  
 [İfade Değerlendirici](../../extensibility/debugger/expression-evaluator.md)  
 EE amacını çalışma zamanında açıklar.  
  
 [Sembol Sağlayıcısı](../../extensibility/debugger/symbol-provider.md)  
 Değişkenleri ve ifadeler uygulama simgesi sağlayıcısı nasıl değerlendirir açıklanır.  
  
 [Tür Görselleştiricisi ve Özel Görüntüleyici](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)  
 Ne anlatılmaktadır türü Görselleştirici ve özel Görüntüleyicisi ve ifade değerlendiricisi hangi rolü oynar her ikisi de destekleme.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Hata Ayıklayıcı Kavramları](../../extensibility/debugger/debugger-concepts.md)  
 Ana hata ayıklama mimari kavramlarını açıklar.  
  
 [Hata Ayıklayıcı Bağlamları](../../extensibility/debugger/debugger-contexts.md)  
 Nasıl DE aynı anda kod, belgeler ve ifade değerlendirme bağlamı içinde çalıştığı açıklanmaktadır. , Her üç bağlamları, konum, konum veya değerlendirme için ilgili açıklar.  
  
 [Hata Ayıklama Görevleri](../../extensibility/debugger/debugging-tasks.md)  
 Bir program başlatma ve ifadeleri değerlendirme gibi çeşitli hata ayıklama görevlere bağlantılar içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)