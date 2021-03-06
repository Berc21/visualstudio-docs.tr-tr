---
title: Karakter denetimi (kaynak denetimi VSPackage) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- glyphs, source control packages
- source control packages, glyphs
ms.assetid: b9413b08-b3c3-4fc3-a6e0-3dc0db3652d7
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e41fc2a7d09f50d70caca939e3fdd691b1d05c9e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="glyph-control-source-control-vspackage"></a>Karakter denetimi (kaynak denetimi VSPackage)
Kaynak denetimi altında öğelerinin durumunu göstermek için kendi karakterlerin görüntüleme yeteneğini kaynak denetim VSPackages kullanılabilir derin tümleştirme parçasıdır.  
  
## <a name="levels-of-glyph-control"></a>Karakter denetim düzeyleri  
 Bir durum karakter görüntülendiğinde örneğin bir öğenin geçerli durumunu belirten bir simge olan **Çözüm Gezgini** veya **sınıf görünümü**. Kaynak denetimi VSPackage karakter denetiminin iki düzey alıştırma yapabilirsiniz. Karakterlerin karakterlerin tarafından sağlanan önceden tanımlanmış bir dizi seçenek sınırlayabilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE veya bu özel karakterlerin görüntülenecek birtakım tanımlayabilirsiniz.  
  
### <a name="default-set-of-glyphs"></a>Varsayılan karakterlerin kümesi  
 Bir öğe ile ilişkili durumu karakterlerin belirlemek için **Çözüm Gezgini**, Denetim Kaynağı kullanarak bir proje durumu karakter istekleri <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.GetSccGlyph%2A>. Kaynak denetimi VSPackage IDE tarafından sağlanan önceden tanımlanmış karakterlerin sınırlı karakterlerin seçimi tutmaya karar verebilirsiniz. Bu durumda, VSPackage geri vsshell.idl içinde tanımlanan karakter numaralandırmaları temsil eden değer dizisi geçirir. Daha fazla bilgi için bkz: <xref:Microsoft.VisualStudio.Shell.Interop.VsStateIcon> . Bu, "İade edildi" karakter ve bir onay işareti "Teslim alındı" karakter olarak asma gibi IDE tarafından ayarlanan karakterlerin önceden tanımlanmış bir kümesidir.  
  
### <a name="custom-set-of-glyphs"></a>Özel karakterleri ayarlama  
 Kaynak denetimi VSPackage yüklendiğinde kendi karakterlerin bir benzersiz "Görünüm için" kullanabilirsiniz. Yeni bir kaynak denetimi VSPackage etkin olduğunda, kendi karakterlerin önceki kaynak denetim olsa bile VSPackage hala yüklendiği kullanmaya başlamak kullanabilirsiniz, ancak etkin olmalıdır. Bu modda, kaynak denetimi VSPackage varolan simgeler ile tutarlı bir görünüm korumak için kullanmaya devam edebilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] onu seçerse.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager> Hizmetini destekleyen bir arabirim <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>, hangi VSPackage isteğe bağlı olarak uygulayabilirsiniz ve hangi istenecektir için IDE tarafından. IDE bir istek yaptığında [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sırayla şu anda kayıtlı kaynak denetiminden VSPackage bu arabirim almaya çalışacaktır. Arabirimi içinde kayıtlı VSPackage varsa, özel karakterlerin IDE'nin talebi başarılı olur; Aksi takdirde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE karakterlerin kendi varsayılan kümesi kullanır.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs.GetCustomGlyphList%2A> Yöntemi tarafından kullanılan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çeşitli kaynak denetimi gösteren görüntüleri listesini elde etmek için belirtir. Kaynak denetimi VSPackage IDE kendi özel karakterlerin için resim listesi için bir tanıtıcı döndürür. IDE resim listesi bir kopyasını bu noktada oluşturur ve daha sonra görüntülemek için karakterleri seçmek için kullanır. Yeni arabirimi desteklenmiyorsa veya `IVsSccGlyphs::GetCustomGlyphList` yöntemi döndürür E_NOTIMPL, IDE karakterlerin tarafından sağlanan varsayılan listeden kendi karakterlerin alır sonra [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>   
 <xref:Microsoft.VisualStudio.Shell.Interop.VsStateIcon>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>