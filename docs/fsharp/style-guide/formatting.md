---
title: 'F # 代码 formattin 指南'
description: '了解有关格式设置 F # 代码的准则。'
ms.date: 05/14/2018
ms.openlocfilehash: e5c700ca9ae3968243f11c1237b9e4b26e580dcf
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
---
# <a name="f-code-formatting-guidelines"></a>F # 代码格式设置准则

本文提供有关如何设置你的代码格式，使你的 F # 代码的准则：

* 通常被视为可读性
* 符合应用的 Visual Studio 中的工具和其他编辑器格式设置约定
* 类似于其他代码联机

这些指导原则基于[F # 格式设置约定的全面指南](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md)通过[Anh Dung Phan](https://github.com/dungpa)。

## <a name="general-rules-for-indentation"></a>用于缩进的一般规则

F # 默认使用有意义的空白。 以下准则旨在提供指导如何能够同时处理这可以施加一些难题。

### <a name="using-spaces"></a>使用空间

需要缩进时，你必须使用空间，不是制表符。 需要至少一个空格。 您的组织可以创建编码标准来指定要用于缩进; 的空格数典型的缩进的出现位置的每个级别的缩进的两个、 三个或四个空格。

**我们建议每个缩进 4 个空格。**

也就是说，缩进的程序是主观一回事。 变体是确定，但应遵循的第一个规则是*缩进的一致性*。 选择广为接受的缩进样式，并在你的基本代码整个系统地使用它。

## <a name="formatting-discriminated-union-declarations"></a>格式设置可区分联合声明

缩进`|`通过 4 个空格的类型定义中：

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

将拆分到多个行的实例化可区分联合应提供包含的数据具有缩进的新作用域：

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

右括号还可以将新行上：

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-tuples"></a>格式设置的元组

元组实例化应该用圆括号括起来，并且在分界逗号应跟一个空格，例如： `(1, 2)`， `(x, y, z)`。

广为接受的异常是省略括号中的元组模式匹配：

```fsharp
let (x, y) = z // Destructuring

match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-records"></a>格式设置的记录

可以在一个行中编写短记录：

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

较长的记录应使用标签的新行：

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

在同一行和上一个新行的结束标记上施加打开令牌也是正常的：

```fsharp
let rainbow = {
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
```

相同的规则适用于列表和数组元素。

## <a name="formatting-lists-and-arrays"></a>格式设置的列表和数组

编写`x :: l`与周围的空格`::`运算符 (`::`是中缀运算符，因此由空格括起来) 和`[1; 2; 3]`(`;`是分隔符，因此跟一个空格)。

始终使用两个不同的大括号类似运算符之间的至少一个空格。 例如，将保留之间留一个空格`[`和`{`。

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

列表和将拆分到多个行的数组遵循类似的规则，记录一样：

```fsharp
let pascalsTriangle = [|
    [|1|]
    [|1; 1|]
    [|1; 2; 1|]
    [|1; 3; 3; 1|]
    [|1; 4; 6; 4; 1|]
    [|1; 5; 10; 10; 5; 1|]
    [|1; 6; 15; 20; 15; 6; 1|]
    [|1; 7; 21; 35; 35; 21; 7; 1|]
    [|1; 8; 28; 56; 70; 56; 28; 8; 1|]
|]
```

## <a name="formatting-if-expressions"></a>如果格式设置表达式

条件语句的缩进量取决于把它们组合起来的表达式的大小。 如果`cond`，`e1`和`e2`很小，只需将它们写入在同一行中：

```fsharp
if cond then e1 else e2
```

如果`e1`和`cond`很小，但`e2`大：

```fsharp
if cond then e1
else
    e2
```

如果`e1`和`cond`大和`e2`小：

```fsharp
if cond then
    e1
else e2
```

如果所有表达式都都大：

```fsharp
if cond then
    e1
else
    e2
```

使用多个条件语句`elif`和`else`都在与同一作用域缩进`if`:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>模式匹配的构造

使用`|`对于无缩进的匹配项的每个子句。 如果表达式是短，你可以使用单个行。

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> _
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> _
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"

// OK
match l with [] -> false | _ :: _ -> true
```

如果模式匹配箭头右侧表达式而言太大，则将其移到下一行中的缩进一个步骤`match` / `|`。

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

模式匹配的匿名函数，通过启动`function`，应通常不缩进得太长。 例如，缩进一个作用域，如下所示是正常的：

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

通过定义的函数中的模式匹配`let`或`let rec`开始之后，应该进行缩进 4 个空格`let`，即使`function`使用关键字：

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

我们不建议对齐箭头。

## <a name="formatting-trywith-expressions"></a>格式设置的 try / 使用表达式

模式匹配的异常类型应为相同级别缩进`with`。

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

## <a name="formatting-function-parameter-application"></a>格式设置的函数参数应用程序

一般情况下，大多数函数参数应用程序是在同一行上完成。

如果你想要应用到一个新行上的函数的参数，将它们缩进一个作用域。

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

匿名函数参数可以是在下一步的行上或与无关联`fun`参数行上：

```fsharp
// OK
let printListWithOffset a list1 =
    List.iter (fun elem ->
        printfn "%d" (a + elem)) list1

// OK, but prefer previous
let printListWithOffset a list1 =
    List.iter (
        fun elem ->
            printfn "%d" (a + elem)) list1
```

### <a name="formatting-infix-operators"></a>格式设置的中缀运算符

用空格的单独运算符。 是此规则的明显例外`!`和`.`运算符。

中缀表达式是在同一列的 lineup 确定:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>格式设置管道运算符

管道`|>`应放在下方于正在操作的表达式行的开头：

```fsharp
// OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
               |> List.ofArray
               |> List.map (fun assm -> assm.GetTypes())
               |> Array.concat
               |> List.ofArray
               |> List.map (fun t -> t.GetMethods())
               |> Array.concat

// OK, but prefer previous
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

### <a name="formatting-modules"></a>格式设置的模块

本地模块中的代码必须缩进相对于该模块，但顶级模块中的代码不应缩进。 Namespace 元素无需进行缩进。

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

### <a name="formatting-object-expressions-and-interfaces"></a>格式设置的对象表达式和接口

对象表达式和接口应对齐的方式使用相同`member`正在缩进后 4 个空格。

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-whitespace-in-expressions"></a>格式设置表达式中的空格

请避免使用 F # 表达式中的多余空白。

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

命名自变量也不应有周围的空间`=`:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-blank-lines"></a>格式设置的空行

* 单独顶级函数和类定义替换为两个空白的行。
* 类中的方法定义由一个空行分隔。
* 可能 （尽量少） 使用额外的空白的行到单独的组相关的函数。 多个相关 one-liners （例如，虚拟实现一组） 之间，可以忽略空行。
* 使用空白的行在函数中，谨慎，以指示逻辑部分。

## <a name="formatting-comments"></a>格式设置的注释

通常选择多个双斜线注释而 ML 样式块注释。

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    Generally avoid these kinds of comments.
*)
```

内联注释应的首字母大写。

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>命名约定

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>使用驼峰匹配类绑定、 表达式绑定和绑定模式值和函数

是很常见，并且接受的 F # 要使用样式驼峰匹配的所有名称绑定为本地变量或在模式匹配和函数定义中。

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

类中的本地绑定函数还应使用驼峰匹配。

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>驼峰匹配用于内部和私有模块绑定值和函数

对于专用模块绑定值，其中包括使用驼峰匹配：

* 在脚本中的即席函数

* 组成的模块或类型的内部实现的值

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="avoid-underscores-in-names"></a>避免在名称中的下划线

从历史上看，某些 F # 库具有名称中使用下划线。 但是，这不再广泛接受，部分原因是因为它与.NET 命名约定冲突。 也就是说，某些 F # 程序员出于历史原因，很大程度，部分使用下划线，容差和遵循十分重要。 但是，请注意，该样式通常并的其他用户可以选择要使用它。

一些例外情况包括与互操作性本机组件下划线很常见。

### <a name="use-standard-f-operators"></a>使用标准 F # 运算符

以下运算符在 F # 标准库中定义和应使用而不是定义等效项。 建议使用这些运算符，如往往会使代码更具可读性且惯例。 具有背景的 OCaml 或其他功能的编程语言的开发人员可能会习惯于不同的惯例。 以下列表总结了建议的 F # 运算符。

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Throwing away a value
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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>前缀语法用于泛型 (`Foo<T>`) 优先于后缀语法 (`T Foo`)

F # 继承的命名的泛型类型的两个后缀 ML 样式 (例如， `int list`) 以及.NET 样式的前缀 (例如， `list<int>`)。 更喜欢的.NET 样式，四种特定类型除外：

1. F # 列出，对于使用后缀形式：`int list`而非`list<int>`。
2. 对于 F # 选项，使用的后缀形式：`int option`而非`option<int>`。
3. 对于 F # 数组，使用语法名称`int[]`而非`int array`或`array<int>`。
4. 对于引用单元格使用`int ref`而非`ref<int>`或`Ref<int>`。

对于所有其他类型，使用的前缀形式。