---
title: 委托 (F#)
description: '了解如何使用 F # 中的委托。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 56520cc631d889f390a7d4300be1cb3185306be9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="delegates"></a><span data-ttu-id="a490f-103">委托</span><span class="sxs-lookup"><span data-stu-id="a490f-103">Delegates</span></span>

<span data-ttu-id="a490f-104">委托表示为对象的函数调用。</span><span class="sxs-lookup"><span data-stu-id="a490f-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="a490f-105">在 F # 中，你通常应使用函数值来表示作为一类值; 函数但是，委托在.NET Framework 中使用，并且因此时，需要与所希望的 Api 进行互操作。</span><span class="sxs-lookup"><span data-stu-id="a490f-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="a490f-106">它们还可能创作库用于从其他.NET Framework 语言使用时将使用。</span><span class="sxs-lookup"><span data-stu-id="a490f-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>


## <a name="syntax"></a><span data-ttu-id="a490f-107">语法</span><span class="sxs-lookup"><span data-stu-id="a490f-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="a490f-108">备注</span><span class="sxs-lookup"><span data-stu-id="a490f-108">Remarks</span></span>
<span data-ttu-id="a490f-109">在上述语法中，`type1`表示或多个自变量类型和`type2`表示的返回类型。</span><span class="sxs-lookup"><span data-stu-id="a490f-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="a490f-110">由表示的参数类型`type1`会自动进行扩充。</span><span class="sxs-lookup"><span data-stu-id="a490f-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="a490f-111">这表示，对于你使用元组形式，如果目标函数的自变量会进行扩充，此类型，并已采用元组形式的自变量用圆括号括起来元组。</span><span class="sxs-lookup"><span data-stu-id="a490f-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="a490f-112">自动扩充将移除一套圆括号，同时保留目标方法相匹配的元组参数。</span><span class="sxs-lookup"><span data-stu-id="a490f-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="a490f-113">请参阅应在每个用例中使用的语法的代码示例。</span><span class="sxs-lookup"><span data-stu-id="a490f-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="a490f-114">委托可以附加到 F # 函数值，和静态方法或实例方法。</span><span class="sxs-lookup"><span data-stu-id="a490f-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="a490f-115">F # 函数值可以直接作为要委托构造函数自变量传递。</span><span class="sxs-lookup"><span data-stu-id="a490f-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="a490f-116">对于静态方法，您可以通过使用类和方法的名称构造委托。</span><span class="sxs-lookup"><span data-stu-id="a490f-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="a490f-117">对于实例方法，你可以提供的对象实例和一个自变量中的方法。</span><span class="sxs-lookup"><span data-stu-id="a490f-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="a490f-118">在这两种情况下，成员访问运算符 (`.`) 使用。</span><span class="sxs-lookup"><span data-stu-id="a490f-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="a490f-119">`Invoke`委托类型的方法调用封装的函数。</span><span class="sxs-lookup"><span data-stu-id="a490f-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="a490f-120">此外，还可以引用不带括号的 Invoke 方法名称作为函数值传递委托。</span><span class="sxs-lookup"><span data-stu-id="a490f-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="a490f-121">下面的代码演示创建表示类中的各种方法的委托的语法。</span><span class="sxs-lookup"><span data-stu-id="a490f-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="a490f-122">具体取决于该方法是否是静态方法或实例方法，以及是否具有元组形式或扩充窗体中的自变量，用于声明和分配委托的语法是稍有不同。</span><span class="sxs-lookup"><span data-stu-id="a490f-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="a490f-123">下面的代码显示了一些你可以使用委托的不同方式。</span><span class="sxs-lookup"><span data-stu-id="a490f-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="a490f-124">前面的代码示例的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a490f-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="a490f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a490f-125">See Also</span></span>
[<span data-ttu-id="a490f-126">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="a490f-126">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="a490f-127">参数和自变量</span><span class="sxs-lookup"><span data-stu-id="a490f-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="a490f-128">事件</span><span class="sxs-lookup"><span data-stu-id="a490f-128">Events</span></span>](members/events.md)
