---
title: PyLint linting Python kodu kullanarak | Microsoft Docs
description: PyLint Visual Studio'da Python kodu sorunlarını denetlemek için nasıl kullanılacağını.
ms.custom: ''
ms.date: 07/12/2017
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
ms.openlocfilehash: 5ef665ae866709aaa39d4b7856434b8fd6ea5af0
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="using-pylint-to-check-python-code"></a>Python kodu denetlemek için PyLint kullanma

[PyLint](https://www.pylint.org/), Python kod hatalarını denetler ve düzenleri kodlama iyi Python teşvik eden yaygın olarak kullanılan bir araç Python projeleri için Visual Studio'ya tümleşiktir.

Yalnızca Çözüm Gezgini'nde Python projesine sağ tıklatın ve **Python > PyLint Çalıştır...** :

![Python projeleri için bağlam menüsündeki PyLint komutu](media/code-pylint-command.png)

Bu komutu kullanarak zaten mevcut değilse PyLint etkin ortamınıza yüklemenizi ister.

PyLint uyarıları ve hataları hata Listesi penceresi görüntülenir:

![PyLint hata listesi](media/code-pylint-error-list.png)

Bir hata çift doğrudan sorunu oluşturulan kaynak koduna alır.

> [!Tip]
> Bkz: [PyLint özellikleri başvurusunu](https://pylint.readthedocs.io/en/latest/technical_reference/features.html) tüm PyLint ayrıntılı listesi için çıktı iletileri.

## <a name="setting-pylint-command-line-options"></a>PyLint komut satırı seçeneklerini ayarlama

[Komut satırı seçenekleri](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) PyLint belgelerine bölümünü açıklar aracılığıyla PyLint'in davranışını denetleme bir `.pylintrc` yapılandırma dosyası. Böyle bir dosya Visual Studio veya başka bir yerde bu ayarları uygulanmış ne ölçüde istediğinize bağlı olarak bir Python proje kökündeki yerleştirilebilir (bkz [komut satırı seçenekleri](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) Ayrıntılar için).

Örneğin, önceki görüntüsüyle gösterilen "docstring eksik" uyarıları gizlemek için bir `.pylintrc` dosya projede, adımları uygulayın:

1. Komut satırında proje kök dizinine gidin (içeren, `.pyproj` dosyası) ve bir açıklamalı yapılandırma dosyası oluşturmak için aşağıdaki komutu çalıştırın:

   ```command
   pylint --generate-rcfile > .pylintrc
   ```

1. Visual Studio Çözüm Gezgini'nde projenize sağ tıklayın, seçin **Ekle > öğesi çıkılıyor...** gidin ve yeni `.pylintrc` dosyasını bulun ve seçin **Ekle**.

1. Çeşitli çalışabileceğiniz ayarları içeren dosyayı düzenlemek için açın. Bir uyarı devre dışı bırakmak için bulun `[MESSAGES CONTROL]` bölümünde sonra bulun `disable` bu bölümünde ayarlama. Uzun bir dize istediğiniz hangi uyarıların ekleyebilirsiniz belirli iletilerinin yoktur. Örnekte, sona `,missing-docstring` (ayırıcı virgülle dahil).

1. Kaydet `.pylintrc` dosya ve uyarılarla şimdi bastırılan yeniden görmek için PyLint çalıştırın.

> [!Tip]
> Kullanılacak bir `.pylintrc` dosya bir ağ paylaşımından, adında bir ortam değişkeni oluşturma `PYLINTRC` bir UNC yolu veya eşlenen sürücü harfini kullanarak ağ üzerinde dosya adı değerini paylaşın. Örneğin, `PYLINTRC=\\myshare\python\.pylintrc`.
