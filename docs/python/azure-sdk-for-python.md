---
title: Python için Azure SDK | Microsoft Docs
description: Python için Azure SDK'sı, Microsoft Azure hizmetlerini herhangi bir platformda çalışan Python uygulamalardan kullanma kolaylaştırır.
ms.custom: ''
ms.date: 01/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 3f03ca08dddb90f6eb86a439f7f92307df3b4335
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="azure-sdk-for-python"></a>Python için Azure SDK

Python için Azure SDK'sını kullanabilir ve Windows, Mac OSX ve Linux üzerinde çalışan uygulamalardan Microsoft Azure hizmetlerini yönetmek kolaylaştırır.

## <a name="installation"></a>Yükleme

Azure SDK'sını gelen yüklü [Python paket dizini](https://pypi.python.org/pypi/azure).

Yükleme **en yeni kararlı sürüm** (gibi Python 2.7 ve 3.x destekler):

```command
pip install azure
```

Ayrıca izleyebilirsiniz [Python yüklemek ve SDK](https://docs.microsoft.com/azure/python-how-to-install/) Azure belgelerinde.

## <a name="documentation"></a>Belgeler

Belge üzerinde bulunabilir [python.readthedocs.org için azure sdk](http://azure-sdk-for-python.readthedocs.org/en/latest/index.html).

[Python Geliştirici Merkezi için Azure SDK](http://azure.microsoft.com/develop/python/) de yararlı kaynaklara öğreticileri sayısı dahil olmak üzere, çeşitli vardır:

- Web uygulamaları ile oluşturma [Django](/azure/app-service-web/web-sites-python-create-deploy-django-app) [Flask](/azure/app-service-web/web-sites-python-create-deploy-flask-app), ve [Bottle](/azure/app-service-web/web-sites-python-create-deploy-bottle-app).
- [BLOB Depolama](/azure/storage/storage-python-how-to-use-blob-storage)
- [Tablo depolama](/azure/storage/storage-python-how-to-use-table-storage)
- [Kuyruk depolama](/azure/storage/storage-python-how-to-use-queue-storage)
- [Azure Cosmos DB](/azure/cosmos-db/sql-api-python-application)
- [Service Bus kuyrukları](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
- [Hizmet veri yolu konuları/abonelikleri](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [Hizmet Yönetimi](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

Belgeler olmadan ortak API'ler için birim testleri içinde [SDK'ın GitHub deposunu](https://github.com/Azure/azure-sdk-for-python) iyi bilgi kaynağıdır:

- [Birim testleri](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Hizmet veri yolu birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [Hizmet Yönetimi birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)
- [Kaynak Yönetimi birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-mgmt/tests)

## <a name="support"></a>Destek

SDK'sı için Git deposu adresindedir [ https://github.com/Azure/azure-sdk-for-python ](https://github.com/Azure/azure-sdk-for-python).

[Depo sorunları dosya](https://github.com/Azure/azure-sdk-for-python/issues) sorunları bulmak ya da SDK'ın kullanımıyla ilgili sorularınız varsa.
