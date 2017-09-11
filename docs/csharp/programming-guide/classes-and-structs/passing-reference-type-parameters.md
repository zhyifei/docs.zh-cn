---
title: "传递引用类型参数（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: 14
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
ms.openlocfilehash: 3f57dc9f0de6fae6da3ec8e6e6cfdc3a21baeaea
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="passing-reference-type-parameters-c-programming-guide"></a><span data-ttu-id="782ab-102">传递引用类型参数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="782ab-102">Passing Reference-Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="782ab-103">[引用类型](../../../csharp/language-reference/keywords/reference-types.md)的变量不直接包含其数据；它包含对其数据的引用。</span><span class="sxs-lookup"><span data-stu-id="782ab-103">A variable of a [reference type](../../../csharp/language-reference/keywords/reference-types.md) does not contain its data directly; it contains a reference to its data.</span></span> <span data-ttu-id="782ab-104">如果按值传递引用类型参数，则可能会按引用更改指向的数据，例如类成员的值。</span><span class="sxs-lookup"><span data-stu-id="782ab-104">When you pass a reference-type parameter by value, it is possible to change the data pointed to by the reference, such as the value of a class member.</span></span> <span data-ttu-id="782ab-105">但是，不能更改引用本身的值；也就是说，不能使用相同引用为新类分配内存，并将其保留在程序块外部。</span><span class="sxs-lookup"><span data-stu-id="782ab-105">However, you cannot change the value of the reference itself; that is, you cannot use the same reference to allocate memory for a new class and have it persist outside the block.</span></span> <span data-ttu-id="782ab-106">为此，请使用 [ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out.md) 关键字传递参数。</span><span class="sxs-lookup"><span data-stu-id="782ab-106">To do that, pass the parameter using the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) keyword.</span></span> <span data-ttu-id="782ab-107">为简单起见，下面的示例使用 `ref`。</span><span class="sxs-lookup"><span data-stu-id="782ab-107">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-reference-types-by-value"></a><span data-ttu-id="782ab-108">按值传递引用类型</span><span class="sxs-lookup"><span data-stu-id="782ab-108">Passing Reference Types by Value</span></span>  
 <span data-ttu-id="782ab-109">以下示例演示将引用类型参数 `arr` 按值传递给方法 `Change`。</span><span class="sxs-lookup"><span data-stu-id="782ab-109">The following example demonstrates passing a reference-type parameter, `arr`, by value, to a method, `Change`.</span></span> <span data-ttu-id="782ab-110">由于该参数是对 `arr` 的引用，因此可以更改数组元素的值。</span><span class="sxs-lookup"><span data-stu-id="782ab-110">Because the parameter is a reference to `arr`, it is possible to change the values of the array elements.</span></span> <span data-ttu-id="782ab-111">但是，只有在方法内才能将参数重新分配给其他内存位置，且不会影响原始变量 `arr`。</span><span class="sxs-lookup"><span data-stu-id="782ab-111">However, the attempt to reassign the parameter to a different memory location only works inside the method and does not affect the original variable, `arr`.</span></span>  
  
 <span data-ttu-id="782ab-112">[!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="782ab-112">[!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="782ab-113">在前面的示例中，数组 `arr` 属于引用类型，传递给不含 `ref` 参数的方法。</span><span class="sxs-lookup"><span data-stu-id="782ab-113">In the preceding example, the array, `arr`, which is a reference type, is passed to the method without the `ref` parameter.</span></span> <span data-ttu-id="782ab-114">在这种情况下，将向该方法传递一个指向 `arr` 的引用副本。</span><span class="sxs-lookup"><span data-stu-id="782ab-114">In such a case, a copy of the reference, which points to `arr`, is passed to the method.</span></span> <span data-ttu-id="782ab-115">输出表明，此方法可以更改数组元素的内容，在本示例中将 `1` 更改为了 `888`。</span><span class="sxs-lookup"><span data-stu-id="782ab-115">The output shows that it is possible for the method to change the contents of an array element, in this case from `1` to `888`.</span></span> <span data-ttu-id="782ab-116">但是，通过在 `Change` 方法内使用 [new](../../../csharp/language-reference/keywords/new.md) 运算符来分配一份新的内存可使变量 `pArray` 引用新的数组。</span><span class="sxs-lookup"><span data-stu-id="782ab-116">However, allocating a new portion of memory by using the [new](../../../csharp/language-reference/keywords/new.md) operator inside the `Change` method makes the variable `pArray` reference a new array.</span></span> <span data-ttu-id="782ab-117">因此，此后的任意更改都不会影响创建于 `Main` 内的原始数组 `arr`。</span><span class="sxs-lookup"><span data-stu-id="782ab-117">Thus, any changes after that will not affect the original array, `arr`, which is created inside `Main`.</span></span> <span data-ttu-id="782ab-118">实际上，本示例创建了两个数组，一个在 `Main` 方法内，另一个在 `Change` 方法内。</span><span class="sxs-lookup"><span data-stu-id="782ab-118">In fact, two arrays are created in this example, one inside `Main` and one inside the `Change` method.</span></span>  
  
## <a name="passing-reference-types-by-reference"></a><span data-ttu-id="782ab-119">按引用传递引用类型</span><span class="sxs-lookup"><span data-stu-id="782ab-119">Passing Reference Types by Reference</span></span>  
 <span data-ttu-id="782ab-120">除了 `ref` 关键字添加到方法标头和调用，以下示例与上述示例相同。</span><span class="sxs-lookup"><span data-stu-id="782ab-120">The following example is the same as the previous example, except that the `ref` keyword is added to the method header and call.</span></span> <span data-ttu-id="782ab-121">方法中所作的任何更改都会影响调用程序中的原始变量。</span><span class="sxs-lookup"><span data-stu-id="782ab-121">Any changes that take place in the method affect the original variable in the calling program.</span></span>  
  
 <span data-ttu-id="782ab-122">[!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="782ab-122">[!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]</span></span>  
  
 <span data-ttu-id="782ab-123">方法内所作的所有更改都将影响 `Main` 中的原始数组。</span><span class="sxs-lookup"><span data-stu-id="782ab-123">All of the changes that take place inside the method affect the original array in `Main`.</span></span> <span data-ttu-id="782ab-124">事实上，将使用 `new` 运算符重新分配原始数组。</span><span class="sxs-lookup"><span data-stu-id="782ab-124">In fact, the original array is reallocated using the `new` operator.</span></span> <span data-ttu-id="782ab-125">因此，调用 `Change` 方法后，对 `arr` 的任何引用都将指向 `Change` 方法中创建的五元素数组。</span><span class="sxs-lookup"><span data-stu-id="782ab-125">Thus, after calling the `Change` method, any reference to `arr` points to the five-element array, which is created in the `Change` method.</span></span>  
  
## <a name="swapping-two-strings"></a><span data-ttu-id="782ab-126">交换两个字符串</span><span class="sxs-lookup"><span data-stu-id="782ab-126">Swapping Two Strings</span></span>  
 <span data-ttu-id="782ab-127">按引用传递引用类型参数的一个很好的示例是交换字符串。</span><span class="sxs-lookup"><span data-stu-id="782ab-127">Swapping strings is a good example of passing reference-type parameters by reference.</span></span> <span data-ttu-id="782ab-128">在示例中，`str1` 和 `str2`两个字符串在 `Main` 中初始化，然后传递给 `SwapStrings` 方法，作为由 `ref` 关键字修改的参数。</span><span class="sxs-lookup"><span data-stu-id="782ab-128">In the example, two strings, `str1` and `str2`, are initialized in `Main` and passed to the `SwapStrings` method as parameters modified by the `ref` keyword.</span></span> <span data-ttu-id="782ab-129">这两个字符串在该方法以及 `Main` 内交换。</span><span class="sxs-lookup"><span data-stu-id="782ab-129">The two strings are swapped inside the method and inside `Main` as well.</span></span>  
  
 <span data-ttu-id="782ab-130">[!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="782ab-130">[!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]</span></span>  
  
 <span data-ttu-id="782ab-131">在此示例中，需要按引用传递参数，以影响调用程序中的变量。</span><span class="sxs-lookup"><span data-stu-id="782ab-131">In this example, the parameters need to be passed by reference to affect the variables in the calling program.</span></span> <span data-ttu-id="782ab-132">如果同时从方法标头和方法调用中删除 `ref` 关键字，调用程序中不会发生任何更改。</span><span class="sxs-lookup"><span data-stu-id="782ab-132">If you remove the `ref` keyword from both the method header and the method call, no changes will take place in the calling program.</span></span>  
  
 <span data-ttu-id="782ab-133">有关字符串的详细信息，请参阅[字符串](../../../csharp/language-reference/keywords/string.md)。</span><span class="sxs-lookup"><span data-stu-id="782ab-133">For more information about strings, see [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782ab-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="782ab-134">See Also</span></span>  
 <span data-ttu-id="782ab-135">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="782ab-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="782ab-136">[传递参数](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="782ab-136">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 <span data-ttu-id="782ab-137">[使用 ref 和 out 传递数组](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md) </span><span class="sxs-lookup"><span data-stu-id="782ab-137">[Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md) </span></span>  
 <span data-ttu-id="782ab-138">[ref](../../../csharp/language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="782ab-138">[ref](../../../csharp/language-reference/keywords/ref.md) </span></span>  
 [<span data-ttu-id="782ab-139">引用类型</span><span class="sxs-lookup"><span data-stu-id="782ab-139">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)

