---
title: "ItemGroup öğesi (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#ItemGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemGroup element [MSBuild]
- <ItemGroup> element [MSBuild]
ms.assetid: aac894e3-a9f1-4bbc-a796-6ef07001f35b
caps.latest.revision: "24"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 04920978073c85f968c51dc34dae54d90e7b6427
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="itemgroup-element-msbuild"></a>ItemGroup Öğesi (MSBuild)
Kullanıcı tanımlı bir kümesini içerir [öğesi](../msbuild/item-element-msbuild.md) öğeleri. Kullanılan her öğe bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bir alt öğesi olarak proje belirtilen bir `ItemGroup` öğesi.  
  
 \<Proje >  
 \<ItemGroup >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<ItemGroup Condition="'String A' == 'String B'">  
    <Item1>... </Item1>  
    <Item2>... </Item2>  
</ItemGroup>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Condition`|İsteğe bağlı öznitelik. Değerlendirilecek koşulu. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Öğesi](../msbuild/item-element-msbuild.md)|Derleme işlemi için giriş tanımlar. Sıfır veya daha fazla olabilir `Item` öğelerinde bir `ItemGroup`.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Proje](../msbuild/project-element-msbuild.md)|Gerekli kök öğesinin bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası.|  
|[Hedef](../msbuild/target-element-msbuild.md)|.NET Framework 3.5 ile başlayan `ItemGroup` öğesi içinde görünebilir bir `Target` öğesi. Daha fazla bilgi için bkz: [hedefleri](../msbuild/msbuild-targets.md).|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, kullanıcı tanımlı öğe koleksiyonlarını gösterir `Res` ve `CodeFiles` içinde bildirilen bir `ItemGroup` öğesi. Her bir öğe içinde `Res` öğe koleksiyonu içeren bir kullanıcı tarafından tanımlanan alt [Itemmetadata](../msbuild/itemmetadata-element-msbuild.md) öğesi.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Res Include = "Strings.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include = "Dialogs.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
  
        <CodeFiles Include="**\*.cs" Exclude="**\generated\*.cs" />  
        <CodeFiles Include="..\..\Resources\Constants.cs" />  
    </ItemGroup>  
...  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Öğeleri](../msbuild/msbuild-items.md)   
 [Yaygın MSBuild proje öğeleri](../msbuild/common-msbuild-project-items.md)