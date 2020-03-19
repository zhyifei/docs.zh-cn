---
title: 显式接口实现 - C# 编程指南
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: ea32a279b7c464174a7fada5ef93ccf62ef39884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167668"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="075cd-102">显式接口实现（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="075cd-102">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="075cd-103">如果一个[类](../../language-reference/keywords/class.md)实现的两个接口包含签名相同的成员，则在该类上实现此成员会导致这两个接口将此成员用作其实现。</span><span class="sxs-lookup"><span data-stu-id="075cd-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="075cd-104">如下示例中，所有对 `Paint` 的调用皆调用同一方法。</span><span class="sxs-lookup"><span data-stu-id="075cd-104">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="075cd-105">第一个示例定义类型：</span><span class="sxs-lookup"><span data-stu-id="075cd-105">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="075cd-106">下面的示例调用方法：</span><span class="sxs-lookup"><span data-stu-id="075cd-106">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="075cd-107">当两个接口成员不执行相同的功能时，它会导致其中一个或两个接口的实现不正确。</span><span class="sxs-lookup"><span data-stu-id="075cd-107">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="075cd-108">创建仅通过接口调用且特定于该接口的类成员，则有可能显式实现接口成员。</span><span class="sxs-lookup"><span data-stu-id="075cd-108">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="075cd-109">请使用接口名称和句点命名类成员。</span><span class="sxs-lookup"><span data-stu-id="075cd-109">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="075cd-110">例如：</span><span class="sxs-lookup"><span data-stu-id="075cd-110">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="075cd-111">类成员 `IControl.Paint` 仅通过 `IControl` 接口可用，`ISurface.Paint` 仅通过 `ISurface` 可用。</span><span class="sxs-lookup"><span data-stu-id="075cd-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="075cd-112">这两个方法实现相互独立，两者均不可直接在类上使用。</span><span class="sxs-lookup"><span data-stu-id="075cd-112">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="075cd-113">例如：</span><span class="sxs-lookup"><span data-stu-id="075cd-113">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="075cd-114">显式实现还用于处理两个接口分别声明名称相同的不同成员（例如属性和方法）的情况。</span><span class="sxs-lookup"><span data-stu-id="075cd-114">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="075cd-115">若要实现两个接口，类必须对属性 `P` 或方法 `P` 使用显式实现，或对二者同时使用，从而避免编译器错误。</span><span class="sxs-lookup"><span data-stu-id="075cd-115">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="075cd-116">例如：</span><span class="sxs-lookup"><span data-stu-id="075cd-116">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="075cd-117">从 [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods) 开始，你可以为在接口中声明的成员定义一个实现。</span><span class="sxs-lookup"><span data-stu-id="075cd-117">Beginning with [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods), you can define an implementation for members declared in an interface.</span></span> <span data-ttu-id="075cd-118">如果类从接口继承方法实现，则只能通过接口类型的引用访问该方法。</span><span class="sxs-lookup"><span data-stu-id="075cd-118">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="075cd-119">继承的成员不会显示为公共接口的一部分。</span><span class="sxs-lookup"><span data-stu-id="075cd-119">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="075cd-120">下面的示例定义接口方法的默认实现：</span><span class="sxs-lookup"><span data-stu-id="075cd-120">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="075cd-121">下面的示例调用默认实现：</span><span class="sxs-lookup"><span data-stu-id="075cd-121">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="075cd-122">任何实现 `IControl` 接口的类都可以重写默认的 `Paint` 方法，作为公共方法或作为显式接口实现。</span><span class="sxs-lookup"><span data-stu-id="075cd-122">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="075cd-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="075cd-123">See also</span></span>

- [<span data-ttu-id="075cd-124">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="075cd-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="075cd-125">类和结构</span><span class="sxs-lookup"><span data-stu-id="075cd-125">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="075cd-126">接口</span><span class="sxs-lookup"><span data-stu-id="075cd-126">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="075cd-127">继承</span><span class="sxs-lookup"><span data-stu-id="075cd-127">Inheritance</span></span>](../classes-and-structs/inheritance.md)
