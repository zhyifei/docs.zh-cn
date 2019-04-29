---
title: Ref 返回值 (Visual Basic)
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: d0600f7d9030324160343e800c37e0f5e68bff61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791802"
---
# <a name="support-for-reference-return-values-visual-basic"></a><span data-ttu-id="b8664-102">支持引用返回值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8664-102">Support for reference return values (Visual Basic)</span></span>

<span data-ttu-id="b8664-103">从C#7.0 中，C#语言支持*引用返回值*。</span><span class="sxs-lookup"><span data-stu-id="b8664-103">Starting with C# 7.0, the C# language supports *reference return values*.</span></span> <span data-ttu-id="b8664-104">若要了解引用返回值的方法之一是它们是相反的方法引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="b8664-104">One way to understand reference return values is that they are the opposite of arguments that are passed by reference to a method.</span></span> <span data-ttu-id="b8664-105">修改通过引用传递的参数后，所做的更改将在该变量的值反映在调用方中。</span><span class="sxs-lookup"><span data-stu-id="b8664-105">When an argument passed by reference is modified, the changes are reflected in value of the variable on the caller.</span></span> <span data-ttu-id="b8664-106">在一种方法提供给调用方的引用返回值，将引用返回值由调用方所做的修改将反映在被调用的方法的数据。</span><span class="sxs-lookup"><span data-stu-id="b8664-106">When an method provides a reference return value to a caller, modifications made to the reference return value by the caller are reflected in the called method's data.</span></span>

<span data-ttu-id="b8664-107">Visual Basic 不允许您对具有引用作者方法返回的值，但它的确允许你以使用引用返回值。</span><span class="sxs-lookup"><span data-stu-id="b8664-107">Visual Basic does not allow you to author methods with reference return values, but it does allow you to consume reference return values.</span></span> <span data-ttu-id="b8664-108">换而言之，可以调用具有引用返回值的方法并修改该返回值，并对引用返回值的更改反映在被调用的方法的数据。</span><span class="sxs-lookup"><span data-stu-id="b8664-108">In other words, you can call a method with a reference return value and modify that return value, and changes to the reference return value are reflected in the called method's data.</span></span>

## <a name="modifying-the-ref-return-value-directly"></a><span data-ttu-id="b8664-109">直接修改 ref 返回值</span><span class="sxs-lookup"><span data-stu-id="b8664-109">Modifying the ref return value directly</span></span>

<span data-ttu-id="b8664-110">对于方法，始终成功，并且没有任何`ByRef`参数，您可以直接修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="b8664-110">For methods that always succeed and have no `ByRef` parameters, you can modify the reference return value directly.</span></span> <span data-ttu-id="b8664-111">通过将新值分配给返回引用返回值的表达式来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b8664-111">You do this by assigning the new value to the expressions that returns the reference return value.</span></span> 

<span data-ttu-id="b8664-112">以下C#的示例定义了`NumericValue.IncrementValue`方法的内部值递增并将其返回作为引用返回值。</span><span class="sxs-lookup"><span data-stu-id="b8664-112">The following C# example defines a `NumericValue.IncrementValue` method that increments an internal value and returns it as a reference return value.</span></span> 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

<span data-ttu-id="b8664-113">引用返回调用方在下面的 Visual Basic 示例然后修改值。</span><span class="sxs-lookup"><span data-stu-id="b8664-113">The reference return value is then modified by the caller in the following Visual Basic example.</span></span> <span data-ttu-id="b8664-114">请注意，在行的`NumericValue.IncrementValue`方法调用不会分配给该方法的一个值。</span><span class="sxs-lookup"><span data-stu-id="b8664-114">Note that the line with the `NumericValue.IncrementValue` method call does not assign a value to the method.</span></span> <span data-ttu-id="b8664-115">相反，它将值分配给该方法返回的引用返回值。</span><span class="sxs-lookup"><span data-stu-id="b8664-115">Instead, it assigns a value to the reference return value returned by the method.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a><span data-ttu-id="b8664-116">使用一个帮助器方法</span><span class="sxs-lookup"><span data-stu-id="b8664-116">Using a helper method</span></span>

<span data-ttu-id="b8664-117">在其他情况下，直接修改引用返回值的方法调用可能不总是需要。</span><span class="sxs-lookup"><span data-stu-id="b8664-117">In other cases, modifying the reference return value of a method call directly may not always be desirable.</span></span> <span data-ttu-id="b8664-118">例如，返回的字符串搜索方法可能无法始终找到匹配项。</span><span class="sxs-lookup"><span data-stu-id="b8664-118">For example, a search method that returns a string may not always find a match.</span></span> <span data-ttu-id="b8664-119">在这种情况下，你想要修改引用返回值，如果搜索成功。</span><span class="sxs-lookup"><span data-stu-id="b8664-119">In that case, you want to modify the reference return value only if the search is successful.</span></span>

<span data-ttu-id="b8664-120">以下C#的示例演示了此方案。</span><span class="sxs-lookup"><span data-stu-id="b8664-120">The following C# example illustrates this scenario.</span></span> <span data-ttu-id="b8664-121">它定义`Sentence`类编写的C#包括`FindNext`方法，用于以指定子字符串开头的句子中查找下一个词。</span><span class="sxs-lookup"><span data-stu-id="b8664-121">It defines a `Sentence` class written in C# includes a `FindNext` method that finds the next word in a sentence that begins with a specified substring.</span></span> <span data-ttu-id="b8664-122">该字符串作为引用返回值返回，方法引用传递的 `Boolean` 变量指示搜索是否成功。</span><span class="sxs-lookup"><span data-stu-id="b8664-122">The string is returned as a reference return value, and a `Boolean` variable passed by reference to the method indicates whether the search was successful.</span></span> <span data-ttu-id="b8664-123">引用返回值指示调用方可以仅读取返回的值;他或她还可以修改它，并在内部中包含的数据中反映所做的修改`Sentence`类。</span><span class="sxs-lookup"><span data-stu-id="b8664-123">The reference return value indicates that the caller can not only read the returned value; he or she can also modify it, and that modification is reflected in the data contained internally in the `Sentence` class.</span></span>

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

<span data-ttu-id="b8664-124">直接修改引用返回值在此情况下是不可靠，由于方法调用可能无法找到匹配项并返回该句中的第一个单词。</span><span class="sxs-lookup"><span data-stu-id="b8664-124">Directly modifying the reference return value in this case is not reliable, since the method call may fail to find a match and return the first word in the sentence.</span></span> <span data-ttu-id="b8664-125">在这种情况下，调用方无意间修改句子的第一个单词。</span><span class="sxs-lookup"><span data-stu-id="b8664-125">In that case, the caller will inadvertently modify the first word of the sentence.</span></span> <span data-ttu-id="b8664-126">这可能由调用方返回阻止`null`(或`Nothing`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="b8664-126">This could be prevented by the caller returning a `null` (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="b8664-127">在这种情况下，尝试修改其值是一个字符串，但是`Nothing`引发<xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="b8664-127">But in that case, attempting to modify a string whose value is `Nothing` throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="b8664-128">返回调用方还可能禁止<xref:System.String.Empty?displayProperty=nameWithType>，但这需要调用方定义其值是一个字符串变量<xref:System.String.Empty?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="b8664-128">If could also be prevented by the caller returning <xref:System.String.Empty?displayProperty=nameWithType>, but this requires that the caller define a string variable whose value is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b8664-129">当调用方可以修改该字符串时，修改本身没有任何用处，因为修改后的字符串中存储的句子之间没有任何关系的词`Sentence`类。</span><span class="sxs-lookup"><span data-stu-id="b8664-129">While the caller can modify that string, the modification itself serves no purpose, since the modified string has no relationship to the words in the sentence stored by the `Sentence` class.</span></span>

<span data-ttu-id="b8664-130">处理这种情况的最佳方式是通过对一个帮助器方法的引用传递引用返回值。</span><span class="sxs-lookup"><span data-stu-id="b8664-130">The best way to handle this scenario is to pass the reference return value by reference to a helper method.</span></span> <span data-ttu-id="b8664-131">帮助器方法然后包含逻辑，以便确定是否调用该方法成功，如果有的话，若要修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="b8664-131">The helper method then contains the logic to determine whether the method call succeeded and, if it did, to modify the reference return value.</span></span> <span data-ttu-id="b8664-132">下面的示例提供了一种可能实现。</span><span class="sxs-lookup"><span data-stu-id="b8664-132">The following example provides a possible implementation.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a><span data-ttu-id="b8664-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8664-133">See also</span></span>

- [<span data-ttu-id="b8664-134">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="b8664-134">Passing arguments by value and by reference</span></span>](passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="b8664-135">Visual Basic 中的过程</span><span class="sxs-lookup"><span data-stu-id="b8664-135">Procedures in Visual Basic</span></span>](index.md)
