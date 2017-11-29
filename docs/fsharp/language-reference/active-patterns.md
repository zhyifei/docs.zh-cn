---
title: "活动模式 (F#)"
description: "了解如何使用活动模式可以定义将在 F # 编程语言的输入的数据的命名的分区。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 11a724ff-f9ff-4056-b5e0-87e9ed986f4a
ms.openlocfilehash: 845184e6150cf0b93393038ca3d39f0e6d898a2e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="active-patterns"></a><span data-ttu-id="ed4f7-104">活动模式</span><span class="sxs-lookup"><span data-stu-id="ed4f7-104">Active Patterns</span></span>

<span data-ttu-id="ed4f7-105">*活动模式*使您能够定义将输入的数据的命名的分区，以便你可以在匹配表达式，就像可区分联合模式中使用这些名称。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-105">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="ed4f7-106">可使用活动模式以自定义方式为每个分区分解数据。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-106">You can use active patterns to decompose data in a customized manner for each partition.</span></span>


## <a name="syntax"></a><span data-ttu-id="ed4f7-107">语法</span><span class="sxs-lookup"><span data-stu-id="ed4f7-107">Syntax</span></span>

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a><span data-ttu-id="ed4f7-108">备注</span><span class="sxs-lookup"><span data-stu-id="ed4f7-108">Remarks</span></span>
<span data-ttu-id="ed4f7-109">在上述语法中，标识符都是由输入数据的分区名称*参数*，或，换而言之，名称参数的所有值集的子集。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-109">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="ed4f7-110">活动模式定义中可以有最多七个分区。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-110">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="ed4f7-111">*表达式*描述要将数据分解到窗体。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-111">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="ed4f7-112">活动模式定义可用于定义用于确定哪些命名的分区按照自变量属于给定的值的规则。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-112">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="ed4f7-113">(| 和 |) 符号被称为*香蕉夹*和调用函数创建的此类型的 let 绑定*active 识别器*。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-113">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="ed4f7-114">作为示例，请考虑用参数的以下活动模式。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-114">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="ed4f7-115">在模式匹配表达式，如以下示例所示，可以使用活动的模式。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-115">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="ed4f7-116">此程序的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed4f7-116">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="ed4f7-117">活动模式的另一个用途是将分解采用多种方式，例如在相同的基础数据具有各种可能的表示形式之间的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-117">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="ed4f7-118">例如，`Color`对象无法分解为一表示形式，RGB 或 HSB 表示形式。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-118">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="ed4f7-119">上面的程序中的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed4f7-119">The output of the above program is as follows:</span></span>

```
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

<span data-ttu-id="ed4f7-120">在组合中，使用活动的模式的这两种方式使您能够在分区和将数据分解为适当的形式为和最方便的计算窗体中的相应数据执行适当的计算。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-120">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="ed4f7-121">生成的模式匹配表达式启用数据是非常可读，极大地简化潜在的复杂分支和数据分析代码的简便方式写入。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-121">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>


## <a name="partial-active-patterns"></a><span data-ttu-id="ed4f7-122">分部活动模式</span><span class="sxs-lookup"><span data-stu-id="ed4f7-122">Partial Active Patterns</span></span>
<span data-ttu-id="ed4f7-123">有时，你需要进行分区只输入空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-123">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="ed4f7-124">在这种情况下，你编写一组分部模式，其中匹配某些输入，但不能匹配其他输入。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-124">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="ed4f7-125">调用活动的模式，始终不会产生一个值*分部活动模式*; 它们具有一个返回值，是选项类型。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-125">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="ed4f7-126">若要定义部分的活动模式，请在内部香蕉夹模式的列表的末尾使用通配符字符 (_)。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-126">To define a partial active pattern, you use a wildcard character (_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="ed4f7-127">下面的代码演示如何使用分部活动模式。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-127">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="ed4f7-128">前面的示例的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed4f7-128">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="ed4f7-129">当使用部分活动模式时，有时各个选项可以是连续的或互斥的但它们不需要。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-129">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="ed4f7-130">在下面的示例中，模式 Square 和多维数据集的模式不连续的因为一些数字平方和多维数据集，例如 64。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-130">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="ed4f7-131">下面的程序将最多是平方和多维数据集的 1000000 输出所有的整数。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-131">The following program prints out all integers up to 1000000 that are both squares and cubes.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="ed4f7-132">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed4f7-132">The output is as follows:</span></span>

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="ed4f7-133">参数化的活动模式</span><span class="sxs-lookup"><span data-stu-id="ed4f7-133">Parameterized Active Patterns</span></span>
<span data-ttu-id="ed4f7-134">活动模式始终采用要匹配的项的至少一个自变量，但也可能会采用其他参数，这种情况下名称*参数化的活动模式*适用。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="ed4f7-135">其他参数，可专用的常规模式。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="ed4f7-136">例如，使用正则表达式分析字符串通常的活动模式包括正则表达式作为一个附加参数，如下面的代码，还会使用分部活动模式中所示`Integer`在前面的代码示例中定义。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="ed4f7-137">在此示例中，提供用于各种日期格式的正则表达式的字符串的自定义常规 ParseRegex 活动模式。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="ed4f7-138">使用整数 active 模式将匹配的字符串转换为可以传递给 DateTime 构造函数的整数。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="ed4f7-139">上述代码的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed4f7-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="ed4f7-140">活动模式不受限制，只是为了模式匹配的表达式，你还可以让绑定上使用它们。</span><span class="sxs-lookup"><span data-stu-id="ed4f7-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="ed4f7-141">上述代码的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed4f7-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="ed4f7-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed4f7-142">See Also</span></span>
[<span data-ttu-id="ed4f7-143">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="ed4f7-143">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="ed4f7-144">match 表达式</span><span class="sxs-lookup"><span data-stu-id="ed4f7-144">Match Expressions</span></span>](match-expressions.md)

