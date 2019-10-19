---
title: 引用返回值（Visual Basic）
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: 7401fdd0fa876d21a87dbe9faf9d979e6b3bdc5c
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581124"
---
# <a name="support-for-reference-return-values-visual-basic"></a><span data-ttu-id="5a804-102">支持引用返回值（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="5a804-102">Support for reference return values (Visual Basic)</span></span>

<span data-ttu-id="5a804-103">从C# 7.0 开始，该C#语言支持*引用返回值*。</span><span class="sxs-lookup"><span data-stu-id="5a804-103">Starting with C# 7.0, the C# language supports *reference return values*.</span></span> <span data-ttu-id="5a804-104">了解引用返回值的一种方法是，它们与通过引用传递给方法的参数相反。</span><span class="sxs-lookup"><span data-stu-id="5a804-104">One way to understand reference return values is that they are the opposite of arguments that are passed by reference to a method.</span></span> <span data-ttu-id="5a804-105">当修改通过引用传递的参数时，所做的更改将反映在调用方上的变量值中。</span><span class="sxs-lookup"><span data-stu-id="5a804-105">When an argument passed by reference is modified, the changes are reflected in value of the variable on the caller.</span></span> <span data-ttu-id="5a804-106">当方法为调用方提供引用返回值时，调用方对引用返回值所做的修改会反映在被调用方法的数据中。</span><span class="sxs-lookup"><span data-stu-id="5a804-106">When an method provides a reference return value to a caller, modifications made to the reference return value by the caller are reflected in the called method's data.</span></span>

<span data-ttu-id="5a804-107">Visual Basic 不允许使用引用返回值创作方法，但允许使用引用返回值。</span><span class="sxs-lookup"><span data-stu-id="5a804-107">Visual Basic does not allow you to author methods with reference return values, but it does allow you to consume reference return values.</span></span> <span data-ttu-id="5a804-108">换言之，您可以调用具有引用返回值的方法并修改该返回值，对引用返回值所做的更改将反映在被调用方法的数据中。</span><span class="sxs-lookup"><span data-stu-id="5a804-108">In other words, you can call a method with a reference return value and modify that return value, and changes to the reference return value are reflected in the called method's data.</span></span>

## <a name="modifying-the-ref-return-value-directly"></a><span data-ttu-id="5a804-109">直接修改引用返回值</span><span class="sxs-lookup"><span data-stu-id="5a804-109">Modifying the ref return value directly</span></span>

<span data-ttu-id="5a804-110">对于始终成功且无 `ByRef` 参数的方法，您可以直接修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="5a804-110">For methods that always succeed and have no `ByRef` parameters, you can modify the reference return value directly.</span></span> <span data-ttu-id="5a804-111">为此，可将新值分配给返回引用返回值的表达式。</span><span class="sxs-lookup"><span data-stu-id="5a804-111">You do this by assigning the new value to the expressions that returns the reference return value.</span></span>

<span data-ttu-id="5a804-112">下面C#的示例定义了一个 `NumericValue.IncrementValue` 方法，该方法递增内部值并将其作为引用返回值返回。</span><span class="sxs-lookup"><span data-stu-id="5a804-112">The following C# example defines a `NumericValue.IncrementValue` method that increments an internal value and returns it as a reference return value.</span></span>

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

<span data-ttu-id="5a804-113">然后，调用方在下面 Visual Basic 示例中修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="5a804-113">The reference return value is then modified by the caller in the following Visual Basic example.</span></span> <span data-ttu-id="5a804-114">请注意，具有 `NumericValue.IncrementValue` 方法调用的行不会向方法分配值。</span><span class="sxs-lookup"><span data-stu-id="5a804-114">Note that the line with the `NumericValue.IncrementValue` method call does not assign a value to the method.</span></span> <span data-ttu-id="5a804-115">相反，它将值赋给方法返回的引用返回值。</span><span class="sxs-lookup"><span data-stu-id="5a804-115">Instead, it assigns a value to the reference return value returned by the method.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a><span data-ttu-id="5a804-116">使用 helper 方法</span><span class="sxs-lookup"><span data-stu-id="5a804-116">Using a helper method</span></span>

<span data-ttu-id="5a804-117">在其他情况下，可能不会始终需要直接修改方法调用的引用返回值。</span><span class="sxs-lookup"><span data-stu-id="5a804-117">In other cases, modifying the reference return value of a method call directly may not always be desirable.</span></span> <span data-ttu-id="5a804-118">例如，返回字符串的搜索方法可能并不总是找到匹配项。</span><span class="sxs-lookup"><span data-stu-id="5a804-118">For example, a search method that returns a string may not always find a match.</span></span> <span data-ttu-id="5a804-119">在这种情况下，只需在搜索成功时才修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="5a804-119">In that case, you want to modify the reference return value only if the search is successful.</span></span>

<span data-ttu-id="5a804-120">下面C#的示例演示了这种情况。</span><span class="sxs-lookup"><span data-stu-id="5a804-120">The following C# example illustrates this scenario.</span></span> <span data-ttu-id="5a804-121">它定义了一个使用编写的C# `Sentence` 类包含一个 `FindNext` 方法，该方法在以指定的子字符串开头的句子中查找下一个单词。</span><span class="sxs-lookup"><span data-stu-id="5a804-121">It defines a `Sentence` class written in C# includes a `FindNext` method that finds the next word in a sentence that begins with a specified substring.</span></span> <span data-ttu-id="5a804-122">该字符串作为引用返回值返回，方法引用传递的 `Boolean` 变量指示搜索是否成功。</span><span class="sxs-lookup"><span data-stu-id="5a804-122">The string is returned as a reference return value, and a `Boolean` variable passed by reference to the method indicates whether the search was successful.</span></span> <span data-ttu-id="5a804-123">引用返回值指示调用方不能只读取返回的值;他（她）也可以对其进行修改，并且该修改会反映在 `Sentence` 类内部包含的数据中。</span><span class="sxs-lookup"><span data-stu-id="5a804-123">The reference return value indicates that the caller can not only read the returned value; he or she can also modify it, and that modification is reflected in the data contained internally in the `Sentence` class.</span></span>

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

<span data-ttu-id="5a804-124">在这种情况下直接修改引用返回值是不可靠的，因为方法调用可能找不到匹配项，并返回句子中的第一个单词。</span><span class="sxs-lookup"><span data-stu-id="5a804-124">Directly modifying the reference return value in this case is not reliable, since the method call may fail to find a match and return the first word in the sentence.</span></span> <span data-ttu-id="5a804-125">在这种情况下，调用方将无意中修改句子的第一个单词。</span><span class="sxs-lookup"><span data-stu-id="5a804-125">In that case, the caller will inadvertently modify the first word of the sentence.</span></span> <span data-ttu-id="5a804-126">调用方可以通过返回 `null` （或 Visual Basic 中的 `Nothing`）来防止此情况。</span><span class="sxs-lookup"><span data-stu-id="5a804-126">This could be prevented by the caller returning a `null` (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="5a804-127">但在这种情况下，尝试修改其值为 `Nothing` 的字符串将引发 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="5a804-127">But in that case, attempting to modify a string whose value is `Nothing` throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="5a804-128">如果调用方也可能会阻止 <xref:System.String.Empty?displayProperty=nameWithType>，但这要求调用方定义值为 <xref:System.String.Empty?displayProperty=nameWithType> 的字符串变量。</span><span class="sxs-lookup"><span data-stu-id="5a804-128">If could also be prevented by the caller returning <xref:System.String.Empty?displayProperty=nameWithType>, but this requires that the caller define a string variable whose value is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5a804-129">虽然调用方可以修改该字符串，但修改本身并没有作用，因为修改后的字符串与 `Sentence` 类存储的句子中的单词无关。</span><span class="sxs-lookup"><span data-stu-id="5a804-129">While the caller can modify that string, the modification itself serves no purpose, since the modified string has no relationship to the words in the sentence stored by the `Sentence` class.</span></span>

<span data-ttu-id="5a804-130">处理此方案的最佳方式是通过引用向 helper 方法传递引用返回值。</span><span class="sxs-lookup"><span data-stu-id="5a804-130">The best way to handle this scenario is to pass the reference return value by reference to a helper method.</span></span> <span data-ttu-id="5a804-131">然后，帮助器方法包含用于确定方法调用是否成功的逻辑，如果是，则修改引用返回值。</span><span class="sxs-lookup"><span data-stu-id="5a804-131">The helper method then contains the logic to determine whether the method call succeeded and, if it did, to modify the reference return value.</span></span> <span data-ttu-id="5a804-132">下面的示例提供了一个可能的实现。</span><span class="sxs-lookup"><span data-stu-id="5a804-132">The following example provides a possible implementation.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a><span data-ttu-id="5a804-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a804-133">See also</span></span>

- [<span data-ttu-id="5a804-134">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="5a804-134">Passing arguments by value and by reference</span></span>](passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="5a804-135">Visual Basic 中的过程</span><span class="sxs-lookup"><span data-stu-id="5a804-135">Procedures in Visual Basic</span></span>](index.md)
