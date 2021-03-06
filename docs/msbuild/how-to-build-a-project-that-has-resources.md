---
title: "Nasıl yapılır: kaynaklara sahip olan bir projeyi derleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resource files, compiling with MSBuild
- resources [Visual Studio], compiling with MSBuild
- projects [.NET Framework], building
- MSBuild, building a project with resources
ms.assetid: d07ac73f-2c2d-4e9a-812a-6dcb632bafe2
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0ca7978c4b50794b0c165ce8251da989a1653364
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-build-a-project-that-has-resources"></a>Nasıl Yapılır: Kaynaklara Sahip Olan Bir Projeyi Derleme
Bir proje yerelleştirilmiş sürümleri oluşturuluyorsa, tüm kullanıcı arabirimi öğeleri kaynak dosyalara farklı diller için ayrılmış olması gerekir. Proje yalnızca dizeleri kullanıyorsa, kaynak dosyaları metin dosyalarını kullanabilirsiniz. Alternatif olarak, .resx dosyaları kaynak dosya olarak kullanabilirsiniz.  
  
## <a name="compiling-resources-with-msbuild"></a>Kaynakları MSBuild ile derleme  
 Kitaplığı ile sağlanan ortak görevler [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] içeren bir `GenerateResource` .resx veya metin dosyaları kaynaklarında derlemek için kullanabileceğiniz bir görev. Bu görevi içeren `Sources` derlemek için hangi kaynak dosyaları belirtmek için parametre ve `OutputResources` parametre adları çıkış kaynak dosyaları için belirtin. Daha fazla bilgi için `GenerateResource` görev için bkz: [GenerateResource görevi](../msbuild/generateresource-task.md).  
  
#### <a name="to-compile-resources-with-msbuild"></a>MSBuild ile kaynakları derlemek için  
  
1.  Projenin kaynak dosyaları tanımlamak ve bunlara geçirin `GenerateResource` öğesi listeleri olarak da, görev veya gibi dosya adları.  
  
2.  Belirtin `OutputResources` parametresinin `GenerateResource` Görev çıkış kaynak dosyaları için adları ayarlamanıza olanak tanır.  
  
3.  Kullanım `Output` değeri depolamak için görev öğesi `OutputResources` öğeyi parametresi.  
  
4.  Oluşturulan öğesini kullanmak `Output` öğesi başka bir görev bir giriş olarak.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği kod nasıl `Output` öğesi belirttiğinden `OutputResources` özniteliği `GenerateResource` görev derlenmiş kaynak dosyalarını içerecek `alpha.resources` ve `beta.resources` ve bu iki dosya içine yerleştirilecek `Resources` öğe listesi. .Resources dosyaları öğeleri aynı ada sahip bir koleksiyonu belirleyerek kolayca girdi olarak başka bir görev için aşağıdaki gibi kullanabilmek için [Csc](../msbuild/csc-task.md) görev.  
  
 Bu görev kullanmakla eşdeğerdir **/derleme** için geçiş [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator):  
  
 `Resgen.exe /compile alpha.resx,alpha.resources /compile beta.txt,beta.resources`  
  
```xml  
<GenerateResource  
    Sources="alpha.resx; beta.txt"  
    OutputResources="alpha.resources; beta.resources">  
    <Output TaskParameter="OutputResources"  
        ItemName="Resources"/>  
</GenerateResource>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek proje iki görevleri içerir: `GenerateResource` kaynakları derlemek için görev ve `Csc` kaynak kodu dosyaları ve derlenmiş kaynak dosyalarını derlemek için görev. Kaynak dosyaları derlenmiş tarafından `GenerateResource` görev depolanır `Resources` öğesi ve geçirilen `Csc` görev.  
  
```xml  
<Project DefaultTargets = "Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <Target Name="Resources">  
        <GenerateResource  
            Sources="alpha.resx; beta.txt"  
            OutputResources="alpha.resources; beta.resources">  
            <Output TaskParameter="OutputResources"  
                ItemName="Resources"/>  
        </GenerateResource>  
    </Target>  
  
    <Target Name="Build" DependsOnTargets="Resources">  
        <Csc Sources="hello.cs"  
                Resources="@(Resources)"  
                OutputAssembly="hello.exe"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[MSBuild](../msbuild/msbuild.md)  
 [GenerateResource görevi](../msbuild/generateresource-task.md)   
 [CSC görevi](../msbuild/csc-task.md)   
 [Resgen.exe (Kaynak Dosya Oluşturucu)](/dotnet/framework/tools/resgen-exe-resource-file-generator)