---
title: "Nasıl yapılır: ClickOnce dağıtımları için ayrıntılı günlük dosyalarını belirtmek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- logs, ClickOnce deployment
- ClickOnce deployment, logging
ms.assetid: 0807a28d-2e40-4a51-ab10-308d808ded6b
caps.latest.revision: "9"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 6cac7764a941e88dd3901a3280e78717955e86b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-verbose-log-files-for-clickonce-deployments"></a>Nasıl yapılır: ClickOnce Dağıtımları İçin Ayrıntılı Günlük Dosyası Belirtme
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]tüm dağıtımlar için etkinlik günlük dosyalarını korur. Bu günlükler yükleme, başlatma, güncelleştirme ve kaldırma için ilgili belge ayrıntılarını bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım. Ayrıntı düzeyini, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bu günlük dosyaları yazma işlemlerini Kayıt Defteri Düzenleyicisi'ni (**regedit.exe**) ayrıntı düzeyini belirtir.  
  
> [!CAUTION]
>  Kayıt Defteri Düzenleyicisi'ni yanlış kullanırsanız, işletim sistemini yeniden yüklemenizi gerektirebilecek önemli sorunlara neden olabilir. Kayıt Defteri Düzenleyicisi'ni kullanmak, kendi sorumluluğunuzdadır.  
  
 Aşağıdaki yordam için ayrıntı düzeyini belirtmek amacıyla açıklar [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] günlük dosyalarını geçerli kullanıcı için. Ayrıntı düzeyini azaltmak için bu kayıt defteri değerini kaldırın.  
  
### <a name="to-specify-verbose-log-files"></a>Ayrıntılı günlük dosyası belirtmek için  
  
1.  Açık **Regedit.exe**.  
  
2.  Düğümüne gidin `HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment`.  
  
3.  Gerekirse, adlı yeni bir dize değeri oluşturun `LogVerbosityLevel`.  
  
4.  Ayarlama `LogVerbosityLevel` değeri `1`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Dağıtım Sorunlarını Giderme](../deployment/troubleshooting-clickonce-deployments.md)