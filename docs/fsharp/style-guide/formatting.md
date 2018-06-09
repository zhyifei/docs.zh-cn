---
title: 'F # 代码格式设置准则'
description: '了解有关格式设置 F # 代码的准则。'
ms.date: 05/14/2018
ms.openlocfilehash: 6c8e4059fd4bf1e7450118a6df02609217c4f4db
ms.sourcegitcommit: 2ad7d06f4f469b5d8a5280ac0e0289a81867fc8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "35231498"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="c7f38-103">F # 代码格式设置准则</span><span class="sxs-lookup"><span data-stu-id="c7f38-103">F# code formatting guidelines</span></span>

<span data-ttu-id="c7f38-104">本文提供有关如何设置你的代码格式，使你的 F # 代码的准则：</span><span class="sxs-lookup"><span data-stu-id="c7f38-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="c7f38-105">通常被视为可读性</span><span class="sxs-lookup"><span data-stu-id="c7f38-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="c7f38-106">符合应用的 Visual Studio 中的工具和其他编辑器格式设置约定</span><span class="sxs-lookup"><span data-stu-id="c7f38-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="c7f38-107">类似于其他代码联机</span><span class="sxs-lookup"><span data-stu-id="c7f38-107">Similar to other code online</span></span>

<span data-ttu-id="c7f38-108">这些指导原则基于[F # 格式设置约定的全面指南](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md)通过[Anh Dung Phan](https://github.com/dungpa)。</span><span class="sxs-lookup"><span data-stu-id="c7f38-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="c7f38-109">用于缩进的一般规则</span><span class="sxs-lookup"><span data-stu-id="c7f38-109">General rules for indentation</span></span>

<span data-ttu-id="c7f38-110">F # 默认使用有意义的空白。</span><span class="sxs-lookup"><span data-stu-id="c7f38-110">F# uses significant whitespace by default.</span></span> <span data-ttu-id="c7f38-111">以下准则旨在提供指导如何能够同时处理这可以施加一些难题。</span><span class="sxs-lookup"><span data-stu-id="c7f38-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="c7f38-112">使用空间</span><span class="sxs-lookup"><span data-stu-id="c7f38-112">Using spaces</span></span>

<span data-ttu-id="c7f38-113">需要缩进时，你必须使用空间，不是制表符。</span><span class="sxs-lookup"><span data-stu-id="c7f38-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="c7f38-114">需要至少一个空格。</span><span class="sxs-lookup"><span data-stu-id="c7f38-114">At least one space is required.</span></span> <span data-ttu-id="c7f38-115">您的组织可以创建编码标准来指定要用于缩进; 的空格数典型的缩进的出现位置的每个级别的缩进的两个、 三个或四个空格。</span><span class="sxs-lookup"><span data-stu-id="c7f38-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="c7f38-116">**我们建议每个缩进 4 个空格。**</span><span class="sxs-lookup"><span data-stu-id="c7f38-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="c7f38-117">也就是说，缩进的程序是主观一回事。</span><span class="sxs-lookup"><span data-stu-id="c7f38-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="c7f38-118">变体是确定，但应遵循的第一个规则是*缩进的一致性*。</span><span class="sxs-lookup"><span data-stu-id="c7f38-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="c7f38-119">选择广为接受的缩进样式，并在你的基本代码整个系统地使用它。</span><span class="sxs-lookup"><span data-stu-id="c7f38-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-blank-lines"></a><span data-ttu-id="c7f38-120">格式设置的空行</span><span class="sxs-lookup"><span data-stu-id="c7f38-120">Formatting blank lines</span></span>

* <span data-ttu-id="c7f38-121">单独顶级函数和类定义替换为两个空白的行。</span><span class="sxs-lookup"><span data-stu-id="c7f38-121">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="c7f38-122">类中的方法定义由一个空行分隔。</span><span class="sxs-lookup"><span data-stu-id="c7f38-122">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="c7f38-123">可能 （尽量少） 使用额外的空白的行到单独的组相关的函数。</span><span class="sxs-lookup"><span data-stu-id="c7f38-123">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="c7f38-124">多个相关 one-liners （例如，虚拟实现一组） 之间，可以忽略空行。</span><span class="sxs-lookup"><span data-stu-id="c7f38-124">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="c7f38-125">使用空白的行在函数中，谨慎，以指示逻辑部分。</span><span class="sxs-lookup"><span data-stu-id="c7f38-125">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="c7f38-126">格式设置的注释</span><span class="sxs-lookup"><span data-stu-id="c7f38-126">Formatting comments</span></span>

<span data-ttu-id="c7f38-127">通常选择多个双斜线注释而 ML 样式块注释。</span><span class="sxs-lookup"><span data-stu-id="c7f38-127">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="c7f38-128">内联注释应的首字母大写。</span><span class="sxs-lookup"><span data-stu-id="c7f38-128">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="c7f38-129">命名约定</span><span class="sxs-lookup"><span data-stu-id="c7f38-129">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="c7f38-130">使用驼峰匹配类绑定、 表达式绑定和绑定模式值和函数</span><span class="sxs-lookup"><span data-stu-id="c7f38-130">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="c7f38-131">是很常见，并且接受的 F # 要使用样式驼峰匹配的所有名称绑定为本地变量或在模式匹配和函数定义中。</span><span class="sxs-lookup"><span data-stu-id="c7f38-131">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="c7f38-132">类中的本地绑定函数还应使用驼峰匹配。</span><span class="sxs-lookup"><span data-stu-id="c7f38-132">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="c7f38-133">驼峰匹配用于绑定到模块的公共函数</span><span class="sxs-lookup"><span data-stu-id="c7f38-133">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="c7f38-134">当模块绑定函数是一个公共 API 的一部分时，它应使用驼峰匹配：</span><span class="sxs-lookup"><span data-stu-id="c7f38-134">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="c7f38-135">驼峰匹配用于内部和私有模块绑定值和函数</span><span class="sxs-lookup"><span data-stu-id="c7f38-135">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="c7f38-136">对于专用模块绑定值，其中包括使用驼峰匹配：</span><span class="sxs-lookup"><span data-stu-id="c7f38-136">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="c7f38-137">在脚本中的即席函数</span><span class="sxs-lookup"><span data-stu-id="c7f38-137">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="c7f38-138">组成的模块或类型的内部实现的值</span><span class="sxs-lookup"><span data-stu-id="c7f38-138">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="c7f38-139">对参数使用驼峰匹配</span><span class="sxs-lookup"><span data-stu-id="c7f38-139">Use camelCase for parameters</span></span>

<span data-ttu-id="c7f38-140">所有参数应都使用驼峰匹配根据.NET 命名约定。</span><span class="sxs-lookup"><span data-stu-id="c7f38-140">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="c7f38-141">用于模块的 PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7f38-141">Use PascalCase for modules</span></span>

<span data-ttu-id="c7f38-142">（顶级、 内部、 私有、 嵌套） 的所有模块都应都使用 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="c7f38-142">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="c7f38-143">PascalCase 用于类型声明、 成员和标签</span><span class="sxs-lookup"><span data-stu-id="c7f38-143">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="c7f38-144">类、 接口、 结构、 枚举、 委托、 记录和可区分的联合所有的命名应当与 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="c7f38-144">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="c7f38-145">类型和记录和可区分的联合的标签中的成员还应使用 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="c7f38-145">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="c7f38-146">PascalCase 用于构造固有的.NET</span><span class="sxs-lookup"><span data-stu-id="c7f38-146">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="c7f38-147">命名空间、 异常、 事件和项目 /`.dll`名称还应使用 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="c7f38-147">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="c7f38-148">不仅这会使感觉到使用者更自然的其他.NET 语言的消耗，也是与.NET，则可能会遇到的命名约定保持一致。</span><span class="sxs-lookup"><span data-stu-id="c7f38-148">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="c7f38-149">避免在名称中的下划线</span><span class="sxs-lookup"><span data-stu-id="c7f38-149">Avoid underscores in names</span></span>

<span data-ttu-id="c7f38-150">从历史上看，某些 F # 库具有名称中使用下划线。</span><span class="sxs-lookup"><span data-stu-id="c7f38-150">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="c7f38-151">但是，这不再广泛接受，部分原因是因为它与.NET 命名约定冲突。</span><span class="sxs-lookup"><span data-stu-id="c7f38-151">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="c7f38-152">也就是说，某些 F # 程序员出于历史原因，很大程度，部分使用下划线，容差和遵循十分重要。</span><span class="sxs-lookup"><span data-stu-id="c7f38-152">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="c7f38-153">但是，请注意，该样式通常并的其他用户可以选择要使用它。</span><span class="sxs-lookup"><span data-stu-id="c7f38-153">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="c7f38-154">一些例外情况包括与互操作性本机组件下划线很常见。</span><span class="sxs-lookup"><span data-stu-id="c7f38-154">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="c7f38-155">使用标准 F # 运算符</span><span class="sxs-lookup"><span data-stu-id="c7f38-155">Use standard F# operators</span></span>

<span data-ttu-id="c7f38-156">以下运算符在 F # 标准库中定义和应使用而不是定义等效项。</span><span class="sxs-lookup"><span data-stu-id="c7f38-156">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="c7f38-157">建议使用这些运算符，如往往会使代码更具可读性且惯例。</span><span class="sxs-lookup"><span data-stu-id="c7f38-157">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="c7f38-158">具有背景的 OCaml 或其他功能的编程语言的开发人员可能会习惯于不同的惯例。</span><span class="sxs-lookup"><span data-stu-id="c7f38-158">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="c7f38-159">以下列表总结了建议的 F # 运算符。</span><span class="sxs-lookup"><span data-stu-id="c7f38-159">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="c7f38-160">前缀语法用于泛型 (`Foo<T>`) 优先于后缀语法 (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="c7f38-160">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="c7f38-161">F # 继承的命名的泛型类型的两个后缀 ML 样式 (例如， `int list`) 以及.NET 样式的前缀 (例如， `list<int>`)。</span><span class="sxs-lookup"><span data-stu-id="c7f38-161">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="c7f38-162">更喜欢的.NET 样式，四种特定类型除外：</span><span class="sxs-lookup"><span data-stu-id="c7f38-162">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="c7f38-163">F # 列出，对于使用后缀形式：`int list`而非`list<int>`。</span><span class="sxs-lookup"><span data-stu-id="c7f38-163">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="c7f38-164">对于 F # 选项，使用的后缀形式：`int option`而非`option<int>`。</span><span class="sxs-lookup"><span data-stu-id="c7f38-164">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="c7f38-165">对于 F # 数组，使用语法名称`int[]`而非`int array`或`array<int>`。</span><span class="sxs-lookup"><span data-stu-id="c7f38-165">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="c7f38-166">对于引用单元格使用`int ref`而非`ref<int>`或`Ref<int>`。</span><span class="sxs-lookup"><span data-stu-id="c7f38-166">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="c7f38-167">对于所有其他类型，使用的前缀形式。</span><span class="sxs-lookup"><span data-stu-id="c7f38-167">For all other types, use the prefix form.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="c7f38-168">格式设置可区分联合声明</span><span class="sxs-lookup"><span data-stu-id="c7f38-168">Formatting discriminated union declarations</span></span>

<span data-ttu-id="c7f38-169">缩进`|`通过 4 个空格的类型定义中：</span><span class="sxs-lookup"><span data-stu-id="c7f38-169">Indent `|` in type definition by 4 spaces:</span></span>

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

<span data-ttu-id="c7f38-170">将拆分到多个行的实例化可区分联合应提供包含的数据具有缩进的新作用域：</span><span class="sxs-lookup"><span data-stu-id="c7f38-170">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="c7f38-171">右括号还可以将新行上：</span><span class="sxs-lookup"><span data-stu-id="c7f38-171">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-tuples"></a><span data-ttu-id="c7f38-172">格式设置的元组</span><span class="sxs-lookup"><span data-stu-id="c7f38-172">Formatting tuples</span></span>

<span data-ttu-id="c7f38-173">元组实例化应该用圆括号括起来，并且在分界逗号应跟一个空格，例如： `(1, 2)`， `(x, y, z)`。</span><span class="sxs-lookup"><span data-stu-id="c7f38-173">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="c7f38-174">广为接受的异常是省略括号中的元组模式匹配：</span><span class="sxs-lookup"><span data-stu-id="c7f38-174">A commonly accepted exception is to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring

match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-records"></a><span data-ttu-id="c7f38-175">格式设置的记录</span><span class="sxs-lookup"><span data-stu-id="c7f38-175">Formatting records</span></span>

<span data-ttu-id="c7f38-176">可以在一个行中编写短记录：</span><span class="sxs-lookup"><span data-stu-id="c7f38-176">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="c7f38-177">较长的记录应使用标签的新行：</span><span class="sxs-lookup"><span data-stu-id="c7f38-177">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="c7f38-178">在同一行和上一个新行的结束标记上施加打开令牌也是正常的：</span><span class="sxs-lookup"><span data-stu-id="c7f38-178">Placing the opening token on the same line and the closing token on a new line is also fine:</span></span>

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

<span data-ttu-id="c7f38-179">相同的规则适用于列表和数组元素。</span><span class="sxs-lookup"><span data-stu-id="c7f38-179">The same rules apply for list and array elements.</span></span>

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="c7f38-180">格式设置的列表和数组</span><span class="sxs-lookup"><span data-stu-id="c7f38-180">Formatting lists and arrays</span></span>

<span data-ttu-id="c7f38-181">编写`x :: l`与周围的空格`::`运算符 (`::`是中缀运算符，因此由空格括起来) 和`[1; 2; 3]`(`;`是分隔符，因此跟一个空格)。</span><span class="sxs-lookup"><span data-stu-id="c7f38-181">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces) and `[1; 2; 3]` (`;` is a delimiter, hence followed by a space).</span></span>

<span data-ttu-id="c7f38-182">始终使用两个不同的大括号类似运算符之间的至少一个空格。</span><span class="sxs-lookup"><span data-stu-id="c7f38-182">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="c7f38-183">例如，将保留之间留一个空格`[`和`{`。</span><span class="sxs-lookup"><span data-stu-id="c7f38-183">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="c7f38-184">列表和将拆分到多个行的数组遵循类似的规则，记录一样：</span><span class="sxs-lookup"><span data-stu-id="c7f38-184">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

## <a name="formatting-if-expressions"></a><span data-ttu-id="c7f38-185">如果格式设置表达式</span><span class="sxs-lookup"><span data-stu-id="c7f38-185">Formatting if expressions</span></span>

<span data-ttu-id="c7f38-186">条件语句的缩进量取决于把它们组合起来的表达式的大小。</span><span class="sxs-lookup"><span data-stu-id="c7f38-186">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="c7f38-187">如果`cond`，`e1`和`e2`很小，只需将它们写入在同一行中：</span><span class="sxs-lookup"><span data-stu-id="c7f38-187">If `cond`, `e1` and `e2` are small, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="c7f38-188">如果`e1`和`cond`很小，但`e2`大：</span><span class="sxs-lookup"><span data-stu-id="c7f38-188">If `e1` and `cond` are small, but `e2` is large:</span></span>

```fsharp
if cond then e1
else
    e2
```

<span data-ttu-id="c7f38-189">如果`e1`和`cond`大和`e2`小：</span><span class="sxs-lookup"><span data-stu-id="c7f38-189">If `e1` and `cond` are large and `e2` is small:</span></span>

```fsharp
if cond then
    e1
else e2
```

<span data-ttu-id="c7f38-190">如果所有表达式都都大：</span><span class="sxs-lookup"><span data-stu-id="c7f38-190">If all the expressions are large:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="c7f38-191">使用多个条件语句`elif`和`else`都在与同一作用域缩进`if`:</span><span class="sxs-lookup"><span data-stu-id="c7f38-191">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="c7f38-192">模式匹配的构造</span><span class="sxs-lookup"><span data-stu-id="c7f38-192">Pattern matching constructs</span></span>

<span data-ttu-id="c7f38-193">使用`|`对于无缩进的匹配项的每个子句。</span><span class="sxs-lookup"><span data-stu-id="c7f38-193">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="c7f38-194">如果表达式是短，可以考虑使用单个行，如果每一子表达式也非常简单。</span><span class="sxs-lookup"><span data-stu-id="c7f38-194">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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
```

<span data-ttu-id="c7f38-195">如果模式匹配箭头右侧表达式而言太大，则将其移到下一行中的缩进一个步骤`match` / `|`。</span><span class="sxs-lookup"><span data-stu-id="c7f38-195">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="c7f38-196">模式匹配的匿名函数，通过启动`function`，应通常不缩进得太长。</span><span class="sxs-lookup"><span data-stu-id="c7f38-196">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="c7f38-197">例如，缩进一个作用域，如下所示是正常的：</span><span class="sxs-lookup"><span data-stu-id="c7f38-197">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="c7f38-198">通过定义的函数中的模式匹配`let`或`let rec`开始之后，应该进行缩进 4 个空格`let`，即使`function`使用关键字：</span><span class="sxs-lookup"><span data-stu-id="c7f38-198">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="c7f38-199">我们不建议对齐箭头。</span><span class="sxs-lookup"><span data-stu-id="c7f38-199">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="c7f38-200">格式设置的 try / 使用表达式</span><span class="sxs-lookup"><span data-stu-id="c7f38-200">Formatting try/with expressions</span></span>

<span data-ttu-id="c7f38-201">模式匹配的异常类型应为相同级别缩进`with`。</span><span class="sxs-lookup"><span data-stu-id="c7f38-201">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="c7f38-202">格式设置的函数参数应用程序</span><span class="sxs-lookup"><span data-stu-id="c7f38-202">Formatting function parameter application</span></span>

<span data-ttu-id="c7f38-203">一般情况下，大多数函数参数应用程序是在同一行上完成。</span><span class="sxs-lookup"><span data-stu-id="c7f38-203">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="c7f38-204">如果你想要应用到一个新行上的函数的参数，将它们缩进一个作用域。</span><span class="sxs-lookup"><span data-stu-id="c7f38-204">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="c7f38-205">相同的准则将 lambda 表达式应用于函数自变量。</span><span class="sxs-lookup"><span data-stu-id="c7f38-205">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="c7f38-206">如果 lambda 表达式，主体的主体可以有另一个行，缩进一个作用域</span><span class="sxs-lookup"><span data-stu-id="c7f38-206">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="c7f38-207">但是，如果 lambda 表达式的主体是多个行，请考虑将其分解为单独的函数而不具有向函数应用作为单个参数的多行构造。</span><span class="sxs-lookup"><span data-stu-id="c7f38-207">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="c7f38-208">格式设置的中缀运算符</span><span class="sxs-lookup"><span data-stu-id="c7f38-208">Formatting infix operators</span></span>

<span data-ttu-id="c7f38-209">用空格的单独运算符。</span><span class="sxs-lookup"><span data-stu-id="c7f38-209">Separate operators by spaces.</span></span> <span data-ttu-id="c7f38-210">是此规则的明显例外`!`和`.`运算符。</span><span class="sxs-lookup"><span data-stu-id="c7f38-210">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="c7f38-211">中缀表达式是在同一列的 lineup 确定:</span><span class="sxs-lookup"><span data-stu-id="c7f38-211">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="c7f38-212">格式设置管道运算符</span><span class="sxs-lookup"><span data-stu-id="c7f38-212">Formatting pipeline operators</span></span>

<span data-ttu-id="c7f38-213">管道`|>`运算符应转下它们对操作的表达式。</span><span class="sxs-lookup"><span data-stu-id="c7f38-213">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="c7f38-214">格式设置的模块</span><span class="sxs-lookup"><span data-stu-id="c7f38-214">Formatting modules</span></span>

<span data-ttu-id="c7f38-215">本地模块中的代码必须缩进相对于该模块，但顶级模块中的代码不应缩进。</span><span class="sxs-lookup"><span data-stu-id="c7f38-215">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="c7f38-216">Namespace 元素无需进行缩进。</span><span class="sxs-lookup"><span data-stu-id="c7f38-216">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="c7f38-217">格式设置的对象表达式和接口</span><span class="sxs-lookup"><span data-stu-id="c7f38-217">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="c7f38-218">对象表达式和接口应对齐的方式使用相同`member`正在缩进后 4 个空格。</span><span class="sxs-lookup"><span data-stu-id="c7f38-218">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-whitespace-in-expressions"></a><span data-ttu-id="c7f38-219">格式设置表达式中的空格</span><span class="sxs-lookup"><span data-stu-id="c7f38-219">Formatting whitespace in expressions</span></span>

<span data-ttu-id="c7f38-220">请避免使用 F # 表达式中的多余空白。</span><span class="sxs-lookup"><span data-stu-id="c7f38-220">Avoid extraneous whitespace in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="c7f38-221">命名自变量也不应有周围的空间`=`:</span><span class="sxs-lookup"><span data-stu-id="c7f38-221">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```
