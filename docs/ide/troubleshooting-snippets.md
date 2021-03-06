---
title: "Kod parçacıkları sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliSense Code Snippets, troubleshooting
- troubleshooting IntelliSense Code Snippets
- troubleshooting Visual Basic, IntelliSense Code Snippets
ms.assetid: 7b6dd40e-2f78-4b50-8e68-41fac1bcb81e
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bc17b237d2bd38d146a70fb05c1c4f6a91f98b37
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-snippets"></a>Sorun Giderme Parçacıkları
IntelliSense kod parçacıkları sorunlarını genellikle iki sorunlarından neden: bozuk parçacık dosyasını veya parçacığı dosyasında hatalı içeriği.  
  
## <a name="common-problems"></a>Sık karşılaşılan sorunları  
  
### <a name="the-snippet-cannot-be-dragged-from-file-explorer-to-a-visual-studio-source-file"></a>Kod parçacığını dosya Gezgini'nden bir Visual Studio kaynak dosyaya sürüklediğiniz olamaz  
  
-   Kod parçacığında dosyasındaki XML bozulmuş olabilir. **XML Düzenleyicisi** içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sorunları XML yapısı içinde bulabilirsiniz.  
  
-   Parçacık dosyasını parçacığı şemaya uygun olmayabilir. **XML Düzenleyicisi** içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sorunları XML yapısı içinde bulabilirsiniz.  
  
### <a name="the-code-has-compiler-errors-that-are-not-highlighted"></a>Kod değil vurgulanmıştır derleyici hataları var  
  
-   Proje başvurusu eksik olabilir. Kod parçacığını ilgili belgelere inceleyin. Referans bilgisayarda bulunmazsa yüklemeniz gerekir. Parçacık ekleme projeye gerekli tüm başvuruları eklemeniz gerekir. Kod parçacığını başvuru bilgileri eksikse, hata olarak parçacığı oluşturan bildirilebilir.  
  
-   Bir değişken tanımlanmamış olabilir. Tanımsız değişkenlerde parçacık vurgulanmış olması gerekir. Aksi durumda, hata olarak parçacığı oluşturucusu olarak bildirilebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod Parçacıkları](../ide/code-snippets.md)