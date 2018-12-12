---
title: C# 委托 - C# 语言介绍
description: 了解包含 C# 委托的晚期绑定
ms.date: 08/10/2016
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: 2744f774392ef021974535de535b063264ae9a54
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151273"
---
# <a name="delegates"></a><span data-ttu-id="dcaef-103">委托</span><span class="sxs-lookup"><span data-stu-id="dcaef-103">Delegates</span></span>

<span data-ttu-id="dcaef-104">***委托类型***表示对具有特定参数列表和返回类型的方法的引用。</span><span class="sxs-lookup"><span data-stu-id="dcaef-104">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="dcaef-105">通过委托，可以将方法视为可分配给变量并可作为参数传递的实体。</span><span class="sxs-lookup"><span data-stu-id="dcaef-105">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="dcaef-106">委托类似于其他一些语言中的函数指针概念，但与函数指针不同的是，委托不仅面向对象，还类型安全。</span><span class="sxs-lookup"><span data-stu-id="dcaef-106">Delegates are similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="dcaef-107">下面的示例声明并使用 `Function` 委托类型。</span><span class="sxs-lookup"><span data-stu-id="dcaef-107">The following example declares and uses a delegate type named `Function`.</span></span>

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

<span data-ttu-id="dcaef-108">`Function` 委托类型实例可以引用需要使用 `double` 自变量并返回 `double` 值的方法。</span><span class="sxs-lookup"><span data-stu-id="dcaef-108">An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value.</span></span> <span data-ttu-id="dcaef-109">`Apply` 方法将给定的函数应用于 `double[]` 的元素，从而返回包含结果的 `double[]`。</span><span class="sxs-lookup"><span data-stu-id="dcaef-109">The `Apply` method applies a given Function to the elements of a `double[]`, returning a `double[]` with the results.</span></span> <span data-ttu-id="dcaef-110">在 `Main` 方法中，`Apply` 用于向 `double[]` 应用三个不同的函数。</span><span class="sxs-lookup"><span data-stu-id="dcaef-110">In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.</span></span>

<span data-ttu-id="dcaef-111">委托可以引用静态方法（如上面示例中的 `Square` 或 `Math.Sin`）或实例方法（如上面示例中的 `m.Multiply`）。</span><span class="sxs-lookup"><span data-stu-id="dcaef-111">A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example).</span></span> <span data-ttu-id="dcaef-112">引用实例方法的委托还会引用特定对象，通过委托调用实例方法时，该对象会变成调用中的 `this`。</span><span class="sxs-lookup"><span data-stu-id="dcaef-112">A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.</span></span>

<span data-ttu-id="dcaef-113">还可以使用匿名函数创建委托，这些函数是便捷创建的“内联方法”。</span><span class="sxs-lookup"><span data-stu-id="dcaef-113">Delegates can also be created using anonymous functions, which are "inline methods" that are created on the fly.</span></span> <span data-ttu-id="dcaef-114">匿名函数可以查看周围方法的局部变量。</span><span class="sxs-lookup"><span data-stu-id="dcaef-114">Anonymous functions can see the local variables of the surrounding methods.</span></span> <span data-ttu-id="dcaef-115">因此，可以更轻松地编写上面的乘数示例，而无需使用 Multiplier 类：</span><span class="sxs-lookup"><span data-stu-id="dcaef-115">Thus, the multiplier example above can be written more easily without using a Multiplier class:</span></span>

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

<span data-ttu-id="dcaef-116">委托的一个有趣且有用的属性是，它不知道也不关心所引用的方法的类；只关心引用的方法是否具有与委托相同的参数和返回类型。</span><span class="sxs-lookup"><span data-stu-id="dcaef-116">An interesting and useful property of a delegate is that it does not know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dcaef-117">[上一页](enums.md)
>[下一页](attributes.md)</span><span class="sxs-lookup"><span data-stu-id="dcaef-117">[Previous](enums.md)
[Next](attributes.md)</span></span>