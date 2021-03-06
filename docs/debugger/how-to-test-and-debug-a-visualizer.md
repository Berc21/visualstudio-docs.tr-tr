---
title: "Nasıl yapılır: Test ve hata ayıklama Görselleştirici | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- visualizers, testing
- visualizers, debugging
- debugging [Visual Studio], visualizers
ms.assetid: 5cc12ce8-c819-48e4-b487-98d403001b28
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 75102abacbf93c90b6c24d2884224dd9dd1e1bae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-test-and-debug-a-visualizer"></a>Nasıl Yapılır: Görselleştiriciyi Test Etme ve Hata Ayıklama
Bir kez hata ayıklama ve test etmeniz, Görselleştirici yazmıştır.  
  
 Görselleştirici test etmek için bir Visual Studio yükleyerek ve bir hata ayıklayıcı penceresinden çağırma yoldur. (Bkz [nasıl yapılır: Görselleştiriciyi yükleme](../debugger/how-to-install-a-visualizer.md).) Bunu yaparsanız, ekleme ve hata ayıklayıcısı ilk örneğinde çalışan Görselleştirici hata ayıklamak için Visual Studio ikinci bir örneğini kullanmanız gerekir.  
  
 Görselleştirici hata ayıklamak için daha kolay bir yolu, bir test sürücüsünden Görselleştirici çalıştırmaktır. Görselleştirici API'leri olarak adlandırılan bu tür bir sürücü oluşturmak kolaylaştırır *Görselleştirici geliştirme konak*.  
  
### <a name="to-create-a-visualizer-development-host"></a>Görselleştirici geliştirme konak oluşturmak için  
  
1.  Hata ayıklayıcı tarafı sınıfınızda oluşturan bir statik yöntem dahil bir <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerDevelopmentHost> nesne ve onun show yöntemi çağırır:  
  
    ```  
    public static void TestShowVisualizer(object objectToVisualize)  
    {  
       VisualizerDevelopmentHost myHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));  
       myHost.ShowVisualizer();  
    }  
    ```  
  
     Ana bilgisayar oluşturmak için kullanılan Görselleştirici gösterilen veri nesnesi parametreleridir (`objectToVisualize`) ve hata ayıklayıcı yan sınıf türü.  
  
2.  Çağırmak için aşağıdaki ifadeyi ekleyin `TestShowVisualizer`. Bir sınıf kitaplığı'nda, Görselleştirici oluşturduysanız, sınıf kitaplığı çağırın ve bu deyimi, yürütülebilir dosya yerleştirmek için yürütülebilir bir dosya oluşturmanız gerekir:  
  
    ```  
    DebuggerSide.TestShowVisualizer(myString);  
    ```  
  
     Daha eksiksiz bir örnek için bkz: [izlenecek yol: C# ile Görselleştirici yazma](../debugger/walkthrough-writing-a-visualizer-in-csharp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Görselleştirici C# ile yazma](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)   
 [Nasıl yapılır: Görselleştiriciyi yükleme](../debugger/how-to-install-a-visualizer.md)   
 [Özel Görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md)