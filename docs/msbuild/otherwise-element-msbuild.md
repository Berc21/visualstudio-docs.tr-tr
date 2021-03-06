---
title: "Otherwise öğesi (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Otherwise
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Otherwise> Element [MSBuild]
- Otherwise Element [MSBuild]
ms.assetid: de3997e9-1595-4263-a886-95530b56a319
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e0b824b8be8b3697673d0d1f09a20b6a7c1cee58
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="otherwise-element-msbuild"></a>Otherwise Öğesi (MSBuild)
Blok kod, yürütmeyi ve yalnızca tüm koşulları belirtir `When` öğeleri değerlendirmek için `false`.  

 \<Project>  
 \<Seçin >  
 \<Zaman >  
 \<Seçin >  
 ...  
 \<Aksi takdirde >  
 \<Seçin >  
 ...  

## <a name="syntax"></a>Sözdizimi  

```  
<Otherwise>  
    <PropertyGroup>... </PropertyGroup>  
    <ItemGroup>... </ItemGroup>  
    <Choose>... </Choose>  
</Otherwise>  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  
 Yok.  

### <a name="child-elements"></a>Alt Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Seçin](../msbuild/choose-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Kod yürütmek için bir bölüm seçmek için alt öğeler değerlendirir. Sıfır veya daha fazla olabilir `Choose` öğelerinde bir `Otherwise` öğesi.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Kullanıcı tanımlı bir kümesini içerir [öğesi](../msbuild/item-element-msbuild.md) öğeleri. Sıfır veya daha fazla olabilir `ItemGroup` öğelerinde bir `Otherwise` öğesi.|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Kullanıcı tanımlı bir kümesini içerir [özelliği](../msbuild/property-element-msbuild.md) öğeleri. Sıfır veya daha fazla olabilir `PropertyGroup` öğelerinde bir `Otherwise` öğesi.|  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Seçin](../msbuild/choose-element-msbuild.md)|Kod yürütmek için bir bölüm seçmek için alt öğeler değerlendirir.|  

## <a name="remarks"></a>Açıklamalar  
 Olabilir tek `Otherwise` öğesinde bir `Choose` öğesi ve onu son öğe olmalıdır.  

 `Choose`, `When`, Ve `Otherwise` öğelerini birlikte bir dizi olası alternatifler dışında yürütülecek kod bir bölüm seçmek için bir yol sağlamak için kullanılır. Daha fazla bilgi için bkz: [koşullu yapıları](../msbuild/msbuild-conditional-constructs.md).  

## <a name="example"></a>Örnek  
 Aşağıdaki proje kullanır `Choose` özellik değerlerinde hangi kümesini seçmek için öğe `When` öğeleri ayarlayın. Varsa `Condition` her ikisi de özniteliklerini `When` öğeleri değerlendirmek için `false`, özellik değerleri `Otherwise` öğesi ayarlanır.  

```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <PropertyGroup>  
        <Configuration Condition="'$(Configuration)' == ''">Debug</Configuration>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>ConsoleApplication1</RootNamespace>  
        <AssemblyName>ConsoleApplication1</AssemblyName>  
        <WarningLevel>4</WarningLevel>  
    </PropertyGroup>  
    <Choose>  
        <When Condition=" '$(Configuration)'=='debug' ">  
            <PropertyGroup>  
                <DebugSymbols>true</DebugSymbols>  
                <DebugType>full</DebugType>  
                <Optimize>false</Optimize>  
                <OutputPath>.\bin\Debug\</OutputPath>  
                <DefineConstants>DEBUG;TRACE</DefineConstants>  
            </PropertyGroup>  
            <ItemGroup>  
                <Compile Include="UnitTesting\*.cs" />  
                <Reference Include="NUnit.dll" />  
            </ItemGroup>  
        </When>  
        <When Condition=" '$(Configuration)'=='retail' ">  
            <PropertyGroup>  
                <DebugSymbols>false</DebugSymbols>  
                <Optimize>true</Optimize>  
                <OutputPath>.\bin\Release\</OutputPath>  
                <DefineConstants>TRACE</DefineConstants>  
            </PropertyGroup>  
        </When>  
        <Otherwise>  
            <PropertyGroup>  
                <DebugSymbols>true</DebugSymbols>  
                <Optimize>false</Optimize>  
                <OutputPath>.\bin\$(Configuration)\</OutputPath>  
                <DefineConstants>DEBUG;TRACE</DefineConstants>  
            </PropertyGroup>  
        </Otherwise>  
        </Choose>  
    <Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />  
</Project>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Koşullu yapılar](../msbuild/msbuild-conditional-constructs.md)   
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)
