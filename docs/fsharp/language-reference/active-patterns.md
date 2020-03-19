---
title: 活动模式
description: 了解如何使用活动模式定义在 F# 编程语言中细分输入数据的命名分区。
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187063"
---
# <a name="active-patterns"></a><span data-ttu-id="6d785-103">活动模式</span><span class="sxs-lookup"><span data-stu-id="6d785-103">Active Patterns</span></span>

<span data-ttu-id="6d785-104">*活动模式*使您能够定义细分输入数据的命名分区，以便可以在模式匹配表达式中使用这些名称，就像对受歧视联合一样。</span><span class="sxs-lookup"><span data-stu-id="6d785-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="6d785-105">可使用活动模式以自定义方式为每个分区分解数据。</span><span class="sxs-lookup"><span data-stu-id="6d785-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="6d785-106">语法</span><span class="sxs-lookup"><span data-stu-id="6d785-106">Syntax</span></span>

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a><span data-ttu-id="6d785-107">备注</span><span class="sxs-lookup"><span data-stu-id="6d785-107">Remarks</span></span>

<span data-ttu-id="6d785-108">在前面的语法中，标识符是由*参数*表示的输入数据分区的名称，或者换句话说，是参数所有值集的子集的名称。</span><span class="sxs-lookup"><span data-stu-id="6d785-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="6d785-109">活动模式定义中最多只能有七个分区。</span><span class="sxs-lookup"><span data-stu-id="6d785-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="6d785-110">表达式*描述*要将数据分解到的窗体。</span><span class="sxs-lookup"><span data-stu-id="6d785-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="6d785-111">可以使用活动模式定义定义规则，以确定作为参数给定的值属于哪个命名分区。</span><span class="sxs-lookup"><span data-stu-id="6d785-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="6d785-112">（\* 和 |） 符号称为*香蕉剪辑*，这种类型的 let 绑定创建的函数称为*活动识别器*。</span><span class="sxs-lookup"><span data-stu-id="6d785-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="6d785-113">例如，请考虑以下具有参数的活动模式。</span><span class="sxs-lookup"><span data-stu-id="6d785-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="6d785-114">您可以在模式匹配表达式中使用活动模式，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="6d785-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="6d785-115">此程序的输出如下：</span><span class="sxs-lookup"><span data-stu-id="6d785-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="6d785-116">活动模式的另一个用途是以多种方式分解数据类型，例如当同一基础数据具有各种可能的表示形式时。</span><span class="sxs-lookup"><span data-stu-id="6d785-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="6d785-117">例如，`Color`对象可以分解为 RGB 表示形式或汇丰表示形式。</span><span class="sxs-lookup"><span data-stu-id="6d785-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="6d785-118">上述程序的输出如下：</span><span class="sxs-lookup"><span data-stu-id="6d785-118">The output of the above program is as follows:</span></span>

```console
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

<span data-ttu-id="6d785-119">结合，这两种使用活动模式的方法使您能够将数据分区和分解为适当的形式，并在最方便的计算形式中对适当的数据执行适当的计算。</span><span class="sxs-lookup"><span data-stu-id="6d785-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="6d785-120">生成的模式匹配表达式使数据能够以易于读的便捷方式写入，从而大大简化了潜在的复杂分支和数据分析代码。</span><span class="sxs-lookup"><span data-stu-id="6d785-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="6d785-121">部分活动模式</span><span class="sxs-lookup"><span data-stu-id="6d785-121">Partial Active Patterns</span></span>

<span data-ttu-id="6d785-122">有时，您只需要分区部分输入空间。</span><span class="sxs-lookup"><span data-stu-id="6d785-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="6d785-123">在这种情况下，您编写一组部分模式，每个模式与某些输入匹配，但无法匹配其他输入。</span><span class="sxs-lookup"><span data-stu-id="6d785-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="6d785-124">并不总是生成值的活动模式称为*部分活动模式*;它们具有作为选项类型的返回值。</span><span class="sxs-lookup"><span data-stu-id="6d785-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="6d785-125">要定义部分活动模式，请使用在香蕉夹内模式列表末尾\_的通配符 （ ） 。</span><span class="sxs-lookup"><span data-stu-id="6d785-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="6d785-126">以下代码说明了部分活动模式的使用。</span><span class="sxs-lookup"><span data-stu-id="6d785-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="6d785-127">上一个示例的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d785-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="6d785-128">使用部分活动模式时，有时各个选项可以是脱节的，也可以是互斥的，但它们不需要。</span><span class="sxs-lookup"><span data-stu-id="6d785-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="6d785-129">在下面的示例中，模式方形和模式立方体并不脱节，因为某些数字既是正方形，也是立方体，如 64。</span><span class="sxs-lookup"><span data-stu-id="6d785-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="6d785-130">以下程序使用 AND 模式组合方形和立方体模式。</span><span class="sxs-lookup"><span data-stu-id="6d785-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="6d785-131">它打印出所有整数最多 1000 个，这些整数既是正方形和立方体，也是仅多维数据集的整数。</span><span class="sxs-lookup"><span data-stu-id="6d785-131">It prints out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="6d785-132">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d785-132">The output is as follows:</span></span>

```console
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="6d785-133">参数化活动模式</span><span class="sxs-lookup"><span data-stu-id="6d785-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="6d785-134">活动模式始终对要匹配的项至少采用一个参数，但它们也可能采用其他参数，在这种情况下，名称*参数化的活动模式*适用。</span><span class="sxs-lookup"><span data-stu-id="6d785-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="6d785-135">其他参数允许将常规模式专门化。</span><span class="sxs-lookup"><span data-stu-id="6d785-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="6d785-136">例如，使用正则表达式解析字符串的活动模式通常包括正则表达式作为额外参数，如以下代码，该代码还使用前一个代码示例中定义的部分活动模式`Integer`。</span><span class="sxs-lookup"><span data-stu-id="6d785-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="6d785-137">在此示例中，为各种日期格式提供正则表达式的字符串用于自定义常规 ParseRegex 活动模式。</span><span class="sxs-lookup"><span data-stu-id="6d785-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="6d785-138">整数活动模式用于将匹配的字符串转换为可传递给 DateTime 构造函数的整数。</span><span class="sxs-lookup"><span data-stu-id="6d785-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="6d785-139">前一个代码的输出如下：</span><span class="sxs-lookup"><span data-stu-id="6d785-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="6d785-140">活动模式不仅局限于模式匹配表达式，还可以在 let 绑定上使用它们。</span><span class="sxs-lookup"><span data-stu-id="6d785-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="6d785-141">前一个代码的输出如下：</span><span class="sxs-lookup"><span data-stu-id="6d785-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="6d785-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d785-142">See also</span></span>

- [<span data-ttu-id="6d785-143">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="6d785-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="6d785-144">Match 表达式</span><span class="sxs-lookup"><span data-stu-id="6d785-144">Match Expressions</span></span>](match-expressions.md)
