---
title: Kural ayarları için Visual Studio EditorConfig kodlama .NET | Microsoft Docs
ms.date: 02/28/2018
ms.topic: article
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- coding conventions [EditorConfig]
- EditorConfig coding conventions
- language conventions [EditorConfig]
- formatting conventions [EditorConfig]
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.technology: vs-ide-general
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e69d7e291d1b13a5205aa4798c78c6a4e337db50
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="net-coding-convention-settings-for-editorconfig"></a>.NET EditorConfig kuralı ayarlarını kodlama

Visual Studio 2017 içinde tanımlamak ve tutarlı kod stilde korumak, kullanımı ile codebase bir [EditorConfig](../ide/create-portable-custom-editor-options.md) dosya. EditorConfig içeren birkaç çekirdek biçimlendirme özellikleri, gibi `indent_style` ve `indent_size`. Visual Studio'da .NET kuralları ayarları kodlama EditorConfig dosyasını kullanarak da yapılandırılabilir. EditorConfig dosyaları etkinleştirmek veya devre dışı kodlama kuralları tek tek .NET ve bir önem düzeyi zorlanan kuralı istediğiniz derece yapılandırmak için izin verin. EditorConfig temelinizde tutarlılığı zorlamak için nasıl kullanılacağı hakkında daha fazla bilgi için okuma [oluşturma taşınabilir özel düzenleyici seçenekleri](../ide/create-portable-custom-editor-options.md). Ayrıca bakabilir [.NET derleyici platformun .editorconfig dosya](https://github.com/dotnet/roslyn/blob/master/.editorconfig) bir örnek olarak.

Üç desteklenen .NET kodlama kuralı kategoriye ayrılır:

- [Dil kuralları](#language-conventions)

   C# veya Visual Basic Dil ilgili kuralları. Örneğin, kullanarak geçici kuralları belirtebilirsiniz `var` veya açık olduğunda türleri değişkenleri tanımlama veya üye ifadesi bodied tercih ederek.

- [Biçimlendirme kuralları](#formatting-conventions)

   Düzen ve okunmasını kolaylaştırmak için kodunuzu yapısını ilgili kuralları. Örneğin, denetim blokları Allman küme ayraçları veya tercih ederek alanları çevresinde kuralları belirtebilirsiniz.

- [Adlandırma Kuralları](../ide/editorconfig-naming-conventions.md)

   Kod öğelerini adlandırma ile ilgili kurallar. Örneğin, belirtebilirsiniz `async` yöntemleri "Zaman uyumsuz" bitmelidir.

## <a name="language-conventions"></a>Dil kuralları

Dil kuralları için kurallar aşağıdaki biçime sahiptir:

`options_name = false|true : none|suggestion|warning|error`

Her dil kuralı kural için ya da belirtmeniz gerekir **true** (Bu stili tercih et) veya **false** (Bu stili tercih değil) ve bir **önem**. Önem derecesi bu stili için zorlama düzeyini belirtir.

Aşağıdaki tabloda olası önem derecesi değerlerini ve etkilerini listeler:

Önem Derecesi | Efekt
:------- | ------
None veya Sessiz | Bu kural ihlal edildiğinde herhangi bir şey kullanıcıya gösterme. Kod oluşturma özellikleri kod, ancak bu stilde'ı oluşturun.
Öneri | Bu stil kuralı ihlal edildiğinde kullanıcıya öneri olarak göster. İlk iki karakter altında üç gri nokta olarak öneriler görünür.
uyarı | Bu stil kuralı ihlal edildiğinde derleyici uyarısı gösterir.
Hata | Bu stil kuralı ihlal edildiğinde derleyici hatası gösterir.

Aşağıdaki liste, izin verilen dil kuralı kuralları gösterir:

- .NET kodu stilini ayarlar
    - ["This." ve "Me" niteleyicileri](#this_and_me)
        - dotnet\_style\_qualification\_for_field
        - DotNet\_stili\_niteliğe\_for_property
        - DotNet\_stili\_niteliğe\_for_method
        - dotnet\_style\_qualification\_for_event
    - [Dil anahtar sözcükleri framework yerine tür başvuruları adlarını yazın](#language_keywords)
        - dotnet\_style\_predefined\_type\_for\_locals\_parameters_members
        - dotnet\_style\_predefined\_type\_for\_member_access
    - [Değiştirici tercihleri](#normalize_modifiers)
        - DotNet\_stili\_gerektiren\_accessibility_modifiers
        - csharp\_preferred\_modifier_order
        - visual\_basic\_preferred\_modifier_order
    - [İfade düzeyi tercihleri](#expression_level)
        - dotnet\_style\_object_initializer
        - dotnet\_style\_collection_initializer
        - dotnet\_style\_explicit\_tuple_names
        - dotnet\_prefer\_inferred\_tuple_names
        - DotNet\_tercih\_çıkarımı yapılan\_anonim\_türü\_member_names
    - ["Null" Tercihler denetleniyor](#null_checking)
        - dotnet\_style\_coalesce_expression
        - dotnet\_style\_null_propagation
- C# kod stili ayarları
    - [Örtük ve açık türleri](#var)
        - csharp\_style\_var\_for\_built\_in_types
        - CSharp\_stili\_var\_zaman\_türü\_is_apparent
        - csharp\_style\_var_elsewhere
    - [İfade gövdeli üyeler](#expression_bodied_members)
        - csharp\_style\_expression\_bodied_methods
        - csharp\_style\_expression\_bodied_constructors
        - csharp\_style\_expression\_bodied_operators
        - csharp\_style\_expression\_bodied_properties
        - csharp\_style\_expression\_bodied_indexers
        - csharp\_style\_expression\_bodied_accessors
    - [Desen eşleştirme](#pattern_matching)
        - CSharp\_stili\_düzeni\_eşleşen\_üzerinden\_olan\_ile\_cast_check
        - CSharp\_stili\_düzeni\_eşleşen\_üzerinden\_olarak\_ile\_null_check
    - [Satır içi değişken bildirimleri](#inlined_variable_declarations)
        - CSharp\_stili\_içermesinden\_variable_declaration
    - [İfade düzeyi tercihleri](#expression_level_csharp)
        - csharp\_prefer\_simple\_default_expression
        - csharp\_style\_deconstructed\_variable_declaration
        - CSharp\_stili\_düzeni\_yerel\_üzerinden\_anonymous_function
    - ["Null" Tercihler denetleniyor](#null_checking_csharp)
        - csharp\_style\_throw_expression
        - csharp\_style\_conditional\_delegate_call
    - [Kod bloğu tercihleri](#code_block)
        - csharp\_prefer_braces

### <a name="net-code-style-settings"></a>.NET kodu stilini ayarlar

Bu bölümdeki stil kurallarını hem C# ve Visual Basic için geçerlidir. Tercih ettiğiniz programlama dili kod örneklerinde görmek için açılan seçin **dil** tarayıcı pencerenizin sağ üst köşesindeki menüsü.

#### <a name="this_and_me">"This." ve "Me" niteleyicileri</a>

Bu stil kuralı (kuralı kimlikleri IDE0003 ve IDE0009) alanları, özellikleri, yöntemleri veya olayları için uygulanabilir. Değerini **true** anlamına gelir tercih kod simge ile başlayan `this.` C# veya `Me.` Visual Basic'te. Değerini **false** anlamına gelir tercih code öğesi _değil_ ile başlayan için `this.` veya `Me.`.

Aşağıdaki tabloda, kural adları, uygun programlama dilleri ve varsayılan değerleri gösterir:

| Kural adı | Geçerli diller | Visual Studio varsayılan değer |
| ----------- | -------------------- | ----------------------|
| dotnet_style_qualification_for_field | C# ve Visual Basic | false:none |
| dotnet_style_qualification_for_property | C# ve Visual Basic | false:none |
| dotnet_style_qualification_for_method | C# ve Visual Basic | false:none |
| dotnet_style_qualification_for_event | C# ve Visual Basic | false:none |

**dotnet\_style\_qualification\_for_field**

- Bu kural ayarlandığında **true**, alanları ile başlayan tercih `this.` C# veya `Me.` Visual Basic'te.
- Bu kural ayarlandığında **false**, alanları tercih _değil_ ile başlayan için `this.` veya `Me.`.

Kod örnekleri:

```csharp
// dotnet_style_qualification_for_field = true
this.capacity = 0;

// dotnet_style_qualification_for_field = false
capacity = 0;
```

```vb
' dotnet_style_qualification_for_field = true
Me.capacity = 0

' dotnet_style_qualification_for_field = false
capacity = 0
```

**dotnet\_style\_qualification\_for_property**

- Bu kural ayarlandığında **true**, ile başlayan özellikler tercih `this.` C# veya `Me.` Visual Basic'te.
- Bu kural ayarlandığında **false**, Özellikler tercih _değil_ ile başlayan için `this.` veya `Me.`.

Kod örnekleri:

```csharp
// dotnet_style_qualification_for_property = true
this.ID = 0;

// dotnet_style_qualification_for_property = false
ID = 0;
```

```vb
' dotnet_style_qualification_for_property = true
Me.ID = 0

' dotnet_style_qualification_for_property = false
ID = 0
```

**dotnet\_style\_qualification\_for_method**

- Bu kural ayarlandığında **true**, yöntemleri ile başlayan tercih `this.` C# veya `Me.` Visual Basic'te.
- Bu kural ayarlandığında **false**, yöntemleri tercih _değil_ ile başlayan için `this.` veya `Me.`.

Kod örnekleri:

```csharp
// dotnet_style_qualification_for_method = true
this.Display();

// dotnet_style_qualification_for_method = false
Display();
```

```vb
' dotnet_style_qualification_for_method = true
Me.Display()

' dotnet_style_qualification_for_method = false
Display()
```

**dotnet\_style\_qualification\_for_event**

- Bu kural ayarlandığında **true**, olayları ile başlayan tercih `this.` C# veya `Me.` Visual Basic'te.
- Bu kural ayarlandığında **false**, olayları tercih _değil_ ile başlayan için `this.` veya `Me.`.

Kod örnekleri:

```csharp
// dotnet_style_qualification_for_event = true
this.Elapsed += Handler;

// dotnet_style_qualification_for_event = false
Elapsed += Handler;
```

```vb
' dotnet_style_qualification_for_event = true
AddHandler Me.Elapsed, AddressOf Handler

' dotnet_style_qualification_for_event = false
AddHandler Elapsed, AddressOf Handler
```

Bu kurallar bir .editorconfig dosyasında şu şekilde görünebilir:

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_qualification_for_field = false:suggestion
dotnet_style_qualification_for_property = false:suggestion
dotnet_style_qualification_for_method = false:suggestion
dotnet_style_qualification_for_event = false:suggestion
```

#### <a name="language_keywords">Dil anahtar sözcükleri framework yerine tür başvuruları adlarını yazın</a>

Bu stil kuralı, yerel değişkenleri, yöntem parametreleri ve sınıf üyeleri için veya üye erişimi ifadeleri yazmak için ayrı bir kural olarak uygulanabilir. Değerini **true** anlamına gelir tercih ettiğiniz dili anahtar sözcüğü (örneğin `int` veya `Integer`) türü adı yerine (örneğin `Int32`) bunları temsil etmek için bir anahtar sözcüğüne sahip türleri için. Değerini **false** tercih türü adı dil anahtar sözcüğü yerine anlamına gelir.

Aşağıdaki tabloda, kuralı adları, kuralları kimlikleri, geçerli programlama dilleri ve varsayılan değerleri gösterir:

| Kural adı | Kural Kimliği | Geçerli diller | Visual Studio varsayılan |
| --------- | ------- | -------------------- | ----------------------|
| dotnet_style_predefined_type_for_locals_parameters_members | IDE0012 ve IDE0014 | C# ve Visual Basic | true:none |
| dotnet_style_predefined_type_for_member_access | IDE0013 ve IDE0015 | C# ve Visual Basic | true:none |

**dotnet\_style\_predefined\_type\_for\_locals\_parameters_members**

- Bu kural ayarlandığında **doğru**, yerel değişkenleri, yöntem parametreleri dil anahtar sözcüğü tercih ve sınıf adını yazın, bunları temsil etmek için bir anahtar sözcüğüne sahip türleri yerine üyeleri.
- Bu kural ayarlandığında **yanlış**, yerel değişkenleri, yöntem parametreleri için tür adını tercih ve sınıf üyeleri dil anahtar sözcüğü yerine.

Kod örnekleri:

```csharp
// dotnet_style_predefined_type_for_locals_parameters_members = true
private int _member;

// dotnet_style_predefined_type_for_locals_parameters_members = false
private Int32 _member;
```

```vb
' dotnet_style_predefined_type_for_locals_parameters_members = true
Private _member As Integer

' dotnet_style_predefined_type_for_locals_parameters_members = false
Private _member As Int32
```

**dotnet\_style\_predefined\_type\_for\_member_access**

- Bu kural ayarlandığında **doğru**, bunları temsil etmek için bir anahtar sözcüğüne sahip türleri için tür adı yerine üye erişimi ifadeleri dil anahtar sözcüğü tercih eder.
- Bu kural ayarlandığında **yanlış**, dil anahtar sözcüğü yerine üye erişimi ifadeleri türü adı tercih eder.

Kod örnekleri:

```csharp
// dotnet_style_predefined_type_for_member_access = true
var local = int.MaxValue;

// dotnet_style_predefined_type_for_member_access = false
var local = Int32.MaxValue;
```

```vb
' dotnet_style_predefined_type_for_member_access = true
Dim local = Integer.MaxValue

' dotnet_style_predefined_type_for_member_access = false
Dim local = Int32.MaxValue
```

Bu kurallar bir .editorconfig dosyasında şu şekilde görünebilir:

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_predefined_type_for_locals_parameters_members = true:suggestion
dotnet_style_predefined_type_for_member_access = true:suggestion
```

#### <a name="normalize_modifiers">Değiştirici tercihleri</a>

Stil kurallarını erişilebilirlik değiştiricileri gerektiren ve istenen değiştiricisi belirterek dahil olmak üzere bu bölümü sorunu değiştiricisi tercihlerinde sıralama düzeni.

Aşağıdaki tabloda, kuralı adları, kural kimlikleri, geçerli programlama dilleri, varsayılan değerleri ve ilk desteklenen Visual Studio sürümünü gösterir:

| Kural adı | Kural Kimliği | Geçerli diller | Visual Studio varsayılan | Visual Studio 2017 sürümü |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| dotnet_style_require_accessibility_modifiers | IDE0040 | C# ve Visual Basic | for_non_interface_members:none | 15.5 |
| csharp_preferred_modifier_order | IDE0036 | C# | Genel, özel, korumalı, iç, statik extern, yeni, sanal, soyut ve korumalı, geçersiz kılma, salt okunur, güvenli olmayan, geçici, zaman uyumsuz: yok | 15.5 |
| visual_basic_preferred_modifier_order | IDE0036 | Visual Basic | Kısmi, varsayılan, özel, korumalı, Public, arkadaş, NotOverridable, geçersiz kılınabilir, MustOverride, aşırı yüklemeleri, geçersiz kılmalar, MustInherit, NotInheritable, statik, paylaşılan, gölge, salt okunur, WriteOnly, boyutu, Const, WithEvents, genişletme, özel, daraltma Zaman uyumsuz: yok | 15.5 |

**DotNet\_stili\_gerektiren\_accessibility_modifiers**

Bu kural kabul etmediği bir **true** veya **yanlış** değeri; bunun yerine aşağıdaki tablodan bir değer olarak kabul eder:

| Değer | Açıklama |
| ----- |:----------- |
| Her zaman | Erişilebilirlik değiştiricileri belirtilmesi tercih |
| için\_olmayan\_interface_members | Genel arabirim üyeleri dışında bildirilmesi için erişilebilirlik değiştiricileri tercih eder. Bu şu anda farklı değil **her zaman** ve C# varsayılan arabirim yöntemleri eklerse, gelecekteki için sağlama olarak hareket eder. |
| Hiçbir zaman | Erişilebilirlik değiştiricileri belirtilmesi tercih ediyorsunuz |

Kod örnekleri:

```csharp
// dotnet_style_require_accessibility_modifiers = always
// dotnet_style_require_accessibility_modifiers = for_non_interface_members
class MyClass
{
    private const string thisFieldIsConst= "constant";
}

// dotnet_style_require_accessibility_modifiers = never
class MyClass
{
    const string thisFieldIsConst= "constant";
}
```

**csharp_preferred_modifier_order**

- Bu kural değiştiricileri listesine ayarladığınızda, belirtilen sıralama tercih eder.
- Bu kural dosyasından atlandığında, değiştiricisi sipariş tercih ediyorsunuz.

Kod örnekleri:

```csharp
// csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async
class MyClass
{
    private static readonly int _daysInYear = 365;
}
```

**visual_basic_preferred_modifier_order**

- Bu kural değiştiricileri listesine ayarladığınızda, belirtilen sıralama tercih eder.
- Bu kural dosyasından atlandığında, değiştiricisi sipariş tercih ediyorsunuz.

Kod örnekleri:

```vb
' visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async
Public Class MyClass
    Private Shared ReadOnly daysInYear As Int = 365
End Class
```

Bu kurallar bir .editorconfig dosyasında şu şekilde görünebilir:

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_require_accessibility_modifiers = always:suggestion

# CSharp code style settings:
[*.cs]
csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async:suggestion

# Visual Basic code style settings:
[*.vb]
visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async:suggestion
```

#### <a name="expression_level">İfade düzeyi tercihleri</a>

Stil nesne başlatıcılar, koleksiyon başlatıcıları, açık veya oluşturulursa tanımlama grubu adları, kullanımı dahil olmak üzere bu bölümü sorunu ifade düzeyi tercihlerinde, kurallar ve anonim türler sonuçlandı.

Aşağıdaki tabloda, kuralı adları, kural kimlikleri, geçerli programlama dilleri, varsayılan değerleri ve ilk desteklenen Visual Studio sürümünü gösterir:

| Kural adı | Kural Kimliği | Geçerli diller | Visual Studio varsayılan | Visual Studio 2017 sürümü |
| --------- | ------- | -------------------- | ----------------------| ---- |
| dotnet_style_object_initializer | IDE0017 | C# ve Visual Basic | true:suggestion | İlk sürüm |
| dotnet_style_collection_initializer | IDE0028 | C# ve Visual Basic | true:suggestion | İlk sürüm |
| dotnet_style_explicit_tuple_names | IDE0033 | C# ' ta 7.0 + ve Visual Basic 15 + | true:suggestion | İlk sürüm |
| dotnet_style_prefer_inferred_tuple_names | IDE0037 | C# ' ta 7.1 + ve Visual Basic 15 + | true:suggestion | 15.6 |
| dotnet_style_prefer_inferred_anonymous_type_member_names | IDE0037 | C# ve Visual Basic | true:suggestion | 15.6 |

**dotnet\_style\_object_initializer**

- Bu kural ayarlandığında **doğru**, mümkün olduğunda nesne başlatıcıları kullanarak başlatılması için nesneleri tercih.
- Bu kural ayarlandığında **false**, nesnelere tercih *değil* olması nesne başlatıcıları başlatıldı.

Kod örnekleri:

```csharp
// dotnet_style_object_initializer = true
var c = new Customer() { Age = 21 };

// dotnet_style_object_initializer = false
var c = new Customer();
c.Age = 21;
```

```vb
' dotnet_style_object_initializer = true
Dim c = New Customer() With {.Age = 21}

' dotnet_style_object_initializer = false
Dim c = New Customer()
c.Age = 21
```

**dotnet\_style\_collection_initializer**

- Bu kural ayarlandığında **doğru**, mümkün olduğunda koleksiyon başlatıcıları kullanarak başlatılması için koleksiyonları tercih.
- Bu kural ayarlandığında **false**, koleksiyonlara tercih *değil* olması koleksiyon başlatıcıları başlatıldı.

Kod örnekleri:

```csharp
// dotnet_style_collection_initializer = true
var list = new List<int> { 1, 2, 3 };

// dotnet_style_collection_initializer = false
var list = new List<int>();
list.Add(1);
list.Add(2);
list.Add(3);
```

```vb
' dotnet_style_collection_initializer = true
Dim list = New List(Of Integer) From {1, 2, 3}

' dotnet_style_collection_initializer = false
Dim list = New List(Of Integer)
list.Add(1)
list.Add(2)
list.Add(3)
```

**dotnet\_style\_explicit\_tuple_names**

- Bu kural ayarlandığında **doğru**, tanımlama grubu adları ItemX özelliklerine tercih eder.
- Bu kural ayarlandığında **yanlış**, ItemX özellikleri tanımlama grubu adları tercih.

Kod örnekleri:

```csharp
// dotnet_style_explicit_tuple_names = true
(string name, int age) customer = GetCustomer();
var name = customer.name;

// dotnet_style_explicit_tuple_names = false
(string name, int age) customer = GetCustomer();
var name = customer.Item1;
```

```vb
 ' dotnet_style_explicit_tuple_names = true
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.name

' dotnet_style_explicit_tuple_names = false
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.Item1
```

**dotnet\_style\_prefer\_inferred\_tuple_names**

- Bu kural ayarlandığında **doğru**, oluşturulursa tanımlama grubu öğe adları tercih eder.
- Bu kural ayarlandığında **yanlış**, açık tanımlama grubu öğe adları tercih eder.

Kod örnekleri:

```csharp
// dotnet_style_prefer_inferred_tuple_names = true
var tuple = (age, name);

// dotnet_style_prefer_inferred_tuple_names = false
var tuple = (age: age, name: name);
```

**dotnet\_style\_prefer\_inferred\_anonymous\_type\_member_names**

- Bu kural ayarlandığında **doğru**, oluşturulursa anonim tür üye adlarının tercih eder.
- Bu kural ayarlandığında **yanlış**, açık anonim tür üye adlarının tercih eder.

Kod örnekleri:

```csharp
// dotnet_style_prefer_inferred_anonymous_type_member_names = true
var anon = new { age, name };

// dotnet_style_prefer_inferred_anonymous_type_member_names = false
var anon = new { age = age, name = name };

```

Bu kurallar bir .editorconfig dosyasında şu şekilde görünebilir:

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_object_initializer = true:suggestion
dotnet_style_collection_initializer = true:suggestion
dotnet_style_explicit_tuple_names = true:suggestion
dotnet_style_prefer_inferred_tuple_names = true:suggestion
dotnet_style_prefer_inferred_anonymous_type_member_names = true:suggestion
```

#### <a name="null_checking">Null denetimi tercihleri</a>

Bu bölümdeki stil kurallarını null denetimi Tercihler ilgilendiren.

Aşağıdaki tabloda, kuralı adları, kural kimlikleri, geçerli programlama dilleri, varsayılan değerleri ve ilk desteklenen Visual Studio sürümünü gösterir:

| Kural adı | Kural Kimliği | Geçerli diller | Visual Studio varsayılan | Visual Studio 2017 sürümü |
| --------- | ------- | -------------------- | ----------------------| ---- |
| dotnet_style_coalesce_expression | IDE0029 | C# ve Visual Basic | true:suggestion | İlk sürüm |
| dotnet_style_null_propagation | IDE0031 | C# ' ta 6.0 + ve Visual Basic 14 + | true:suggestion | İlk sürüm |

**dotnet\_style\_coalesce_expression**

- Bu kural ayarlandığında **doğru**, null birleştirmesi ifadeleri denetimi Üçlü işleci için tercih ettiğiniz.
- Bu kural ayarlandığında **yanlış**, null birleştirmesi ifadelere denetimi Üçlü işleci tercih eder.

Kod örnekleri:

```csharp
// dotnet_style_coalesce_expression = true
var v = x ?? y;

// dotnet_style_coalesce_expression = false
var v = x != null ? x : y; // or
var v = x == null ? y : x;
```

```vb
' dotnet_style_coalesce_expression = true
Dim v = If(x, y)

' dotnet_style_coalesce_expression = false
Dim v = If(x Is Nothing, y, x) ' or
Dim v = If(x IsNot Nothing, x, y)
```

**dotnet\_style\_null_propagation**

- Bu kural ayarlandığında **doğru**, mümkün olduğunda null koşul işlecini kullanmayı tercih eder.
- Bu kural ayarlandığında **yanlış**, Üçlü null denetimi mümkün olduğunda kullanmayı tercih eder.

Kod örnekleri:

```csharp
// dotnet_style_null_propagation = true
var v = o?.ToString();

// dotnet_style_null_propagation = false
var v = o == null ? null : o.ToString(); // or
var v = o != null ? o.String() : null;
```

```vb
' dotnet_style_null_propagation = true
Dim v = o?.ToString()

' dotnet_style_null_propagation = false
Dim v = If(o Is Nothing, Nothing, o.ToString()) ' or
Dim v = If(o IsNot Nothing, o.ToString(), Nothing)
```

Bu kurallar bir .editorconfig dosyasında şu şekilde görünebilir:

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_coalesce_expression = true:suggestion
dotnet_style_null_propagation = true:suggestion
```

### <a name="c-code-style-settings"></a>C# kod stili ayarları

Bu bölümdeki stil kurallarını yalnızca C# için geçerlidir.

#### <a name="var">Örtük ve açık türleri</a>

Bu bölümdeki stil kurallarını (kimlikleri IDE0007 ve IDE0008 kural) kullanımını ilgilendiren [var](/dotnet/csharp/language-reference/keywords/var) anahtar sözcüğü bir açık tür Değişken bildiriminde karşılaştırması. Bu kural türü görünen olduğunda yerleşik türleri ve diğer yerlerde için ayrı olarak uygulanabilir.

Aşağıdaki tabloda, kural adları, uygun programlama dilleri ve varsayılan değerleri gösterir:

| Kural adı | Geçerli diller | Visual Studio varsayılan |
| ----------- | -------------------- | ----------------------|
| csharp_style_var_for_built_in_types | C# | true:none |
| csharp_style_var_when_type_is_apparent | C# | true:none |
| csharp_style_var_elsewhere | C# | true:none |

**csharp\_style\_var\_for\_built\_in_types**

- Bu kural ayarlandığında **true**, tercih ettiğiniz `var` değişkenler gibi yerleşik sistem türleriyle bildirmek için kullanılan `int`.
- Bu kural ayarlandığında **false**, açık tür üzerinden tercih `var` gibi yerleşik sistem türleriyle değişkenleri bildirmeyi `int`.

Kod örnekleri:

```csharp
// csharp_style_var_for_built_in_types = true
var x = 5;

// csharp_style_var_for_built_in_types = false
int x = 5;
```

**CSharp\_stili\_var\_zaman\_türü\_is_apparent**

- Bu kural ayarlandığında **true**, tercih ettiğiniz `var` zaman türü önceden belirtilen bildirimi ifadesinin sağ tarafta.
- Bu kural ayarlandığında **false**, açık tür üzerinden tercih `var` zaman türü önceden belirtilen bildirimi ifadesinin sağ tarafta.

Kod örnekleri:

```csharp
// csharp_style_var_when_type_is_apparent = true
var obj = new Customer();

// csharp_style_var_when_type_is_apparent = false
Customer obj = new Customer();
```

**csharp\_style\_var_elsewhere**

- Bu kural ayarlandığında **true**, tercih ettiğiniz `var` tüm durumlarda açık tür üzerinden başka bir kod stil kuralı tarafından kılınmadığı sürece.
- Bu kural ayarlandığında **false**, açık tür üzerinden tercih `var` tüm durumlarda, başka bir kod stil kuralı tarafından kılınmadığı sürece.

Kod örnekleri:

```csharp
// csharp_style_var_elsewhere = true
var f = this.Init();

// csharp_style_var_elsewhere = false
bool f = this.Init();
```

Örnek .editorconfig dosyası:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_var_for_built_in_types = true:suggestion
csharp_style_var_when_type_is_apparent = true:suggestion
csharp_style_var_elsewhere = true:suggestion
```

#### <a name="expression_bodied_members">İfade gövdeli üyeler</a>

Bu bölümdeki stil kurallarını kullanımını ilgilendiren [ifade bodied üyeleri](/dotnet/csharp/programming-guide/statements-expressions-operators/expression-bodied-members) zaman mantığı oluşan tek bir ifade. Bu kural, yöntemleri, Oluşturucular, işleçleri, özellikleri, dizin oluşturucular ve erişimciler uygulanabilir.

Aşağıdaki tabloda, kuralı adları, kural kimlikleri, geçerli dil sürümleri, varsayılan değerleri ve ilk desteklenen Visual Studio sürümünü gösterir:

| Kural adı | Kural Kimliği | Geçerli diller | Visual Studio varsayılan | Visual Studio 2017 sürümü |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_style_expression_bodied_methods | IDE0022 | C# 6.0+ | false:none | 15.3 |
| csharp_style_expression_bodied_constructors | IDE0021 | C# ' TA 7.0 + | false:none | 15.3 |
| csharp_style_expression_bodied_operators | IDE0023 ve IDE0024 | C# ' TA 7.0 + | false:none | 15.3 |
| csharp_style_expression_bodied_properties | IDE0025 | C# ' TA 7.0 + | true:none | 15.3 |
| csharp_style_expression_bodied_indexers | IDE0026 | C# ' TA 7.0 + | true:none | 15.3 |
| csharp_style_expression_bodied_accessors | IDE0027 | C# ' TA 7.0 + | true:none | 15.3 |

**csharp\_style\_expression\_bodied_methods**

Bu kural aşağıdaki tabloda değerleri kabul eder:

| Değer | Açıklama |
| ----- |:----------- |
| true | İfade bodied üyeleri yöntemleri için tercih ettiğiniz |
| when_on_single_line | Tek bir satır olacak zaman ifade bodied üyeleri yöntemleri için tercih ettiğiniz |
| false | Blok gövdeleri yöntemleri için tercih ettiğiniz |

Kod örnekleri:

```csharp
// csharp_style_expression_bodied_methods = true
public int GetAge() => this.Age;

// csharp_style_expression_bodied_methods = false
public int GetAge() { return this.Age; }
```

**csharp\_style\_expression\_bodied_constructors**

Bu kural aşağıdaki tabloda değerleri kabul eder:

| Değer | Açıklama |
| ----- |:----------- |
| true | İfade bodied üyeleri oluşturucuları için tercih ettiğiniz |
| when_on_single_line | Tek bir satır olacak zaman ifade bodied üyeleri oluşturucuları için tercih ettiğiniz |
| false | Oluşturucuları bloğunun gövdeleri tercih |

Kod örnekleri:

```csharp
// csharp_style_expression_bodied_constructors = true
public Customer(int age) => Age = age;

// csharp_style_expression_bodied_constructors = false
public Customer(int age) { Age = age; }
```

**csharp\_style\_expression\_bodied_operators**

Bu kural aşağıdaki tabloda değerleri kabul eder:

| Değer | Açıklama |
| ----- |:----------- |
| true | İfade bodied üyeleri işleçleri için tercih ettiğiniz |
| when_on_single_line | Tek bir satır olacak zaman ifade bodied üyeleri işleçleri için tercih ettiğiniz |
| false | Blok gövdeleri işleçlerini tercih |

Kod örnekleri:

```csharp
// csharp_style_expression_bodied_operators = true
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
    => new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);

// csharp_style_expression_bodied_operators = false
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
{ return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary); }
```

**csharp\_style\_expression\_bodied_properties**

Bu kural aşağıdaki tabloda değerleri kabul eder:

| Değer | Açıklama |
| ----- |:----------- |
| true | İfade bodied üyeleri özellikleri için tercih ettiğiniz |
| when_on_single_line | Tek bir satır olacak zaman ifade bodied üyeleri özellikleri için tercih ettiğiniz |
| false | Blok gövdeleri özellikleri için tercih ettiğiniz |

Kod örnekleri:

```csharp
// csharp_style_expression_bodied_properties = true
public int Age => _age;

// csharp_style_expression_bodied_properties = false
public int Age { get { return _age; }}
```

**csharp\_style\_expression\_bodied_indexers**

Bu kural aşağıdaki tabloda değerleri kabul eder:

| Değer | Açıklama |
| ----- |:----------- |
| true | Dizin oluşturucular için ifade bodied üyeleri tercih |
| when_on_single_line | Tek bir satır olacak zaman ifade bodied üyeleri dizin oluşturucular için tercih ettiğiniz |
| false | Dizin oluşturucular için blok gövdeleri tercih |

Kod örnekleri:

```csharp
// csharp_style_expression_bodied_indexers = true
public T this[int i] => _value[i];

// csharp_style_expression_bodied_indexers = false
public T this[int i] { get { return _values[i]; } }
```

**csharp\_style\_expression\_bodied_accessors**

Bu kural aşağıdaki tabloda değerleri kabul eder:

| Değer | Açıklama |
| ----- |:----------- |
| true | İfade bodied üyeleri erişimciler için tercih ettiğiniz |
| when_on_single_line | Tek bir satır olacak zaman ifade bodied üyeleri erişimciler için tercih ettiğiniz |
| false | Erişimcileri bloğu gövdeleri tercih |

Kod örnekleri:

```csharp
// csharp_style_expression_bodied_accessors = true
public int Age { get => _age; set => _age = value; }

// csharp_style_expression_bodied_accessors = false
public int Age { get { return _age; } set { _age = value; } }
```

Örnek .editorconfig dosyası:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_methods = false:none
csharp_style_expression_bodied_constructors = false:none
csharp_style_expression_bodied_operators = false:none
csharp_style_expression_bodied_properties = true:suggestion
csharp_style_expression_bodied_indexers = true:suggestion
csharp_style_expression_bodied_accessors = true:suggestion
```

#### <a name="pattern_matching">Desen eşleştirme</a>

Bu bölümdeki stil kurallarını kullanımını ilgilendiren [desen eşleştirme](/dotnet/csharp/pattern-matching) C#.

Aşağıdaki tabloda, kuralı adları, kural kimlikleri, geçerli dil sürümlerini ve varsayılan değerleri gösterir:

| Kural adı | Kural Kimliği | Geçerli diller | Visual Studio varsayılan |
| --------- | ------- | -------------------- | ----------------------|
| csharp_style_pattern_matching_over_is_with_cast_check | IDE0020 | C# ' TA 7.0 + | true:suggestion |
| csharp_style_pattern_matching_over_as_with_null_check | IDE0019 | C# ' TA 7.0 + | true:suggestion |

**CSharp\_stili\_düzeni\_eşleşen\_üzerinden\_olan\_ile\_cast_check**

- Bu kural ayarlandığında **true**, yerine desen eşleştirme tercih `is` tür atamaları olan ifade.
- Bu kural ayarlandığında **false**, tercih ettiğiniz `is` ifadelerle desen eşleştirme yerine tür atamaları.

Kod örnekleri:

```csharp
// csharp_style_pattern_matching_over_is_with_cast_check = true
if (o is int i) {...}

// csharp_style_pattern_matching_over_is_with_cast_check = false
if (o is int) {var i = (int)o; ... }
```

**CSharp\_stili\_düzeni\_eşleşen\_üzerinden\_olarak\_ile\_null_check**

- Bu kural ayarlandığında **true**, yerine desen eşleştirme tercih `as` bir şey belirli bir tür olup olmadığını belirlemek için null denetimlerinin ifadelerle.
- Bu kural ayarlandığında **false**, tercih ettiğiniz `as` bir şey belirli bir tür olup olmadığını belirlemek için desen eşleştirme yerine null denetimlerinin ifadelerle.

Kod örnekleri:

```csharp
// csharp_style_pattern_matching_over_as_with_null_check = true
if (o is string s) {...}

// csharp_style_pattern_matching_over_as_with_null_check = false
var s = o as string;
if (s != null) {...}
```

Örnek .editorconfig dosyası:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion
```

#### <a name="inlined_variable_declarations">Satır içi değişken bildirimleri</a>

Bu stil kuralı sorunları olup olmadığını `out` değişkenleri, satır içi bildirildiğinde, ya da değil. C# 7'de başlayarak, şunları yapabilirsiniz [yöntem çağrısı bağımsız değişken listesi out bir değişken bildirme](/dotnet/csharp/language-reference/keywords/out-parameter-modifier#calling-a-method-with-an-out-argument), yerine ayrı bir değişken bildirimi.

Kural adı, kural kimliği, geçerli dil sürümlerini ve varsayılan değerleri aşağıdaki tabloda gösterilmektedir:

| Kural adı | Kural Kimliği | Geçerli diller | Visual Studio varsayılan |
| --------- | -------- | -------------------- | ----------------------|
| csharp_style_inlined_variable_declaration | IDE0018 | C# ' TA 7.0 + | true:suggestion |

**csharp\_style\_inlined\_variable_declaration**

- Bu kural ayarlandığında **true**, tercih ettiğiniz `out` satır içi bir yöntem çağrısının mümkün olduğunda bağımsız değişken listesinde bildirilmesi için değişkenleri.
- Bu kural ayarlandığında **false**, tercih ettiğiniz `out` önce yöntem çağrısı bildirilmesi için değişkenleri.

Kod örnekleri:

```csharp
// csharp_style_inlined_variable_declaration = true
if (int.TryParse(value, out int i) {...}

// csharp_style_inlined_variable_declaration = false
int i;
if (int.TryParse(value, out i) {...}
```

Örnek .editorconfig dosyası:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_inlined_variable_declaration = true:suggestion
```

#### <a name="expression_level_csharp">İfade düzeyi tercihleri</a>

Bu bölümdeki stil kurallarını ilgilendiren kullanımı dahil olmak üzere ifade düzeyi Tercihler [varsayılan ifadeleri](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference), deconstructed değişkenleri ve anonim işlevler üzerinden yerel işlevler.

Aşağıdaki tabloda, kural adı, kural kimliği, geçerli dil sürümleri, varsayılan değerleri ve ilk desteklenen Visual Studio sürümünü gösterir:

| Kural adı | Kural Kimliği | Geçerli diller | Visual Studio varsayılan | Visual Studio 2017 sürümü |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_prefer_simple_default_expression | IDE0034 | C# 7.1+ | true:suggestion | 15.3 |
| csharp_style_deconstructed_variable_declaration | IDE0042 | C# ' TA 7.0 + | true:suggestion | 15.5 |
| csharp_style_pattern_local_over_anonymous_function | IDE0039 | C# ' TA 7.0 + | true:suggestion | 15.5 |

**csharp\_prefer\_simple\_default_expression**

Bu stil kuralı kullanarak işlemiyle ilgili [ `default` varsayılan değeri ifadeleri için değişmez değerin](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference) zaman derleyici Infer ifade türü.

- Bu kural ayarlandığında **true**, tercih ettiğiniz `default` üzerinden `default(T)`.
- Bu kural ayarlandığında **false**, tercih ettiğiniz `default(T)` üzerinden `default`.

Kod örnekleri:

```csharp
// csharp_prefer_simple_default_expression = true
void DoWork(CancellationToken cancellationToken = default) { ... }

// csharp_prefer_simple_default_expression = false
void DoWork(CancellationToken cancellationToken = default(CancellationToken)) { ... }
```

**csharp\_style\_deconstructed\_variable_declaration**

- Bu kural ayarlandığında **doğru**, deconstructed değişken bildirimi tercih eder.
- Bu kural ayarlandığında **yanlış**, değişken bildirimleri deconstruction tercih ediyorsunuz.

Kod örnekleri:

```csharp
// csharp_style_deconstructed_variable_declaration = true
var (name, age) = GetPersonTuple();
Console.WriteLine($"{name} {age}");

(int x, int y) = GetPointTuple();
Console.WriteLine($"{x} {y}");

// csharp_style_deconstructed_variable_declaration = false
var person = GetPersonTuple();
Console.WriteLine($"{person.name} {person.age}");

(int x, int y) point = GetPointTuple();
Console.WriteLine($"{point.x} {point.y}");
```

**CSharp\_stili\_düzeni\_yerel\_üzerinden\_anonymous_function**

- Bu kural ayarlandığında **doğru**, yerel işlevler anonim işlevler tercih eder.
- Bu kural ayarlandığında **yanlış**, anonim işlevler yerel işlevler tercih eder.

Kod örnekleri:

```csharp
// csharp_style_pattern_local_over_anonymous_function = true
int fibonacci(int n)
{
    return n <= 1 ? 1 : fibonacci(n-1) + fibonacci(n-2);
}

// csharp_style_pattern_local_over_anonymous_function = false
Func<int, int> fibonacci = null;
fibonacci = (int n) =>
{
    return n <= 1 ? 1 : fibonacci(n - 1) + fibonacci(n - 2);
};
```

Örnek .editorconfig dosyası:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_prefer_simple_default_expression = true:suggestion
csharp_style_deconstructed_variable_declaration = true:suggestion
csharp_style_pattern_local_over_anonymous_function = true:suggestion
```

#### <a name="null_checking_csharp">"Null" Tercihler denetleniyor</a>

Bu kurallar sorunu çevresinde sözdizimi stil `null` denetimi, kullanımı dahil olmak üzere `throw` ifadeler veya `throw` deyimleri ve null denetimi gerçekleştirmek veya koşullu birleştirmesi işlecini kullanın (`?.`) bir çağrılırken,[lambda ifadesi](/dotnet/csharp/lambda-expressions).

Aşağıdaki tabloda, kuralı adları, kural kimlikleri, geçerli dil sürümlerini ve varsayılan değerleri gösterir:

| Kural adı | Kural Kimliği | Geçerli diller | Visual Studio varsayılan |
| --------- | ------- | -------------------- | ----------------------|
| csharp_style_throw_expression | IDE0016 | C# ' TA 7.0 + | true:suggestion |
| csharp_style_conditional_delegate_call | IDE0041 | C# 6.0+ | true:suggestion |

**csharp\_style\_throw_expression**

- Bu kural ayarlandığında **true**, kullanmayı tercih `throw` yerine ifadeleri `throw` deyimleri.
- Bu kural ayarlandığında **false**, kullanmayı tercih `throw` deyimleri yerine `throw` ifadeler.

Kod örnekleri:

```csharp
// csharp_style_throw_expression = true
this.s = s ?? throw new ArgumentNullException(nameof(s));

// csharp_style_throw_expression = false
if (s == null) { throw new ArgumentNullException(nameof(s)); }
this.s = s;
```

**csharp\_style\_conditional\_delegate_call**

- Bu kural ayarlandığında **true**, koşullu birleştirmesi işleci kullanmayı tercih ederseniz (`?.`) bir lambda ifadesi çağrılırken null gerçekleştirmek yerine denetleyin.
- Bu kural ayarlandığında **false**, koşullu birleştirmesi işleci kullanmak yerine bir lambda ifadesi çağırmadan önce null denetimi gerçekleştirmek tercih ettiğiniz (`?.`).

Kod örnekleri:

```csharp
// csharp_style_conditional_delegate_call = true
func?.Invoke(args);

// csharp_style_conditional_delegate_call = false
if (func != null) { func(args); }
```

Örnek .editorconfig dosyası:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_throw_expression = true:suggestion
csharp_style_conditional_delegate_call = false:suggestion
```

#### <a name="code_block">Kod bloğu tercihleri</a>

Bu stil kuralı süslü ayraçlar kullanılmasını işlemiyle ilgili `{ }` kod blokları surround için.

Aşağıdaki tabloda, kural adı, kural kimliği, geçerli dil sürümleri, varsayılan değerleri ve ilk desteklenen Visual Studio sürümünü gösterir:

| Kural adı | Kural Kimliği | Geçerli diller | Visual Studio varsayılan | Visual Studio 2017 sürümü |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_prefer_braces | IDE0011 | C# | true:none | 15.3 |

**CSharp\_tercih\_küme ayraçları**

- Bu kural ayarlandığında **doğru**, bir kod satırı için bile süslü ayraçlar tercih eder.
- Bu kural ayarlandığında **yanlış**, hiçbir süslü ayraçlar izin veriyorsa tercih.

Kod örnekleri:

```csharp
// csharp_prefer_braces = true
if (test) { this.Display(); }

// csharp_prefer_braces = false
if (test) this.Display();
```

Örnek .editorconfig dosyası:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_prefer_braces = true:none
```

## <a name="formatting-conventions"></a>Biçimlendirme kuralları

Çoğu kuralları biçimlendirme kuralları, aşağıdaki biçime sahiptir:

`rule_name = false|true`

Ya da belirttiğiniz **true** (Bu stili tercih et) veya **false** (Bu stili tercih ediyorsunuz). Bir önem derecesi belirtmeyin. True veya false, yerine birkaç kuralları için kuralı uygulamak nerede ve ne zaman açıklamak için diğer değerleri belirtin.

Aşağıdaki listede, Visual Studio'da kullanılabilir biçimlendirme kuralı kurallar gösterilmektedir:

- .NET biçimlendirme ayarları
    - [Using'leri düzenleme](#usings)
        - dotnet_sort_system_directives_first
- C# ayarları biçimlendirme
    - [Yeni satır seçenekleri](#newline)
        - csharp_new_line_before_open_brace
        - csharp_new_line_before_else
        - csharp_new_line_before_catch
        - csharp_new_line_before_finally
        - csharp_new_line_before_members_in_object_initializers
        - csharp_new_line_before_members_in_anonymous_types
        - csharp_new_line_between_query_expression_clauses
    - [Girinti seçenekleri](#indent)
        - csharp_indent_case_contents
        - csharp_indent_switch_labels
        - csharp_indent_labels
    - [Aralık Seçenekleri](#spacing)
        - csharp_space_after_cast
        - csharp_space_after_keywords_in_control_flow_statements
        - csharp_space_between_method_declaration_parameter_list_parentheses
        - csharp_space_between_method_call_parameter_list_parentheses
        - csharp_space_between_parentheses
    - [Kaydırma seçenekleri](#wrapping)
        - csharp_preserve_single_line_statements
        - csharp_preserve_single_line_blocks

### <a name="net-formatting-settings"></a>.NET biçimlendirme ayarları

Bu bölümdeki biçimlendirme kuralları, C# ve Visual Basic için geçerlidir.

#### <a name="usings">Using'leri düzenleme</a>

Biçimlendirme kuralın diğer göre yönergeleri kullanarak System.* yerleşimini işlemiyle ilgili yönergeleri kullanarak.

Aşağıdaki tabloda, kural adı, geçerli diller, varsayılan değer ve ilk desteklenen Visual Studio sürümünü gösterir:

| Kural adı | Geçerli diller | Visual Studio varsayılan | Visual Studio 2017 sürümü |
| ----------- | -------------------- | ----------------------| ----------------  |
| dotnet_sort_system_directives_first |  C# ve Visual Basic | true | 15.3  |

**dotnet\_sort\_system\_directives_first**

- Bu kural ayarlandığında **true**System.* using yönergelerini alfabetik olarak sıralamak ve diğer kullanımları önce yerleştirin.
- Bu kural ayarlandığında **yanlış**, önce diğer yönergeleri kullanarak System.* yerleştirmeyin yönergeleri kullanarak.

Kod örnekleri:

```csharp
// dotnet_sort_system_directives_first = true
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;

// dotnet_sort_system_directives_first = false
using System.Collections.Generic;
using Octokit;
using System.Threading.Tasks;
```

Örnek .editorconfig dosyası:

```EditorConfig
# .NET formatting settings:
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
```

### <a name="c-formatting-settings"></a>C# biçimlendirme ayarları

Bu bölümdeki biçimlendirme kuralları yalnızca C# kod için geçerlidir.

#### <a name="newline">Yeni satır seçenekleri</a>

Bu biçimlendirme kuralları kodunu biçimlendirmek için yeni satır kullanımını ilgilendiren.

Aşağıdaki tabloda "yeni satır" kuralı adları gösterir. geçerli diller, varsayılan değerler ve Visual Studio sürümü ilk desteklenen:

| Kural adı | Geçerli diller | Visual Studio varsayılan | Visual Studio 2017 sürümü |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_new_line_before_open_brace |  C# | tüm | 15.3  |
| csharp_new_line_before_else |  C# | true | 15.3  |
| csharp_new_line_before_catch |  C# | true | 15.3  |
| csharp_new_line_before_finally |  C# | true | 15.3  |
| csharp_new_line_before_members_in_object_initializers |  C# | true | 15.3  |
| csharp_new_line_before_members_in_anonymous_types |  C# | true | 15.3  |
| csharp_new_line_between_query_expression_clauses |  C# | true | 15.3  |

**CSharp\_yeni\_satır\_önce\_open_brace**

Bu kural bir açma ayracı olup olmadığını ilgiliyse `{` önceki kod aynı satır veya yeni bir satır yerleştirilmelidir. Bu kural için belirtmezseniz **true** veya **false**. Bunun yerine, belirttiğiniz **tüm**, **hiçbiri**, veya bir veya daha fazla öğe gibi code **yöntemleri** veya **özellikleri**, bu kuralın ne zaman çalıştırılması tanımlamak için uygulanır. İzin verilen değerlerin tam listesi aşağıdaki tabloda gösterilmiştir:

| Değer | Açıklama
| ------------- |:-------------|
| erişimciler, anonymous_methods, anonymous_types, control_blocks, olaylar, dizin oluşturucular, Lambda'lar, local_functions, yöntemleri, object_collection, özellikler, türleri.<br>(İle birden çok tür için ayrı ','). | Küme parantezleri ("Allman" stil olarak da bilinir) belirtilen kod öğeleri için yeni bir satır üzerinde olmasını gerektirir |
| tüm | Küme ayraçları tüm ifadeler ("Allman" stil) için yeni bir satır üzerinde olmasını gerektirir |
| yok | Küme parantezleri ("K & R") tüm ifadeleri için aynı satır üzerinde olmasını gerektirir |

Kod örnekleri:

```csharp
// csharp_new_line_before_open_brace = all
void MyMethod()
{
    if (...)
    {
        ...
    }
}

// csharp_new_line_before_open_brace = none
void MyMethod() {
    if (...) {
        ...
    }
}
```

**csharp\_new\_line\_before_else**

- Bu kural ayarlandığında **true**, yerleştirin `else` yeni bir satıra deyimleri.
- Bu kural ayarlandığında **false**, yerleştirin `else` aynı satırda deyimleri.

Kod örnekleri:

```csharp
// csharp_new_line_before_else = true
if (...) {
    ...
}
else {
    ...
}

// csharp_new_line_before_else = false
if (...) {
    ...
} else {
    ...
}
```

**csharp\_new\_line\_before_catch**

- Bu kural ayarlandığında **true**, yerleştirin `catch` yeni bir satıra deyimleri.
- Bu kural ayarlandığında **false**, yerleştirin `catch` aynı satırda deyimleri.

Kod örnekleri:

```csharp
// csharp_new_line_before_catch = true
try {
    ...
}
catch (Exception e) {
    ...
}

// csharp_new_line_before_catch = false
try {
    ...
} catch (Exception e) {
    ...
}
```

**CSharp\_yeni\_satır\_before_finally**

- Bu kural ayarlandığında **true**, gerektiren `finally` deyimleri kapanış ayracı sonra yeni bir satırda olmalıdır.
- Bu kural ayarlandığında **false**, gerektiren `finally` deyimleri kapatılan parantez ile aynı satırda olmalıdır.

Kod örnekleri:

```csharp
// csharp_new_line_before_finally = true
try {
    ...
}
catch (Exception e) {
    ...
}
finally {
    ...
}

// csharp_new_line_before_finally = false
try {
    ...
} catch (Exception e) {
    ...
} finally {
    ...
}
```

**CSharp\_yeni\_satır\_önce\_üyeleri\_içinde\_object_initializers**

- Bu kural ayarlandığında **doğru**, ayrı satırlara olmasını nesne intiializers üyeleri gerektirir.
- Bu kural ayarlandığında **yanlış**, aynı çizgi üzerinde olmasını nesne başlatıcıları üyeleri gerektirir.

Kod örnekleri:

```csharp
// csharp_new_line_before_members_in_object_initializers = true
var z = new B()
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_object_initializers = false
var z = new B()
{
    A = 3, B = 4
}
```

**CSharp\_yeni\_satır\_önce\_üyeleri\_içinde\_anonymous_types**

- Bu kural ayarlandığında **doğru**, ayrı satırlara olmasını anonim türdeki üye gerektirir.
- Bu kural ayarlandığında **yanlış**, aynı çizgi üzerinde olmasını anonim türdeki üye gerektirir.

Kod örnekleri:

```csharp
// csharp_new_line_before_members_in_anonymous_types = true
var z = new
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_anonymous_types = false
var z = new
{
    A = 3, B = 4
}
```

**csharp_new_line_between_query_expression_clauses**

- Bu kural ayarlandığında **doğru**, ayrı satırlara olması için sorgu ifadesi yan tümceleri öğeleri gerektirir.
- Bu kural ayarlandığında **yanlış**, aynı çizgi üzerinde olacak şekilde sorgu ifadesi yan tümceleri öğeleri gerektirir.

Kod örnekleri:

```csharp
// csharp_new_line_between_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;

// csharp_new_line_between_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

Örnek .editorconfig dosyası:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_new_line_before_open_brace = methods, properties, control_blocks, types
csharp_new_line_before_else = true
csharp_new_line_before_catch = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_between_query_expression_clauses = true
```

#### <a name="indent">Girinti seçenekleri</a>

Bu biçimlendirme kuralları biçim kodu girinti kullanımını ilgilendiren.

Aşağıdaki tabloda, kural adı, geçerli diller, varsayılan değerleri ve ilk desteklenen Visual Studio sürümünü gösterir:

| Kural adı | Geçerli diller | Visual Studio varsayılan | Visual Studio 2017 sürümü |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_indent_case_contents |  C# | true | 15.3  |
| csharp_indent_switch_labels |  C# | true | 15.3  |
| csharp_indent_labels |  C# | no_change | 15.3  |

**csharp\_indent\_case_contents**

- Bu kural ayarlandığında **true**, girinti `switch` durumda içeriği.
- Bu kural ayarlandığında **false**, değil girinti `switch` durumda içeriği.

Kod örnekleri:

```csharp
// csharp_indent_case_contents = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_case_contents = false
switch(c) {
    case Color.Red:
    Console.WriteLine("The color is red");
    break;
    case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
    default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

**CSharp\_girinti\_switch_labels**

- Bu kural ayarlandığında **true**, girinti `switch` etiketler.
- Bu kural ayarlandığında **false**, değil girinti `switch` etiketler.

Kod örnekleri:

```csharp
// csharp_indent_switch_labels = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_switch_labels = false
switch(c) {
case Color.Red:
    Console.WriteLine("The color is red");
    break;
case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

**CSharp\_indent_labels**

Bu kural kabul etmediği bir **true** veya **yanlış** değeri; bunun yerine aşağıdaki tablodan bir değer olarak kabul eder:

| Değer | Açıklama |
| ----- |:----------- |
| flush_left | Soldaki sütun etiketleri yerleştirilir |
| one_less_than_current | Etiketler tek tek geçerli bağlam için daha az girinti yerleştirilir |
| no_change | Etiketleri aynı girinti geçerli bağlamı olarak yerleştirilmiş |

Kod örnekleri:

```csharp
// csharp_indent_labels= flush_left
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
error:
        throw new Exception(...);
    }
}

// csharp_indent_labels = one_less_than_current
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
    error:
        throw new Exception(...);
    }
}

// csharp_indent_labels= no_change
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
        error:
        throw new Exception(...);
    }
}
```

Örnek .editorconfig dosyası:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_labels = flush_left
```

#### <a name="spacing">Aralık Seçenekleri</a>

Bu biçimlendirme kuralları kodunu biçimlendirmek için boşluk karakterleri kullanımını ilgilendiren.

Aşağıdaki tabloda, kural adı, geçerli diller, varsayılan değerleri ve ilk desteklenen Visual Studio sürümünü gösterir:

| Kural adı | Geçerli diller | Visual Studio varsayılan | Visual Studio 2017 sürümü |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_space_after_cast |  C# | false | 15.3  |
| csharp_space_after_keywords_in_control_flow_statements |  C# | true | 15.3  |
| csharp_space_between_method_declaration_parameter_list_parentheses |  C# | false | 15.3  |
| csharp_space_between_method_call_parameter_list_parentheses |  C# | false | 15.3  |
| csharp_space_between_parentheses |  C# | false | 15.3  |

**csharp\_space\_after_cast**

- Bu kural ayarlandığında **doğru**, bir cast ve değer arasında bir alan gerektirir.
- Bu kural ayarlandığında **false**, gerektiren _hiçbir_ dönüştürme ve değer arasında boşluk.

Kod örnekleri:

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

**csharp_space_after_keywords_in_control_flow_statements**

- Bu kural ayarlandığında **true**, gibi bir alan anahtar sözcüğü bir denetim akışı deyiminde sonra gereken bir `for` döngü.
- Bu kural ayarlandığında **false**, gerektiren _hiçbir_ anahtar sözcüğü bir denetim akışı deyiminde sonra gibi boşluk bir `for` döngü.

Kod örnekleri:

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

**csharp_space_between_method_declaration_parameter_list_parentheses**

- Bu kural ayarlandığında **doğru**, açma parantezi sonra ve kapanış parantezi yöntemi bildirimi parametre listesini önce bir boşluk karakteri yerleştirin.
- Bu kural ayarlandığında **yanlış**, boşluk karakterleri parantez sonra ve kapanış parantezi yöntemi bildirimi parametre listesini önce yerleştirmeyin.

Kod örnekleri:

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

**csharp_space_between_method_call_parameter_list_parentheses**

- Bu kural ayarlandığında **doğru**, açma parantezi sonra ve bir yöntem çağrısının kapanış parantezi önce bir boşluk karakteri yerleştirin.
- Bu kural ayarlandığında **yanlış**, boşluk karakterleri parantez sonra ve bir yöntem çağrısının kapanış parantezi önce yerleştirmeyin.

Kod örnekleri:

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

**csharp_space_between_parentheses**

Bu kural aşağıdaki tablodan bir veya daha fazla değerleri kabul eder:

| Değer | Açıklama |
| ----- |:------------|
| control_flow_statements | Denetim akışı deyimlerinin ayraçlar arasında yer alan |
| ifadeler | İfadelerin ayraçlar arasında yer alan |
| type_casts | Tür atamaları parantezlerde arasında yer alan |

Bu kuralı atla veya başka bir değer kullanmak `control_flow_statements`, `expressions`, veya `type_casts`, ayar uygulanmaz.

Kod örnekleri:

```csharp
// csharp_space_between_parentheses = control_flow_statements
for ( int i = 0; i < 10; i++ ) { }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3 );

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

Örnek .editorconfig dosyası:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_space_after_cast = true
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_method_declaration_parameter_list_parentheses = true
csharp_space_between_method_call_parameter_list_parentheses = true
csharp_space_between_parentheses = control_flow_statements, type_casts
```

#### <a name="wrapping">Kaydırma seçenekleri</a>

Bu biçimlendirme kuralları deyimleri ve kod blokları için ayrı satırlara karşı tek satırları kullanımını ilgilendiren.

Aşağıdaki tabloda, kural adı, geçerli diller, varsayılan değerleri ve ilk desteklenen Visual Studio sürümünü gösterir:

| Kural adı | Geçerli diller | Visual Studio varsayılan | Visual Studio 2017 sürümü |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_preserve_single_line_statements |  C# | true | 15.3  |
| csharp_preserve_single_line_blocks |  C# | true | 15.3  |

**csharp_preserve_single_line_statements**

- Bu kural ayarlandığında **doğru**, ifadeler ve üye bildirimleri aynı çizgi üzerinde bırakın.
- Bu kural ayarlandığında **yanlış**, ifadeler ve üye bildirimleri farklı satırlarına bırakın.

Kod örnekleri:

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

**csharp_preserve_single_line_blocks**

- Bu kural ayarlandığında **doğru**, tek bir satırda kod bloğu bırakın.
- Bu kural ayarlandığında **yanlış**, kod bloğunun ayrı satırlara bırakın.

Kod örnekleri:

```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }

//csharp_preserve_single_line_blocks = false
public int MyProperty
{
    get; set;
}
```

Örnek .editorconfig dosyası:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

## <a name="see-also"></a>Ayrıca bkz.

- [Hızlı Eylemler](../ide/quick-actions.md)
- [.NET EditorConfig için adlandırma kuralları](../ide/editorconfig-naming-conventions.md)
- [Taşınabilir özel düzenleyici seçenekleri oluşturma](../ide/create-portable-custom-editor-options.md)
- [.NET derleme platformun .editorconfig dosyası](https://github.com/dotnet/roslyn/blob/master/.editorconfig)
