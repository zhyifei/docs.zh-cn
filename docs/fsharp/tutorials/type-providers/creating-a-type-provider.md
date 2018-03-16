---
title: "教程：创建类型提供程序 (F#)"
description: "了解如何在 F # 3.0 中创建你自己 F # 类型提供程序，通过检查几个简单类型提供程序来演示基本概念。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 82bec076-19d4-470c-979f-6c3a14b7c70a
ms.openlocfilehash: 30d1c20d66fd0a193c05c97ee726a886f98356ad
ms.sourcegitcommit: 1c0b0f082b3f300e54b4d069b317ac724c88ddc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2018
---
# <a name="tutorial-creating-a-type-provider"></a>教程： 创建类型提供程序

F # 中的类型提供程序机制是支持的其编程信息丰富的重要部分。 本教程介绍如何创建你自己的类型提供程序通过逐步引导您完成开发的几个简单类型提供程序来演示基本概念。 有关 F # 中的类型提供程序机制的详细信息，请参阅[类型提供程序](index.md)。

F # 生态系统包含某个范围的常用的 Internet 和企业数据服务的类型提供程序。 例如：

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/)包括类型提供程序的 JSON、 XML、 CSV 和 HTML 文档格式。

- [SQLProvider](https://fsprojects.github.io/SQLProvider/)提供对这些数据源的查询的到通过对象映射和 F # LINQ 的 SQL 数据库的强类型访问。

- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/)编译时的类型提供程序的一组已选中 T-SQL 的 F # 中的嵌入。

- [FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/)是较旧的用于仅使用.NET Framework 编程时，用于访问 SQL、 实体框架、 OData 和 WSDL 数据服务的类型提供程序集。

在必要时，你可以创建自定义类型提供程序，也可以引用其他人创建的类型提供程序。 例如，你的组织可以提供数量不断增长的命名数据集，每个都有其自己的稳定数据架构的数据服务。 你可以创建的类型提供程序读取架构，强类型方式将当前的数据集提供给程序员。


## <a name="before-you-start"></a>安装前

类型提供程序机制主要用于将稳定数据和服务信息空间注入到 F # 编程体验。

此机制的用途不是将其架构更改在程序执行方式与程序的逻辑相关过程的信息空间注入。 此外，机制不设计内语言元编程，即使该域包含一些有效的用途。 仅在必要时，应使用此机制和类型提供程序的开发其中产生很高的值。

应避免编写架构不可类型提供程序。 同样，应避免编写类型提供程序，其中一个普通 （或甚至的现有）.NET 库便已足够。

在开始之前，你可能会询问以下问题：

- 你是否为你的信息源拥有架构？ 如果是这样，到 F # 和.NET 类型系统映射是什么？

- 可以使用现有 （动态类型化） API 作为起点实现？

- 将你和你的组织具有足够使用类型提供程序，以使编写它值得？ 普通的.NET 库将满足你的需求？

- 将您的架构将更改多少？

- 它会更改在编码期间吗？

- 它会因不同的编码会话？

- 它将更改在程序执行过程？

类型提供程序是最适合于其中的架构是在运行时和已编译代码的生存期内稳定的情况下。


## <a name="a-simple-type-provider"></a>简单类型提供程序

此示例是 Samples.HelloWorldTypeProvider，类似于中的示例`examples`目录[F # 类型提供程序 SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/)。 提供程序使可包含 100 已擦除的类型，如以下代码通过使用 F # 签名语法和省略的除外的详细信息所示的"类型空间" `Type1`。 有关已擦除的类型的详细信息，请参阅[详细信息有关擦除提供类型](#details-about-erased-provided-types)本主题中更高版本。

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

    /// This is an instance property.
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

请注意静态已知的类型和成员提供一套。 此示例不会利用提供程序能够提供依赖于架构的类型。 类型提供程序实现概述在下面的代码中，并在此主题后面部分中提供了详细信息。


>[!WARNING] 
可能有此代码和联机示例之间的差异。

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

若要使用此提供程序，打开 Visual Studio 的单独实例，创建一个 F # 脚本，然后通过使用如以下代码所示的 #r 中添加提供程序对你的脚本中的引用：

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

然后查看下类型`Samples.HelloWorldTypeProvider`类型提供程序生成的命名空间。

重新编译该提供程序之前，请确保你具有已关闭的 Visual Studio 和 F # Interactive 将提供程序 DLL 的所有实例。 否则，因为将锁定输出 DLL，将发生生成错误。

若要调试此提供程序使用打印语句，使脚本公开提供程序，问题以及如何将以下代码：

```fsharp
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

若要通过使用 Visual Studio 中调试此提供程序，使用管理凭据，打开 Visual Studio 命令提示符并运行以下命令：

```fsharp
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

或者，打开 Visual Studio，打开调试菜单，选择`Debug/Attach to process…`，并附加到另一个`devenv`您要在其中编辑你的脚本的过程。 通过使用此方法，可以更轻松地通过第二个实例 （使用完整的 IntelliSense 和其他功能） 中以交互方式键入表达式面向类型提供程序中的特定逻辑。

你可以禁用调试以更好地确定生成的代码中的错误仅我的代码。 有关如何启用或禁用此功能的信息，请参阅[使用调试器浏览代码](/visualstudio/debugger/navigating-through-code-with-the-debugger)。 此外，还可以设置首次异常捕获通过打开`Debug`菜单，然后选择`Exceptions`或通过选择 Ctrl + Alt + E 键以打开`Exceptions`对话框。 在该对话框中，在`Common Language Runtime Exceptions`，选择`Thrown`复选框。


### <a name="implementation-of-the-type-provider"></a>类型提供程序的实现

本部分将指导你完成的类型提供程序实现的主体部分。 首先，定义自定义类型提供程序本身的类型：

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

此类型必须是公共的并且你必须将其与标记[TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947)属性，以便在单独的 F # 项目引用包含类型的程序集时，编译器将识别的类型提供程序。 *配置*参数是可选的，和 （如果存在） 包含的 F # 编译器创建的类型提供程序实例上下文的配置信息。

接下来，实现[ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f)接口。 在这种情况下，使用`TypeProviderForNamespaces`键入从`ProvidedTypes`API 的基类型。 此帮助程序类型可以提供命名空间，其中每个直接包含有限数量的固定，积极提供类型积极提供有限的集合。 在此上下文中，提供程序*积极*生成类型，即使它们不需要或使用。

```fsharp
inherit TypeProviderForNamespaces(config)
```

接下来，定义指定的提供类型的命名空间的本地私有值，并找到该类型提供程序程序集本身。 此程序集可作为已擦除的类型提供的逻辑父类型的更高版本。

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

接下来，创建一个函数来提供每个类型 Type1...Type100。 本主题中后面的更多详细阐述此函数。

```fsharp
let makeOneProvidedType (n:int) = …
```

接下来，生成的 100 的提供的类型：

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

接下来，添加类型为提供的命名空间：

```fsharp
do this.AddNamespace(namespaceName, types)
```

最后，添加程序集属性，该值指示要创建类型提供程序 DLL:

```fsharp
[<assembly:TypeProviderAssembly>] 
do()
```

### <a name="providing-one-type-and-its-members"></a>提供一个类型及其成员

`makeOneProvidedType`函数行为提供一种类型的实际工作。

```fsharp
let makeOneProvidedType (n:int) = 
…
```

此步骤说明了此函数的实现。 首先，创建所提供的类型 (例如，Type1，当 n = 1 或 Type57，当 n = 57)。

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code, 
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

您应该注意以下几点：

- 这提供擦除类型。  因为你指示的基类型是`obj`，实例将显示类型的值为[obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7)在编译的代码。

- 当指定非嵌套类型时，你必须指定的程序集和命名空间。 对于已擦除的类型，该程序集应为类型提供程序程序集本身。

接下来，添加到类型的 XML 文档。 本文档将延迟，也就是说，如果主机编译器需要它计算按需。

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

接下来将提供的静态属性添加到类型：

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty", 
                                  propertyType = typeof<string>, 
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

获取此属性将计算结果始终为字符串"Hello ！"。 `GetterCode`属性使用 F # 引号，它表示主机编译器将为获取的属性生成的代码。 有关引用的详细信息，请参阅[代码引用 （F #）](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155)。

将 XML 文档添加到属性。

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

现在将提供的属性附加到所提供的类型。 必须将提供的成员附加到一个且仅有一个类型。 否则，该成员将永远不会为可访问。

```fsharp
t.AddMember staticProp
```

现在创建不带任何参数提供构造函数。

```fsharp
let ctor = ProvidedConstructor(parameters = [ ], 
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

`InvokeCode`的构造函数将返回 F # 引号，它表示主机编译器时调用的构造函数生成的代码。 例如，你可以使用以下构造函数：

```fsharp
new Type10()
```

所提供的类型的实例将"的对象数据"创建与基础数据。 带引号的代码包含转换为[obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7)因为该类型的擦除这就提供了类型 （按照您指定当声明所提供的类型）。

将 XML 文档添加到构造函数中，并将提供的构造函数添加到所提供的类型：

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

创建另一个提供构造函数接受一个参数：

```fsharp
let ctor2 = 
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ], 
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

`InvokeCode`构造函数再次返回 F # 引号，它表示主机编译器生成的方法的调用的代码。 例如，你可以使用以下构造函数：

```fsharp
new Type10("ten")
```

与基础数据"10"创建所提供的类型的实例。 你可能具有已注意到，`InvokeCode`函数返回的引用。 此函数的输入是表达式，一个，每个构造函数参数的列表。 在这种情况下，一个表达式来表示单个参数值可用于`args.[0]`。 该构造函数调用的代码将为已擦除的类型的返回值强制转换`obj`。 第二个提供的构造函数添加到类型后，你创建提供的实例属性：

```fsharp
let instanceProp = 
    ProvidedProperty(propertyName = "InstanceProperty", 
                     propertyType = typeof<int>, 
                     getterCode= (fun args -> 
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

获取此属性将返回字符串，即表示对象的长度。 `GetterCode`属性返回指定宿主编译器生成要获取其属性的代码中的 F # 引号。 如`InvokeCode`、`GetterCode`函数返回的引用。 主机编译器将调用此函数带自变量列表。 在这种情况下，自变量包括只需单个表达式，它表示对其调用 getter，使用户能够通过使用实例`args.[0]`。实现`GetterCode`然后拼接到已擦除的类型在结果引号引起`obj`，并使用强制转换来满足编译器的机制，以检查该对象是一个字符串的类型。 下的一部分`makeOneProvidedType`带有一个参数提供的实例方法。

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

最后，创建的嵌套的类型，包含 100 个嵌套的属性。 此创建嵌套类型和其属性将延迟，也就是说，计算按需。

```fsharp
t.AddMembersDelayed(fun () -> 
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () -> 
    let staticPropsInNestedType = 
      [ for i in 1 .. 100 do
          let valueOfTheProperty = "I am string "  + string i

          let p = 
            ProvidedProperty(propertyName = "StaticProperty" + string i, 
              propertyType = typeof<string>, 
              isStatic = true,
              getterCode= (fun args -> <@@ valueOfTheProperty @@>))

          p.AddXmlDocDelayed(fun () -> 
              sprintf "This is StaticProperty%d on NestedType" i)

          yield p ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a>有关已擦除的提供类型的详细信息

本部分中的示例仅提供*擦除提供的类型*，这是在以下情况下特别有用：

- 当你正在编写的提供程序只包含数据和方法的信息空间。

- 当你正在编写准确运行时类型语义并不重要的信息空间实际使用的提供程序。

- 当你正在编写的提供程序信息空间，因此大型进行相互连接，不从技术上讲可行，若要生成的信息空间的实际.NET 类型。

在此示例中，提供的每个类型清除键入`obj`，和所有使用该类型将都显示为类型`obj`在编译的代码。 事实上，在这些示例中的基础对象都是字符串，但该类型将显示为`System.Object`在.NET 编译的代码。 当与类型擦除所有使用，可以使用显式装箱，取消装箱，然后将强制转换以破坏擦除类型。 在这种情况下，使用对象时，可能会导致无效的强制转换异常。 提供程序运行时可以定义其自己的私有表示形式类型，以帮助防范 false 表示形式。 不能在 F # 本身中定义已擦除的类型。 仅提供可能擦除类型。 你必须了解后果，这两个实际并语义的使用类型提供程序或服务提供商提供的已擦除的类型清除类型。 一个已擦除的类型有任何真实的.NET 类型。 因此，您不能执行准确反射的类型，并且可能会破坏已擦除的类型，如果你使用运行时强制转换和其他依赖于准确运行时类型语义的方法。 已擦除的类型的子版本号经常会导致在运行时的类型强制转换异常。


### <a name="choosing-representations-for-erased-provided-types"></a>有关擦除选择表示形式之间实现提供类型

有关已擦除的提供类型的某些用法，没有表示形式是必需的。 例如，已擦除提供类型可能包含静态属性和成员和任何构造函数，并且任何方法或属性将返回类型的实例。 如果可以访问的清除实例提供类型，则必须考虑以下问题：

**什么是类型的提供的擦除？**

- 提供的擦除是类型的类型中编译的.NET 代码的显示方式。

- 提供已擦除的类类型的擦除始终是第一个非擦除基类型的继承链中的类型。

- 提供已擦除的接口类型的擦除始终是`System.Object`。

**表示形式提供的类型有哪些？**

- 可能对象已擦除提供类型集称为其表示形式。 在本文档示例中，类型的所有已擦除提供的表示`Type1..Type100`始终是字符串对象。

所有表示形式提供的类型都必须与所提供的类型的擦除兼容。 （否则为类型提供程序，用于，F # 编译器将产生错误或将生成无法验证不是有效的.NET 代码。 如果类型提供程序返回的代码给出无效的表示形式，则该类型提供程序无效。）

通过使用以下方法之一，二者都是很常见，可以选择提供的对象的表示形式：

- 如果你只需提供通过现有的.NET 类型的强类型包装器，它通常很适合擦除到该类型，将该类型的实例用作和 / 或表示形式，您类型。 针对该类型的现有方法的大多数仍在使用强类型的版本时有意义时，此种方法很适合。

- 如果你想要从任何现有的.NET API 显著创建 API 不同，其意义创建将类型擦除并提供类型的表示形式的运行时类型。

本文档中的示例使用以提供的对象的表示形式的字符串。 通常情况下，它可能适合其他对象用于表示形式。 例如，你可能会为属性包使用字典：

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

作为替代方法，你可以将在运行时使用，以形成表示形式，以及一个或多个运行时操作提供程序类型中定义一种类型：

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

提供的成员可以然后构造此对象类型的实例：

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

在这种情况下，不可能 （可选） 将此类型用作类型擦除通过指定此类型作为`baseType`构造时`ProvidedTypeDefinition`:

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>关键经验教训，

前面部分介绍了如何创建简单的擦除类型提供程序提供了广泛的类型、 属性和方法。 本部分还介绍类型擦除，包括的一些优点和缺点的提供类型提供程序，从已擦除的类型的概念，并讨论了已擦除的类型的表示形式。


## <a name="a-type-provider-that-uses-static-parameters"></a>使用静态参数的类型提供程序

参数类型提供程序化的静态数据的能力使许多有趣的情况下，即使在情况下当提供程序不需要访问的任何本地或远程数据。 在本部分中，你将了解一些基本技术进行组合使用这样的提供程序。


### <a name="type-checked-regex-provider"></a>检查类型的正则表达式提供程序

假设你想要实现包装.NET 正则表达式的类型提供<xref:System.Text.RegularExpressions.Regex>提供了以下的编译时保证的接口中的库：

- 验证正则表达式是否有效。

- 提供基于正则表达式中的任何组名称的匹配项的命名的属性。

本部分演示如何使用类型提供程序创建`RegexTyped`键入正则表达式模式使以提供这些优点。 如果提供的模式不有效，并且类型提供程序可以提取组模式中，以便你可以通过使用名为匹配的属性访问它们，编译器将报告错误。 在设计时类型提供程序，应考虑如何查找其公开的 API 应到最终用户，如何这种设计将将转换为.NET 代码。 下面的示例演示如何使用此类 API 来获取区域代码的组件：

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

下面的示例演示类型提供程序将这些调用的转换：

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

请注意以下几点：

- 标准的正则表达式类型表示参数化`RegexTyped`类型。

- `RegexTyped`构造函数会导致对正则表达式构造函数中，在该模式的静态类型参数中传递的调用。

- 结果`Match`方法表示由标准<xref:System.Text.RegularExpressions.Match>类型。

- 每个命名的组将导致提供的属性和访问属性导致使用了匹配项的索引器`Groups`集合。

下面的代码是实现此类提供程序的逻辑的核心，此示例中省略加入到所提供的类型的所有成员。 有关每个添加的成员的信息，请参阅本主题后面的相应部分。 对于完整的代码中，从示例下载[F # 3.0 示例包](https://fsharp3sample.codeplex.com)Codeplex 网站上。

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

- 类型提供程序采用两个静态参数： `pattern`，这是必需的与`options`，这是可选的 （因为提供了默认值）。

- 提供静态自变量后，你将创建正则表达式的实例。 如果正则表达式格式不正确，并且将向用户报告此错误，此实例将引发异常。

- 在`DefineStaticParameters`回调，在定义后提供自变量将返回的类型。

- 此代码将设置`HideObjectMethods`为 true，以便将保留简化的 IntelliSense 体验。 此属性将导致`Equals`， `GetHashCode`， `Finalize`，和`GetType`成员为禁止从提供的对象的智能感知列表。

- 你使用`obj`如的基类型的方法，但你将使用`Regex`作为运行时表示形式的这种类型，如下一步的示例所示的对象。

- 调用`Regex`构造函数引发<xref:System.ArgumentException>正则表达式无效。 编译器将捕获此异常并在编译时或在 Visual Studio 编辑器中向用户报告一条错误消息。 此异常使正则表达式来验证而无需运行应用程序。

上面定义的类型没有用尚未因为它未包含任何有意义的方法或属性。 首先，添加一个静态`IsMatch`方法：

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

前面的代码中定义的方法`IsMatch`，它采用字符串作为输入并返回`bool`。 唯一麻烦的部分是使用`args`中的参数`InvokeCode`定义。 在此示例中，`args`是引用的列表，表示此方法的参数。 如果该方法是实例方法，第一个自变量表示`this`自变量。 但是，对于静态方法，这些参数是所有对象都是该方法的显式自变量。 请注意带引号的值的类型应与匹配的指定返回类型 (在这种情况下， `bool`)。 另请注意，此代码使用`AddXmlDoc`方法以确保提供的方法还具有有用的文档，你可以提供通过智能感知。

接下来，添加实例 Match 方法。 但是，此方法应返回值提供的`Match`类型，以便可在以强类型方式访问组。 因此，你首先声明`Match`类型。 因为此类型取决于已作为静态自变量提供的模式，此类型必须嵌套在参数化的类型定义中：

```fsharp
let matchTy = 
    ProvidedTypeDefinition(
        "MatchType", 
        baseType = Some baseTy, 
        hideObjectMethods = true)

ty.AddMember matchTy
```

然后，你将一个属性添加到每个组的匹配类型中。 在运行时，匹配项都表示为<xref:System.Text.RegularExpressions.Match>值，因此必须使用定义该属性引号<xref:System.Text.RegularExpressions.Match.Groups>索引属性要获取其相关的组。

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

此外，请注意，正在将 XML 文档添加到提供的属性。 另请注意，可以读取属性，如果`GetterCode`提供函数，则和属性可写，如果`SetterCode`提供函数，因此最终生成的属性为只读。

现在，你可以创建可返回的值的实例方法`Match`类型：

```fsharp
let matchMethod = 
    ProvidedMethod(
        methodName = "Match", 
        parameters = [ProvidedParameter("input", typeof<string>)], 
        returnType = matchTy, 
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first ocurrence of this regular expression" 

ty.AddMember matchMeth
```

要创建一个实例方法，因为`args.[0]`表示`RegexTyped`实例在其调用方法，和`args.[1]`是输入的参数。

最后，提供一个构造函数，以便可以创建所提供的类型的实例。

```fsharp
let ctor = 
    ProvidedConstructor(
        parameters = [], 
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

构造函数只是清除因为再次装箱到对象的标准.NET 正则表达式实例创建`obj`所提供的类型的擦除。 进行该更改后，按预期方式工作指定本主题前面的示例 API 用法。 下面的代码是完成和最后一个：

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
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurence of this regular expression"

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

### <a name="key-lessons"></a>关键经验教训，

本部分介绍了如何创建在其静态参数的类型提供程序进行操作。 提供程序检查静态参数，并提供基于其值的操作。


## <a name="a-type-provider-that-is-backed-by-local-data"></a>由本地数据类型提供程序

通常，你可能想类型提供程序提供 Api 基于静态参数不仅从本地或远程系统的信息。 本部分讨论基于本地的数据，如本地数据文件的类型提供程序。


### <a name="simple-csv-file-provider"></a>简单的 CSV 文件提供程序

作为一个简单的示例，请考虑以逗号分隔值 (CSV) 格式的科学数据访问的类型提供程序。 本部分假定 CSV 文件包含浮点型数据后, 跟一个标题行，如以下表所示：


|距离 （计数）|时间 （秒）|
|----------------|-------------|
|50.0|3.7|
|100.0|5.2|
|150.0|6.4|

本部分演示如何提供可用于获取与行类型`Distance`类型的属性`float<meter>`和`Time`类型的属性`float<second>`。 为简单起见，进行以下假设：

- 标头名称都是单元免或"名 （单位）"的形式，且不能包含逗号。

- 单位是为所有 Systeme 国际 (SI) 单位[Microsoft.FSharp.Data.UnitSystems.SI.UnitNames 模块 （F #）](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b)模块定义。

- 单位为所有简单 （例如，计数） 而不是复合 （例如，计数/秒）。

- 所有列都包含的浮点型数据。

更完整的提供程序将放宽了这些限制。

再次第一步是要考虑应外观 API。 由于给出了包含上表内容的 `info.csv` 文件（采用逗号分隔格式），提供程序的用户应该能够编写与以下示例类似的代码：

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

在这种情况下，编译器应将这些调用转换成类似于下面的示例：

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

最佳的转换将需要使用类型提供程序定义实际`CsvFile`类型提供程序的程序集中的类型。 类型提供程序通常依赖于几个帮助器类型和方法包装重要的逻辑。 度量值在运行时被删除，因为你可以使用`float[]`作为行已擦除的类型。 编译器会将视为不同的列具有不同的度量值类型。 例如，在本示例中的第一列具有类型`float<meter>`，第二个`float<second>`。 但是，已擦除的表示形式可以保持非常简单。

下面的代码演示实现的核心。

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data = 
        seq { for line in File.ReadAllLines(filename) |> Seq.skip 1 do
                 yield line.Split(',') |> Array.map float }
        |> Seq.cache
    member __.Data = data

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

- 重载的构造函数允许原始文件或一个要读取了相同的架构。 当你编写的类型提供程序本地或远程数据源，并且此模式允许本地文件以用于远程数据的作为模板时，此模式很常见。

- 你可以使用[TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44)中传递给类型提供程序构造函数来解析相对文件名称的值。

- 你可以使用`AddDefinitionLocation`方法定义的提供的属性的位置。 因此，如果你使用`Go To Definition`CSV 文件将在提供的属性，在 Visual Studio 中打开。

- 你可以使用`ProvidedMeasureBuilder`类型来查找 SI 单位并生成相关`float<_>`类型。

### <a name="key-lessons"></a>关键经验教训，

本部分介绍了如何使用数据源本身中包含的简单架构创建的类型提供程序的本地数据源。


## <a name="going-further"></a>继续

下列部分包括有关进一步研究的建议。


### <a name="a-look-at-the-compiled-code-for-erased-types"></a>查看已擦除的类型的已编译代码

若要向你提供使用类型提供程序是如何响应，将发出的代码的一些思路，查看下面的函数使用`HelloWorldTypeProvider`本主题前面的使用。

```fsharp
let function1 () = 
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

下面是代码的生成通过使用 ildasm.exe 反编译的映像：

```
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

如示例所示，类型的所有提及`Type1`和`InstanceProperty`属性已清除，离开仅对运行时类型的操作所涉及。


### <a name="design-and-naming-conventions-for-type-providers"></a>设计和类型提供程序的命名约定
创作类型提供程序时，请观察以下约定。

**提供程序连接协议**一般情况下，对于数据和服务的连接协议，如 OData 或 SQL 连接的大多数提供程序 Dll 的名称应以结尾`TypeProvider`或`TypeProviders`。 例如，使用一个 DLL 名称类似于以下字符串：

```
  Fabrikam.Management.BasicTypeProviders.dll
```

确保你提供的类型成员的对应的命名空间，并指示你实现的连接协议：

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**实用工具提供程序常规编码**。  对于如正则表达式的实用程序类型的提供，类型提供程序可能是的基库的一部分，如以下示例所示：

```fsharp
  #r "Fabrikam.Core.Text.Utilities.dll"
```

在这种情况下，所提供的类型将出现在合适的点根据正常.NET 设计约定：

```fsharp
  open Fabrikam.Core.Text.RegexTyped
  
  let regex = new RegexTyped<"a+b+a+b+">()
```

**单独数据源**。 某些类型提供程序连接到单个专用的数据源，并且提供仅数据。 在这种情况下，应删除`TypeProvider`后缀和使用的.NET 正常规则：

```fsharp
#r "Fabrikam.Data.Freebase.dll"
  
let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

有关详细信息，请参阅`GetConnection`设计在本主题后面所述的约定。


### <a name="design-patterns-for-type-providers"></a>类型提供程序的设计模式

以下各节描述了创作类型提供程序时，可以使用的设计模式。


#### <a name="the-getconnection-design-pattern"></a>GetConnection 设计模式
大多数类型提供程序应将编写为使用`GetConnection`由 FSharp.Data.TypeProviders.dll 中的类型提供程序，如以下示例所示的模式：

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>由远程数据和服务支持的类型提供程序

在创建的类型提供程序支持远程数据和服务之前，必须考虑一系列连接的编程中固有的问题。 这些问题包括以下注意事项：

- 架构映射

- 活动和失效的出现情况下，架构更改

- 架构缓存

- 数据访问操作的异步实现

- 支持的查询，包括 LINQ 查询

- 凭据和身份验证

本主题不了解进一步的这些问题。

### <a name="additional-authoring-techniques"></a>其他创作技术

当你编写自己的类型提供程序时，你可能想要使用以下其他技术。

### <a name="creating-types-and-members-on-demand"></a>类型和成员按需创建

ProvidedType API 具有延迟 AddMember 的版本。

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

这些版本用于创建按需空间的类型。

### <a name="providing-array-types-and-generic-type-instantiations"></a>提供数组类型和泛型类型实例化

通过使用正常使提供的成员 （其签名包括数组类型、 byref 类型和泛型类型的实例化） `MakeArrayType`， `MakePointerType`，和`MakeGenericType`上的任何实例<xref:System.Type>，包括`ProvidedTypeDefinitions`。

> [!NOTE]
> 在某些情况下，你可能需要使用中的帮助程序`ProvidedTypeBuilder.MakeGenericType`。  请参阅[类型提供程序 SDK 文档](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations)有关详细信息。

### <a name="providing-unit-of-measure-annotations"></a>提供的度量值批注的单元

ProvidedTypes API 提供帮助器，用于提供度量值批注。 例如，若要提供的类型`float<kg>`，使用以下代码：

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  若要提供的类型`Nullable<decimal<kg/m^2>>`，使用以下代码：

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>访问项目的本地或脚本本地资源

类型提供程序的每个实例可以将提供`TypeProviderConfig`在构造期间的值。 此值包含"解析文件夹"提供程序 （也就是说，编译或包含的脚本的目录的项目文件夹）、 引用程序集、 列表和其他信息。

### <a name="invalidation"></a>失效

提供程序可以引发失效信号以通知可能已更改架构假设 F # 语言服务。 失效时，要在 Visual Studio 中承载提供程序，则是重做一次。 当在 F # Interactive 中或由 F # 编译器 (fsc.exe) 托管提供程序时，将忽略此信号。

### <a name="caching-schema-information"></a>缓存的架构信息

提供程序通常必须缓存架构信息的访问权限。 应通过使用提供的文件名称，作为静态参数或作为用户数据存储中缓存的数据。 架构缓存的一个示例是`LocalSchemaFile`中的类型提供程序中的参数`FSharp.Data.TypeProviders`程序集。 在这些提供程序实现中，此静态参数指示要指定本地文件而不是通过网络访问数据源中使用的架构信息的类型提供程序。 若要使用缓存的架构信息，还必须设置静态参数`ForceUpdate`到`false`。 可以使用类似的技术来启用联机和脱机数据访问。

### <a name="backing-assembly"></a>备份程序集

编译时`.dll`或`.exe`文件，后备.dll 文件生成的类型静态链接到生成的程序集。 通过复制到最终的程序集中的后备程序集的中间语言 (IL) 类型定义和任何托管的资源来创建此链接。 当你使用 F # Interactive 时，后备.dll 文件不复制，并且改为直接加载到 F # 交互的进程。

### <a name="exceptions-and-diagnostics-from-type-providers"></a>异常和从类型提供程序的诊断

从提供的类型的所有成员的所有使用可能会都引发异常。 在所有情况下，类型提供程序引发异常，如果宿主编译器就属性错误特定类型提供程序。

- 类型提供程序异常应永远不会导致内部编译器错误。

- 类型提供程序不能报告警告。

- 类型提供程序托管在 F # 编译器、 F # 开发环境中，或 F # Interactive 中，则也将同时捕获从该提供程序的所有异常。 消息属性始终错误文本中，并且没有堆栈跟踪将出现。 如果你要引发异常，则可以引发下面的示例： `System.NotSupportedException`， `System.IO.IOException`， `System.Exception`。

#### <a name="providing-generated-types"></a>提供生成的类型

到目前为止，本文档介绍了如何提供已擦除的类型。 你可以使用 F # 中的类型提供程序机制来提供生成的类型，添加到用户的程序的实际.NET 类型定义为。 你必须引用生成提供通过使用的类型定义的类型。

```fsharp
open Microsoft.FSharp.TypeProviders 

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

F # 3.0 发行版的一部分的 ProvidedTypes 0.2 帮助器代码仅提供有限支持用于提供生成的类型。 以下语句为真，生成的类型定义：

- `isErased` 必须设置为`false`。

- 必须将生成的类型添加到新构造`ProvidedAssembly()`，它表示生成的代码片段的容器。

- 提供程序必须具有具有磁盘上的匹配.dll 文件的实际后备.NET.dll 文件的程序集。


## <a name="rules-and-limitations"></a>规则和限制

当你编写类型提供程序时，请记住以下规则和限制。


### <a name="provided-types-must-be-reachable"></a>提供的类型必须是可访问

所有提供的类型应该是可从非嵌套类型。 非嵌套类型可以在调用`TypeProviderForNamespaces`构造函数或调用`AddNamespace`。 例如，如果提供程序提供一种类型`StaticClass.P : T`，你必须确保 T 为非嵌套类型或嵌套在下一个。

例如，某些提供程序都具有静态类如`DataTypes`，包含这些`T1, T2, T3, ...`类型。 否则，该错误指出找对程序集 A 中的 T 类型的引用，但该程序集中找不到类型。 如果出现此错误，请验证可以从提供程序类型到达所有的子类型。 注意： 这些`T1, T2, T3...`类型统称为*即时上*类型。 请记住将它们放在可访问的命名空间或父类型。

### <a name="limitations-of-the-type-provider-mechanism"></a>类型提供程序机制的限制

F # 中的类型提供程序机制具有以下限制：

- 提供泛型类型或提供的泛型方法，不支持 F # 中的类型提供程序的底层基础架构。

- 机制不支持使用静态参数的嵌套的类型。

## <a name="development-tips"></a>开发提示

你可能会发现以下提示很有帮助在开发过程中。

### <a name="run-two-instances-of-visual-studio"></a>运行 Visual Studio 的两个实例

可以在一个实例中开发类型提供程序和测试另一部分中的提供程序，因为测试 IDE 将获取一个锁防止类型提供程序正在重新生成的.dll 文件。 因此，您必须关闭 Visual Studio 的第二个实例，而在第一个实例中，生成提供程序，然后你必须重新打开第二个实例后生成提供程序。

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>通过调用 fsc.exe 调试类型提供程序

你可以通过使用以下工具调用类型提供程序：

- fsc.exe （F # 命令行编译器）

- fsi.exe （F # Interactive 编译器）

- devenv.exe (Visual Studio)

您通常可以通过在测试脚本文件 (例如，script.fsx) 上使用 fsc.exe 非常轻松地调试类型提供程序。 你可以启动命令提示符下的调试器。

```
  devenv /debugexe fsc.exe script.fsx
```

  你可以使用打印到 stdout 日志记录。


## <a name="see-also"></a>另请参阅

* [类型提供程序](index.md)

* [类型提供程序 SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK)

