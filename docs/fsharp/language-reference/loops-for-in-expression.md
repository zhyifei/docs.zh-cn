---
title: 循环：for...in 表达式
description: F#请参阅in 表达式循环构造用于循环访问可枚举集合中的模式匹配项。
ms.date: 05/16/2016
ms.openlocfilehash: 5a2ca59ca4199ece5d78010ff780e86ae2b25181
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216448"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="55b64-103">循环：for...in 表达式</span><span class="sxs-lookup"><span data-stu-id="55b64-103">Loops: for...in Expression</span></span>

<span data-ttu-id="55b64-104">此循环构造用于循环访问可枚举集合中的模式匹配，如范围表达式、序列、列表、数组或支持枚举的其他构造。</span><span class="sxs-lookup"><span data-stu-id="55b64-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>

## <a name="syntax"></a><span data-ttu-id="55b64-105">语法</span><span class="sxs-lookup"><span data-stu-id="55b64-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="55b64-106">备注</span><span class="sxs-lookup"><span data-stu-id="55b64-106">Remarks</span></span>

<span data-ttu-id="55b64-107">表达式可以与其他 .net 语言中`for each`的语句进行比较，因为它用于循环对可枚举集合中的值。 `for...in`</span><span class="sxs-lookup"><span data-stu-id="55b64-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="55b64-108">但是， `for...in`还支持对集合进行模式匹配，而不是只是对整个集合进行迭代。</span><span class="sxs-lookup"><span data-stu-id="55b64-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="55b64-109">可枚举的表达式可以指定为可枚举的集合，也可以通过`..`使用运算符作为整数类型的范围。</span><span class="sxs-lookup"><span data-stu-id="55b64-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="55b64-110">可枚举集合包括列表、序列、数组、集、映射等。</span><span class="sxs-lookup"><span data-stu-id="55b64-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="55b64-111">可以使用任何实现`System.Collections.IEnumerable`的类型。</span><span class="sxs-lookup"><span data-stu-id="55b64-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="55b64-112">使用`..`运算符表示范围时，可以使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="55b64-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="55b64-113">*start* 。</span><span class="sxs-lookup"><span data-stu-id="55b64-113">*start* ..</span></span> <span data-ttu-id="55b64-114">*finish*</span><span class="sxs-lookup"><span data-stu-id="55b64-114">*finish*</span></span>

<span data-ttu-id="55b64-115">你还可以使用包含名为*skip*的增量的版本，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="55b64-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="55b64-116">*start* 。</span><span class="sxs-lookup"><span data-stu-id="55b64-116">*start* ..</span></span> <span data-ttu-id="55b64-117">*skip* 。</span><span class="sxs-lookup"><span data-stu-id="55b64-117">*skip* ..</span></span> <span data-ttu-id="55b64-118">*finish*</span><span class="sxs-lookup"><span data-stu-id="55b64-118">*finish*</span></span>

<span data-ttu-id="55b64-119">如果使用整数范围和简单计数器变量作为模式，则典型的行为是在每次迭代时将计数器变量递增1，但如果该范围包含 skip 值，则该计数器将改为按 skip 值递增。</span><span class="sxs-lookup"><span data-stu-id="55b64-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="55b64-120">在模式中匹配的值还可以在正文表达式中使用。</span><span class="sxs-lookup"><span data-stu-id="55b64-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="55b64-121">下面的代码示例阐释了`for...in`表达式的用法。</span><span class="sxs-lookup"><span data-stu-id="55b64-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="55b64-122">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="55b64-122">The output is as follows.</span></span>

```console
1
5
100
450
788
```

<span data-ttu-id="55b64-123">下面的示例演示如何在序列上循环，以及如何使用元组模式而不是简单变量。</span><span class="sxs-lookup"><span data-stu-id="55b64-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="55b64-124">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="55b64-124">The output is as follows.</span></span>

```console
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

<span data-ttu-id="55b64-125">下面的示例演示如何在一个简单的整数范围内循环。</span><span class="sxs-lookup"><span data-stu-id="55b64-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="55b64-126">Function1 的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="55b64-126">The output of function1 is as follows.</span></span>

```console
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="55b64-127">下面的示例演示如何在 skip 为2的范围内循环，其中包括范围中的所有其他元素。</span><span class="sxs-lookup"><span data-stu-id="55b64-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="55b64-128">的输出`function2`如下所示。</span><span class="sxs-lookup"><span data-stu-id="55b64-128">The output of `function2` is as follows.</span></span>

```console
1 3 5 7 9
```

<span data-ttu-id="55b64-129">下面的示例演示如何使用字符范围。</span><span class="sxs-lookup"><span data-stu-id="55b64-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="55b64-130">的输出`function3`如下所示。</span><span class="sxs-lookup"><span data-stu-id="55b64-130">The output of `function3` is as follows.</span></span>

```console
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="55b64-131">下面的示例演示如何对反向迭代使用负值 skip 值。</span><span class="sxs-lookup"><span data-stu-id="55b64-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="55b64-132">的输出`function4`如下所示。</span><span class="sxs-lookup"><span data-stu-id="55b64-132">The output of `function4` is as follows.</span></span>

```console
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="55b64-133">范围的开始和结束也可以是表达式，如函数，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="55b64-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="55b64-134">`function5`带有此输入的的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="55b64-134">The output of `function5` with this input is as follows.</span></span>

```console
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="55b64-135">下一个示例演示在循环中不需要元素时\_，如何使用通配符（）。</span><span class="sxs-lookup"><span data-stu-id="55b64-135">The next example shows the use of a wildcard character (\_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="55b64-136">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="55b64-136">The output is as follows.</span></span>

```console
Number of elements in list1: 5
```

<span data-ttu-id="55b64-137">`Note`可以在序列`for...in`表达式和其他计算表达式中使用，在这种情况下，将使用`for...in`自定义版本的表达式。</span><span class="sxs-lookup"><span data-stu-id="55b64-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="55b64-138">有关详细信息，请参阅[序列](sequences.md)、[异步工作流](asynchronous-workflows.md)和[计算表达式](computation-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="55b64-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="55b64-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="55b64-139">See also</span></span>

- [<span data-ttu-id="55b64-140">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="55b64-140">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="55b64-141">循环`for...to`表达式</span><span class="sxs-lookup"><span data-stu-id="55b64-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
- [<span data-ttu-id="55b64-142">循环`while...do`表达式</span><span class="sxs-lookup"><span data-stu-id="55b64-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
