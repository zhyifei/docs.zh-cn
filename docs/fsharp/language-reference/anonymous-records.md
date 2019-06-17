---
title: 匿名的记录
description: 了解如何使用构造和使用一种语言功能，可帮助与操作数据的匿名记录。
ms.date: 06/12/2019
ms.openlocfilehash: e576210d4fb76ccfd09f8feb157ef4542aa94ccf
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041801"
---
# <a name="anonymous-records"></a>匿名的记录

匿名记录是无需使用之前声明的命名值的简单聚合。 可以将它们声明为结构或引用类型。 它们是默认情况下引用类型。

## <a name="syntax"></a>语法

下面的示例演示的匿名记录语法。 项分隔为`[item]`都是可选的。

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>基本用法

匿名记录最佳的想法作为F#记录不需要在实例化之前声明的类型。

例如，此处您可以使用函数进行交互的方式，生成的匿名记录：

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

下面的示例与前一个扩展`printCircleStats`采用作为输入的匿名记录函数：

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

调用`printCircleStats`与任何不具有相同的"形状"，如输入的类型将无法进行编译的匿名记录类型：

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>结构的匿名记录

此外可以定义作为结构，它有可选的匿名记录`struct`关键字。 下面的示例生成和使用结构的匿名记录与前一增加的内容：

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

### <a name="structness-inference"></a>Structness 推理

结构匿名记录还允许为"structness 推理"不需要指定`struct`调用站点上的关键字。 在此示例中，您 elide`struct`关键字调用时`printCircleStats`:

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

反向模式-指定`struct`时输入的类型不是结构的匿名记录-将无法进行编译。

## <a name="embedding-anonymous-records-within-other-types"></a>嵌入内其他类型的匿名记录

可用于声明[可区分联合](discriminated-unions.md)的记录。 但是，在记录中的数据是否可区分联合类型相同，必须将所有类型都定义为相互递归的。 使用匿名记录可避免此限制。 下面是一个示例通过其类型和函数匹配该模式：

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named for Manager and Executive would require mutually recursive definitions.
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

匿名记录支持与构造[复制和更新表达式](copy-and-update-record-expressions.md)。 例如，下面是如何构造的新实例将复制的一个现有的匿名记录数据：

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

但是，命名记录与匿名记录，可构造副本完全不同的窗体和更新表达式。 下面的示例采用相同的匿名记录上一示例中，并将其扩展到新的匿名记录：

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

还有可能构造命名记录的实例中的匿名记录：

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

此外可以将数据复制到和从引用和结构的匿名记录：

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

匿名记录具有大量特征对完全了解如何使用它们至关重要的。

### <a name="anonymous-records-are-nominal"></a>匿名记录是名义上

记录匿名[名义类型](https://en.wikipedia.org/wiki/Nominal_type_system)。 它们是最佳的思想，如名为[记录](records.md)类型 （这也是名义上的） 不需要预先声明的。

请考虑下面的示例使用两个匿名记录声明：

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

`x`和`y`值具有不同的类型和与另一个不兼容。 它们不是可以相等和不可比较。 为了说明这一点，请考虑命名的记录等效:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

没有任何与它们命名的记录的等效项时，就类型等效性或比较的匿名记录有关本质上是不同的内容。

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>匿名的记录，请使用结构相等和比较

记录类型，如匿名记录是结构是可以相等和比较。 这只是如果所有构成类型都支持相等性和比较，如与记录类型，则返回 true。 若要支持相等或比较，两个匿名记录必须具有相同的"形状"。

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>匿名记录是可序列化

就像可以使用命名的记录一样，可以序列化匿名记录。 下面是一个示例使用[Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

匿名记录可用于通过网络而无需定义用于序列化/反序列化类型预先域发送轻型的数据。

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>与的匿名记录进行互操作C#匿名类型

可以使用需要使用.NET API [ C#匿名类型](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)。 C#匿名类型是普通与进行互操作使用的匿名记录。 下面的示例演示如何使用匿名记录，以调用[LINQ](../../csharp/programming-guide/concepts/linq/index.md)需要匿名类型的重载：

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

有多种其他需要传递一个匿名类型中使用的 Api 在.NET 中使用。 匿名记录是用于使用这些工具。

## <a name="limitations"></a>限制

匿名记录其使用情况中具有一些限制。 某些可归结于它们的设计，但有些则是易于更改。

### <a name="limitations-with-pattern-matching"></a>模式匹配的限制

模式匹配，命名记录与不支持匿名记录。 有三个原因：

1. 一种模式必须为每个字段的匿名记录，与名为的记录类型不同的帐户。 这是因为匿名记录不支持结构子类型化的 – 名义类型。
2. (1)，因此没有在模式匹配表达式中，有其他模式能为每个非重复模式的含义不同的匿名记录类型。
3. 由于 (3)，任何匿名记录模式是使用"dot"表示法相比更详细。

没有到打开语言建议[允许在模式匹配有限上下文](https://github.com/fsharp/fslang-suggestions/issues/713)。

### <a name="limitations-with-mutability"></a>可变性的限制

它不是当前无法定义使用的匿名记录`mutable`数据。 没有[打开语言建议](https://github.com/fsharp/fslang-suggestions/issues/732)允许可变的数据。

### <a name="limitations-with-struct-anonymous-records"></a>结构的匿名记录的限制

不能声明为匿名记录的结构`IsByRefLike`或`IsReadOnly`。 没有[打开语言建议](https://github.com/fsharp/fslang-suggestions/issues/712)到有关`IsByRefLike`和`IsReadOnly`匿名记录。
