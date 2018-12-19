---
title: 传递值类型参数 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
ms.openlocfilehash: df394a6b71a06edc064fba0925398f87ed1802a8
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245358"
---
# <a name="passing-value-type-parameters-c-programming-guide"></a><span data-ttu-id="fd49a-102">传递值类型参数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fd49a-102">Passing Value-Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="fd49a-103">一个[值类型](../../../csharp/language-reference/keywords/value-types.md)变量包含它直接与[引用类型](../../../csharp/language-reference/keywords/reference-types.md)变量相对的数据，其中包含对其数据的引用。</span><span class="sxs-lookup"><span data-stu-id="fd49a-103">A [value-type](../../../csharp/language-reference/keywords/value-types.md) variable contains its data directly as opposed to a [reference-type](../../../csharp/language-reference/keywords/reference-types.md) variable, which contains a reference to its data.</span></span> <span data-ttu-id="fd49a-104">按值将值-类型变量传递给方法，意味着将变量副本传递给该方法。</span><span class="sxs-lookup"><span data-stu-id="fd49a-104">Passing a value-type variable to a method by value means passing a copy of the variable to the method.</span></span> <span data-ttu-id="fd49a-105">在方法内发生的对该实参进行的任何更改不会影响存储在形参变量中的原始数据。</span><span class="sxs-lookup"><span data-stu-id="fd49a-105">Any changes to the parameter that take place inside the method have no affect on the original data stored in the argument variable.</span></span> <span data-ttu-id="fd49a-106">如果想用调用的方法来更改参数的值，必须使用 [ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 关键字，通过引用进行传递。</span><span class="sxs-lookup"><span data-stu-id="fd49a-106">If you want the called method to change the value of the parameter, you must pass it by reference, using the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) keyword.</span></span> <span data-ttu-id="fd49a-107">还可以使用 [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) 关键字来按引用传递值参数，以避免复制并同时保证不更改值。</span><span class="sxs-lookup"><span data-stu-id="fd49a-107">You may also use the [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) keyword to pass a value parameter by reference to avoid the copy while guaranteeing that the value will not be changed.</span></span> <span data-ttu-id="fd49a-108">为简单起见，下面的示例使用 `ref`。</span><span class="sxs-lookup"><span data-stu-id="fd49a-108">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-value-types-by-value"></a><span data-ttu-id="fd49a-109">按值传递值类型</span><span class="sxs-lookup"><span data-stu-id="fd49a-109">Passing Value Types by Value</span></span>  
 <span data-ttu-id="fd49a-110">下面的示例演示按值传递值-类型参数。</span><span class="sxs-lookup"><span data-stu-id="fd49a-110">The following example demonstrates passing value-type parameters by value.</span></span> <span data-ttu-id="fd49a-111">变量 `n` 按值传递给方法 `SquareIt`。</span><span class="sxs-lookup"><span data-stu-id="fd49a-111">The variable `n` is passed by value to the method `SquareIt`.</span></span> <span data-ttu-id="fd49a-112">在方法内发生的任何更改不会影响该变量的原始值。</span><span class="sxs-lookup"><span data-stu-id="fd49a-112">Any changes that take place inside the method have no affect on the original value of the variable.</span></span>  
  
 [!code-csharp[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]  
  
 <span data-ttu-id="fd49a-113">变量 `n` 是值类型。</span><span class="sxs-lookup"><span data-stu-id="fd49a-113">The variable `n` is a value type.</span></span> <span data-ttu-id="fd49a-114">它包含其数据，值为 `5`。</span><span class="sxs-lookup"><span data-stu-id="fd49a-114">It contains its data, the value `5`.</span></span> <span data-ttu-id="fd49a-115">调用 `SquareIt` 时，`n` 的内容复制到参数 `x` 中，这是该方法内的平方值。</span><span class="sxs-lookup"><span data-stu-id="fd49a-115">When `SquareIt` is invoked, the contents of `n` are copied into the parameter `x`, which is squared inside the method.</span></span> <span data-ttu-id="fd49a-116">但是在 `Main` 中，`n` 的值在调用 `SquareIt` 方法之后与之前相同。</span><span class="sxs-lookup"><span data-stu-id="fd49a-116">In `Main`, however, the value of `n` is the same after calling the `SquareIt` method as it was before.</span></span> <span data-ttu-id="fd49a-117">在方法内发生的更改只影响本地变量 `x`。</span><span class="sxs-lookup"><span data-stu-id="fd49a-117">The change that takes place inside the method only affects the local variable `x`.</span></span>  
  
## <a name="passing-value-types-by-reference"></a><span data-ttu-id="fd49a-118">按引用传递值类型</span><span class="sxs-lookup"><span data-stu-id="fd49a-118">Passing Value Types by Reference</span></span>  
 <span data-ttu-id="fd49a-119">下面的示例与上述示例相同，除了自变量是作为 `ref` 参数传递的。</span><span class="sxs-lookup"><span data-stu-id="fd49a-119">The following example is the same as the previous example, except that the argument is passed as a `ref` parameter.</span></span> <span data-ttu-id="fd49a-120">`x` 在方法中更改时，基础自变量的值 `n` 也更改。</span><span class="sxs-lookup"><span data-stu-id="fd49a-120">The value of the underlying argument, `n`, is changed when `x` is changed in the method.</span></span>  
  
 [!code-csharp[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]  
  
 <span data-ttu-id="fd49a-121">在此示例中，它传递的不是 `n` 的值；而是传递 `n` 的引用。</span><span class="sxs-lookup"><span data-stu-id="fd49a-121">In this example, it is not the value of `n` that is passed; rather, a reference to `n` is passed.</span></span> <span data-ttu-id="fd49a-122">参数 `x` 不是 [int](../../../csharp/language-reference/keywords/int.md)；它是对 `int` 的引用，在这种情况下，是对 `n` 的引用。</span><span class="sxs-lookup"><span data-stu-id="fd49a-122">The parameter `x` is not an [int](../../../csharp/language-reference/keywords/int.md); it is a reference to an `int`, in this case, a reference to `n`.</span></span> <span data-ttu-id="fd49a-123">因此，当 `x` 在方法中进行平方计算时，实际求平方值的就是 `x` 所指的 `n`。</span><span class="sxs-lookup"><span data-stu-id="fd49a-123">Therefore, when `x` is squared inside the method, what actually is squared is what `x` refers to, `n`.</span></span>  
  
## <a name="swapping-value-types"></a><span data-ttu-id="fd49a-124">交换值类型</span><span class="sxs-lookup"><span data-stu-id="fd49a-124">Swapping Value Types</span></span>  
 <span data-ttu-id="fd49a-125">更改自变量值的一个常见示例是交换方法，其中将两个变量传递给方法，并由该方法交换其内容。</span><span class="sxs-lookup"><span data-stu-id="fd49a-125">A common example of changing the values of arguments is a swap method, where you pass two variables to the method, and the method swaps their contents.</span></span> <span data-ttu-id="fd49a-126">必须通过引用将自变量传递给交换方法。</span><span class="sxs-lookup"><span data-stu-id="fd49a-126">You must pass the arguments to the swap method by reference.</span></span> <span data-ttu-id="fd49a-127">否则，交换参数在方法中的本地副本，并且调用方法中不会发生更改。</span><span class="sxs-lookup"><span data-stu-id="fd49a-127">Otherwise, you swap local copies of the parameters inside the method, and no change occurs in the calling method.</span></span> <span data-ttu-id="fd49a-128">下面的示例交换整数值。</span><span class="sxs-lookup"><span data-stu-id="fd49a-128">The following example swaps integer values.</span></span>  
  
 [!code-csharp[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]  
  
 <span data-ttu-id="fd49a-129">调用 `SwapByRef` 方法时，在调用中使用 `ref` 关键字，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="fd49a-129">When you call the `SwapByRef` method, use the `ref` keyword in the call, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fd49a-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd49a-130">See Also</span></span>

- [<span data-ttu-id="fd49a-131">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fd49a-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="fd49a-132">传递参数</span><span class="sxs-lookup"><span data-stu-id="fd49a-132">Passing Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)  
- [<span data-ttu-id="fd49a-133">传递引用类型参数</span><span class="sxs-lookup"><span data-stu-id="fd49a-133">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)
