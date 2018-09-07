---
title: 结构设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3879dc3f0270a56132b44882a74c50d05914ff89
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44067446"
---
# <a name="struct-design"></a><span data-ttu-id="2afa4-102">结构设计</span><span class="sxs-lookup"><span data-stu-id="2afa4-102">Struct Design</span></span>
<span data-ttu-id="2afa4-103">常规用途的值类型通常称为结构，其 C# 关键字。</span><span class="sxs-lookup"><span data-stu-id="2afa4-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="2afa4-104">本部分提供有关常规结构设计指导原则。</span><span class="sxs-lookup"><span data-stu-id="2afa4-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="2afa4-105">**X DO NOT** 结构提供默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="2afa4-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="2afa4-106">遵循此原则，而无需对数组的每个项运行构造函数创建的结构数组。</span><span class="sxs-lookup"><span data-stu-id="2afa4-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="2afa4-107">请注意，C# 不允许结构拥有默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="2afa4-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="2afa4-108">**X DO NOT** 定义可变值类型。</span><span class="sxs-lookup"><span data-stu-id="2afa4-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="2afa4-109">可变值类型具有几个问题。</span><span class="sxs-lookup"><span data-stu-id="2afa4-109">Mutable value types have several problems.</span></span> <span data-ttu-id="2afa4-110">例如，当属性 getter 将返回值类型，调用方会接收一个副本。</span><span class="sxs-lookup"><span data-stu-id="2afa4-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="2afa4-111">隐式创建的副本，因为开发人员可能不知道它们转变副本，而不是原始值。</span><span class="sxs-lookup"><span data-stu-id="2afa4-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="2afa4-112">此外，某些语言 （尤其是动态语言） 有问题使用可变值类型，因为即使本地变量，取消引用时，会导致副本来进行。</span><span class="sxs-lookup"><span data-stu-id="2afa4-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="2afa4-113">**✓ DO** 确保其中所有实例数据的状态设置为零，false，或 null （根据需要） 是否有效。</span><span class="sxs-lookup"><span data-stu-id="2afa4-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="2afa4-114">这可以防止意外创建无效的实例时创建的结构数组。</span><span class="sxs-lookup"><span data-stu-id="2afa4-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="2afa4-115">**✓ DO** 实现<xref:System.IEquatable%601>有关值类型。</span><span class="sxs-lookup"><span data-stu-id="2afa4-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="2afa4-116"><xref:System.Object.Equals%2A?displayProperty=nameWithType>值类型上的方法会导致装箱，并且其默认实现不是非常高效，因为它使用反射。</span><span class="sxs-lookup"><span data-stu-id="2afa4-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="2afa4-117"><xref:System.IEquatable%601.Equals%2A> 可以更好的性能，并且可以实现，以便它不会导致装箱。</span><span class="sxs-lookup"><span data-stu-id="2afa4-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="2afa4-118">**X DO NOT** 显式延长<xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="2afa4-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="2afa4-119">实际上，大多数语言禁止此行为。</span><span class="sxs-lookup"><span data-stu-id="2afa4-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="2afa4-120">一般情况下，结构可能非常有用，但仅用于不会频繁装箱的小规模、 单个的不可变值。</span><span class="sxs-lookup"><span data-stu-id="2afa4-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="2afa4-121">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="2afa4-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2afa4-122">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="2afa4-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2afa4-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2afa4-123">See also</span></span>

- [<span data-ttu-id="2afa4-124">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="2afa4-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="2afa4-125">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="2afa4-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="2afa4-126">在类和结构之间选择</span><span class="sxs-lookup"><span data-stu-id="2afa4-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
