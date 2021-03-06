---
title: "Özel Parametreler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wizards, custom parameters
- custom parameters
ms.assetid: ba5c364b-66e6-47ea-9760-a0b70de8f0a0
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 17a629c2d93bb5e91fb301d4da9dca825e5b8917
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="custom-parameters"></a>Özel Parametreler
Sihirbaz başlatıldıktan sonra özel parametreler sihirbaz işlemi denetler. İlgili .vsz dosyası tümleşik geliştirme ortamı (IDE) paketlenir ve Sihirbazı başlattığınızda sihirbaz dize dizisi geçirilen kullanıcı tarafından tanımlanan parametre dizisi sağlar. Sihirbaz dize dizisi ayrıştırır ve Sihirbazı'nın gerçek işlemi denetlemek için bilgileri kullanır. Bu şekilde, bir sihirbaz işlevselliği .vsz dosyasının içeriğini bağlı olarak özelleştirebilirsiniz.  
  
 Sihirbazı başlattığınızda bağlam parametreleri, diğer yandan, proje durumunu tanımlayın. Daha fazla bilgi için bkz: [bağlam parametreleri](../../extensibility/internals/context-parameters.md).  
  
 Özel parametrelere sahip bir .vsz dosyası örneği verilmiştir:  
  
```  
VSWIZARD 8.0  
Wizard=VsWizard.VsWizard_Engine  
Param="WIZARD_NAME = Sample Wizard"  
Param="WIZARD_UI = FALSE"  
Param="RELATIVE_PATH = VSWizards\Classwiz\ATL"  
Param="PREPROCESS_FUNCTION = CanAddATLSupport"  
Param="PROJECT_TYPE = CSPROJ"  
```  
  
 .Vsz dosyası yazarı parametrelerinin değerlerini ekler. Bir kullanıcı seçtiğinde **yeni proje** veya **Yeni Öğe Ekle** Dosya menüsünden veya bir projeye sağ tıklanarak **Çözüm Gezgini**, IDE bu değerleri dizisi toplar. dizeleri. IDE sonra projenin çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.AddItem%2A> yöntemiyle <xref:Microsoft.VisualStudio.Shell.Interop.VSADDITEMOPERATION> bayrak kümesi ve proje çağrıları <xref:EnvDTE.IVsExtensibility.RunWizardFile%2A> Sihirbazı'nı çalıştıran ve sonucu döndürerek sorumlu yöntemi.  
  
 Sihirbaz, dize dizisi ayrıştırma ve dizeleri uygun şekilde davranan sorumludur. Bu şekilde, özel parametre uygulayarak, çeşitli işlevler gerçekleştiren bir sihirbaz oluşturabilirsiniz. Diğer bir deyişle, bir sihirbaz üç farklı .vsz dosyaları olabilir. Her dosya Sihirbazı çeşitli durumlarda davranışını denetlemek için özel parametreler farklı kümelerini geçirir.  
  
 Daha fazla bilgi için bkz: [Sihirbazı'nı (. Vsz) dosya](../../extensibility/internals/wizard-dot-vsz-file.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>   
 [Bağlam parametreleri](../../extensibility/internals/context-parameters.md)   
 [Sihirbazlar](../../extensibility/internals/wizards.md)   
 [Sihirbaz (.Vsz) Dosyası](../../extensibility/internals/wizard-dot-vsz-file.md)