---
title: 构造函数设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
ms.openlocfilehash: 7ab795cd4c6e0ff5e1451c05987848c41bd69577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401243"
---
# <a name="constructor-design"></a><span data-ttu-id="27200-102">构造函数设计</span><span class="sxs-lookup"><span data-stu-id="27200-102">Constructor Design</span></span>

<span data-ttu-id="27200-103">有两种构造函数：类型构造函数和实例构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="27200-104">类型构造函数是静态的，在使用类型之前由 CLR 运行。</span><span class="sxs-lookup"><span data-stu-id="27200-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="27200-105">实例构造函数在创建类型的实例时运行。</span><span class="sxs-lookup"><span data-stu-id="27200-105">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="27200-106">类型构造函数不能采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="27200-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="27200-107">实例构造函数可以。</span><span class="sxs-lookup"><span data-stu-id="27200-107">Instance constructors can.</span></span> <span data-ttu-id="27200-108">不采用任何参数的实例构造函数通常称为无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="27200-109">构造函数是创建类型实例的最自然方法。</span><span class="sxs-lookup"><span data-stu-id="27200-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="27200-110">大多数开发人员在考虑创建实例（如工厂方法）的替代方法之前，将搜索并尝试使用构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="27200-111">✔️ 考虑提供简单、理想的默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-111">✔️ CONSIDER providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="27200-112">简单的构造函数具有非常少量的参数，并且所有参数都是基元或枚举。</span><span class="sxs-lookup"><span data-stu-id="27200-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="27200-113">这种简单的构造函数提高了框架的可用性。</span><span class="sxs-lookup"><span data-stu-id="27200-113">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="27200-114">✔️如果所需操作的语义不直接映射到新实例的构造，或者遵循构造函数设计准则感觉不自然，则考虑使用静态工厂方法而不是构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-114">✔️ CONSIDER using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="27200-115">✔️ DO 使用构造函数参数作为设置主属性的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="27200-115">✔️ DO use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="27200-116">在语义上，使用空构造函数后跟某些属性集和使用具有多个参数的构造函数之间应该没有区别。</span><span class="sxs-lookup"><span data-stu-id="27200-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="27200-117">如果构造函数参数用于简单地设置属性，则✔️ DO 对构造函数参数使用相同的名称和属性。</span><span class="sxs-lookup"><span data-stu-id="27200-117">✔️ DO use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="27200-118">此类参数和属性之间的唯一区别应该是套管。</span><span class="sxs-lookup"><span data-stu-id="27200-118">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="27200-119">✔️在构造函数中执行最小工作。</span><span class="sxs-lookup"><span data-stu-id="27200-119">✔️ DO minimal work in the constructor.</span></span>

<span data-ttu-id="27200-120">除了捕获构造函数参数之外，构造函数不应执行太多工作。</span><span class="sxs-lookup"><span data-stu-id="27200-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="27200-121">任何其他处理的成本应延迟到需要。</span><span class="sxs-lookup"><span data-stu-id="27200-121">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="27200-122">✔️如果适用，从实例构造函数引发异常。</span><span class="sxs-lookup"><span data-stu-id="27200-122">✔️ DO throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="27200-123">✔️如果需要这样的构造函数，则在类中显式声明公共无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-123">✔️ DO explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="27200-124">如果不显式声明类型上的任何构造函数，则许多语言（如 C#）将自动添加公共无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="27200-125">（抽象类获取受保护的构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-125">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="27200-126">向类添加参数化构造函数可防止编译器添加无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="27200-127">这通常会导致意外的中断更改。</span><span class="sxs-lookup"><span data-stu-id="27200-127">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="27200-128">❌AVOID 在结构上显式定义无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-128">❌ AVOID explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="27200-129">这使得数组创建速度更快，因为如果未定义无参数构造函数，则不必在数组中的每个插槽上运行。</span><span class="sxs-lookup"><span data-stu-id="27200-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="27200-130">请注意，许多编译器（包括 C#）不允许结构具有无参数构造函数。因此。</span><span class="sxs-lookup"><span data-stu-id="27200-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="27200-131">❌AVOID 在其构造函数内的对象上调用虚拟成员。</span><span class="sxs-lookup"><span data-stu-id="27200-131">❌ AVOID calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="27200-132">调用虚拟成员将导致调用最派生的重写，即使最派生类型的构造函数尚未完全运行。</span><span class="sxs-lookup"><span data-stu-id="27200-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="27200-133">类型构造函数指南</span><span class="sxs-lookup"><span data-stu-id="27200-133">Type Constructor Guidelines</span></span>

<span data-ttu-id="27200-134">✔️将静态构造函数作为私有。</span><span class="sxs-lookup"><span data-stu-id="27200-134">✔️ DO make static constructors private.</span></span>

<span data-ttu-id="27200-135">静态构造函数（也称为类构造函数）用于初始化类型。</span><span class="sxs-lookup"><span data-stu-id="27200-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="27200-136">CLR 在创建类型的第一个实例或调用该类型上的任何静态成员之前调用静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="27200-137">用户无法控制何时调用静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="27200-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="27200-138">如果静态构造函数不是私有的，则可以由 CLR 以外的代码调用它。</span><span class="sxs-lookup"><span data-stu-id="27200-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="27200-139">根据构造函数中执行的操作，这可能导致意外行为。</span><span class="sxs-lookup"><span data-stu-id="27200-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="27200-140">C# 编译器强制静态构造函数为私有。</span><span class="sxs-lookup"><span data-stu-id="27200-140">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="27200-141">❌不要从静态构造函数引发异常。</span><span class="sxs-lookup"><span data-stu-id="27200-141">❌ DO NOT throw exceptions from static constructors.</span></span>

<span data-ttu-id="27200-142">如果从类型构造函数引发异常，则该类型在当前应用程序域中不可用。</span><span class="sxs-lookup"><span data-stu-id="27200-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="27200-143">✔️考虑内联初始化静态字段，而不是显式使用静态构造函数，因为运行时能够优化没有显式定义的静态构造函数的类型的性能。</span><span class="sxs-lookup"><span data-stu-id="27200-143">✔️ CONSIDER initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="27200-144">*部分© 2005， 2009 微软公司.保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="27200-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="27200-145">*经 Pearson 教育公司许可，从[框架设计指南：可重用的约定、习语和模式 .NET 库重新打印，第二版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)由 Krzysztof Cwalina 和 Brad Abrams 出版，由艾迪森-韦斯利专业公司作为微软 Windows 开发系列的一部分于 2008 年 10 月 22 日出版。*</span><span class="sxs-lookup"><span data-stu-id="27200-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="27200-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27200-146">See also</span></span>

- [<span data-ttu-id="27200-147">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="27200-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="27200-148">框架设计准则</span><span class="sxs-lookup"><span data-stu-id="27200-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
