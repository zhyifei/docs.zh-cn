---
title: 显式接口实现 - C# 编程指南
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: c6f1f849e0d4e831802b4c9b8b4bc3887363a34c
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628145"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="60b39-102">显式接口实现（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="60b39-102">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="60b39-103">如果一个[类](../../language-reference/keywords/class.md)实现的两个接口包含签名相同的成员，则在该类上实现此成员会导致这两个接口将此成员用作其实现。</span><span class="sxs-lookup"><span data-stu-id="60b39-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="60b39-104">如下示例中，所有对 `Paint` 的调用皆调用同一方法。</span><span class="sxs-lookup"><span data-stu-id="60b39-104">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="60b39-105">第一个示例定义类型：</span><span class="sxs-lookup"><span data-stu-id="60b39-105">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="60b39-106">下面的示例调用方法：</span><span class="sxs-lookup"><span data-stu-id="60b39-106">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="60b39-107">当两个接口成员不执行相同的功能时，它会导致其中一个或两个接口的实现不正确。</span><span class="sxs-lookup"><span data-stu-id="60b39-107">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="60b39-108">创建仅通过接口调用且特定于该接口的类成员，则有可能显式实现接口成员。</span><span class="sxs-lookup"><span data-stu-id="60b39-108">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="60b39-109">请使用接口名称和句点命名类成员。</span><span class="sxs-lookup"><span data-stu-id="60b39-109">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="60b39-110">例如：</span><span class="sxs-lookup"><span data-stu-id="60b39-110">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="60b39-111">类成员 `IControl.Paint` 仅通过 `IControl` 接口可用，`ISurface.Paint` 仅通过 `ISurface` 可用。</span><span class="sxs-lookup"><span data-stu-id="60b39-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="60b39-112">这两个方法实现相互独立，两者均不可直接在类上使用。</span><span class="sxs-lookup"><span data-stu-id="60b39-112">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="60b39-113">例如：</span><span class="sxs-lookup"><span data-stu-id="60b39-113">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="60b39-114">显式实现还用于处理两个接口分别声明名称相同的不同成员（例如属性和方法）的情况。</span><span class="sxs-lookup"><span data-stu-id="60b39-114">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="60b39-115">若要实现两个接口，类必须对属性 `P` 或方法 `P` 使用显式实现，或对二者同时使用，从而避免编译器错误。</span><span class="sxs-lookup"><span data-stu-id="60b39-115">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="60b39-116">例如：</span><span class="sxs-lookup"><span data-stu-id="60b39-116">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="60b39-117">如果类从接口继承方法实现，则只能通过接口类型的引用访问该方法。</span><span class="sxs-lookup"><span data-stu-id="60b39-117">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="60b39-118">继承的成员不会显示为公共接口的一部分。</span><span class="sxs-lookup"><span data-stu-id="60b39-118">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="60b39-119">下面的示例定义接口方法的默认实现：</span><span class="sxs-lookup"><span data-stu-id="60b39-119">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="60b39-120">下面的示例调用默认实现：</span><span class="sxs-lookup"><span data-stu-id="60b39-120">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="60b39-121">任何实现 `IControl` 接口的类都可以重写默认的 `Paint` 方法，作为公共方法或作为显式接口实现。</span><span class="sxs-lookup"><span data-stu-id="60b39-121">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="60b39-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="60b39-122">See also</span></span>

- [<span data-ttu-id="60b39-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="60b39-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="60b39-124">类和结构</span><span class="sxs-lookup"><span data-stu-id="60b39-124">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="60b39-125">接口</span><span class="sxs-lookup"><span data-stu-id="60b39-125">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="60b39-126">继承</span><span class="sxs-lookup"><span data-stu-id="60b39-126">Inheritance</span></span>](../classes-and-structs/inheritance.md)
