---
title: 字段设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65c54fe9a076a219c61280a98c390b16f56b5015
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43873937"
---
# <a name="field-design"></a><span data-ttu-id="7f478-102">字段设计</span><span class="sxs-lookup"><span data-stu-id="7f478-102">Field Design</span></span>
<span data-ttu-id="7f478-103">封装原则是最重要的概念之一中面向对象的设计。</span><span class="sxs-lookup"><span data-stu-id="7f478-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="7f478-104">此原则指出，应仅对该对象可访问的对象内存储的数据。</span><span class="sxs-lookup"><span data-stu-id="7f478-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="7f478-105">有用的方式来解释原则是说，以便对该类型 （名称或类型的更改） 的字段的更改可以进行而不会破坏代码以外的其他类型的成员，应设计一种类型。</span><span class="sxs-lookup"><span data-stu-id="7f478-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="7f478-106">此解释立即意味着所有字段必须都为私有。</span><span class="sxs-lookup"><span data-stu-id="7f478-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="7f478-107">因为此类字段，根据定义，几乎从不需要更改，我们会从这种严格限制，排除常量和静态只读字段。</span><span class="sxs-lookup"><span data-stu-id="7f478-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="7f478-108">**X DO NOT** 提供公共或受保护的实例字段。</span><span class="sxs-lookup"><span data-stu-id="7f478-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="7f478-109">您应提供用于访问而不是使它们成为公共或受保护的字段的属性。</span><span class="sxs-lookup"><span data-stu-id="7f478-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="7f478-110">**✓ DO** 常量字段用于将永远不会更改的常量。</span><span class="sxs-lookup"><span data-stu-id="7f478-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="7f478-111">编译器加深直接到调用代码的常量字段的值。</span><span class="sxs-lookup"><span data-stu-id="7f478-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="7f478-112">因此，可以永远不会更改常量值，而不必冒险破坏兼容性。</span><span class="sxs-lookup"><span data-stu-id="7f478-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="7f478-113">**✓ DO** 使用公共静态`readonly`预定义的对象实例的字段。</span><span class="sxs-lookup"><span data-stu-id="7f478-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="7f478-114">如果有预定义的类型实例，请将它们声明为公共只读静态字段的类型本身。</span><span class="sxs-lookup"><span data-stu-id="7f478-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="7f478-115">**X DO NOT** 分配到的可变类型的实例`readonly`字段。</span><span class="sxs-lookup"><span data-stu-id="7f478-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="7f478-116">可变类型是具有可将它们实例化之后修改的实例的类型。</span><span class="sxs-lookup"><span data-stu-id="7f478-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="7f478-117">例如，数组中，大多数集合和流是可变类型，但<xref:System.Int32?displayProperty=nameWithType>， <xref:System.Uri?displayProperty=nameWithType>，和<xref:System.String?displayProperty=nameWithType>是所有固定不变。</span><span class="sxs-lookup"><span data-stu-id="7f478-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="7f478-118">上一个引用类型字段的只读修饰符可以防止实例存储在字段中被替换，但不会阻止该字段的实例数据更改的实例的调用成员被修改。</span><span class="sxs-lookup"><span data-stu-id="7f478-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="7f478-119">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="7f478-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="7f478-120">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="7f478-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f478-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f478-121">See also</span></span>

- [<span data-ttu-id="7f478-122">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="7f478-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="7f478-123">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="7f478-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
