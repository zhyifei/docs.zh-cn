---
title: 构造函数设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d7ca279dc1626cd526910af93326280bcd8301d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="constructor-design"></a><span data-ttu-id="fd85e-102">构造函数设计</span><span class="sxs-lookup"><span data-stu-id="fd85e-102">Constructor Design</span></span>
<span data-ttu-id="fd85e-103">有两种类型的构造函数： 键入构造函数和实例构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>  
  
 <span data-ttu-id="fd85e-104">类型构造函数是静态的它们由 CLR 之前使用的类型。</span><span class="sxs-lookup"><span data-stu-id="fd85e-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="fd85e-105">创建类型的实例时，将运行实例构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-105">Instance constructors run when an instance of a type is created.</span></span>  
  
 <span data-ttu-id="fd85e-106">类型构造函数不能接受任何参数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="fd85e-107">实例构造函数可以。</span><span class="sxs-lookup"><span data-stu-id="fd85e-107">Instance constructors can.</span></span> <span data-ttu-id="fd85e-108">不采用任何参数的实例构造函数通常称为默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-108">Instance constructors that don’t take any parameters are often called default constructors.</span></span>  
  
 <span data-ttu-id="fd85e-109">构造函数是创建类型的实例的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="fd85e-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="fd85e-110">大多数开发人员将搜索，并尝试使用构造函数之前他们考虑备选方法创建 （如工厂方法） 的实例。</span><span class="sxs-lookup"><span data-stu-id="fd85e-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>  
  
 <span data-ttu-id="fd85e-111">**请考虑 ✓**提供简单，理想情况下是默认值，构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>  
  
 <span data-ttu-id="fd85e-112">简单的构造函数具有极小的数字的参数，和所有参数都是基元或枚举。</span><span class="sxs-lookup"><span data-stu-id="fd85e-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="fd85e-113">此类简单的构造函数提高可用性的框架。</span><span class="sxs-lookup"><span data-stu-id="fd85e-113">Such simple constructors increase usability of the framework.</span></span>  
  
 <span data-ttu-id="fd85e-114">**请考虑 ✓**而不一个构造函数中使用的静态工厂方法，如果所需的操作的语义执行不直接映射到的新实例的构造，或遵循的构造函数设计准则是不合理。</span><span class="sxs-lookup"><span data-stu-id="fd85e-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>  
  
 <span data-ttu-id="fd85e-115">**✓ 执行**设置主属性构造函数参数用作快捷方式。</span><span class="sxs-lookup"><span data-stu-id="fd85e-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>  
  
 <span data-ttu-id="fd85e-116">应在语义方面之间没有差异使用跟某些属性集的空构造函数和使用具有多个自变量的构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>  
  
 <span data-ttu-id="fd85e-117">**✓ 执行**使用相同的名称用于构造函数参数和属性，如果使用构造函数参数只需设置属性。</span><span class="sxs-lookup"><span data-stu-id="fd85e-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>  
  
 <span data-ttu-id="fd85e-118">此类参数和属性的唯一区别应大小写不同。</span><span class="sxs-lookup"><span data-stu-id="fd85e-118">The only difference between such parameters and the properties should be casing.</span></span>  
  
 <span data-ttu-id="fd85e-119">**✓ 执行**构造函数中的最小工作。</span><span class="sxs-lookup"><span data-stu-id="fd85e-119">**✓ DO** minimal work in the constructor.</span></span>  
  
 <span data-ttu-id="fd85e-120">构造函数不应执行极大的工作以外捕获构造函数参数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="fd85e-121">所需之前，应延迟的成本的其他任何处理。</span><span class="sxs-lookup"><span data-stu-id="fd85e-121">The cost of any other processing should be delayed until required.</span></span>  
  
 <span data-ttu-id="fd85e-122">**✓ 执行**根据引发从实例构造函数的异常。</span><span class="sxs-lookup"><span data-stu-id="fd85e-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>  
  
 <span data-ttu-id="fd85e-123">**✓ 执行**显式声明在类中，公共默认构造函数，如果这样的构造函数是必需的。</span><span class="sxs-lookup"><span data-stu-id="fd85e-123">**✓ DO** explicitly declare the public default constructor in classes, if such a constructor is required.</span></span>  
  
 <span data-ttu-id="fd85e-124">如果你不显式声明任何构造函数，在类型上，许多语言 （如 C# 中) 将会自动添加公共默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public default constructor.</span></span> <span data-ttu-id="fd85e-125">（抽象类获取受保护的构造函数。）</span><span class="sxs-lookup"><span data-stu-id="fd85e-125">(Abstract classes get a protected constructor.)</span></span>  
  
 <span data-ttu-id="fd85e-126">向类中添加参数化构造函数可阻止编译器添加默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-126">Adding a parameterized constructor to a class prevents the compiler from adding the default constructor.</span></span> <span data-ttu-id="fd85e-127">这通常会导致意外的重大更改。</span><span class="sxs-lookup"><span data-stu-id="fd85e-127">This often causes accidental breaking changes.</span></span>  
  
 <span data-ttu-id="fd85e-128">**请避免 x**显式在结构上定义默认的构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-128">**X AVOID** explicitly defining default constructors on structs.</span></span>  
  
 <span data-ttu-id="fd85e-129">这使数组创建速度更快，因为如果未定义默认构造函数，它没有在数组中每个插槽上运行。</span><span class="sxs-lookup"><span data-stu-id="fd85e-129">This makes array creation faster, because if the default constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="fd85e-130">请注意，许多编译器，包括 C# 中，不允许为此具有无参数构造函数的结构。</span><span class="sxs-lookup"><span data-stu-id="fd85e-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>  
  
 <span data-ttu-id="fd85e-131">**请避免 x**调用其构造函数内的对象上的虚拟成员。</span><span class="sxs-lookup"><span data-stu-id="fd85e-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>  
  
 <span data-ttu-id="fd85e-132">调用的虚拟成员将导致派生程度最高的替代，用于调用，即使派生程度最高的类型的构造函数已完全尚未运行。</span><span class="sxs-lookup"><span data-stu-id="fd85e-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>  
  
### <a name="type-constructor-guidelines"></a><span data-ttu-id="fd85e-133">类型构造函数准则</span><span class="sxs-lookup"><span data-stu-id="fd85e-133">Type Constructor Guidelines</span></span>  
 <span data-ttu-id="fd85e-134">**✓ 执行**将设为私有静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-134">**✓ DO** make static constructors private.</span></span>  
  
 <span data-ttu-id="fd85e-135">静态构造函数，也称为类构造函数，用于初始化类型。</span><span class="sxs-lookup"><span data-stu-id="fd85e-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="fd85e-136">CLR 创建的第一个实例的类型或调用该类型上的任何静态成员之前调用静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="fd85e-137">用户具有无法控制当调用该静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="fd85e-138">如果静态构造函数不是私有的则可以调用 CLR 以外的代码。</span><span class="sxs-lookup"><span data-stu-id="fd85e-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="fd85e-139">根据构造函数中执行的操作，这可能导致意外的行为。</span><span class="sxs-lookup"><span data-stu-id="fd85e-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="fd85e-140">C# 编译器强制静态构造函数来为私有构造函数。</span><span class="sxs-lookup"><span data-stu-id="fd85e-140">The C# compiler forces static constructors to be private.</span></span>  
  
 <span data-ttu-id="fd85e-141">**X 不**从静态构造函数引发异常。</span><span class="sxs-lookup"><span data-stu-id="fd85e-141">**X DO NOT** throw exceptions from static constructors.</span></span>  
  
 <span data-ttu-id="fd85e-142">如果从类型构造函数引发异常，类型不适合于当前的应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="fd85e-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>  
  
 <span data-ttu-id="fd85e-143">**请考虑 ✓**初始化以内的静态字段，而不用显式静态构造函数，由于运行时能够优化没有显式定义的静态构造函数的类型的性能。</span><span class="sxs-lookup"><span data-stu-id="fd85e-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>  
  
 <span data-ttu-id="fd85e-144">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="fd85e-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="fd85e-145">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="fd85e-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd85e-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd85e-146">See Also</span></span>  
 [<span data-ttu-id="fd85e-147">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="fd85e-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="fd85e-148">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="fd85e-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
