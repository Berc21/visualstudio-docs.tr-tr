---
title: "Visual Studio'da değeriyle geçici bir değişken Değiştir | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 836f7b847a2a57de83f6bea7f05bed83571e7485
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="inline-a-temporary-variable-refactoring"></a>Satır içi bir geçici değişken yeniden düzenleme

Bu yeniden düzenleme için geçerlidir:

- C#

- Visual Basic

**Ne:** geçici bir değişken kaldırın ve bunun yerine, değeriyle değiştirmenizi sağlar.

**Ne zaman:** geçici değişken kullanımını kodunu anlamanın zorlaştırır.

**Neden:** geçici bir değişken kaldırılması hale kodu kolay okunur.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Vurgula veya metin imleci geçici değişkenin içermesinden olmasını içinde:

   - C# ' TA:

    ![Vurgulanmış kodu - C#](media/inline-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu - Visual Basic](media/inline-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Kod sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.

1. Seçin **satır içi geçici değişken** gelen önizleme penceresi açılır.

   Değişkeni kaldırılır ve kendi kullanımları değişkenin değeriyle değiştirilir.

   - C# ' TA:

    ![Satır içi sonucu - C#](media/inline-result-cs.png)

   - Visual Basic:

    ![Satır içi sonucu - Visual Basic](media/inline-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)