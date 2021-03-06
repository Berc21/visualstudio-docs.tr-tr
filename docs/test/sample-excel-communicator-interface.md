---
title: "Excel Communicator arabirimi örnekleme | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: bc372077b36680e3b0dc8ec0ad482f8df0c52609
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="sample-excel-communicator-interface"></a>Excel Communicator Arabirimi Örnekleme
Örnek `IExcelUICommunication` arabirimi kullanılır `ExcelUICommunicator` nesnesinde `ExcelAddIn` projesi.

## <a name="iexceluicommunication-interface"></a>IExcelUICommunication Interface
 Bu arabirim arasındaki iletişim noktalarını tanımlar `CodedUIExtension`, kodlanmış UI testi işleminde çalışır ve `ExcelCodedUIAddIn`, çalışan [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] işlemi.

 `ExcelCodedUIAddinHelper` Derleme sahip bir `ExcelUICommunicator` bu arabirimden oluşan ve Excel nesne modeli yöntemleri işlemek için kullandığı sınıf.

 Bazı yöntemler Excel'den istenen bilgileri alın ardından oluşturup gibi bilgileri birini nesneleri dönmek `CellInformation` nesnesi.

 Diğer yöntemleri sağlanan bilgi nesnesini kullanın, karşılık gelen denetim Excel'de bulun ve bazı işlem denetimi gerçekleştirin. Örneğin, `ScrollIntoView` yöntemi kayar çalışma belirlenen hücrenin görünür olmasını sağlayın.

## <a name="codeduiextensibilitysample-and-excelcodeduiaddinhelper-communication"></a>CodedUIExtensibilitySample ve ExcelCodedUIAddinHelper iletişim
 `ExcelCodedUIAddinHelper` Derleme Excel işleminde çalışır ve olan `UICommunicator` uygulayan sınıf `IExcelUITestCommunication` arabirim ve alır veya gerekli bilgileri doğrudan Excel Arabiriminden ayarlar.

 `CodedUIExtensibilitySample` Derleme Visual Studio Kodlanmış UI Test işleminde çalışır. Bu derleme sahip `Communicator` bir .NET uzaktan iletişim kanal açar ve sağlayan sınıf bir `Instance` kullanan özelliği `IExcelUICommunication` kullanılacak arabirimi `UICommunicator` nesnesinde `ExcelCodedUIAddinHelper` istekleri ve bilgileri geçirmek için derleme nesneleri, gibi bir `CellInformation` iki derleme arasında ileri ve geri nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

- [Kodlanmış Kullanıcı Arabirimi Testlerini ve Eylem Kayıtlarını Microsoft Excel'i Desteklemek için Genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
- [Kodlanmış UI Testi için Excel Eklenti Örneği](../test/sample-excel-add-in-for-coded-ui-testing.md)
- [Excel için Kodlanmış UI Testi Uzantısı Örneği](../test/sample-coded-ui-test-extension-for-excel.md)
