---
title: "Kodunuzda başvurular bulma | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code editor, find all references
- find all references
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 92c12e4d51255849843f938c032ca17b611eeeab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="finding-references-in-your-code"></a>Kodunuzda başvurular bulma  
Kullanabileceğiniz **tüm başvuruları Bul** belirli kod öğeleri temelinizde Burada başvurulan bulmak için komutu. **Tüm başvuruları Bul** başvurular bulmak istediğiniz öğesinin (sağ tıklatma) bağlam menüsünde komutu kullanılabilir. Veya, klavye kullanıcısıysanız basın **Shift + F12**.  

Sonuçları adlı bir araç penceresinde görünen  **'*öğesi*' başvuruları ** nerede *öğesi* aradığınız öğe adı. Araç çubuğunda **başvuruları** penceresi olanak sağlar:  
- Aşağı açılan liste kutusunda arama kapsamını değiştirin. Yalnızca bu süreç boyunca tüm çözümün tamamında kadar değişen belgeleri bakın seçebilirsiniz.  
- Seçili başvurulan öğeyi seçerek kopyalama **kopyalama** düğmesi.  
- Listedeki veya tuşuna sonraki veya önceki konuma gitmek için düğmeler seçim **F8** ve **Shift + F8** Bunu yapmak için anahtarları.  
- Seçerek döndürülen sonuçların tüm filtreleri kaldırır **Temizle tüm filtreleri** düğmesi.  
- Nasıl döndürülen öğeleri değiştirmek bir ayar seçerek gruplandırılır **gruplandırma ölçütü:** aşağı açılan liste kutusu.  
- Geçerli arama sonuçları penceresinde seçerek tutmak **tutmak sonuçları** düğmesi. Bu düğme seçtiğinizde, geçerli arama sonuçları bu pencerede kalır ve yeni arama sonuçları yeni bir aracı penceresi görüntülenir.  
- Arama dizelerini arama sonuçları içindeki metin girerek **arama tüm başvuruları Bul** metin kutusu.  

Fare başvuru önizlemesini görmek için herhangi bir arama sonucunu de gelebilirsiniz.  

![Araç penceresi tüm başvuruları Bul](../ide/media/vside_findallreferences.png)  

### <a name="navigate-to-references"></a>Başvurular gidin
Başvuruları gitmek için aşağıdaki yöntemleri kullanabilirsiniz **başvuruları** penceresi:  

- Tuşuna **F8** sonraki referansı Git veya **Shift + F8** önceki referansı gidin.  
- Tuşuna **Enter** anahtar üzerinde bir başvuru ya da ona kodda gitmek için çift tıklatın.  
- Bir başvuru bağlam menüsünde seçin **önceki konumu** veya **sonraki konumu** komutları.  
- Seçin **yukarı ok** ve **aşağı ok** (Seçenekleri iletişim kutusunda etkinse) anahtarları. Menü çubuğunda, bu işlevselliği etkinleştirmek için seçin **Araçları**, **seçenekleri**, **ortam**, **sekmeler ve pencereler**,  **Önizleme sekmesi**ve ardından **Önizleme sekmede açılacak yeni dosyalar izin** ve **Bul sonuçları seçili dosyaları Önizleme** kutuları.  

### <a name="change-reference-groupings"></a>Değişiklik başvuru gruplandırmaları  
Varsayılan olarak, başvuruları projesi tarafından sonra tanımına göre gruplandırılır. Ancak, bu Gruplandırma sırası ayarlarını değiştirerek değiştirebileceğiniz **gruplandırma ölçütü:** araç çubuğundaki aşağı açılan liste kutusu. Örneğin, gelen varsayılan ayarı değiştirebilirsiniz **tanımı proje** için **tanımı sonra proje**, diğer ayarları da için.  

**Tanım** ve **proje** iki varsayılan gruplandırması kullanılır, ancak diğer seçerek eklemek **gruplandırma** seçilen öğenin bağlam menüsünde komutu. Daha fazla gruplandırmaları eklenmesi çözümünüzü dosyaları ve yolları miktarda varsa yararlı olabilir.  

## <a name="see-also"></a>Ayrıca bkz.  
[Kodda gezinme](../ide/navigating-code.md)  