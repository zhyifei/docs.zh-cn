---
title: C# 委托 - C# 语言介绍
description: 了解包含 C# 委托的晚期绑定
ms.date: 02/27/2020
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: b1740ddc65dcb0ee8775f4cbaa8356293ea55fae
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159164"
---
# <a name="delegates"></a><span data-ttu-id="02f9b-103">委托</span><span class="sxs-lookup"><span data-stu-id="02f9b-103">Delegates</span></span>

<span data-ttu-id="02f9b-104">***委托类型***表示对具有特定参数列表和返回类型的方法的引用。</span><span class="sxs-lookup"><span data-stu-id="02f9b-104">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="02f9b-105">通过委托，可以将方法视为可分配给变量并可作为参数传递的实体。</span><span class="sxs-lookup"><span data-stu-id="02f9b-105">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="02f9b-106">委托还类似于其他一些语言中存在的“函数指针”概念。</span><span class="sxs-lookup"><span data-stu-id="02f9b-106">Delegates are similar to the concept of function pointers found in some other languages.</span></span> <span data-ttu-id="02f9b-107">与函数指针不同，委托是面向对象且类型安全的。</span><span class="sxs-lookup"><span data-stu-id="02f9b-107">Unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="02f9b-108">下面的示例声明并使用 `Function` 委托类型。</span><span class="sxs-lookup"><span data-stu-id="02f9b-108">The following example declares and uses a delegate type named `Function`.</span></span>

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

<span data-ttu-id="02f9b-109">`Function` 委托类型实例可以引用需要使用 `double` 自变量并返回 `double` 值的方法。</span><span class="sxs-lookup"><span data-stu-id="02f9b-109">An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value.</span></span> <span data-ttu-id="02f9b-110">`Apply` 方法将给定的函数应用于 `double[]` 的元素，从而返回包含结果的 `double[]`。</span><span class="sxs-lookup"><span data-stu-id="02f9b-110">The `Apply` method applies a given Function to the elements of a `double[]`, returning a `double[]` with the results.</span></span> <span data-ttu-id="02f9b-111">在 `Main` 方法中，`Apply` 用于向 `double[]` 应用三个不同的函数。</span><span class="sxs-lookup"><span data-stu-id="02f9b-111">In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.</span></span>

<span data-ttu-id="02f9b-112">委托可以引用静态方法（如上面示例中的 `Square` 或 `Math.Sin`）或实例方法（如上面示例中的 `m.Multiply`）。</span><span class="sxs-lookup"><span data-stu-id="02f9b-112">A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example).</span></span> <span data-ttu-id="02f9b-113">引用实例方法的委托还会引用特定对象，通过委托调用实例方法时，该对象会变成调用中的 `this`。</span><span class="sxs-lookup"><span data-stu-id="02f9b-113">A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.</span></span>

<span data-ttu-id="02f9b-114">还可以使用匿名函数创建委托，这些函数是在声明时创建的“内联方法”。</span><span class="sxs-lookup"><span data-stu-id="02f9b-114">Delegates can also be created using anonymous functions, which are "inline methods" that are created when declared.</span></span> <span data-ttu-id="02f9b-115">匿名函数可以查看周围方法的局部变量。</span><span class="sxs-lookup"><span data-stu-id="02f9b-115">Anonymous functions can see the local variables of the surrounding methods.</span></span> <span data-ttu-id="02f9b-116">以下示例不创建类：</span><span class="sxs-lookup"><span data-stu-id="02f9b-116">The following example doesn't create a class:</span></span>

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

<span data-ttu-id="02f9b-117">委托不知道也不关心所引用的方法的类；只关心引用的方法是否具有与委托相同的参数和返回类型。</span><span class="sxs-lookup"><span data-stu-id="02f9b-117">A delegate doesn't know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="02f9b-118">[上一页](interfaces.md)
>[下一页](attributes.md)</span><span class="sxs-lookup"><span data-stu-id="02f9b-118">[Previous](interfaces.md)
[Next](attributes.md)</span></span>
