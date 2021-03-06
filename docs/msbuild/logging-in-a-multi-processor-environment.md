---
title: Birden çok işlemcili ortamda oturum açma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, multi-processor logging
- MSBuild, logging
ms.assetid: dd4dae65-ed04-4883-b48d-59bcb891c4dc
caps.latest.revision: 9
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c1bca3a76bbf64303baea36ff7dac2abacf85443
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="logging-in-a-multi-processor-environment"></a>Birden Çok İşlemcili Ortamda Oturum Açma
MSBuild birden çok işlemci kullanma yeteneğini zaman derleme projesi önemli ölçüde düşürebilir ancak de günlük tutmayı karmaşıklık ekler. Bir tek işlemcili ortamda Günlükçü gelen olayları, iletilerini, uyarıları ve hataları tahmin edilebilir ve sıralı bir şekilde işleyebilir. Ancak, birden çok işlemcili ortamda çeşitli kaynaklardan gelen olayların aynı anda veya sıra dışı ulaşır. MSBuild özel "iletme günlükçüleri." oluşturmayı etkinleştirir ve yeni bir çok işlemciye duyarlı Günlükçü sağlar  
  
## <a name="logging-multiple-processor-builds"></a>Birden çok işlemcili günlük derlemeler  
 Birden çok işlemcili veya çok çekirdekli bir sistemde bir veya daha fazla projeler derlerken MSBuild derleme olaylarını tüm projeleri eşzamanlı olarak oluşturulur. Olay verilerini bir avalanche Günlükçü aynı anda veya sıra dışı gelebilir. Günlükçü doldurmaya ve artan derleme sürelerini, yanlış Günlükçü çıkış veya bozuk bir yapı neden olabilir. Bu sorunları gidermek için MSBuild Günlükçü sırası olayları işlemek ve olaylar ve kaynakları ilişkilendirmek.  
  
 Özel iletme Günlükçü oluşturarak daha fazla günlük verimliliğini artırabilir. Özel iletme Günlükçü izin vererek, bir filtre işlevi görür seçin, oluşturmadan önce izlemek istediğiniz olayları. Özel iletme Günlükçü kullandığınızda, istenmeyen olayları değil Günlükçü doldurmaya, günlüklerinizi karmaşıklığa veya yavaş kez oluşturabilir.  
  
### <a name="central-logging-model"></a>Merkezi günlük kaydı modeli  
 Birden çok işlemcili derlemeler için MSBuild "Merkezi günlük kaydı modeli." kullanır. Merkezi günlük kaydı modelinde MSBuild.exe örneği birincil oluşturma işlemi, veya "merkezi düğümü." hareket eder İkincil örneğini MSBuild.exe veya "ikincil düğümü," merkezi düğümüne eklenir. Merkezi düğüme bağlı tüm ILogger tabanlı günlükçüleri "merkezi günlükçüleri" denir ve ikincil düğümlerine ekli günlükçüleri "ikincil günlükçüleri." bilinen  
  
 Bir yapı ortaya çıktığında, ikincil günlükçüleri merkezi günlükçüleri kendi olay trafiği yönlendirmek. Olayları birkaç ikincil düğümlerde kaynaklı olduğundan, veri merkezi düğümde aynı anda ulaşır ancak araya eklemeli. Olay proje ve olay hedefi başvuruları çözümlemek için olay bağımsız ek yapı olay bağlam bilgilerini içerir.  
  
 Yalnızca rağmen <xref:Microsoft.Build.Framework.ILogger> olduğu merkezi Günlükçü tarafından uygulanması için gereken, aynı zamanda uygulama öneririz <xref:Microsoft.Build.Framework.INodeLogger> yapı katılan düğüm sayısı ile başlatmak için merkezi Günlükçü istiyorsanız. Aşağıdaki aşırı yükleme <xref:Microsoft.Build.Framework.ILogger.Initialize%2A> yöntemi Günlükçü altyapısını başlatır olduğunda çağrılır:  
  
```csharp
public interface INodeLogger: ILogger  
{  
    public void Initialize(IEventSource eventSource, int nodeCount);  
}  
```  
  
### <a name="distributed-logging-model"></a>Dağıtılmış günlük modeli  
 Merkezi günlük kaydı modelinde gibi derleme zaman birçok projeleri aynı anda çok fazla gelen ileti trafiği sistem stresses ve yapı performansı düşürür merkezi bir düğüme yük getirebilir.  
  
 MSBuild, bu sorunu azaltmak için "iletme günlükçüleri oluşturmanıza izin vererek Merkezi günlük kaydı modelini genişletir bir dağıtılmış günlük modeli" de sağlar. İletme Günlükçü ikincil düğüme bağlı ve bu düğümden gelen derleme olaylarını alır. Bu olayları filtrelemek ve merkezi düğümü yalnızca istenen ayarlara iletmek iletme Günlükçü yalnızca normal Günlükçü gibi olmasıdır. Bu merkezi düğümde ileti trafiğini azaltır ve bu nedenle daha iyi performans sağlar.  
  
 Bir iletme Kaydedici uygulayarak oluşturabileceğiniz <xref:Microsoft.Build.Framework.IForwardingLogger> türetilen arabirimi <xref:Microsoft.Build.Framework.ILogger>. Arabirim olarak tanımlanır:  
  
```csharp
public interface IForwardingLogger: INodeLogger  
{  
    public IEventRedirector EventRedirector { get; set; }  
    public int NodeId { get; set; }  
}  
```  
  
 Bir iletme Kaydedici olayları iletmek için arama <xref:Microsoft.Build.Framework.IEventRedirector.ForwardEvent%2A> yöntemi <xref:Microsoft.Build.Framework.IEventRedirector> arabirimi. Uygun geçirmek <xref:Microsoft.Build.Framework.BuildEventArgs>, ya da parametre olarak bir türevi.  
  
 Daha fazla bilgi için bkz: [iletme Günlükçüleri oluşturma](../msbuild/creating-forwarding-loggers.md).  
  
### <a name="attaching-a-distributed-logger"></a>Dağıtılmış bir Günlükçü ekleme  
 Bir komut satırı derleme üzerinde dağıtılmış Günlükçü ekleme için kullanmak `/distributedlogger` (veya `/dl` kısaca) geçin. Günlükçü türleri ve sınıf adları belirtmek için biçim aynıdır olanlar için `/logger` dağıtılmış Günlükçü iki günlük kaydı sınıfları oluşmaktadır dışında geçiş: iletme Günlükçü ve merkezi bir Günlükçü. Dağıtılmış bir Günlükçü ekleme örneği aşağıda verilmiştir:  
  
```  
msbuild.exe *.proj /distributedlogger:XMLCentralLogger,MyLogger,Version=1.0.2,  
Culture=neutral*XMLForwardingLogger,MyLogger,Version=1.0.2,  
Culture=neutral  
```  
  
 Bir yıldız işareti (*) iki Günlükçü adlarında ayıran `/dl` geçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Günlükçüleri derleme](../msbuild/build-loggers.md)   
 [İletme Günlükçüleri Oluşturma](../msbuild/creating-forwarding-loggers.md)