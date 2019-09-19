---
title: 活动模式
description: 了解如何使用活动模式来定义用F#编程语言细分输入数据的已命名分区。
ms.date: 05/16/2016
ms.openlocfilehash: 0c1315f2386b3cea2def698f4725e4c1cf030609
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083083"
---
# <a name="active-patterns"></a><span data-ttu-id="b6382-103">活动模式</span><span class="sxs-lookup"><span data-stu-id="b6382-103">Active Patterns</span></span>

<span data-ttu-id="b6382-104">*活动模式*使您能够定义细分输入数据的命名分区，以便在模式匹配表达式中使用这些名称，就像对可区分联合使用这些名称一样。</span><span class="sxs-lookup"><span data-stu-id="b6382-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="b6382-105">可使用活动模式以自定义方式为每个分区分解数据。</span><span class="sxs-lookup"><span data-stu-id="b6382-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="b6382-106">语法</span><span class="sxs-lookup"><span data-stu-id="b6382-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="b6382-107">备注</span><span class="sxs-lookup"><span data-stu-id="b6382-107">Remarks</span></span>

<span data-ttu-id="b6382-108">在前面的语法中，标识符是由*参数*表示的输入数据的分区名称，换句话说，是参数的所有值的集合的子集的名称。</span><span class="sxs-lookup"><span data-stu-id="b6382-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="b6382-109">活动模式定义中最多可以有七个分区。</span><span class="sxs-lookup"><span data-stu-id="b6382-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="b6382-110">*表达式*描述数据要分解到的窗体。</span><span class="sxs-lookup"><span data-stu-id="b6382-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="b6382-111">您可以使用活动模式定义来定义规则，这些规则用于确定作为参数提供的值所属于的指定分区。</span><span class="sxs-lookup"><span data-stu-id="b6382-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="b6382-112">(| 和 |) 符号嘿*香蕉夹*并创建此类型的 let 绑定的函数调用*活动的识别器*。</span><span class="sxs-lookup"><span data-stu-id="b6382-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="b6382-113">例如，请考虑以下具有参数的活动模式。</span><span class="sxs-lookup"><span data-stu-id="b6382-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="b6382-114">可以在模式匹配表达式中使用活动模式，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="b6382-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="b6382-115">此程序的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6382-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="b6382-116">活动模式的另一个用法是通过多种方式分解数据类型，例如，当相同的基础数据具有各种可能的表示形式时。</span><span class="sxs-lookup"><span data-stu-id="b6382-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="b6382-117">例如， `Color`对象可以分解为 RGB 表示形式或 HSB 表示形式。</span><span class="sxs-lookup"><span data-stu-id="b6382-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="b6382-118">上述程序的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6382-118">The output of the above program is as follows:</span></span>

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

<span data-ttu-id="b6382-119">结合使用这两种使用活动模式的方法，您可以将数据分区和分解为适当的形式，并对最方便计算的窗体中的相应数据执行适当的计算。</span><span class="sxs-lookup"><span data-stu-id="b6382-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="b6382-120">生成的模式匹配表达式使数据能够以一种易于阅读的方便方式写入，从而极大地简化了可能复杂的分支和数据分析代码。</span><span class="sxs-lookup"><span data-stu-id="b6382-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="b6382-121">部分活动模式</span><span class="sxs-lookup"><span data-stu-id="b6382-121">Partial Active Patterns</span></span>

<span data-ttu-id="b6382-122">有时，您需要只对部分输入空间进行分区。</span><span class="sxs-lookup"><span data-stu-id="b6382-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="b6382-123">在这种情况下，你编写一组部分模式，其中每个模式都匹配某些输入但无法匹配其他输入。</span><span class="sxs-lookup"><span data-stu-id="b6382-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="b6382-124">不会始终产生值的活动模式称为*部分活动模式*;它们具有作为选项类型的返回值。</span><span class="sxs-lookup"><span data-stu-id="b6382-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="b6382-125">若要定义部分活动模式，请在香蕉剪辑中的\_模式列表的末尾使用通配符（）。</span><span class="sxs-lookup"><span data-stu-id="b6382-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="b6382-126">下面的代码演示如何使用部分活动模式。</span><span class="sxs-lookup"><span data-stu-id="b6382-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="b6382-127">上一个示例的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6382-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="b6382-128">使用部分活动的模式时，有时个别选择可能是不连续的或互斥的，但它们不需要。</span><span class="sxs-lookup"><span data-stu-id="b6382-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="b6382-129">在下面的示例中，模式正方形和模式多维数据集不是连续的，因为某些数字既是正方形又是多维数据集，例如64。</span><span class="sxs-lookup"><span data-stu-id="b6382-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="b6382-130">下面的程序使用和模式来合并正方形和立方体模式。</span><span class="sxs-lookup"><span data-stu-id="b6382-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="b6382-131">它输出所有最大为1000的整数，它们都是平方和多维数据集，以及只是多维数据集的所有整数。</span><span class="sxs-lookup"><span data-stu-id="b6382-131">It print out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span> 

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="b6382-132">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6382-132">The output is as follows:</span></span>

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

## <a name="parameterized-active-patterns"></a><span data-ttu-id="b6382-133">参数化活动模式</span><span class="sxs-lookup"><span data-stu-id="b6382-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="b6382-134">活动模式始终为要匹配的项至少使用一个参数，但也可能采用其他参数，在这种情况下，将应用名为*参数化活动模式*的名称。</span><span class="sxs-lookup"><span data-stu-id="b6382-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="b6382-135">其他参数允许专用化常规模式。</span><span class="sxs-lookup"><span data-stu-id="b6382-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="b6382-136">例如，使用正则表达式分析字符串的活动模式通常包含正则表达式作为额外参数，如以下代码所示，它还使用在上一个代码示例中`Integer`定义的部分活动模式。</span><span class="sxs-lookup"><span data-stu-id="b6382-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="b6382-137">在此示例中，将为使用各种日期格式的正则表达式的字符串自定义常规 ParseRegex 活动模式。</span><span class="sxs-lookup"><span data-stu-id="b6382-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="b6382-138">整数活动模式用于将匹配的字符串转换为可传递到 DateTime 构造函数的整数。</span><span class="sxs-lookup"><span data-stu-id="b6382-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="b6382-139">上述代码的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6382-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="b6382-140">活动模式并不局限于模式匹配表达式，还可以在 let 绑定上使用它们。</span><span class="sxs-lookup"><span data-stu-id="b6382-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="b6382-141">上述代码的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6382-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="b6382-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6382-142">See also</span></span>

- [<span data-ttu-id="b6382-143">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="b6382-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b6382-144">match 表达式</span><span class="sxs-lookup"><span data-stu-id="b6382-144">Match Expressions</span></span>](match-expressions.md)
