---
title: 教程：创建类型提供程序
description: 通过检查几个简单类型提供程序来说明基本概念，了解如何在 F# 3.0 中创建自己的 F# 类型提供程序。
ms.date: 11/04/2019
ms.openlocfilehash: 3b8145d4c2d8bf96b6dcf66de02e9f2d83927d74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186122"
---
# <a name="tutorial-create-a-type-provider"></a>教程：创建类型提供程序

F# 中的类型提供程序机制是其支持信息丰富编程的重要组成部分。 本教程介绍如何通过引导您完成几个简单类型提供程序的开发来说明基本概念，从而创建自己的类型提供程序。 有关 F# 中的类型提供程序机制的详细信息，请参阅[类型提供程序](index.md)。

F# 生态系统包含一系列用于常用 Internet 和企业数据服务的类型提供程序。 例如：

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/)包括 JSON、XML、CSV 和 HTML 文档格式的类型提供程序。

- [SQLProvider](https://fsprojects.github.io/SQLProvider/)通过对象映射和针对这些数据源的 F# LINQ 查询提供对 SQL 数据库的强类型访问。

- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/)具有一组类型提供程序，用于在 F# 中编译时检查的 T-SQL 嵌入。

- [FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/)是一组较旧的类型提供程序，仅用于 .NET 框架编程，用于访问 SQL、实体框架、OData 和 WSDL 数据服务。

必要时，您可以创建自定义类型提供程序，也可以引用其他人创建的类型提供程序。 例如，您的组织可以有一个数据服务，该服务提供大量且不断增加的命名数据集，每个数据集都有自己的稳定数据架构。 您可以创建一个类型提供程序，用于读取架构，并以强类型方式向程序员显示当前数据集。

## <a name="before-you-start"></a>开始之前

类型提供程序机制主要用于将稳定的数据和服务信息空间注入 F# 编程体验。

此机制不是为注入信息空间而设计的，其架构在程序执行期间以与程序逻辑相关的方式更改。 此外，该机制不是为语言内部元编程而设计的，即使该域包含一些有效的用途。 仅当必要且类型提供程序的开发产生非常高的值时，才应使用此机制。

应避免编写架构不可用的类型提供程序。 同样，应避免编写普通（甚至现有）.NET 库就足够了的类型提供程序。

在开始之前，您可能会提出以下问题：

- 您是否有信息源的架构？ 如果是，则什么是映射到 F# 和 .NET 类型系统？

- 能否使用现有（动态类型）API 作为实现的起点？

- 您和您的组织是否有足够的类型提供程序的使用来使编写它是值得的？ 普通的 .NET 库能满足您的需求吗？

- 架构将更改多少？

- 在编码过程中会发生变化吗？

- 它会在编码会话之间更改吗？

- 在程序执行期间会更改吗？

类型提供程序最适合在运行时和编译代码的生存期内架构稳定的情况。

## <a name="a-simple-type-provider"></a>简单类型提供程序

此示例是示例。HelloWorldTypeProvider，类似于`examples`[F# 类型提供程序 SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/)目录中的示例。 提供程序提供包含 100 种擦除类型的"类型空间"，如下代码通过使用 F# 签名语法和省略除 之外`Type1`的所有代码的详细信息来显示的。 有关擦除类型的详细信息，请参阅本主题后面的[有关已擦除提供类型的详细信息](#details-about-erased-provided-types)。

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    nested type NestedType =
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

请注意，提供的类型和成员集是静态已知的。 此示例不利用提供程序提供依赖于架构的类型的能力。 类型提供程序的实现在以下代码中概述，本主题的后续部分将介绍详细信息。

> [!WARNING]
> 此代码和联机示例之间可能存在差异。

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open ProviderImplementation.ProvidedTypes
open FSharp.Core.CompilerServices
open FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =

  // Inheriting from this type provides implementations of ITypeProvider
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces(config)

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) =
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

[<assembly:TypeProviderAssembly>]
do()
```

要使用此提供程序，请打开 Visual Studio 的单独实例，创建 F# 脚本，然后使用#r添加对提供程序的引用，如以下代码所示：

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

然后查找类型提供程序生成的`Samples.HelloWorldTypeProvider`命名空间下的类型。

在重新编译提供程序之前，请确保已关闭使用提供程序 DLL 的所有 Visual Studio 和 F# 交互式实例。 否则，将发生生成错误，因为输出 DLL 将被锁定。

要使用打印语句调试此提供程序，请制作一个显示提供程序问题的脚本，然后使用以下代码：

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

要使用 Visual Studio 调试此提供程序，请使用管理凭据打开 Visual Studio 的开发人员命令提示符，并运行以下命令：

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

作为替代，打开 Visual Studio，打开调试菜单，选择`Debug/Attach to process…`，并附加到编辑`devenv`脚本的其他进程。 通过使用此方法，您可以通过将表达式交互地键入第二个实例（具有完整的 IntelliSense 和其他功能）来更轻松地定位类型提供程序中的特定逻辑。

您可以禁用"仅我的代码"调试，以便更好地识别生成的代码中的错误。 有关如何启用或禁用此功能的信息，请参阅[使用调试器 通过代码导航](/visualstudio/debugger/navigating-through-code-with-the-debugger)。 此外，您还可以通过打开`Debug`菜单，然后选择或选择`Exceptions`Ctrl_Alt_E 键来打开`Exceptions`对话框来设置第一次异常捕获。 在该对话框中，在`Common Language Runtime Exceptions`下，`Thrown`选择复选框。

### <a name="implementation-of-the-type-provider"></a>类型提供程序的实现

本节将介绍类型提供程序实现的主要部分。 首先，定义自定义类型提供程序本身的类型：

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

此类型必须是公共的，并且必须使用[TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947)属性标记它，以便编译器在单独的 F# 项目引用包含该类型的程序集时识别类型提供程序。 *配置*参数是可选的，如果存在，则包含 F# 编译器创建的类型提供程序实例的上下文配置信息。

接下来，实现[ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f)接口。 在这种情况下，您将 API`TypeProviderForNamespaces`中的`ProvidedTypes`类型用作基本类型。 此帮助器类型可以提供热切提供的命名空间的有限集合，每个命名空间都直接包含有限数量的固定、热切提供的类型。 在此上下文中，提供程序*热切地*生成类型，即使它们不需要或使用。

```fsharp
inherit TypeProviderForNamespaces(config)
```

接下来，定义指定提供类型的命名空间的本地私有值，并查找类型提供程序程序集本身。 稍后，此程序集用作提供的擦除类型的逻辑父类型。

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

接下来，创建一个函数来提供 Type1...类型 100。 本主题稍后将更详细地介绍此功能。

```fsharp
let makeOneProvidedType (n:int) = …
```

接下来，生成 100 个提供的类型：

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

接下来，将类型添加为提供的命名空间：

```fsharp
do this.AddNamespace(namespaceName, types)
```

最后，添加一个程序集属性，指示要创建类型提供程序 DLL：

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a>提供一种类型及其成员

函数`makeOneProvidedType`执行提供其中一种类型的实际工作。

```fsharp
let makeOneProvidedType (n:int) =
…
```

此步骤解释了此函数的实现。 首先，创建提供的类型（例如，类型 1，当 n = 1 时，或 Type57，当 n = 57）。

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

您应该注意以下几点：

- 此提供的类型将被删除。  由于您指示基类型为`obj`，因此实例将在编译代码中显示为[obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7)类型的值。

- 指定非嵌套类型时，必须指定程序集和命名空间。 对于擦除的类型，程序集应是类型提供程序程序集本身。

接下来，将 XML 文档添加到类型中。 本文档延迟，即，如果主机编译器需要，则按需计算。

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

接下来，向类型添加提供的静态属性：

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

获取此属性将始终评估到字符串"你好！ 属性`GetterCode`使用 F# 引号，它表示主机编译器为获取该属性而生成的代码。 有关报价单的详细信息，请参阅[代码报价 （F#）。](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155)

将 XML 文档添加到属性。

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

现在，将提供的属性附加到提供的类型。 您必须将提供的成员附加到一种和仅一种类型。 否则，该成员将永远无法访问。

```fsharp
t.AddMember staticProp
```

现在创建一个不需要参数的提供的构造函数。

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

构造`InvokeCode`函数返回一个 F# 引号，它表示在调用构造函数时主机编译器生成的代码。 例如，可以使用以下构造函数：

```fsharp
new Type10()
```

使用基础数据"对象数据"创建提供的类型的实例。 引号代码包括转换为[obj，](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7)因为该类型是此提供类型的擦除（如您声明提供的类型时指定的）。

将 XML 文档添加到构造函数，并将提供的构造函数添加到提供的类型：

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

创建第二个提供的构造函数，该构造函数采用一个参数：

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

构造`InvokeCode`函数的 引号再次返回一个 F# 引号，它表示主机编译器为调用 方法生成的代码。 例如，可以使用以下构造函数：

```fsharp
new Type10("ten")
```

使用基础数据"10"创建提供的类型的实例。 您可能已经注意到函数`InvokeCode`返回引号。 此函数的输入是表达式列表，每个构造函数参数一个。 在这种情况下，表示单个参数值的表达式在 中`args.[0]`可用。 调用构造函数的代码强制返回值到擦除的类型`obj`。 将第二个提供的构造函数添加到类型后，将创建一个提供的实例属性：

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

获取此属性将返回字符串的长度，该长度是表示对象。 该`GetterCode`属性返回一个 F# 引号，该引号指定主机编译器为获取该属性而生成的代码。 与`InvokeCode`一`GetterCode`样，函数返回引号。 主机编译器使用参数列表调用此函数。 在这种情况下，参数仅包括表示调用 getter 的实例的单个表达式，您可以使用 访问 该表达式`args.[0]`。 `GetterCode`然后在擦除类型`obj`中拼接到结果引号中的实现，以及强制转换用于满足编译器检查对象是字符串的类型的机制。 的下`makeOneProvidedType`一部分提供了一个实例方法，其中有一个参数。

```fsharp
let instanceMeth =
    ProvidedMethod(methodName = "InstanceMethod",
                   parameters = [ProvidedParameter("x",typeof<int>)],
                   returnType = typeof<char>,
                   invokeCode = (fun args ->
                       <@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

最后，创建包含 100 个嵌套属性的嵌套类型。 此嵌套类型的创建及其属性延迟，即按需计算。

```fsharp
t.AddMembersDelayed(fun () ->
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () ->
    let staticPropsInNestedType =
      [
          for i in 1 .. 100 ->
              let valueOfTheProperty = "I am string "  + string i

              let p =
                ProvidedProperty(propertyName = "StaticProperty" + string i,
                  propertyType = typeof<string>,
                  isStatic = true,
                  getterCode= (fun args -> <@@ valueOfTheProperty @@>))

              p.AddXmlDocDelayed(fun () ->
                  sprintf "This is StaticProperty%d on NestedType" i)

              p
      ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a>有关已擦除提供的类型的详细信息

本节中的示例仅提供*擦除的提供类型*，这些类型在以下情况下特别有用：

- 为仅包含数据和方法的信息空间编写提供程序时。

- 编写提供程序时，准确运行时类型的语义对于实际使用信息空间并不重要。

- 当您为信息空间编写提供程序时，该提供程序非常大且相互关联，因此在技术上为信息空间生成真正的 .NET 类型是不可行的。

在此示例中，每个提供的类型将擦除为类型`obj`，并且该类型的所有用途都将在编译的代码中显示为类型`obj`。 事实上，这些示例中的基础对象是字符串，但类型将显示为`System.Object`.NET 编译代码中。 与类型擦除的所有用途一样，您可以使用显式装箱、取消装箱和强制转换来颠覆擦除的类型。 在这种情况下，当使用对象时，可能会出现无效的强制转换异常。 提供程序运行时可以定义其自己的私有表示类型，以帮助防止虚假陈述。 不能在 F# 本身中定义已擦除的类型。 只能擦除提供的类型。 您必须了解为类型提供程序或提供擦除类型的提供程序使用擦除类型的后果（无论是实际的还是语义的）。 擦除的类型没有实际的 .NET 类型。 因此，您不能对类型进行准确反射，如果使用运行时强制转换和其他依赖于精确运行时类型语义的技术，则可能会颠覆擦除的类型。 擦除类型的颠覆经常导致运行时的类型强制异常。

### <a name="choosing-representations-for-erased-provided-types"></a>为已擦除的提供类型选择表示形式

对于已擦除提供的类型的某些用途，不需要表示形式。 例如，擦除的提供类型可能仅包含静态属性和成员，并且不包含构造函数，并且任何方法或属性都无法返回类型的实例。 如果可以到达已擦除提供的类型的实例，则必须考虑以下问题：

**提供类型的擦除是什么？**

- 提供类型的擦除是该类型在编译的 .NET 代码中的显示方式。

- 提供的擦除类类型的擦除始终是类型继承链中的第一个未擦除基类型。

- 提供的擦除接口类型的擦除始终`System.Object`为 。

**提供的类型的表示形式是什么？**

- 擦除提供的类型的可能对象的集称为其表示形式。 在本文档中的示例中，所有擦除提供的类型的`Type1..Type100`表示形式始终是字符串对象。

提供类型的所有表示形式必须与提供的类型的擦除兼容。 （否则，F# 编译器将给出使用类型提供程序的错误，或者将生成无效的不可验证的 .NET 代码。 如果类型提供程序返回的代码给出无效的表示形式，则该类型提供程序无效。）

可以使用以下任一方法为提供的对象选择表示形式，这两种方法都很常见：

- 如果只是在现有 .NET 类型上提供强类型包装，则类型通常可以擦除到该类型，使用该类型的实例作为表示，或者两者兼而有之。 当使用强类型版本时，该类型上的大多数现有方法仍然有意义时，此方法是合适的。

- 如果要创建与任何现有 .NET API 有显著差异的 API，则创建运行时类型是提供的类型擦除和表示形式，这是有道理的。

本文档中的示例使用字符串作为提供对象的表示形式。 通常，使用其他对象进行表示可能很合适。 例如，您可以将字典用作属性包：

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

作为替代方法，您可以在类型提供程序中定义将在运行时用于形成表示的类型以及一个或多个运行时操作：

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

然后，如果成员可以构造此对象类型的实例：

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

在这种情况下，您可以（有选择地）在构造 时`baseType``ProvidedTypeDefinition`将此类型指定为

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>重点课程

上一节介绍了如何创建一个简单的解排类型提供程序，该提供程序提供一系列类型、属性和方法。 本节还解释了类型擦除的概念，包括从类型提供程序提供擦除类型的一些优点和缺点，并讨论了擦除类型的表示形式。

## <a name="a-type-provider-that-uses-static-parameters"></a>使用静态参数的类型提供程序

通过静态数据对类型提供程序进行参数化的能力支持许多有趣的方案，即使提供程序不需要访问任何本地或远程数据也是如此。 在本节中，您将学习一些组合此类提供程序的基本技术。

### <a name="type-checked-regex-provider"></a>键入已检查的正则表达式提供程序

假设您要为正则表达式实现类型提供程序，该正则表达式在提供以下编译时间<xref:System.Text.RegularExpressions.Regex>保证的接口中包装 .NET 库：

- 验证正则表达式是否有效。

- 在基于正则表达式中的任何组名称的匹配项上提供命名属性。

本节介绍如何使用类型提供程序创建`RegexTyped`正则表达式模式参数化的类型以提供这些好处。 如果提供的模式无效，编译器将报告错误，并且类型提供程序可以从模式中提取组，以便可以使用匹配上的命名属性访问这些组。 在设计类型提供程序时，应考虑其公开的 API 应如何查看最终用户，以及此设计将如何转换为 .NET 代码。 下面的示例演示如何使用此类 API 获取区号组件：

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

下面的示例显示了类型提供程序如何转换这些调用：

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

请注意以下几点：

- 标准 Regex 类型表示参数化`RegexTyped`类型。

- 构造`RegexTyped`函数会导致对 Regex 构造函数的调用，从而传入模式的静态类型参数。

- `Match`该方法的结果由标准<xref:System.Text.RegularExpressions.Match>类型表示。

- 每个命名组都会导致提供的属性，访问该属性会导致在匹配的集合`Groups`上使用索引器。

以下代码是实现此类提供程序的逻辑的核心，此示例省略了向提供的类型添加所有成员。 有关每个添加成员的信息，请参阅本主题后面的相应部分。 有关完整代码，请从 CodePlex 网站上的[F# 3.0 示例包](https://archive.codeplex.com/?p=fsharp3sample)下载示例。

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

          match parameterValues with
          | [| :? string as pattern|] ->

            // Create an instance of the regular expression.
            //
            // This will fail with System.ArgumentException if the regular expression is not valid.
            // The exception will escape the type provider and be reported in client code.
            let r = System.Text.RegularExpressions.Regex(pattern)

            // Declare the typed regex provided type.
            // The type erasure of this type is 'obj', even though the representation will always be a Regex
            // This, combined with hiding the object methods, makes the IntelliSense experience simpler.
            let ty =
              ProvidedTypeDefinition(
                thisAssembly,
                rootNamespace,
                typeName,
                baseType = Some baseTy)

            ...

            ty
          | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

请注意以下几点：

- 类型提供程序采用两个静态参数：`pattern`必填项和 可选的`options`。（因为提供了默认值）。

- 提供静态参数后，将创建正则表达式的实例。 如果 Regex 格式不正确，此实例将引发异常，并且此错误将报告给用户。

- 在回调`DefineStaticParameters`中，定义提供参数后将返回的类型。

- 此代码设置`HideObjectMethods`为 true，以便 IntelliSense 体验将保持流线型。 此属性会导致`Equals`从提供对象的`GetHashCode` `Finalize`IntelliSense 列表中禁止 、 和`GetType`成员。

- 使用作为`obj`方法的基础类型，但您将使用`Regex`对象作为此类型的运行时表示形式，如下例所示。

- 当正则表达式`Regex`无效时，对<xref:System.ArgumentException>构造函数的调用将引发 。 编译器捕获此异常，并在编译时或在 Visual Studio 编辑器中向用户报告错误消息。 此异常允许在不运行应用程序的情况下验证正则表达式。

上面定义的类型还不用，因为它不包含任何有意义的方法或属性。 首先，添加静态`IsMatch`方法：

```fsharp
let isMatch =
    ProvidedMethod(
        methodName = "IsMatch",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = typeof<bool>,
        isStatic = true,
        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string."
ty.AddMember isMatch
```

前面的代码定义一个方法`IsMatch`，该方法以字符串作为输入并返回 。 `bool` 唯一棘手的部分是在`args``InvokeCode`定义中使用参数。 在此示例中，`args`是表示此方法的参数的报价单列表。 如果该方法是实例方法，则第一个参数表示参数`this`。 但是，对于静态方法，参数都只是方法的显式参数。 请注意，引号值的类型应与指定的返回类型匹配（在本例中为`bool`）。 另请注意，此代码使用`AddXmlDoc`方法可确保提供的方法也具有有用的文档，您可以通过 IntelliSense 提供这些文档。

接下来，添加实例匹配方法。 但是，此方法应返回提供的`Match`类型的值，以便以强类型方式访问组。 因此，您首先声明类型`Match`。 由于此类型取决于作为静态参数提供的模式，因此此类型必须嵌套在参数化类型定义中：

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

然后，向每个组的"匹配"类型添加一个属性。 在运行时，匹配表示为<xref:System.Text.RegularExpressions.Match>值，因此定义属性的报价单必须使用<xref:System.Text.RegularExpressions.Match.Groups>索引属性来获取相关组。

```fsharp
for group in r.GetGroupNames() do
    // Ignore the group named 0, which represents all input.
    if group <> "0" then
    let prop =
      ProvidedProperty(
        propertyName = group,
        propertyType = typeof<Group>,
        getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
    matchTy.AddMember prop
```

同样，请注意，您将 XML 文档添加到提供的属性。 另请注意，如果提供了`GetterCode`函数，则可以读取属性，如果提供了`SetterCode`函数，则可以写入该属性，因此生成的属性是只读的。

现在，您可以创建返回此`Match`类型值的实例方法：

```fsharp
let matchMethod =
    ProvidedMethod(
        methodName = "Match",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = matchTy,
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

ty.AddMember matchMeth
```

因为您正在创建实例方法，表示`args.[0]`正在调用`RegexTyped`该方法的实例，并且`args.[1]`是输入参数。

最后，提供一个构造函数，以便可以创建提供类型的实例。

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

构造函数仅擦除为创建标准 .NET Regex 实例，该实例再次盒装到对象，因为`obj`是提供类型的擦除。 通过该更改，主题前面指定的示例 API 用法将按预期方式工作。 以下代码已完成且最终：

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types.
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

            match parameterValues with
            | [| :? string as pattern|] ->

                // Create an instance of the regular expression.

                let r = System.Text.RegularExpressions.Regex(pattern)

                // Declare the typed regex provided type.

                let ty =
                    ProvidedTypeDefinition(
                        thisAssembly,
                        rootNamespace,
                        typeName,
                        baseType = Some baseTy)

                ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

                // Provide strongly typed version of Regex.IsMatch static method.
                let isMatch =
                    ProvidedMethod(
                        methodName = "IsMatch",
                        parameters = [ProvidedParameter("input", typeof<string>)],
                        returnType = typeof<bool>,
                        isStatic = true,
                        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

                isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

                ty.AddMember isMatch

                // Provided type for matches
                // Again, erase to obj even though the representation will always be a Match
                let matchTy =
                    ProvidedTypeDefinition(
                        "MatchType",
                        baseType = Some baseTy,
                        hideObjectMethods = true)

                // Nest the match type within parameterized Regex type.
                ty.AddMember matchTy

                // Add group properties to match type
                for group in r.GetGroupNames() do
                    // Ignore the group named 0, which represents all input.
                    if group <> "0" then
                        let prop =
                          ProvidedProperty(
                            propertyName = group,
                            propertyType = typeof<Group>,
                            getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
                        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
                        matchTy.AddMember(prop)

                // Provide strongly typed version of Regex.Match instance method.
                let matchMeth =
                  ProvidedMethod(
                    methodName = "Match",
                    parameters = [ProvidedParameter("input", typeof<string>)],
                    returnType = matchTy,
                    invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

                ty.AddMember matchMeth

                // Declare a constructor.
                let ctor =
                  ProvidedConstructor(
                    parameters = [],
                    invokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

                // Add documentation to the constructor.
                ctor.AddXmlDoc "Initializes a regular expression instance"

                ty.AddMember ctor

                ty
            | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

### <a name="key-lessons"></a>重点课程

本节介绍如何创建对其静态参数运行的类型提供程序。 提供程序检查静态参数，并根据其值提供操作。

## <a name="a-type-provider-that-is-backed-by-local-data"></a>由本地数据支持的类型提供程序

通常，您可能希望类型提供程序不仅基于静态参数，还基于本地或远程系统的信息来显示 API。 本节讨论基于本地数据（如本地数据文件）的类型提供程序。

### <a name="simple-csv-file-provider"></a>简单的 CSV 文件提供程序

作为一个简单的示例，请考虑一个类型提供程序，用于以逗号分隔值 （CSV） 格式访问科学数据。 本节假定 CSV 文件包含标头行，后跟浮点数据，如下表所示：

|距离（米）|时间（秒）|
|----------------|-------------|
|50.0|3.7|
|100.0|5.2|
|150.0|6.4|

本节演示如何提供一种类型，可用于`Distance`获取具有类型`float<meter>`属性和类型的`Time``float<second>`属性的行。 为简单起见，我们做了以下假设：

- 标题名称不是无单元的，或者有"名称（单位）"的窗体，并且不包含逗号。

- 单位均为[Microsoft.FSharp.Data.UnitSystems.SI.单元名称模块 （F#）](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b)模块定义的系统国际 （SI） 单元。

- 单位都是简单的（例如，仪表），而不是复合的（例如，仪表/秒）。

- 所有列都包含浮点数据。

更完整的提供商将放松这些限制。

同样，第一步是考虑 API 的外观。 由于给出了包含上表内容的 `info.csv` 文件（采用逗号分隔格式），提供程序的用户应该能够编写与以下示例类似的代码：

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

在这种情况下，编译器应将这些调用转换为类似以下示例的内容：

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

最佳转换将要求类型提供程序在类型提供程序的程序集中定义`CsvFile`实际类型。 类型提供程序通常依赖于一些帮助器类型和方法来包装重要逻辑。 由于度量值在运行时被擦除，因此可以使用 作为`float[]`行的擦除类型。 编译器将不同的列视为具有不同的度量值类型。 例如，我们示例中的第一列具有类型`float<meter>`，第二列具有`float<second>`。 但是，擦除的表示形式可以保持非常简单。

以下代码显示了实现的核心。

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data =
        seq {
            for line in File.ReadAllLines(filename) |> Seq.skip 1 ->
                line.Split(',') |> Array.map float
        }
        |> Seq.cache
    member _.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
    inherit TypeProviderForNamespaces(cfg)

    // Get the assembly and namespace used to house the provided types.
    let asm = System.Reflection.Assembly.GetExecutingAssembly()
    let ns = "Samples.FSharp.MiniCsvProvider"

    // Create the main provided type.
    let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

    // Parameterize the type by the file to use as a template.
    let filename = ProvidedStaticParameter("filename", typeof<string>)
    do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->

        // Resolve the filename relative to the resolution folder.
        let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

        // Get the first line from the file.
        let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

        // Define a provided type for each row, erasing to a float[].
        let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

        // Extract header names from the file, splitting on commas.
        // use Regex matching to get the position in the row at which the field occurs
        let headers = Regex.Matches(headerLine, "[^,]+")

        // Add one property per CSV field.
        for i in 0 .. headers.Count - 1 do
            let headerText = headers.[i].Value

            // Try to decompose this header into a name and unit.
            let fieldName, fieldTy =
                let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
                if m.Success then

                    let unitName = m.Groups.["unit"].Value
                    let units = ProvidedMeasureBuilder.Default.SI unitName
                    m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])

                else
                    // no units, just treat it as a normal float
                    headerText, typeof<float>

            let prop =
                ProvidedProperty(fieldName, fieldTy,
                    getterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

            // Add metadata that defines the property's location in the referenced file.
            prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
            rowTy.AddMember(prop)

        // Define the provided type, erasing to CsvFile.
        let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

        // Add a parameterless constructor that loads the file that was used to define the schema.
        let ctor0 =
            ProvidedConstructor([],
                invokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
        ty.AddMember ctor0

        // Add a constructor that takes the file name to load.
        let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)],
            invokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
        ty.AddMember ctor1

        // Add a more strongly typed Data property, which uses the existing property at runtime.
        let prop =
            ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy),
                getterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
        ty.AddMember prop

        // Add the row type as a nested type.
        ty.AddMember rowTy
        ty)

    // Add the type to the namespace.
    do this.AddNamespace(ns, [csvTy])
```

请注意有关实现的以下几点：

- 重载构造函数允许读取原始文件或具有相同架构的文件。 当您为本地或远程数据源编写类型提供程序时，此模式很常见，并且此模式允许将本地文件用作远程数据的模板。

- 您可以使用传递给类型提供程序构造函数的[TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44)值解析相对文件名。

- 可以使用 方法`AddDefinitionLocation`定义提供的属性的位置。 因此，如果您在提供的属性`Go To Definition`上使用，CSV 文件将在 Visual Studio 中打开。

- 您可以使用 类型`ProvidedMeasureBuilder`查找 SI 单位并生成相关`float<_>`类型。

### <a name="key-lessons"></a>重点课程

本节介绍如何使用数据源本身中包含的简单架构为本地数据源创建类型提供程序。

## <a name="going-further"></a>深入探索

以下各节包括进一步研究的建议。

### <a name="a-look-at-the-compiled-code-for-erased-types"></a>查看已编译的擦除类型代码

为了让您了解类型提供程序的使用如何与所发出的代码相对应，请使用`HelloWorldTypeProvider`本主题前面使用的代码来查看以下函数。

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

下面是使用 ildasm.exe 编译的结果代码的图像：

```il
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

如示例所示，所有提及的类型`Type1`和`InstanceProperty`属性都已被删除，仅保留有关运行时类型的操作。

### <a name="design-and-naming-conventions-for-type-providers"></a>类型提供程序的设计和命名约定

创作类型提供程序时，请遵守以下约定。

**连接协议的提供程序**通常，大多数提供程序 DlL 用于数据和服务连接协议（如 OData 或 SQL 连接）的名称应以`TypeProvider``TypeProviders`或 结尾。 例如，使用类似于以下字符串的 DLL 名称：

`Fabrikam.Management.BasicTypeProviders.dll`

确保您提供的类型是相应命名空间的成员，并指示您实现的连接协议：

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**通用编码提供程序**。  对于实用程序类型提供程序（如正则表达式提供程序），类型提供程序可能是基本库的一部分，如下例所示：

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

在这种情况下，根据正常的 .NET 设计约定，提供的类型将显示在适当的点：

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

**单顿数据源**. 某些类型提供程序连接到单个专用数据源，并且仅提供数据。 在这种情况下，应删除`TypeProvider`后缀，并使用正常的约定进行 .NET 命名：

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

有关详细信息，请参阅本主题后面`GetConnection`介绍的设计约定。

### <a name="design-patterns-for-type-providers"></a>类型提供程序的设计模式

以下各节介绍在创作类型提供程序时可以使用的设计模式。

#### <a name="the-getconnection-design-pattern"></a>获取连接设计模式

大多数类型提供程序都应编写用于使用 FSharp.Data.TypeProvider.dll 中类型提供程序使用的`GetConnection`模式，如下例所示：

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>由远程数据和服务支持的类型提供程序

在创建由远程数据和服务支持的类型提供程序之前，必须考虑连接编程中固有的一系列问题。 这些问题包括以下注意事项：

- 架构映射

- 存在架构更改时的实时性和失效性

- 架构缓存

- 数据访问操作的异步实现

- 支持查询，包括 LINQ 查询

- 凭据和身份验证

本主题没有进一步探讨这些问题。

### <a name="additional-authoring-techniques"></a>其他创作技术

编写自己的类型提供程序时，可能需要使用以下附加技术。

### <a name="creating-types-and-members-on-demand"></a>按需创建类型和成员

提供类型 API 已延迟添加成员版本。

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

这些版本用于创建类型的按需空间。

### <a name="providing-array-types-and-generic-type-instantiations"></a>提供数组类型和通用类型实例化

通过使用`MakeArrayType`法线 和`MakePointerType`的任何`MakeGenericType`实例<xref:System.Type>（包括`ProvidedTypeDefinitions`） 使提供的成员（其签名包括数组类型、byref 类型和泛型类型的实例）。

> [!NOTE]
> 在某些情况下，您可能需要在 中使用`ProvidedTypeBuilder.MakeGenericType`帮助程序。  有关详细信息，请参阅[类型提供程序 SDK 文档](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations)。

### <a name="providing-unit-of-measure-annotations"></a>提供度量单位注释

提供类型 API 提供用于提供度量值注释的帮助器。 例如，要提供类型`float<kg>`，请使用以下代码：

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  要提供类型`Nullable<decimal<kg/m^2>>`，请使用以下代码：

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>访问项目-本地资源或脚本本地资源

类型提供程序的每个实例都可以在构造期间给出一`TypeProviderConfig`个值。 此值包含提供程序的"解析文件夹"（即编译的项目文件夹或包含脚本的目录）、引用程序集的列表和其他信息。

### <a name="invalidation"></a>失效

提供程序可以引发失效信号，以通知 F# 语言服务架构假设可能已更改。 当发生失效时，如果提供程序在 Visual Studio 中托管，则重新检查类型检查。 当提供程序托管在 F# 交互式或 F# 编译器 （fsc.exe） 中时，将忽略此信号。

### <a name="caching-schema-information"></a>缓存架构信息

提供程序必须经常缓存对架构信息的访问。 缓存的数据应使用作为静态参数或用户数据给出的文件名进行存储。 架构缓存的一个示例是`LocalSchemaFile``FSharp.Data.TypeProviders`程序集类型提供程序中的参数。 在实现这些提供程序时，此静态参数指示类型提供程序在指定的本地文件中使用架构信息，而不是通过网络访问数据源。 要使用缓存的架构信息，还必须将静态参数`ForceUpdate`设置为`false`。 您可以使用类似的技术来启用联机和脱机数据访问。

### <a name="backing-assembly"></a>支持程序集

编译`.dll`或`.exe`文件时，生成的类型的备份 .dll 文件将静态链接到生成的程序集中。 此链接是通过将中间语言 （IL） 类型定义和任何托管资源从备份程序集复制到最终程序集来创建的。 使用 F# 交互式时，不会复制支持 .dll 文件，而是直接加载到 F# 交互式进程中。

### <a name="exceptions-and-diagnostics-from-type-providers"></a>来自类型提供程序的异常和诊断

提供类型中所有成员的所有使用都可能会引发异常。 在所有情况下，如果类型提供程序引发异常，主机编译器将错误属性归因于特定类型提供程序。

- 类型提供程序异常不应导致内部编译器错误。

- 类型提供程序无法报告警告。

- 当类型提供程序托管在 F# 编译器、F# 开发环境或 F# 交互式中时，将捕获该提供程序的所有异常。 消息属性始终是错误文本，并且不显示堆栈跟踪。 如果要引发异常，可以引发以下示例： `System.NotSupportedException`、 `System.IO.IOException`。 `System.Exception`。

#### <a name="providing-generated-types"></a>提供生成的类型

到目前为止，本文档已解释如何提供擦除类型。 您还可以使用 F# 中的类型提供程序机制提供生成的类型，这些类型将作为真正的 .NET 类型定义添加到用户的程序中。 您必须使用类型定义来引用生成的提供类型。

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

作为 F# 3.0 版本的一部分的"提供类型-0.2 帮助器"代码对提供生成的类型的支持有限。 对于生成的类型定义，以下语句必须为 true：

- `isErased` 必须设置为 `false`。

- 生成的类型必须添加到新构造`ProvidedAssembly()`的 ，该类型表示生成的代码片段的容器。

- 提供程序必须具有具有实际支持 .NET .dll 文件的程序集，该文件在磁盘上具有匹配的 .dll 文件。

## <a name="rules-and-limitations"></a>规则和限制

编写类型提供程序时，请记住以下规则和限制。

### <a name="provided-types-must-be-reachable"></a>提供的类型必须可到达

所有提供的类型都应从非嵌套类型中进行。 非嵌套类型在对`TypeProviderForNamespaces`构造函数的调用或对`AddNamespace`的调用中给出。 例如，如果提供程序提供类型`StaticClass.P : T`，则必须确保 T 是非嵌套类型或嵌套在一个类型下。

例如，某些提供程序具有包含这些`DataTypes``T1, T2, T3, ...`类型的静态类。 否则，错误表示在程序集 A 中找到对类型 T 的引用，但在该程序集中找不到该类型。 如果出现此错误，请验证可以从提供程序类型中到达所有子类型。 注意：这些`T1, T2, T3...`类型称为*动态*类型。 请记住将它们放在可访问的命名空间或父类型中。

### <a name="limitations-of-the-type-provider-mechanism"></a>类型提供程序机制的限制

F# 中的类型提供程序机制具有以下限制：

- F# 中类型提供程序的基础基础结构不支持提供泛型类型或提供泛型方法。

- 该机制不支持具有静态参数的嵌套类型。

## <a name="development-tips"></a>开发提示

您可能会发现以下提示在开发过程中很有帮助：

### <a name="run-two-instances-of-visual-studio"></a>运行可视化工作室的两个实例

您可以在一个实例中开发类型提供程序，并在另一个实例中测试提供程序，因为测试 IDE 将对 .dll 文件进行锁定，以防止重新生成类型提供程序。 因此，在第一个实例中生成提供程序时，必须关闭 Visual Studio 的第二个实例，然后在构建提供程序后重新打开第二个实例。

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>使用 fsc.exe 调用调试类型提供程序

您可以使用以下工具调用类型提供程序：

- fsc.exe（F# 命令行编译器）

- fsi.exe（F# 交互式编译器）

- 德文夫.exe（视觉工作室）

通常，通过在测试脚本文件（例如，脚本.fsx）上使用 fsc.exe，您通常最容易调试类型提供程序。 可以从命令提示符启动调试器。

```console
devenv /debugexe fsc.exe script.fsx
```

  您可以使用打印到打印的日志记录。

## <a name="see-also"></a>另请参阅

- [类型提供程序](index.md)
- [类型提供程序 SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
