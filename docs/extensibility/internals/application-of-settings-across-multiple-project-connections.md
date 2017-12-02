---
title: "Birden çok proje bağlantılar üzerinden ayarları uygulaması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control plug-ins, application of settings
ms.assetid: 2116d3d0-c46c-4d0a-b482-08a178584f46
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9750d946a941e86a6c0a6973661f00f8f44cf9b5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="application-of-settings-across-multiple-project-connections"></a>Birden çok proje bağlantılar üzerinden ayarları uygulama
Kaynak Denetim Eklentisi Kaynak Denetim eklentisi API 1.2 kullanılarak oluşturulan bir toplu işlem birden çok projeleri veya birden çok bağlantı bağlamları arasında aynı kaynak denetimi işlemi yürütmek için kullanabilirsiniz. Toplu kullanılabilir yedek ortadan kaldırmak için her proje için kullanıcı deneyimini iletişim kutularından.  
  
 Bir kullanıcı birden fazla bağlantı kaynak denetim eklentisi API 1.1, (örneğin, iki Web projeleri farklı dosya paylaşımı makinelerde) kullanılarak oluşturulmuş eklenti bir kaynak denetiminde ait birden çok öğe seçer ve bunları denetler, kullanıcı aynı iletişim kutusu görür. sürekli olarak. Kullanıcı olsa bile bu gerçekleşir **tümüne uygula** IDE her bağlantı bağlamı için durumuna sıfırlar çünkü iletişim kutusunda, kutuyu işaretleyin.  
  
## <a name="new-capability-flag"></a>Yeni özellik bayrağı  
 `SccBeginBatch`İşlev kümeleri `SCC_CAP_BATCH` bir toplu işlem devam ediyor belirten bayrak  
  
## <a name="new-functions"></a>Yeni işlevleri  
 Aşağıdaki yeni işlevleri toplu işlem destekler:  
  
-   [SccBeginBatch](../../extensibility/sccbeginbatch-function.md)  
  
-   [SccEndBatch](../../extensibility/sccendbatch-function.md)  
  
 `SCCBeginBatch` İşlevi bir grup kaynak denetimi işlemleri başlatır. `SccEndBatch`Grup kapatır. Grupları bulunmayabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API sürümü 1.2 yenilikler nelerdir?](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)