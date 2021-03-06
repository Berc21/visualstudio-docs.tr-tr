---
title: Yüklemeyi kaldırma ve yeniden değerlendirmeleri iç içe projeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- nested projects, unloading and reloading
- projects [Visual Studio SDK], unloading and reloading nested
ms.assetid: 06c3427e-c874-45b1-b9af-f68610ed016c
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bfe39e82a9f15825a5328fe1950347add9d182bb
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="considerations-for-unloading-and-reloading-nested-projects"></a>Yüklemeyi kaldırma ve yeniden iç içe geçmiş projeleri için ilgili önemli noktalar

İç içe proje türleri uyguladığınızda, kaldırma ve projeleri yeniden ek adımları gerçekleştirmeniz gerekir. Çözüm olayları dinleyicileri doğru şekilde bildirmek için doğru şekilde yükseltmeniz gerekir `OnBeforeUnloadProject` ve `OnAfterLoadProject` olaylar.

Bu olaylar yükseltmek için bir kaynak kodu denetimi (SCC) nedenidir. Sunucudan öğeleri silin ve sonra bunları eklemek için SCC istemediğiniz olarak geri *yeni* varsa bir `Get` SCC işlemi. Bu durumda, yeni bir dosya SCC dışında yüklenmesi. Unload ve farklı durumunda tüm dosyaları yeniden etmesi gerekir.

Kaynak kodu denetim çağrıları `ReloadItem`. Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> çağırmak için arabirimi `OnBeforeUnloadProject` ve `OnAfterLoadProject` projeyi silin ve yeniden oluşturun. Bu şekilde arabirimi uyguladığınızda SCC proje geçici olarak silinmiş ve yeniden eklenmesi, bilgilendirilir. Bu nedenle, projeyi boşmuş gibi projeye SCC çalışmaz *gerçekten* silinir ve yeniden eklendi.

## <a name="reloading-projects"></a>Projeleri yeniden yükleme

İç içe geçmiş projeleri yeniden yükleme desteklemek için uygulamanız <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> yöntemi. Uygulamanızda `ReloadItem`, iç içe geçmiş projeleri kapatın ve sonra yeniden oluşturun.

Genellikle bir projeyi yeniden yüklendiğinde, IDE başlatır <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeUnloadProject%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> olaylar. Ancak, silindiğinde ve yeniden iç içe geçmiş projeleri için ana proje IDE işlemi başlatır. Ana proje çözümü olayları yükseltmek değil ve IDE başlatma işleminin hakkında hiçbir bilgi olduğundan olayları yükseltilmiş değil.

Bu işlem, ana proje çağrıları işlemek için `QueryInterface` üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> arabirimi. `IVsFireSolutionEvents` yükseltmek için IDE söyleyin işlevleri sahip `OnBeforeUnloadProject` iç içe proje kaldırın ve ardından yükseltmek için olay `OnAfterLoadProject` olay aynı projeyi yeniden yükleyin.

## <a name="see-also"></a>Ayrıca Bkz.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>
- [Projeleri İç İçe Geçirme](../../extensibility/internals/nesting-projects.md)