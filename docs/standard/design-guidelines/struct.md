---
title: 结构设计
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: dfa32112a2eb85a93cdd1e7a72d4411a3b197a1a
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="struct-design"></a><span data-ttu-id="acd9e-102">结构设计</span><span class="sxs-lookup"><span data-stu-id="acd9e-102">Struct Design</span></span>
<span data-ttu-id="acd9e-103">通用值类型最常称为结构，其 C# 关键字。</span><span class="sxs-lookup"><span data-stu-id="acd9e-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="acd9e-104">本部分提供常规结构设计的准则。</span><span class="sxs-lookup"><span data-stu-id="acd9e-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="acd9e-105">**X 不**结构提供默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="acd9e-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="acd9e-106">遵循这一准则允许的结构而无需在该数组的每个项上运行构造函数创建的数组。</span><span class="sxs-lookup"><span data-stu-id="acd9e-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="acd9e-107">请注意，C# 不允许结构拥有默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="acd9e-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="acd9e-108">**X 不**定义可变值类型。</span><span class="sxs-lookup"><span data-stu-id="acd9e-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="acd9e-109">可变值类型具有几个问题。</span><span class="sxs-lookup"><span data-stu-id="acd9e-109">Mutable value types have several problems.</span></span> <span data-ttu-id="acd9e-110">例如，当属性 getter 返回值类型时，调用方将收到副本。</span><span class="sxs-lookup"><span data-stu-id="acd9e-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="acd9e-111">隐式创建的副本，因为开发人员可能不知道它们变异副本，而不是原始值。</span><span class="sxs-lookup"><span data-stu-id="acd9e-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="acd9e-112">此外，某些语言 （尤其是动态语言） 有问题使用可变值类型，因为即使本地变量，取消引用时，会导致副本进行。</span><span class="sxs-lookup"><span data-stu-id="acd9e-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="acd9e-113">**✓ 执行**确保其中所有实例数据的状态设置为零，false，或 null （根据需要） 是否有效。</span><span class="sxs-lookup"><span data-stu-id="acd9e-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="acd9e-114">这样可防止意外创建无效的实例时创建结构的数组。</span><span class="sxs-lookup"><span data-stu-id="acd9e-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="acd9e-115">**✓ 执行**实现<xref:System.IEquatable%601>有关值类型。</span><span class="sxs-lookup"><span data-stu-id="acd9e-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="acd9e-116"><xref:System.Object.Equals%2A?displayProperty=nameWithType>有关值类型的方法会导致装箱，和其默认实现不是非常高效，因为它使用反射。</span><span class="sxs-lookup"><span data-stu-id="acd9e-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="acd9e-117"><xref:System.IEquatable%601.Equals%2A> 可以更好的性能，并且可以实现，以便它不会导致装箱。</span><span class="sxs-lookup"><span data-stu-id="acd9e-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="acd9e-118">**X 不**显式延长<xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="acd9e-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="acd9e-119">事实上，大多数语言防止这种情况。</span><span class="sxs-lookup"><span data-stu-id="acd9e-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="acd9e-120">一般情况下，结构可能非常有用，但应仅用于小型、 单个、 不可变将不经常装箱的值。</span><span class="sxs-lookup"><span data-stu-id="acd9e-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="acd9e-121">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="acd9e-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="acd9e-122">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="acd9e-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acd9e-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="acd9e-123">See Also</span></span>  
 [<span data-ttu-id="acd9e-124">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="acd9e-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="acd9e-125">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="acd9e-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="acd9e-126">在类和结构之间选择</span><span class="sxs-lookup"><span data-stu-id="acd9e-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
