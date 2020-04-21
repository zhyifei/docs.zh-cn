---
title: 匿名记录
description: 了解如何使用构造和使用匿名记录，匿名记录是帮助处理数据的语言功能。
ms.date: 06/12/2019
ms.openlocfilehash: 121f0f638dff2ae529b2488d8e3b1ad9c064cf90
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738504"
---
# <a name="anonymous-records"></a>匿名记录

匿名记录是命名值的简单聚合，在使用前不需要声明。 您可以将它们声明为结构类型或引用类型。 默认情况下，它们是引用类型。

## <a name="syntax"></a>语法

以下示例演示了匿名记录语法。 项分隔为`[item]`可选。

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>基本用法

匿名记录最好视为 F# 记录类型，不需要在实例化之前声明。

例如，在这里，如何与生成匿名记录的函数进行交互：

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

下面的示例扩展了上一`printCircleStats`个示例，该函数将匿名记录作为输入：

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let printCircleStats r (stats: {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

使用`printCircleStats`与输入类型没有相同"形状"的任何匿名记录类型的调用将无法编译：

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>结构匿名记录

匿名记录也可以定义为使用可选`struct`关键字进行结构。 以下示例通过生成和使用结构匿名记录来增强前一个示例：

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    // Note that the keyword comes before the '{| |}' brace pair
    struct {| Area = a; Circumference = c; Diameter = d |}

// the 'struct' keyword also comes before the '{| |}' brace pair when declaring the parameter type
let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

### <a name="structness-inference"></a>结构推理

结构匿名记录还允许"结构推理"，其中不需要在呼叫站点指定`struct`关键字。 在此示例中，在调用`struct``printCircleStats`时删除关键字：

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

反向模式 （指定`struct`输入类型何时不是结构匿名记录 ） 将无法编译。

## <a name="embedding-anonymous-records-within-other-types"></a>将匿名记录嵌入其他类型的

声明案例为记录[的受歧视工会](discriminated-unions.md)是很有用的。 但是，如果记录中的数据与受区别的联合类型相同，则必须将所有类型定义为互递归。 使用匿名记录可避免此限制。 以下是模式与它匹配的示例类型和函数：

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named record for Manager and Executive would require mutually recursive definitions.
type Employee =
    | Engineer of FullName
    | Manager of {| Name: FullName; Reports: Employee list |}
    | Executive of {| Name: FullName; Reports: Employee list; Assistant: Employee |}

let getFirstName e =
    match e with
    | Engineer fullName -> fullName.FirstName
    | Manager m -> m.Name.FirstName
    | Executive ex -> ex.Name.FirstName
```

## <a name="copy-and-update-expressions"></a>复制和更新表达式

匿名记录支持使用[复制和更新表达式构建](copy-and-update-record-expressions.md)。 例如，下面介绍如何构造复制现有数据的匿名记录的新实例：

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

但是，与命名记录不同，匿名记录允许您使用复制和更新表达式构造完全不同的窗体。 以下示例采用上一示例中的相同匿名记录，并将其扩展到新的匿名记录：

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

还可以从命名记录实例构造匿名记录：

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

您还可以将数据复制到引用和结构匿名记录：

```fsharp
// Copy data from a reference record into a struct anonymous record
type R1 = { X: int }
let r1 = { X = 1 }

let data1 = struct {| r1 with Y = 1 |}

// Copy data from a struct record into a reference anonymous record
[<Struct>]
type R2 = { X: int }
let r2 = { X = 1 }

let data2 = {| r1 with Y = 1 |}

// Copy the reference anonymous record data into a struct anonymous record
let data3 = struct {| data2 with Z = r2.X |}
```

## <a name="properties-of-anonymous-records"></a>匿名记录的属性

匿名记录具有许多特征，这些特征对于完全理解如何使用这些特征至关重要。

### <a name="anonymous-records-are-nominal"></a>匿名记录是名义上的

匿名记录是[名义类型](https://en.wikipedia.org/wiki/Nominal_type_system)。 它们最好视为不需要预先声明的命名[记录](records.md)类型（也是名义上的）。

请考虑以下包含两个匿名记录声明的示例：

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

`x`和`y`值的类型不同，并且彼此不兼容。 它们不相等，也不可比拟。 为了说明这一点，请考虑命名的记录等效项：

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

与命名的记录等效项相比，匿名记录在类型等效性或比较方面没有任何内在区别。

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>匿名记录使用结构相等性和比较

与记录类型一样，匿名记录在结构上是等同的，并且具有可比性。 仅当所有组成类型都支持相等性和比较性（如记录类型）时，才如此。 为了支持相等或比较，两个匿名记录必须具有相同的"形状"。

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>匿名记录可序列化

您可以像使用命名记录一样序列化匿名记录。 下面是一个使用[牛顿软的示例。](https://www.nuget.org/packages/Newtonsoft.Json/)

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip')

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

匿名记录可用于通过网络发送轻量级数据，而无需预先为序列化/反序列化类型定义域。

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>匿名记录与 C# 匿名类型互操作

可以使用需要使用[C# 匿名类型的](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).NET API。 使用匿名记录进行互操作的 C# 匿名类型微不足道。 下面的示例演示如何使用匿名记录来调用需要匿名类型的[LINQ](../../csharp/programming-guide/concepts/linq/index.md)重载：

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

在 .NET 中使用许多其他 API 需要使用匿名类型传递。 匿名记录是您处理这些记录的工具。

## <a name="limitations"></a>限制

匿名记录的使用有一些限制。 有些是其设计固有的，但另一些是可以改变的。

### <a name="limitations-with-pattern-matching"></a>模式匹配的限制

匿名记录不支持模式匹配，与命名记录不同。 有三个原因：

1. 模式必须考虑匿名记录的每个字段，这与命名的记录类型不同。 这是因为匿名记录不支持结构子类型 - 它们是标称类型。
2. 由于 （1），无法在模式匹配表达式中具有其他模式，因为每个不同的模式都意味着不同的匿名记录类型。
3. 由于 （3），任何匿名记录模式将比使用"点"表示法更详细。

有一个开放语言建议，[允许在有限的上下文中进行模式匹配](https://github.com/fsharp/fslang-suggestions/issues/713)。

### <a name="limitations-with-mutability"></a>具有可变性的限制

当前无法使用`mutable`数据定义匿名记录。 有一个[开放语言建议](https://github.com/fsharp/fslang-suggestions/issues/732)，以允许可变数据。

### <a name="limitations-with-struct-anonymous-records"></a>结构匿名记录的限制

无法将结构匿名记录声明为`IsByRefLike`或`IsReadOnly`。 对于`IsByRefLike`和`IsReadOnly`匿名记录，有一个[开放语言建议](https://github.com/fsharp/fslang-suggestions/issues/712)。
