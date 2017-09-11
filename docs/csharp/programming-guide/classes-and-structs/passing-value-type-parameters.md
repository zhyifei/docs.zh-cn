---
title: "传递值类型参数（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3377630fc4294831f6b9d66a69377aa42d973f1
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="passing-value-type-parameters-c-programming-guide"></a><span data-ttu-id="285a6-102">传递值类型参数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="285a6-102">Passing Value-Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="285a6-103">一个[值类型](../../../csharp/language-reference/keywords/value-types.md)变量包含它直接与[引用类型](../../../csharp/language-reference/keywords/reference-types.md)变量相对的数据，其中包含对其数据的引用。</span><span class="sxs-lookup"><span data-stu-id="285a6-103">A [value-type](../../../csharp/language-reference/keywords/value-types.md) variable contains its data directly as opposed to a [reference-type](../../../csharp/language-reference/keywords/reference-types.md) variable, which contains a reference to its data.</span></span> <span data-ttu-id="285a6-104">按值将值-类型变量传递给方法，意味着将变量副本传递给该方法。</span><span class="sxs-lookup"><span data-stu-id="285a6-104">Passing a value-type variable to a method by value means passing a copy of the variable to the method.</span></span> <span data-ttu-id="285a6-105">在方法内发生的对该实参进行的任何更改不会影响存储在形参变量中的原始数据。</span><span class="sxs-lookup"><span data-stu-id="285a6-105">Any changes to the parameter that take place inside the method have no affect on the original data stored in the argument variable.</span></span> <span data-ttu-id="285a6-106">如果想用调用的方法来更改参数的值，必须使用 [ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out.md) 关键字，通过引用进行传递。</span><span class="sxs-lookup"><span data-stu-id="285a6-106">If you want the called method to change the value of the parameter, you must pass it by reference, using the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) keyword.</span></span> <span data-ttu-id="285a6-107">为简单起见，下面的示例使用 `ref`。</span><span class="sxs-lookup"><span data-stu-id="285a6-107">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-value-types-by-value"></a><span data-ttu-id="285a6-108">按值传递值类型</span><span class="sxs-lookup"><span data-stu-id="285a6-108">Passing Value Types by Value</span></span>  
 <span data-ttu-id="285a6-109">下面的示例演示按值传递值-类型参数。</span><span class="sxs-lookup"><span data-stu-id="285a6-109">The following example demonstrates passing value-type parameters by value.</span></span> <span data-ttu-id="285a6-110">变量 `n` 按值传递给方法 `SquareIt`。</span><span class="sxs-lookup"><span data-stu-id="285a6-110">The variable `n` is passed by value to the method `SquareIt`.</span></span> <span data-ttu-id="285a6-111">在方法内发生的任何更改不会影响该变量的原始值。</span><span class="sxs-lookup"><span data-stu-id="285a6-111">Any changes that take place inside the method have no affect on the original value of the variable.</span></span>  
  
 <span data-ttu-id="285a6-112">[!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="285a6-112">[!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="285a6-113">变量 `n` 是值类型。</span><span class="sxs-lookup"><span data-stu-id="285a6-113">The variable `n` is a value type.</span></span> <span data-ttu-id="285a6-114">它包含其数据，值为 `5`。</span><span class="sxs-lookup"><span data-stu-id="285a6-114">It contains its data, the value `5`.</span></span> <span data-ttu-id="285a6-115">调用 `SquareIt` 时，`n` 的内容复制到参数 `x` 中，这是该方法内的平方值。</span><span class="sxs-lookup"><span data-stu-id="285a6-115">When `SquareIt` is invoked, the contents of `n` are copied into the parameter `x`, which is squared inside the method.</span></span> <span data-ttu-id="285a6-116">但是在 `Main` 中，`n` 的值在调用 `SquareIt` 方法之后与之前相同。</span><span class="sxs-lookup"><span data-stu-id="285a6-116">In `Main`, however, the value of `n` is the same after calling the `SquareIt` method as it was before.</span></span> <span data-ttu-id="285a6-117">在方法内发生的更改只影响本地变量 `x`。</span><span class="sxs-lookup"><span data-stu-id="285a6-117">The change that takes place inside the method only affects the local variable `x`.</span></span>  
  
## <a name="passing-value-types-by-reference"></a><span data-ttu-id="285a6-118">按引用传递值类型</span><span class="sxs-lookup"><span data-stu-id="285a6-118">Passing Value Types by Reference</span></span>  
 <span data-ttu-id="285a6-119">下面的示例与上述示例相同，除了自变量是作为 `ref` 参数传递的。</span><span class="sxs-lookup"><span data-stu-id="285a6-119">The following example is the same as the previous example, except that the argument is passed as a `ref` parameter.</span></span> <span data-ttu-id="285a6-120">`x` 在方法中更改时，基础自变量的值 `n` 也更改。</span><span class="sxs-lookup"><span data-stu-id="285a6-120">The value of the underlying argument, `n`, is changed when `x` is changed in the method.</span></span>  
  
 <span data-ttu-id="285a6-121">[!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="285a6-121">[!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]</span></span>  
  
 <span data-ttu-id="285a6-122">在此示例中，它传递的不是 `n` 的值；而是传递 `n` 的引用。</span><span class="sxs-lookup"><span data-stu-id="285a6-122">In this example, it is not the value of `n` that is passed; rather, a reference to `n` is passed.</span></span> <span data-ttu-id="285a6-123">参数 `x` 不是 [int](../../../csharp/language-reference/keywords/int.md)；它是对 `int` 的引用，在这种情况下，是对 `n` 的引用。</span><span class="sxs-lookup"><span data-stu-id="285a6-123">The parameter `x` is not an [int](../../../csharp/language-reference/keywords/int.md); it is a reference to an `int`, in this case, a reference to `n`.</span></span> <span data-ttu-id="285a6-124">因此，当 `x` 在方法中进行平方计算时，实际求平方值的就是 `x` 所指的 `n`。</span><span class="sxs-lookup"><span data-stu-id="285a6-124">Therefore, when `x` is squared inside the method, what actually is squared is what `x` refers to, `n`.</span></span>  
  
## <a name="swapping-value-types"></a><span data-ttu-id="285a6-125">交换值类型</span><span class="sxs-lookup"><span data-stu-id="285a6-125">Swapping Value Types</span></span>  
 <span data-ttu-id="285a6-126">更改自变量值的一个常见示例是交换方法，其中将两个变量传递给方法，并由该方法交换其内容。</span><span class="sxs-lookup"><span data-stu-id="285a6-126">A common example of changing the values of arguments is a swap method, where you pass two variables to the method, and the method swaps their contents.</span></span> <span data-ttu-id="285a6-127">必须通过引用将自变量传递给交换方法。</span><span class="sxs-lookup"><span data-stu-id="285a6-127">You must pass the arguments to the swap method by reference.</span></span> <span data-ttu-id="285a6-128">否则，交换参数在方法中的本地副本，并且调用方法中不会发生更改。</span><span class="sxs-lookup"><span data-stu-id="285a6-128">Otherwise, you swap local copies of the parameters inside the method, and no change occurs in the calling method.</span></span> <span data-ttu-id="285a6-129">下面的示例交换整数值。</span><span class="sxs-lookup"><span data-stu-id="285a6-129">The following example swaps integer values.</span></span>  
  
 <span data-ttu-id="285a6-130">[!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="285a6-130">[!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]</span></span>  
  
 <span data-ttu-id="285a6-131">调用 `SwapByRef` 方法时，在调用中使用 `ref` 关键字，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="285a6-131">When you call the `SwapByRef` method, use the `ref` keyword in the call, as shown in the following example.</span></span>  
  
 <span data-ttu-id="285a6-132">[!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="285a6-132">[!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="285a6-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="285a6-133">See Also</span></span>  
 <span data-ttu-id="285a6-134">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="285a6-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="285a6-135">[传递参数](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="285a6-135">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 [<span data-ttu-id="285a6-136">传递引用类型参数</span><span class="sxs-lookup"><span data-stu-id="285a6-136">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)

