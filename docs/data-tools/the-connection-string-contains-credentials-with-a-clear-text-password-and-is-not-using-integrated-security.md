---
title: "Bağlantı dizesi şifresiz bir parola ile kimlik bilgilerini içerir ve tümleşik güvenlik kullanmayan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 1ecca5a69893c92edbeb996606f94cac71e4a3c1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>Bağlantı dizesi Integrated security kullanmayan ve kimlik bilgileri düz metin parolası ile içerir
Geçerli DBML dosya ve uygulama yapılandırma dosyaları hassas bilgiler bağlantı dizesini kaydetmek istiyor musunuz?  Bağlantı dizesi hassas bilgileri olmadan kaydetmek için Hayır'ı tıklatın.  
  
 Hassas bilgileri (bağlantı dizesine dahil parolalar) dahil veri bağlantıları ile çalışırken, bir projenin DBML dosya ve uygulama yapılandırma dosyası ile veya olmadan bağlantı dizesi kaydetme seçeneği sunulur hassas bilgileri.  
  
> [!WARNING]
>  Açıkça ayarı **bağlantı** özellikleri **uygulama ayarları** özelliğine **False** parola DBML dosyaya ekleyeceksiniz.  
  
### <a name="to-save-the-connection-string-with-the-sensitive-information-in-the-projects-application-settings"></a>Hassas bilgilerin projenin uygulama ayarlarında bağlantı dizesini kaydetmek için  
  
-   **Evet**'i tıklayın.  
  
     Bağlantı dizesi, bir uygulama ayarı olarak depolanır. Bağlantı dizesine hassas bilgileri düz metin olarak içerir. DBML dosyası hassas bilgileri içermiyor.  
  
### <a name="to-save-the-connection-string-without-the-sensitive-information-in-the-projects-application-settings"></a>Projenin uygulama ayarlarında bağlantı dizesini hassas bilgileri olmadan kaydetmek için  
  
-   **Hayır**'a tıklayın.  
  
     Bağlantı dizesi bir uygulama ayarı olarak depolanır, ancak parola dahil değildir.  
  
## <a name="see-also"></a>Ayrıca bkz.
[O/R Tasarımcısı iletileri](../data-tools/o-r-designer-messages.md)  
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)