---
title: "Nasıl yapılır: belgeleri veritabanı verileriyle doldurma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents, populating with data
- data, adding to documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 0a5a88cf34e0710869aaf4ac82d78cb79b37ffde
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-populate-documents-with-data-from-a-database"></a>Nasıl Yapılır: Belgeleri Veritabanı Verileriyle Doldurma
  Aynı şekilde verilere Windows Forms projelerindeki verilere erişmek için Microsoft Office belge düzeyi projelerine verilerine erişebilir. Verileri bir veritabanından çözümünüze getirmek için aynı araçları ve kod kullanmak ve verileri görüntülemek için Windows Forms denetimleri kullanabilirsiniz.  
  
 Ayrıca, ana bilgisayar denetimleri kullanarak verileri görüntüleyebilirsiniz. Konak denetimleri, olaylar ve veri bağlama özelliğiyle geliştirilmiş yerel Microsoft Office Word nesneleridir. Daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Aşağıdaki örnek bir tasarımcı kullanarak belge düzeyi projelerine verilere bağlı denetimler ekleme gösterir. Verilere bağlı denetimler çalışma zamanında VSTO eklentisi projelerine ekleme konusunda bir örnek için bkz: [izlenecek yol: Basit Veri bağlamada VSTO eklenti proje](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md).  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [Word 2007 içerik denetimlerini kullanarak Visual Studio Araçları (3.0) Office sistemi için veri bağlama](http://go.microsoft.com/fwlink/?LinkId=136785).  
  
## <a name="adding-a-control-to-a-document-at-design-time"></a>Belgeye tasarım zamanında denetim ekleme  
  
#### <a name="to-populate-a-document-with-data-from-a-database"></a>Bir belgeyi bir veritabanından verilerle doldurmak için  
  
1.  Word belge düzeyi projede açmak [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], belge tasarımcıda açık.  
  
2.  Açık **veri kaynakları** penceresi ve veritabanını bir veri kaynağı oluşturun. Daha fazla bilgi için bkz: [yeni bağlantılar eklemek](../data-tools/add-new-connections.md).  
  
3.  İstediğiniz alanı sürükleyin **veri kaynakları** belgenizi penceresine.  
  
 İçerik denetimi belgeye eklenir. İçerik denetimi türü seçtiğiniz alan veri türüne bağlıdır. Daha fazla bilgi için bkz: [içerik denetimleri](../vsto/content-controls.md).  
  
 Veri alanında seçerek farklı bir denetim ekleyebilirsiniz **veri kaynakları** penceresini açın ve ardından farklı bir denetim aşağı açılan listeden seçerek.  
  
## <a name="objects-in-the-project"></a>Projesindeki nesneleri  
 Denetim ek olarak aşağıdaki verilerle ilgili nesnelerle projenize otomatik olarak eklenir:  
  
-   Veritabanında bağlı veri tabloları yalıtır türü belirtilmiş veri kümesi. Daha fazla bilgi için bkz: [Visual Studio'da veri kümesi Araçları](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
-   A <xref:System.Windows.Forms.BindingSource> , Denetim türü belirtilmiş veri kümesine bağlanır. Daha fazla bilgi için bkz: [BindingSource bileşenine genel bakış](/dotnet/framework/winforms/controls/bindingsource-component-overview).  
  
-   Türü belirtilmiş veri kümesi veritabanına bağlanan bir TableAdapter. Daha fazla bilgi için bkz: [oluşturma ve TableAdapters öğelerini yapılandırma](../data-tools/create-and-configure-tableadapters.md).  
  
-   Hiyerarşik güncelleştirmeleri etkinleştirmek için tablo bağdaştırıcıları kümesindeki koordine etmek için kullanılan bir TableAdapterManager. Daha fazla bilgi için bkz: [hiyerarşik güncelleştirme](../data-tools/hierarchical-update.md) ve [TableAdapterManager başvuru](../data-tools/fill-datasets-by-using-tableadapters.md#tableadaptermanager-reference).  
  
 Projeyi çalıştırdığınızda, denetimi veri kaynağındaki ilk kaydı görüntüler. Kullanabileceğiniz <xref:System.Windows.Forms.BindingSource> kullanıcıların kayıtlar arasında gezinmek.  
  
#### <a name="to-scroll-through-the-records"></a>Kayıtlar arasında gezinmek için  
  
-   Kullanım <xref:System.Windows.Forms.BindingSource> gibi yöntemler <xref:System.Windows.Forms.BindingSource.MoveNext%2A> ve <xref:System.Windows.Forms.BindingSource.MovePrevious%2A>.  
  
 Türü belirtilmiş veri kümesi ve veritabanı güncellemelerin hakkında daha fazla bilgi için bkz: [nasıl yapılır: konak kontrolü verileriyle veri kaynağını güncelleme](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Yeni veri kaynakları ekleyin](/visualstudio/data-tools/add-new-data-sources)   
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Nasıl yapılır: belgeleri nesne verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [Nasıl yapılır: konak kontrolü verileriyle veri kaynağını güncelleme](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Office çözümleri genel bakış yerel veritabanı dosyaları kullanma](../vsto/using-local-database-files-in-office-solutions-overview.md)   
 [Windows Forms uygulamalarındaki verilere bağlanma](/visualstudio/data-tools/connecting-to-data-in-windows-forms-applications)   
 [BindingSource Bileşenine Genel Bakış](/dotnet/framework/winforms/controls/bindingsource-component-overview)  
  
  