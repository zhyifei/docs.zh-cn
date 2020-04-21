---
title: F# 代码格式设置准则
description: 了解 F# 代码的格式设置指南。
ms.date: 11/04/2019
ms.openlocfilehash: b8be70dd29a04e71614308164e541b99a1724305
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739551"
---
# <a name="f-code-formatting-guidelines"></a>F# 代码格式设置准则

本文提供了如何设置代码格式的指南，以便 F# 代码具有：

* 更清晰
* 根据可视化工作室和其他编辑器中格式工具应用的约定
* 类似于其他在线代码

这些准则基于[由安-邓潘](https://github.com/dungpa)[对 F# 格式约定的全面指南](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md)。

## <a name="general-rules-for-indentation"></a>缩进的一般规则

默认情况下，F# 使用大量空白。 以下准则旨在就如何应对可能带来的一些挑战提供指导。

### <a name="using-spaces"></a>使用空格

当需要缩进时，必须使用空格，而不是选项卡。 至少需要一个空格。 您的组织可以创建编码标准来指定用于缩进的空间数;在发生缩进的每个级别，2 个、3 个或 4 个缩进空间是典型的。

**我们建议每个缩进四个空格。**

这就是说，程序缩进是一个主观问题。 变异是可以的，但您应该遵循的第一条规则是*缩进的一致性*。 选择一种普遍接受的缩进样式，并在代码库中系统地使用它。

## <a name="formatting-white-space"></a>设置空白格式

F# 对空白敏感。 尽管空白的大多数语义都由适当的缩进覆盖，但还有其他一些需要考虑。

### <a name="formatting-operators-in-arithmetic-expressions"></a>算术表达式中的运算符格式

始终在二进制算术表达式周围使用空白：

```fsharp
let subtractThenAdd x = x - 1 + 3
```

一元`-`运算符应始终立即跟随他们否定的值：

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

在`-`运算符之后添加空格字符可能会导致其他人混淆。

总之，始终：

* 环绕具有空白的二进制运算符
* 一个一元运算符后，永远不会有尾随空格

二进制算术运算符准则尤为重要。 如果无法包围二进制`-`运算符，当与某些格式选项结合使用时，可能会导致将其解释为一元`-`。

### <a name="surround-a-custom-operator-definition-with-white-space"></a>用空格环绕自定义运算符定义

始终使用空白环绕运算符定义：

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

对于任何以开头`*`且具有多个字符的自定义运算符，都需要向定义开头添加一个空格以避免编译器歧义。 因此，我们建议您只需使用单个空格字符括括所有运算符的定义。

### <a name="surround-function-parameter-arrows-with-white-space"></a>带空格的环绕函数参数箭头

定义函数的签名时，请使用`->`符号周围的空白：

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a>带空格的环绕函数参数

定义函数时，在每个参数周围使用空白。

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-member-definitions"></a>将参数放在长成员定义的新行上

如果您有很长的成员定义，则将参数放在新行上，并缩进它们一个作用域。

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

这也适用于构造函数：

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a>类型注释

#### <a name="right-pad-function-argument-type-annotations"></a>右垫函数参数类型注释

使用类型注释定义参数时，在`:`符号之后使用空格：

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a>带空格的环绕返回类型注释

在允许绑定函数或值类型注释（在函数的情况下返回类型）中，在`:`符号之前和之后使用空格：

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a>设置空白行的格式

* 使用两条空白行分隔顶级函数和类定义。
* 类中的方法定义由单个空白行分隔。
* 额外的空白行可用于（谨慎）分隔相关函数组。 在一堆相关的单行（例如，一组虚拟实现）之间可以省略空白行。
* 请谨慎在函数中使用空白行来指示逻辑部分。

## <a name="formatting-comments"></a>设置注释的格式

通常更喜欢多个双斜杠注释，而不是 ML 样式块注释。

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

内联注释应将第一个字母大写。

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>命名约定

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>对类绑定、表达式绑定和模式绑定值和函数使用 camelCase

对于绑定为局部变量的所有名称或在模式匹配和函数定义中，使用 camelCase 是常见且公认的 F# 样式。

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

类中的本地绑定函数还应使用 camelCase。

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>将 CamelCase 用于模块绑定的公共函数

当模块绑定函数是公共 API 的一部分时，它应使用 camelCase：

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>将 camelCase 用于内部和私有模块绑定值和函数

对专用模块绑定值使用 camelCase，包括：

* 脚本中的临时函数

* 组成模块或类型的内部实现的值

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>使用 camelCase 进行参数

所有参数都应根据 .NET 命名约定使用 camelCase。

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>将帕斯卡包用于模块

所有模块（顶级、内部、私有、嵌套）都应使用 PascalCase。

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>将 PascalCase 用于类型声明、成员和标签

类、接口、结构、枚举、委托、记录和受歧视的联合都应使用 PascalCase 命名。 记录和受歧视结合的类型和标签中的成员也应使用 PascalCase。

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>使用 PascalCase 进行 .NET 固有的构造

命名空间、异常、事件和项目/`.dll`名称也应使用 PascalCase。 这不仅使来自其他 .NET 语言的使用者感觉更自然，而且与您可能遇到的 .NET 命名约定一致。

### <a name="avoid-underscores-in-names"></a>避免在名称中下划线

从历史上看，某些 F# 库在名称中使用了下划线。 但是，这不再被广泛接受，部分原因是它与 .NET 命名约定冲突。 也就是说，一些 F# 程序员使用强调很大，部分原因是历史原因，宽容和尊重很重要。 但是，请注意，对于是否使用该样式，其他人通常不喜欢这种风格。

一个例外包括与本机组件进行互操作，其中下划线很常见。

### <a name="use-standard-f-operators"></a>使用标准 F# 运算符

以下运算符在 F# 标准库中定义，应使用而不是定义等效项。 建议使用这些运算符，因为它会使代码更具可读性和惯用性。 具有 OCaml 或其他函数编程语言背景的开发人员可能习惯于不同的习语。 下面的列表总结了推荐的 F# 运算符。

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>使用泛型的前缀语法`Foo<T>`（ ） 优先于后缀语法`T Foo`（ ）

F# 既继承命名泛型类型的后缀 ML 样式（例如`int list`），也继承前缀 .NET 样式（例如）。 `list<int>` 首选 .NET 样式，但五种特定类型除外：

1. 对于 F# 列表，请使用后修复窗体`int list`：而不是`list<int>`。
2. 对于 F# 选项，请使用后修复窗体`int option`：而不是`option<int>`。
3. 对于 F# 值选项，请使用后修复窗体`int voption`：而不是`voption<int>`。
4. 对于 F# 数组，请使用句法名称`int[]`而不是`int array`或`array<int>`。
5. 对于参考单元格，使用`int ref`而不是`ref<int>``Ref<int>`或 。

对于所有其他类型，请使用前缀窗体。

## <a name="formatting-tuples"></a>格式化元数

元组实例化应为括号，其中的分隔逗号应后跟单个空格，例如： `(1, 2)`。 `(x, y, z)`

在组合的图案匹配中省略括号是通常接受的：

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

如果元组是函数的返回值，则通常也接受省略括号：

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

总之，首选括号组实例化，但当使用组合体进行模式匹配或返回值时，避免括号被认为是好的。

## <a name="formatting-discriminated-union-declarations"></a>格式化受歧视的工会声明

类型定义`|`中按四个空格缩进：

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a>格式化受歧视的工会

跨多行拆分的实例化歧视联合应为包含的数据提供具有缩进的新作用域：

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

闭合括号也可以位于新行上：

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>格式化记录声明

按四`{`个空格在类型定义中缩进，并在同一行上启动字段列表：

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

如果要声明接口实现或记录上的成员，最好在新行上放置首开令牌，在新行上放置结束令牌：

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a>设置记录格式

短记录可以写在一行：

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

较长的记录应使用新行用于标签：

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

将首开令牌放在新行上，内容在一个作用域上选项卡，如果是：

* 在具有不同缩进作用域的代码中移动记录
* 将它们放入函数中

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

相同的规则适用于列表和数组元素。

## <a name="formatting-copy-and-update-record-expressions"></a>格式化复制和更新记录表达式

复制和更新记录表达式仍然是记录，因此适用类似的准则。

短表达式可以适合在一行上：

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

较长的表达式应使用新行：

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

与记录指南一样，您可能希望为大括号专用单独的行，并将一个范围缩进到右侧。 在某些特殊情况下，例如使用可选的无括号包装值，您可能需要在一行上保留大括号：

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a>设置列表和数组的格式

使用`x :: l``::`运算符周围的空格写入（`::`是一个内缀运算符，因此被空格包围）。

在单行上声明的列表和数组应在开口括号后和右括号之前具有空格：

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

始终在两个不同的大括号运算符之间至少使用一个空格。 例如，在 和`[`之间留一个`{`空格。

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

同样的准则也适用于元组的列表或数组。

跨行拆分的列表和数组遵循与记录类似的规则：

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

与记录一样，在自己的行上声明首括号和关闭括号将使移动代码和管道进入功能变得更加容易。

以编程方式生成数组和列表时，请`->`首选`do ... yield`始终生成值时：

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

在可能有条件地生成数据或可能需要`yield`计算连续表达式的情况下，需要指定较旧版本的 F# 语言。 首选省略这些`yield`关键字，除非您必须使用较旧的 F# 语言版本进行编译：

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

在某些情况下，`do...yield`可能有助于可读性。 这些案件虽然是主观的，但应当加以考虑。

## <a name="formatting-if-expressions"></a>格式化表达式

条件缩进取决于构成条件的表达式的大小。 如果`cond``e1`和`e2`短，只需将它们写在一行上：

```fsharp
if cond then e1 else e2
```

如果`cond`或`e1``e2`较长，但不是多行：

```fsharp
if cond
then e1
else e2
```

如果任何表达式是多行的：

```fsharp
if cond then
    e1
else
    e2
```

具有`elif`和`else``if`的多个条件与

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>模式匹配构造

`|`对匹配的每个子句使用，没有缩进。 如果表达式较短，则可以考虑使用单行，如果每个子表达式也很简单。

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

如果模式匹配箭头右侧的表达式太大，将其移动到下一行，从 缩进一`match`/`|`步。

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

以 开头`function`的匿名函数的模式匹配通常不应缩进太远。 例如，按照如下方式缩进一个作用域可以：

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

在`let`函数中定义的`let rec`或应在 启动后缩进四个空格中的`let`模式匹配，即使`function`使用了关键字：

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

我们不建议对齐箭头。

## <a name="formatting-trywith-expressions"></a>设置尝试/包含表达式的格式

异常类型的模式匹配应缩进与 的级别`with`相同。

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a>格式化功能参数应用程序

通常，大多数函数参数应用都在同一行上完成。

如果要将参数应用于新行上的函数，请按一个作用域缩进参数。

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

相同的准则适用于 lambda 表达式和函数参数。 如果 lambda 表达式的正文，正文可以有另一条线，由一个作用域缩进

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

但是，如果 lambda 表达式的正文是多行，请考虑将其分解为单独的函数，而不是将多行构造作为单个参数应用于函数。

### <a name="formatting-infix-operators"></a>格式化固定运算符

按空格分隔运算符。 此规则的明显例外是`!`和`.`运算符。

infix 表达式可以在同一列上提供阵容：

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>格式化管道运算符

管道`|>`操作员应位于其操作的表达式下方。

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a>格式化模块

本地模块中的代码必须相对于模块缩进，但顶层模块中的代码不应缩进。 命名空间元素不必缩进。

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a>设置对象表达式和接口的格式

对象表达式和接口应与在四个空格后缩进`member`的方式对齐。

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>设置表达式中的空白格式

避免 F# 表达式中的无关空白。

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

命名参数也不应围绕 ： `=`

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a>设置属性的格式

[属性](../language-reference/attributes.md)放置在构造上方：

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a>参数上的格式设置属性

属性也可以是参数上的放置。 在这种情况下，将放在与参数相同的行上，并在名称之前：

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>设置多个属性的格式

当多个属性应用于不是参数的构造时，应放置这些属性，以便每行有一个属性：

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

应用于参数时，它们必须位于同一`;`行上，并由分隔符分隔。

## <a name="formatting-literals"></a>格式化文本

使用 属性`Literal`的[F# 文本](../language-reference/literals.md)应将属性放在自己的行上，并使用 PascalCase 命名：

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

避免将属性放在与值相同的行上。
