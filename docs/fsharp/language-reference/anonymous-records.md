---
title: 匿名记录
description: 了解如何使用构造和使用匿名记录，这种语言功能有助于处理数据。
ms.date: 06/12/2019
ms.openlocfilehash: 061fd3279c84b9a3161c687d9392947ee7ce9c83
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453021"
---
# <a name="anonymous-records"></a><span data-ttu-id="415e3-103">匿名记录</span><span class="sxs-lookup"><span data-stu-id="415e3-103">Anonymous Records</span></span>

<span data-ttu-id="415e3-104">匿名记录是命名值的简单聚合，在使用之前无需声明。</span><span class="sxs-lookup"><span data-stu-id="415e3-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="415e3-105">可以将它们声明为结构或引用类型。</span><span class="sxs-lookup"><span data-stu-id="415e3-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="415e3-106">默认情况下，它们是引用类型。</span><span class="sxs-lookup"><span data-stu-id="415e3-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="415e3-107">语法</span><span class="sxs-lookup"><span data-stu-id="415e3-107">Syntax</span></span>

<span data-ttu-id="415e3-108">下面的示例演示了匿名记录语法。</span><span class="sxs-lookup"><span data-stu-id="415e3-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="415e3-109">以 `[item]` 分隔的项是可选的。</span><span class="sxs-lookup"><span data-stu-id="415e3-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="415e3-110">基本用法</span><span class="sxs-lookup"><span data-stu-id="415e3-110">Basic usage</span></span>

<span data-ttu-id="415e3-111">匿名记录最适用于不需要F#在实例化之前声明的记录类型。</span><span class="sxs-lookup"><span data-stu-id="415e3-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="415e3-112">例如，在这里，你可以如何与生成匿名记录的函数进行交互：</span><span class="sxs-lookup"><span data-stu-id="415e3-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

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

<span data-ttu-id="415e3-113">下面的示例使用采用匿名记录作为输入的 `printCircleStats` 函数对上一个进行扩展：</span><span class="sxs-lookup"><span data-stu-id="415e3-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

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

<span data-ttu-id="415e3-114">使用不具有与输入类型相同的 "shape" 的任何匿名记录类型调用 `printCircleStats` 将无法编译：</span><span class="sxs-lookup"><span data-stu-id="415e3-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="415e3-115">结构匿名记录</span><span class="sxs-lookup"><span data-stu-id="415e3-115">Struct anonymous records</span></span>

<span data-ttu-id="415e3-116">匿名记录还可以定义为具有可选 `struct` 关键字的结构。</span><span class="sxs-lookup"><span data-stu-id="415e3-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="415e3-117">下面的示例通过生成和使用结构匿名记录来补充前一个示例：</span><span class="sxs-lookup"><span data-stu-id="415e3-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

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

### <a name="structness-inference"></a><span data-ttu-id="415e3-118">Structness 推理</span><span class="sxs-lookup"><span data-stu-id="415e3-118">Structness inference</span></span>

<span data-ttu-id="415e3-119">结构匿名记录还允许 "structness 推理"，在这种情况下，你无需在调用站点指定 `struct` 关键字。</span><span class="sxs-lookup"><span data-stu-id="415e3-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="415e3-120">在此示例中，当调用 `printCircleStats`时，将 elide `struct` 关键字：</span><span class="sxs-lookup"><span data-stu-id="415e3-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="415e3-121">如果输入类型不是结构匿名记录，则指定 `struct` 的反向模式-将无法进行编译。</span><span class="sxs-lookup"><span data-stu-id="415e3-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="415e3-122">在其他类型中嵌入匿名记录</span><span class="sxs-lookup"><span data-stu-id="415e3-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="415e3-123">声明事例为记录的可[区分联合](discriminated-unions.md)很有用。</span><span class="sxs-lookup"><span data-stu-id="415e3-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="415e3-124">但是，如果记录中的数据与可区分联合的类型相同，则必须将所有类型定义为互相递归。</span><span class="sxs-lookup"><span data-stu-id="415e3-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="415e3-125">使用匿名记录可避免此限制。</span><span class="sxs-lookup"><span data-stu-id="415e3-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="415e3-126">下面是与模式匹配的示例类型和函数：</span><span class="sxs-lookup"><span data-stu-id="415e3-126">What follows is an example type and function that pattern matches over it:</span></span>

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

## <a name="copy-and-update-expressions"></a><span data-ttu-id="415e3-127">复制和更新表达式</span><span class="sxs-lookup"><span data-stu-id="415e3-127">Copy and update expressions</span></span>

<span data-ttu-id="415e3-128">匿名记录支持带有[复制和更新表达式](copy-and-update-record-expressions.md)的构造。</span><span class="sxs-lookup"><span data-stu-id="415e3-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="415e3-129">例如，下面介绍了如何构造用于复制现有数据的匿名记录的新实例：</span><span class="sxs-lookup"><span data-stu-id="415e3-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="415e3-130">但是，与命名记录不同，匿名记录允许您用复制和更新表达式构造完全不同的窗体。</span><span class="sxs-lookup"><span data-stu-id="415e3-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="415e3-131">下面的示例使用上一示例中的相同匿名记录，并将其扩展为新的匿名记录：</span><span class="sxs-lookup"><span data-stu-id="415e3-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="415e3-132">还可以通过命名记录的实例构造匿名记录：</span><span class="sxs-lookup"><span data-stu-id="415e3-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="415e3-133">您还可以将数据复制到引用和结构匿名记录：</span><span class="sxs-lookup"><span data-stu-id="415e3-133">You can also copy data to and from reference and struct anonymous records:</span></span>

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

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="415e3-134">匿名记录的属性</span><span class="sxs-lookup"><span data-stu-id="415e3-134">Properties of anonymous records</span></span>

<span data-ttu-id="415e3-135">匿名记录有很多特性，这些特性对于完全理解它们的使用方式至关重要。</span><span class="sxs-lookup"><span data-stu-id="415e3-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="415e3-136">匿名记录为名义</span><span class="sxs-lookup"><span data-stu-id="415e3-136">Anonymous records are nominal</span></span>

<span data-ttu-id="415e3-137">匿名记录是[名义类型](https://en.wikipedia.org/wiki/Nominal_type_system)。</span><span class="sxs-lookup"><span data-stu-id="415e3-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="415e3-138">它们最适用于不需要前期声明的命名[记录](records.md)类型（也称名义）。</span><span class="sxs-lookup"><span data-stu-id="415e3-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="415e3-139">请考虑以下示例，其中包含两个匿名记录声明：</span><span class="sxs-lookup"><span data-stu-id="415e3-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="415e3-140">`x` 和 `y` 值具有不同的类型，并且彼此不兼容。</span><span class="sxs-lookup"><span data-stu-id="415e3-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="415e3-141">它们不是可相等的，也不是可比较的。</span><span class="sxs-lookup"><span data-stu-id="415e3-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="415e3-142">为了说明这一点，请考虑等效的命名记录：</span><span class="sxs-lookup"><span data-stu-id="415e3-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="415e3-143">如果匿名记录与与类型等效性或比较相关的已命名记录等效项进行比较，则没有什么差异。</span><span class="sxs-lookup"><span data-stu-id="415e3-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="415e3-144">匿名记录使用结构相等性和比较</span><span class="sxs-lookup"><span data-stu-id="415e3-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="415e3-145">与记录类型类似，匿名记录是结构可相等和可比较的。</span><span class="sxs-lookup"><span data-stu-id="415e3-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="415e3-146">如果所有构成类型都支持相等和比较（如记录类型），则此值为 true。</span><span class="sxs-lookup"><span data-stu-id="415e3-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="415e3-147">若要支持相等或比较，两个匿名记录必须具有相同的 "形状"。</span><span class="sxs-lookup"><span data-stu-id="415e3-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="415e3-148">匿名记录可序列化</span><span class="sxs-lookup"><span data-stu-id="415e3-148">Anonymous records are serializable</span></span>

<span data-ttu-id="415e3-149">可以像处理命名记录一样序列化匿名记录。</span><span class="sxs-lookup"><span data-stu-id="415e3-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="415e3-150">下面是使用[newtonsoft.json](https://www.nuget.org/packages/Newtonsoft.Json/)的示例：</span><span class="sxs-lookup"><span data-stu-id="415e3-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip') 

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

<span data-ttu-id="415e3-151">匿名记录适用于通过网络发送轻型数据，无需为前面的序列化/反序列化类型定义域。</span><span class="sxs-lookup"><span data-stu-id="415e3-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="415e3-152">匿名记录与C#匿名类型互操作</span><span class="sxs-lookup"><span data-stu-id="415e3-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="415e3-153">可以使用需要使用[ C#匿名类型](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)的 .net API。</span><span class="sxs-lookup"><span data-stu-id="415e3-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="415e3-154">C#匿名类型与使用匿名记录互操作非常简单。</span><span class="sxs-lookup"><span data-stu-id="415e3-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="415e3-155">下面的示例演示如何使用匿名记录调用需要匿名类型的[LINQ](../../csharp/programming-guide/concepts/linq/index.md)重载：</span><span class="sxs-lookup"><span data-stu-id="415e3-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

<span data-ttu-id="415e3-156">在整个 .NET 中使用的其他许多 Api 需要使用传入匿名类型。</span><span class="sxs-lookup"><span data-stu-id="415e3-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="415e3-157">匿名记录是用于处理它们的工具。</span><span class="sxs-lookup"><span data-stu-id="415e3-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="415e3-158">限制</span><span class="sxs-lookup"><span data-stu-id="415e3-158">Limitations</span></span>

<span data-ttu-id="415e3-159">匿名记录在使用时有一些限制。</span><span class="sxs-lookup"><span data-stu-id="415e3-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="415e3-160">有些是其设计固有的，但其他一些则适合更改。</span><span class="sxs-lookup"><span data-stu-id="415e3-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="415e3-161">模式匹配的限制</span><span class="sxs-lookup"><span data-stu-id="415e3-161">Limitations with pattern matching</span></span>

<span data-ttu-id="415e3-162">匿名记录不支持模式匹配，这与命名记录不同。</span><span class="sxs-lookup"><span data-stu-id="415e3-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="415e3-163">有以下三个原因：</span><span class="sxs-lookup"><span data-stu-id="415e3-163">There are three reasons:</span></span>

1. <span data-ttu-id="415e3-164">与命名的记录类型不同，模式必须为匿名记录的每个字段提供帐户。</span><span class="sxs-lookup"><span data-stu-id="415e3-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="415e3-165">这是因为匿名记录不支持结构子类型化–它们是名义类型。</span><span class="sxs-lookup"><span data-stu-id="415e3-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="415e3-166">由于为（1），因此无法在模式匹配表达式中添加其他模式，因为每个 distinct 模式将意味着不同的匿名记录类型。</span><span class="sxs-lookup"><span data-stu-id="415e3-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="415e3-167">由于（3），任何匿名记录模式比使用 "点" 表示法更详细。</span><span class="sxs-lookup"><span data-stu-id="415e3-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="415e3-168">有一个开放语言建议，[允许在有限的上下文中匹配模式](https://github.com/fsharp/fslang-suggestions/issues/713)。</span><span class="sxs-lookup"><span data-stu-id="415e3-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="415e3-169">可变性限制</span><span class="sxs-lookup"><span data-stu-id="415e3-169">Limitations with mutability</span></span>

<span data-ttu-id="415e3-170">目前不能使用 `mutable` 数据定义匿名记录。</span><span class="sxs-lookup"><span data-stu-id="415e3-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="415e3-171">有一种[开放语言建议](https://github.com/fsharp/fslang-suggestions/issues/732)，允许使用可变数据。</span><span class="sxs-lookup"><span data-stu-id="415e3-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="415e3-172">结构匿名记录的限制</span><span class="sxs-lookup"><span data-stu-id="415e3-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="415e3-173">不能将结构匿名记录声明为 `IsByRefLike` 或 `IsReadOnly`。</span><span class="sxs-lookup"><span data-stu-id="415e3-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="415e3-174">对于 `IsByRefLike` 和 `IsReadOnly` 匿名记录，有一种[开放语言建议](https://github.com/fsharp/fslang-suggestions/issues/712)。</span><span class="sxs-lookup"><span data-stu-id="415e3-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
