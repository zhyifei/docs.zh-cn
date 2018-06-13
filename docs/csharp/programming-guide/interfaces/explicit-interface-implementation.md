---
title: 显式接口实现（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: 7494f7d6a3897d56419f9d3aa96668fd9dab5f35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331586"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="0a649-102">显式接口实现（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="0a649-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="0a649-103">如果一个[类](../../../csharp/language-reference/keywords/class.md)实现的两个接口包含签名相同的成员，则在该类上实现此成员会导致这两个接口将此成员用作其实现。</span><span class="sxs-lookup"><span data-stu-id="0a649-103">If a [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="0a649-104">如下示例中，所有对 `Paint` 的调用皆调用同一方法。</span><span class="sxs-lookup"><span data-stu-id="0a649-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 <span data-ttu-id="0a649-105">但是，如果两个[接口](../../../csharp/language-reference/keywords/interface.md)成员不执行同一功能，则会导致其中一个接口或两个接口的实现不正确。</span><span class="sxs-lookup"><span data-stu-id="0a649-105">If the two [interface](../../../csharp/language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="0a649-106">创建仅通过接口调用且特定于该接口的类成员，则有可能显式实现接口成员。</span><span class="sxs-lookup"><span data-stu-id="0a649-106">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="0a649-107">这可通过使用接口名称和句点命名类成员来完成。</span><span class="sxs-lookup"><span data-stu-id="0a649-107">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="0a649-108">例如:</span><span class="sxs-lookup"><span data-stu-id="0a649-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 <span data-ttu-id="0a649-109">类成员 `IControl.Paint` 仅通过 `IControl` 接口可用，`ISurface.Paint` 仅通过 `ISurface` 可用。</span><span class="sxs-lookup"><span data-stu-id="0a649-109">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="0a649-110">这两个方法实现相互独立，两者均不可直接在类上使用。</span><span class="sxs-lookup"><span data-stu-id="0a649-110">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="0a649-111">例如:</span><span class="sxs-lookup"><span data-stu-id="0a649-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 <span data-ttu-id="0a649-112">显式实现还用于处理两个接口分别声明名称相同的不同成员（例如属性和方法）的情况：</span><span class="sxs-lookup"><span data-stu-id="0a649-112">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 <span data-ttu-id="0a649-113">若要实现两个接口，类必须对属性 P 或方法 P 使用显式实现，或对二者同时使用，从而避免编译器错误。</span><span class="sxs-lookup"><span data-stu-id="0a649-113">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="0a649-114">例如:</span><span class="sxs-lookup"><span data-stu-id="0a649-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0a649-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a649-115">See Also</span></span>  
 [<span data-ttu-id="0a649-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0a649-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0a649-117">类和结构</span><span class="sxs-lookup"><span data-stu-id="0a649-117">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="0a649-118">接口</span><span class="sxs-lookup"><span data-stu-id="0a649-118">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="0a649-119">继承</span><span class="sxs-lookup"><span data-stu-id="0a649-119">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
