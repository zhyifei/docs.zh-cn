---
title: 字段设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: KrzysztofCwalina
ms.openlocfilehash: 34c5a163e545b78c188f37b2819962b4c7c56f80
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144346"
---
# <a name="field-design"></a><span data-ttu-id="9c498-102">字段设计</span><span class="sxs-lookup"><span data-stu-id="9c498-102">Field Design</span></span>
<span data-ttu-id="9c498-103">封装原则是面向对象的设计中最重要的概念之一。</span><span class="sxs-lookup"><span data-stu-id="9c498-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="9c498-104">该原则规定，存储在对象内的数据只能由该对象访问。</span><span class="sxs-lookup"><span data-stu-id="9c498-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="9c498-105">解释该原则的一种有效的方式是，设计一种可在不破坏类型成员以外的代码的情况下对类型的字段（名称或类型更改）进行更改的类型。</span><span class="sxs-lookup"><span data-stu-id="9c498-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="9c498-106">这种解释随即表明所有字段必须为专用。</span><span class="sxs-lookup"><span data-stu-id="9c498-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="9c498-107">我们将常量和静态只读字段排除在了这一严格限制之外，因为根据定义，此类字段几乎从不需要更改。</span><span class="sxs-lookup"><span data-stu-id="9c498-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="9c498-108">X 请勿提供公共或受保护的实例字段。</span><span class="sxs-lookup"><span data-stu-id="9c498-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="9c498-109">应提供用于访问字段而非使其成为公共或受保护字段的属性。</span><span class="sxs-lookup"><span data-stu-id="9c498-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="9c498-110">**✓ 务必** 使用常量字段表示永不改变的常量。</span><span class="sxs-lookup"><span data-stu-id="9c498-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="9c498-111">编译器将 const 字段的值直接烧写到调用代码中。</span><span class="sxs-lookup"><span data-stu-id="9c498-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="9c498-112">因此，在没有破坏兼容性的风险的情况下，永远不能更改const值。</span><span class="sxs-lookup"><span data-stu-id="9c498-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="9c498-113">**✓ 务必** 对预定义的对象实例使用公共的静态的 `readonly` 字段。</span><span class="sxs-lookup"><span data-stu-id="9c498-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="9c498-114">如果存在该类型的预定义实例，则将它们声明为该类型本身的公共只读静态字段。</span><span class="sxs-lookup"><span data-stu-id="9c498-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="9c498-115">**X 切忌** 将可变类型的实例分配给 `readonly` 字段。</span><span class="sxs-lookup"><span data-stu-id="9c498-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="9c498-116">可变类型是具有可在实例化后修改的实例的类型。</span><span class="sxs-lookup"><span data-stu-id="9c498-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="9c498-117">例如，数组，大多数集合和流都是可变类型，但是 <xref:System.Int32?displayProperty=nameWithType>、<xref:System.Uri?displayProperty=nameWithType>、和 <xref:System.String?displayProperty=nameWithType> 都是不变的。</span><span class="sxs-lookup"><span data-stu-id="9c498-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="9c498-118">引用类型字段上的只读修饰符可防止存储在字段中的实例被替换，但它不会阻止通过调用更改实例的员来修改字段的实例数据。</span><span class="sxs-lookup"><span data-stu-id="9c498-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="9c498-119">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="9c498-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9c498-120">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="9c498-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c498-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c498-121">See also</span></span>

- [<span data-ttu-id="9c498-122">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="9c498-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="9c498-123">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="9c498-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
