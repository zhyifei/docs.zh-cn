---
title: 확장명 메서드
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 13f92470b23d138e0d30bed947ff1932f2605d28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741619"
---
# <a name="extension-methods"></a><span data-ttu-id="d3f6b-102">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="d3f6b-102">Extension Methods</span></span>
<span data-ttu-id="d3f6b-103">扩展方法是一种语言特性，允许使用实例方法调用语法来调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-103">Extension methods are a language feature that allows static methods to be called using instance method call syntax.</span></span> <span data-ttu-id="d3f6b-104">这些方法必须至少使用一个参数，该参数表示方法要操作的实例。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-104">These methods must take at least one parameter, which represents the instance the method is to operate on.</span></span>

 <span data-ttu-id="d3f6b-105">定义此类扩展方法的类称“sponsor”类，必须将其声明为静态。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-105">The class that defines such extension methods is referred to as the "sponsor" class, and it must be declared as static.</span></span> <span data-ttu-id="d3f6b-106">要使用扩展方法，必须导入定义 sponsor 类的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-106">To use extension methods, one must import the namespace defining the sponsor class.</span></span>

 <span data-ttu-id="d3f6b-107">❌ 避免 frivolously 定义扩展方法，特别是对于不属于您的类型。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-107">❌ AVOID frivolously defining extension methods, especially on types you don’t own.</span></span>

 <span data-ttu-id="d3f6b-108">如果拥有某一类型的源代码，请考虑使用常规实例方法。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-108">If you do own source code of a type, consider using regular instance methods instead.</span></span> <span data-ttu-id="d3f6b-109">如果没有，并且想要添加方法，请务必小心。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-109">If you don’t own, and you want to add a method, be very careful.</span></span> <span data-ttu-id="d3f6b-110">随意使用扩展方法可能会使本来不具备这些方法的类型产生混乱的API。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-110">Liberal use of extension methods has the potential of cluttering APIs of types that were not designed to have these methods.</span></span>

 <span data-ttu-id="d3f6b-111">✔️考虑在以下任何情况下使用扩展方法：</span><span class="sxs-lookup"><span data-stu-id="d3f6b-111">✔️ CONSIDER using extension methods in any of the following scenarios:</span></span>

- <span data-ttu-id="d3f6b-112">提供与接口的每个实现相关的辅助功能（如果上述功能可以根据核心接口编写）。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-112">To provide helper functionality relevant to every implementation of an interface, if said functionality can be written in terms of the core interface.</span></span> <span data-ttu-id="d3f6b-113">这是因为不能将具体实现分配给接口。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-113">This is because concrete implementations cannot otherwise be assigned to interfaces.</span></span> <span data-ttu-id="d3f6b-114">例如，`LINQ to Objects` 运算符作为所有 <xref:System.Collections.Generic.IEnumerable%601> 类型的扩展方法被实现。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-114">For example, the `LINQ to Objects` operators are implemented as extension methods for all <xref:System.Collections.Generic.IEnumerable%601> types.</span></span> <span data-ttu-id="d3f6b-115">因此，任何 `IEnumerable<>` 实现都会自动启用LINQ。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-115">Thus, any `IEnumerable<>` implementation is automatically LINQ-enabled.</span></span>

- <span data-ttu-id="d3f6b-116">当实例方法在某种类型上引入依赖关系，但这样的依赖关系会破坏依赖关系管理规则的时候。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-116">When an instance method would introduce a dependency on some type, but such a dependency would break dependency management rules.</span></span> <span data-ttu-id="d3f6b-117">例如，从 <xref:System.String> 到 <xref:System.Uri?displayProperty=nameWithType> 的依赖关系可能是不可取的，因此返回 `System.Uri` 的 `String.ToUri()` 实例方法从依赖关系管理的角度来看可能存在设计错误。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-117">For example, a dependency from <xref:System.String> to <xref:System.Uri?displayProperty=nameWithType> is probably not desirable, and so `String.ToUri()` instance method returning `System.Uri` would be the wrong design from a dependency management perspective.</span></span> <span data-ttu-id="d3f6b-118">返回 `System.Uri` 的静态扩展方法 `Uri.ToUri(this string str)` 可能是更好的设计。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-118">A static extension method `Uri.ToUri(this string str)` returning `System.Uri` would be a much better design.</span></span>

 <span data-ttu-id="d3f6b-119">❌ 避免在 <xref:System.Object?displayProperty=nameWithType>上定义扩展方法。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-119">❌ AVOID defining extension methods on <xref:System.Object?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="d3f6b-120">Visual Basic 用户将无法使用扩展方法语法对对象引用调用此类方法。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-120">Visual Basic users will not be able to call such methods on object references using the extension method syntax.</span></span> <span data-ttu-id="d3f6b-121">Visual Basic 不支持调用此类方法，因为在 Visual Basic 中，将引用声明为对象将强制其上的所有方法调用都是后期绑定的（在运行时确定调用的实际成员），而扩展方法的绑定则在编译时（早期绑定）。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-121">Visual Basic does not support calling such methods because, in Visual Basic, declaring a reference as Object forces all method invocations on it to be late bound (actual member called is determined at runtime), while bindings to extension methods are determined at compile-time (early bound).</span></span>

 <span data-ttu-id="d3f6b-122">请注意，该准则适用于存在相同绑定行为的其他语言，或者不支持扩展方法的其他语言。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-122">Note that the guideline applies to other languages where the same binding behavior is present, or where extension methods are not supported.</span></span>

 <span data-ttu-id="d3f6b-123">❌ 不要将扩展方法放在与扩展类型相同的命名空间中，除非它用于向接口添加方法或用于依赖项管理。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-123">❌ DO NOT put extension methods in the same namespace as the extended type unless it is for adding methods to interfaces or for dependency management.</span></span>

 <span data-ttu-id="d3f6b-124">❌ 避免定义具有相同签名的两个或多个扩展方法，即使它们驻留在不同的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-124">❌ AVOID defining two or more extension methods with the same signature, even if they reside in different namespaces.</span></span>

 <span data-ttu-id="d3f6b-125">如果类型是一个接口，则✔️考虑在与扩展类型相同的命名空间中定义扩展方法，并且在大多数或所有情况下都使用扩展方法。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-125">✔️ CONSIDER defining extension methods in the same namespace as the extended type if the type is an interface and if the extension methods are meant to be used in most or all cases.</span></span>

 <span data-ttu-id="d3f6b-126">❌ 不会定义实现通常与其他功能关联的命名空间中的功能的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-126">❌ DO NOT define extension methods implementing a feature in namespaces normally associated with other features.</span></span> <span data-ttu-id="d3f6b-127">而是在与它们所属的功能相关联的命名空间中定义它们。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-127">Instead, define them in the namespace associated with the feature they belong to.</span></span>

 <span data-ttu-id="d3f6b-128">❌ 避免命名空间专用于扩展方法（例如 "Extension"）的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-128">❌ AVOID generic naming of namespaces dedicated to extension methods (e.g., "Extensions").</span></span> <span data-ttu-id="d3f6b-129">而是使用描述性名称（例如，“路由”）。</span><span class="sxs-lookup"><span data-stu-id="d3f6b-129">Use a descriptive name (e.g., "Routing") instead.</span></span>

 <span data-ttu-id="d3f6b-130">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="d3f6b-130">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d3f6b-131">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d3f6b-131">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d3f6b-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3f6b-132">See also</span></span>

- [<span data-ttu-id="d3f6b-133">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d3f6b-133">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="d3f6b-134">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d3f6b-134">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
