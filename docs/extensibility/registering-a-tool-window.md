---
title: Araç penceresi kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tool windows, registering managed
- tool windows, registering
ms.assetid: 8c8c4a24-3da4-497b-9db2-0ddd7cfbfdd2
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: cbaa3accdd926a4a09f4eee3e2e83b9677db56e2
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="registering-a-tool-window"></a>Araç penceresi kaydetme
Kullanarak, aracı windows kaydedebilirsiniz <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> ve  <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute>  
  
## <a name="example"></a>Örnek  
  
```csharp  
  
[ProvideToolWindow(typeof(PersistedWindowPane), Style = MsVsShell.VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")]
[ProvideToolWindow(typeof(DynamicWindowPane), PositionX=250, PositionY=250, Width=160, Height=180, Transient=true)]
[ProvideToolWindowVisibility(typeof(DynamicWindowPane), /*UICONTEXT_SolutionExists*/"f1536ef8-92ec-443c-9ed7-fdadf150da82")]  
[ProvideMenuResource(1000, 1)]  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")]  
public class PackageToolWindow : Package  
{  
```  
  
 Yukarıdaki kod <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> PersistedWindowPane ve DynamicWindowPane aracı windows Visual Studio ile kaydeder. Kalıcı araç penceresi takılıyken hem ile sekmeli **Çözüm Gezgini**, ve dinamik pencerenin başlangıç konumu ve boyutu varsayılan verilir. Dinamik penceresi başlangıçta oluşturulmaz belirten geçici hale getirilir. Sistem kayıt defteri ToolWindows anahtarında DontForceCreate değer yazar. Daha fazla bilgi için bkz: [araç penceresi ekran yapılandırması](../extensibility/tool-window-display-configuration.md).
