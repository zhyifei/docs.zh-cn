---
title: Ref 返回值 (Visual Basic)
ms.custom: ''
ms.date: 04/28/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6055028ac92016cbc4b6f7bffa7f483e5ea76608
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="support-for-reference-return-values-visual-basic"></a><span data-ttu-id="ec40d-102">引用返回值 (Visual Basic 中) 的支持</span><span class="sxs-lookup"><span data-stu-id="ec40d-102">Support for reference return values (Visual Basic)</span></span>

<span data-ttu-id="ec40d-103">从 C# 7.0 开始，C# 语言支持*引用返回值*。</span><span class="sxs-lookup"><span data-stu-id="ec40d-103">Starting with C# 7.0, the C# language supports *reference return values*.</span></span> <span data-ttu-id="ec40d-104">若要了解引用返回值的一种方法是它们与通过对方法的引用传递的自变量的符号相反。</span><span class="sxs-lookup"><span data-stu-id="ec40d-104">One way to understand reference return values is that they are the opposite of arguments that are passed by reference to a method.</span></span> <span data-ttu-id="ec40d-105">通过引用传递的自变量修改时，更改变量值中反映在调用方。</span><span class="sxs-lookup"><span data-stu-id="ec40d-105">When an argument passed by reference is modified, the changes are reflected in value of the variable on the caller.</span></span> <span data-ttu-id="ec40d-106">当方法调用方提供的引用返回值时，由调用方对引用返回值所做的修改将反映在调用的方法的数据。</span><span class="sxs-lookup"><span data-stu-id="ec40d-106">When an method provides a reference return value to a caller, modifications made to the reference return value by the caller are reflected in the called method's data.</span></span>

<span data-ttu-id="ec40d-107">Visual Basic 不允许你到引用作者方法返回值，但它允许你使用引用返回值。</span><span class="sxs-lookup"><span data-stu-id="ec40d-107">Visual Basic does not allow you to author methods with reference return values, but it does allow you to consume reference return values.</span></span> <span data-ttu-id="ec40d-108">换而言之，可以调用具有引用返回值的方法，还可以修改该返回值，并为引用返回值的更改会反映在调用的方法的数据。</span><span class="sxs-lookup"><span data-stu-id="ec40d-108">In other words, you can call a method with a reference return value and modify that return value, and changes to the reference return value are reflected in the called method's data.</span></span>

## <a name="modifying-the-ref-return-value-directly"></a><span data-ttu-id="ec40d-109">直接修改 ref 返回值</span><span class="sxs-lookup"><span data-stu-id="ec40d-109">Modifying the ref return value directly</span></span>

<span data-ttu-id="ec40d-110">方法始终会成功并且没有`ByRef`参数，你可以直接修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="ec40d-110">For methods that always succeed and have no `ByRef` parameters, you can modify the reference return value directly.</span></span> <span data-ttu-id="ec40d-111">通过将新值分配给返回的引用返回值的表达式来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ec40d-111">You do this by assigning the new value to the expressions that returns the reference return value.</span></span> 

<span data-ttu-id="ec40d-112">下面的 C# 示例定义`NumericValue.IncrementValue`递增内部值并将其返回作为引用的方法返回值。</span><span class="sxs-lookup"><span data-stu-id="ec40d-112">The following C# example defines a `NumericValue.IncrementValue` method that increments an internal value and returns it as a reference return value.</span></span> 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

<span data-ttu-id="ec40d-113">引用返回调用方在下面的 Visual Basic 示例然后修改值。</span><span class="sxs-lookup"><span data-stu-id="ec40d-113">The reference return value is then modified by the caller in the following Visual Basic example.</span></span> <span data-ttu-id="ec40d-114">请注意，在行的`NumericValue.IncrementValue`方法调用不会分配给该方法的一个值。</span><span class="sxs-lookup"><span data-stu-id="ec40d-114">Note that the line with the `NumericValue.IncrementValue` method call does not assign a value to the method.</span></span> <span data-ttu-id="ec40d-115">相反，它将值分配给该方法返回的引用返回值。</span><span class="sxs-lookup"><span data-stu-id="ec40d-115">Instead, it assigns a value to the reference return value returned by the method.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a><span data-ttu-id="ec40d-116">使用一个帮助器方法</span><span class="sxs-lookup"><span data-stu-id="ec40d-116">Using a helper method</span></span>

<span data-ttu-id="ec40d-117">在其他情况下，直接修改方法调用的引用返回值可能不始终需要。</span><span class="sxs-lookup"><span data-stu-id="ec40d-117">In other cases, modifying the reference return value of a method call directly may not always be desirable.</span></span> <span data-ttu-id="ec40d-118">例如，返回的字符串的搜索方法可能无法始终找到匹配项。</span><span class="sxs-lookup"><span data-stu-id="ec40d-118">For example, a search method that returns a string may not always find a match.</span></span> <span data-ttu-id="ec40d-119">在这种情况下，你想要修改的引用返回值，如果搜索成功。</span><span class="sxs-lookup"><span data-stu-id="ec40d-119">In that case, you want to modify the reference return value only if the search is successful.</span></span>

<span data-ttu-id="ec40d-120">下面的 C# 示例阐释了这种情况。</span><span class="sxs-lookup"><span data-stu-id="ec40d-120">The following C# example illustrates this scenario.</span></span> <span data-ttu-id="ec40d-121">它定义`Sentence`用 C# 编写的类包括`FindNext`以指定的子字符串开头的句子中查找下一步的单词的方法。</span><span class="sxs-lookup"><span data-stu-id="ec40d-121">It defines a `Sentence` class written in C# includes a `FindNext` method that finds the next word in a sentence that begins with a specified substring.</span></span> <span data-ttu-id="ec40d-122">该字符串作为引用返回值返回，方法引用传递的 `Boolean` 变量指示搜索是否成功。</span><span class="sxs-lookup"><span data-stu-id="ec40d-122">The string is returned as a reference return value, and a `Boolean` variable passed by reference to the method indicates whether the search was successful.</span></span> <span data-ttu-id="ec40d-123">引用返回值指示调用方可以仅读取返回的值;他或她还可以修改它，并在内部中包含的数据中反映所做的修改`Sentence`类。</span><span class="sxs-lookup"><span data-stu-id="ec40d-123">The reference return value indicates that the caller can not only read the returned value; he or she can also modify it, and that modification is reflected in the data contained internally in the `Sentence` class.</span></span>

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

<span data-ttu-id="ec40d-124">直接修改引用返回值在这种情况下是不可靠的因为方法调用可能会失败，以查找匹配项并返回该句中的第一个单词。</span><span class="sxs-lookup"><span data-stu-id="ec40d-124">Directly modifying the reference return value in this case is not reliable, since the method call may fail to find a match and return the first word in the sentence.</span></span> <span data-ttu-id="ec40d-125">在这种情况下，调用方将无意中修改句子的第一个单词。</span><span class="sxs-lookup"><span data-stu-id="ec40d-125">In that case, the caller will inadvertently modify the first word of the sentence.</span></span> <span data-ttu-id="ec40d-126">这可能会阻止由调用方返回`null`(或`Nothing`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="ec40d-126">This could be prevented by the caller returning a `null` (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="ec40d-127">但在这种情况下，尝试修改一个字符串，其值`Nothing`引发<xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="ec40d-127">But in that case, attempting to modify a string whose value is `Nothing` throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="ec40d-128">如果无法设置还将阻止由调用方返回<xref:System.String.Empty?displayProperty=nameWithType>，但这要求调用方定义其值是一个字符串变量<xref:System.String.Empty?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ec40d-128">If could also be prevented by the caller returning <xref:System.String.Empty?displayProperty=nameWithType>, but this requires that the caller define a string variable whose value is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ec40d-129">当调用方可以修改该字符串时，修改本身没有任何用途，因为修改后的字符串存储该句中的单词没有关系`Sentence`类。</span><span class="sxs-lookup"><span data-stu-id="ec40d-129">While the caller can modify that string, the modification itself serves no purpose, since the modified string has no relationship to the words in the sentence stored by the `Sentence` class.</span></span>

<span data-ttu-id="ec40d-130">处理这种情况的最佳方法是将引用返回值传递通过引用向一个帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="ec40d-130">The best way to handle this scenario is to pass the reference return value by reference to a helper method.</span></span> <span data-ttu-id="ec40d-131">帮助器方法然后包含逻辑，以便确定是否方法调用成功，否则，若要修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="ec40d-131">The helper method then contains the logic to determine whether the method call succeeded and, if it did, to modify the reference return value.</span></span> <span data-ttu-id="ec40d-132">下面的示例提供一个可能的实现。</span><span class="sxs-lookup"><span data-stu-id="ec40d-132">The following example provides a possible implementation.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a><span data-ttu-id="ec40d-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec40d-133">See also</span></span>

<span data-ttu-id="ec40d-134">[通过值和通过引用传递自变量](passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ec40d-134">[Passing arguments by value and by reference](passing-arguments-by-value-and-by-reference.md) </span></span>  
[<span data-ttu-id="ec40d-135">Visual Basic 中的过程</span><span class="sxs-lookup"><span data-stu-id="ec40d-135">Procedures in Visual Basic</span></span>](index.md)   


