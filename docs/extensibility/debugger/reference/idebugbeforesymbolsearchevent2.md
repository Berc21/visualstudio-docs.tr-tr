---
title: IDebugBeforeSymbolSearchEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugBeforeSymbolSearchEvent2 interface
ms.assetid: 679fd7b1-765a-41a8-a046-63240c09a499
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4ec023384ab95e72d0341fb728eb0fd6a4f58480
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbeforesymbolsearchevent2"></a>IDebugBeforeSymbolSearchEvent2
Hata ayıklama altyapısı (DE) Bu arabirim oturum hata ayıklama Yöneticisi durumunu ayarlama (SDM) simgesi yükleri sırasında iletisi gönderir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugBeforeSymbolSearchEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Sembol yükleri sırasında Durum Çubuğu iletisini ayarlamalısınız zaman DE bu arabirimi uygular. Bu arabirim çalışmak veya komut dosyası yorumlayıcılar parçası olan hata ayıklama motorları tarafından uygulanır. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) arabirimi uygulanan, bu arabirimle aynı nesne üzerinde (SDM kullanan **QueryInterface** erişimi **IDebugEvent2** arabirimi).  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 DE oluşturur ve Durum Çubuğu iletisini simgesi yükleri sırasında ayarlamanız gerekir, bu olay nesnesi gönderir. Olay kullanılarak gönderilen [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) ayıklanacak programın eklendiğinde SDM tarafından sağlanan geri çağırma işlevi.  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugBeforeSymbolSearchEvent2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetModuleName](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2-getmodulename.md)|Şu anda ayıklanacak modülünün adını alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll