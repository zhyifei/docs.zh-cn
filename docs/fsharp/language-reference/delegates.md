---
title: 委托
description: 了解如何在中F#使用委托。
ms.date: 05/16/2016
ms.openlocfilehash: 65875897d5fc4b2ac66f1dfbe913f29fb74137cd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630366"
---
# <a name="delegates"></a><span data-ttu-id="5f2a8-103">委托</span><span class="sxs-lookup"><span data-stu-id="5f2a8-103">Delegates</span></span>

<span data-ttu-id="5f2a8-104">委托将函数调用表示为对象。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="5f2a8-105">在F#中, 通常应使用函数值将函数表示为第一类值;但是, 在 .NET Framework 中使用委托, 因此在与预期它们的 Api 进行互操作时需要使用委托。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="5f2a8-106">在创作旨在使用其他 .NET Framework 语言的库时, 还可以使用它们。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="5f2a8-107">语法</span><span class="sxs-lookup"><span data-stu-id="5f2a8-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="5f2a8-108">备注</span><span class="sxs-lookup"><span data-stu-id="5f2a8-108">Remarks</span></span>

<span data-ttu-id="5f2a8-109">在前面的语法中`type1` , 表示参数类型或类型, `type2`表示返回类型。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="5f2a8-110">所表示`type1`的参数类型会自动扩充。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="5f2a8-111">这表明, 对于此类型, 如果目标函数的参数为扩充, 则使用元组窗体, 并为已在元组格式中的参数使用带括号的元组。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="5f2a8-112">自动 currying 将删除一组括号, 并保留与目标方法匹配的元组参数。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="5f2a8-113">有关应在每种情况下使用的语法, 请参阅代码示例。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="5f2a8-114">委托可以附加到F#函数值、静态方法或实例方法。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="5f2a8-115">F#函数值可以作为参数直接作为委托构造函数的参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="5f2a8-116">对于静态方法, 您可以使用类的名称和方法构造委托。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="5f2a8-117">对于实例方法, 请在一个参数中提供对象实例和方法。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="5f2a8-118">在这两种情况下, 都使用`.`成员访问运算符 ()。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="5f2a8-119">委托`Invoke`类型上的方法调用封装的函数。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="5f2a8-120">此外, 可以通过引用调用方法名称 (不带括号) 将委托作为函数值进行传递。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="5f2a8-121">下面的代码演示了用于创建委托的语法, 这些委托表示类中的各种方法。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="5f2a8-122">根据该方法是静态方法还是实例方法, 以及它是否具有元组格式或扩充形式的参数, 声明和分配委托的语法略有不同。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="5f2a8-123">下面的代码演示了一些可以使用委托的不同方式。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="5f2a8-124">前面的代码示例的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="5f2a8-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="5f2a8-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f2a8-125">See also</span></span>

- [<span data-ttu-id="5f2a8-126">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="5f2a8-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="5f2a8-127">参数和自变量</span><span class="sxs-lookup"><span data-stu-id="5f2a8-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="5f2a8-128">事件</span><span class="sxs-lookup"><span data-stu-id="5f2a8-128">Events</span></span>](./members/events.md)
