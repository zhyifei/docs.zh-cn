---
title: 参考返回值
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: f2a92c584dbb12a322e28435d797fa4d7c2f6dbb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186926"
---
# <a name="support-for-reference-return-values-visual-basic"></a><span data-ttu-id="80f92-102">支持参考返回值（可视基本值）</span><span class="sxs-lookup"><span data-stu-id="80f92-102">Support for reference return values (Visual Basic)</span></span>

<span data-ttu-id="80f92-103">从 C# 7.0 开始，C# 语言支持*参考返回值*。</span><span class="sxs-lookup"><span data-stu-id="80f92-103">Starting with C# 7.0, the C# language supports *reference return values*.</span></span> <span data-ttu-id="80f92-104">理解引用返回值的一种方法是，它们是通过引用传递给方法的参数的相反。</span><span class="sxs-lookup"><span data-stu-id="80f92-104">One way to understand reference return values is that they are the opposite of arguments that are passed by reference to a method.</span></span> <span data-ttu-id="80f92-105">修改引用传递的参数时，更改将反映在调用方上的变量的值中。</span><span class="sxs-lookup"><span data-stu-id="80f92-105">When an argument passed by reference is modified, the changes are reflected in value of the variable on the caller.</span></span> <span data-ttu-id="80f92-106">当方法向调用方提供引用返回值时，调用方对引用返回值所做的修改将反映在被调用方法的数据中。</span><span class="sxs-lookup"><span data-stu-id="80f92-106">When an method provides a reference return value to a caller, modifications made to the reference return value by the caller are reflected in the called method's data.</span></span>

<span data-ttu-id="80f92-107">Visual Basic 不允许使用引用返回值编写方法，但它确实允许您使用引用返回值。</span><span class="sxs-lookup"><span data-stu-id="80f92-107">Visual Basic does not allow you to author methods with reference return values, but it does allow you to consume reference return values.</span></span> <span data-ttu-id="80f92-108">换句话说，可以调用具有引用返回值的方法并修改该返回值，对引用返回值的更改将反映在被调用的方法的数据中。</span><span class="sxs-lookup"><span data-stu-id="80f92-108">In other words, you can call a method with a reference return value and modify that return value, and changes to the reference return value are reflected in the called method's data.</span></span>

## <a name="modifying-the-ref-return-value-directly"></a><span data-ttu-id="80f92-109">直接修改 ref 返回值</span><span class="sxs-lookup"><span data-stu-id="80f92-109">Modifying the ref return value directly</span></span>

<span data-ttu-id="80f92-110">对于始终成功且没有`ByRef`参数的方法，可以直接修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="80f92-110">For methods that always succeed and have no `ByRef` parameters, you can modify the reference return value directly.</span></span> <span data-ttu-id="80f92-111">为此，通过将新值分配给返回引用返回值的表达式。</span><span class="sxs-lookup"><span data-stu-id="80f92-111">You do this by assigning the new value to the expressions that returns the reference return value.</span></span>

<span data-ttu-id="80f92-112">下面的 C# 示例定义了一`NumericValue.IncrementValue`个方法，该方法将内部值递增并返回为引用返回值。</span><span class="sxs-lookup"><span data-stu-id="80f92-112">The following C# example defines a `NumericValue.IncrementValue` method that increments an internal value and returns it as a reference return value.</span></span>

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

<span data-ttu-id="80f92-113">然后，调用方在以下 Visual Basic 示例中修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="80f92-113">The reference return value is then modified by the caller in the following Visual Basic example.</span></span> <span data-ttu-id="80f92-114">请注意，使用 方法调用`NumericValue.IncrementValue`的行不会为 方法分配值。</span><span class="sxs-lookup"><span data-stu-id="80f92-114">Note that the line with the `NumericValue.IncrementValue` method call does not assign a value to the method.</span></span> <span data-ttu-id="80f92-115">相反，它将值分配给方法返回的引用返回值。</span><span class="sxs-lookup"><span data-stu-id="80f92-115">Instead, it assigns a value to the reference return value returned by the method.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a><span data-ttu-id="80f92-116">使用帮助器方法</span><span class="sxs-lookup"><span data-stu-id="80f92-116">Using a helper method</span></span>

<span data-ttu-id="80f92-117">在其他情况下，直接修改方法调用的引用返回值可能并不总是可取的。</span><span class="sxs-lookup"><span data-stu-id="80f92-117">In other cases, modifying the reference return value of a method call directly may not always be desirable.</span></span> <span data-ttu-id="80f92-118">例如，返回字符串的搜索方法可能并不总是找到匹配项。</span><span class="sxs-lookup"><span data-stu-id="80f92-118">For example, a search method that returns a string may not always find a match.</span></span> <span data-ttu-id="80f92-119">在这种情况下，仅当搜索成功时，才要修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="80f92-119">In that case, you want to modify the reference return value only if the search is successful.</span></span>

<span data-ttu-id="80f92-120">以下 C# 示例说明了此方案。</span><span class="sxs-lookup"><span data-stu-id="80f92-120">The following C# example illustrates this scenario.</span></span> <span data-ttu-id="80f92-121">它定义用`Sentence`C# 编写的类包括一`FindNext`个方法，该方法在以指定的子字符串开头的句子中查找下一个单词。</span><span class="sxs-lookup"><span data-stu-id="80f92-121">It defines a `Sentence` class written in C# includes a `FindNext` method that finds the next word in a sentence that begins with a specified substring.</span></span> <span data-ttu-id="80f92-122">该字符串作为引用返回值返回，方法引用传递的 `Boolean` 变量指示搜索是否成功。</span><span class="sxs-lookup"><span data-stu-id="80f92-122">The string is returned as a reference return value, and a `Boolean` variable passed by reference to the method indicates whether the search was successful.</span></span> <span data-ttu-id="80f92-123">引用返回值指示除了读取返回的值外，调用方还可以修改它，并且该修改反映在`Sentence`类内部包含的数据中。</span><span class="sxs-lookup"><span data-stu-id="80f92-123">The reference return value indicates that in addition to reading the returned value, the caller can also modify it, and that modification is reflected in the data contained internally in the `Sentence` class.</span></span>

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

<span data-ttu-id="80f92-124">在这种情况下，直接修改引用返回值不可靠，因为方法调用可能无法找到匹配项并返回句子中的第一个单词。</span><span class="sxs-lookup"><span data-stu-id="80f92-124">Directly modifying the reference return value in this case is not reliable, since the method call may fail to find a match and return the first word in the sentence.</span></span> <span data-ttu-id="80f92-125">在这种情况下，调用方将无意中修改句子的第一个单词。</span><span class="sxs-lookup"><span data-stu-id="80f92-125">In that case, the caller will inadvertently modify the first word of the sentence.</span></span> <span data-ttu-id="80f92-126">调用方返回 （`null`或`Nothing`视觉基本值） 可以防止这种情况。</span><span class="sxs-lookup"><span data-stu-id="80f92-126">This could be prevented by the caller returning a `null` (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="80f92-127">但是在这种情况下，尝试修改其值为`Nothing`的字符串将引发 。 <xref:System.NullReferenceException></span><span class="sxs-lookup"><span data-stu-id="80f92-127">But in that case, attempting to modify a string whose value is `Nothing` throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="80f92-128">如果调用方也可以阻止 返回<xref:System.String.Empty?displayProperty=nameWithType>，但这需要调用方定义其值为<xref:System.String.Empty?displayProperty=nameWithType>的字符串变量。</span><span class="sxs-lookup"><span data-stu-id="80f92-128">If could also be prevented by the caller returning <xref:System.String.Empty?displayProperty=nameWithType>, but this requires that the caller define a string variable whose value is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span> <span data-ttu-id="80f92-129">虽然调用方可以修改该字符串，但修改本身没有用处，因为修改后的字符串与`Sentence`类存储的句子中的单词没有关系。</span><span class="sxs-lookup"><span data-stu-id="80f92-129">While the caller can modify that string, the modification itself serves no purpose, since the modified string has no relationship to the words in the sentence stored by the `Sentence` class.</span></span>

<span data-ttu-id="80f92-130">处理此方案的最佳方法是通过引用帮助器方法传递引用返回值。</span><span class="sxs-lookup"><span data-stu-id="80f92-130">The best way to handle this scenario is to pass the reference return value by reference to a helper method.</span></span> <span data-ttu-id="80f92-131">然后，帮助器方法包含逻辑，以确定方法调用是否成功，如果成功，则修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="80f92-131">The helper method then contains the logic to determine whether the method call succeeded and, if it did, to modify the reference return value.</span></span> <span data-ttu-id="80f92-132">下面的示例提供了一个可能的实现。</span><span class="sxs-lookup"><span data-stu-id="80f92-132">The following example provides a possible implementation.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a><span data-ttu-id="80f92-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80f92-133">See also</span></span>

- [<span data-ttu-id="80f92-134">按值和引用传递参数</span><span class="sxs-lookup"><span data-stu-id="80f92-134">Passing arguments by value and by reference</span></span>](passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="80f92-135">Visual Basic 中的过程</span><span class="sxs-lookup"><span data-stu-id="80f92-135">Procedures in Visual Basic</span></span>](index.md)
