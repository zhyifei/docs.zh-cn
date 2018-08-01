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
ms.openlocfilehash: 2d47934c3fed17f75a97ef5da0397c6ceba53d68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571107"
---
# <a name="field-design"></a><span data-ttu-id="8997d-102">字段设计</span><span class="sxs-lookup"><span data-stu-id="8997d-102">Field Design</span></span>
<span data-ttu-id="8997d-103">封装原则是最重要的概念之一在面向对象的设计。</span><span class="sxs-lookup"><span data-stu-id="8997d-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="8997d-104">这一原则指出，应仅供该对象存储在对象内的数据。</span><span class="sxs-lookup"><span data-stu-id="8997d-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="8997d-105">有用的方式解释原则是说，以便对该类型 （名称或类型的更改） 的字段可以进行更改而不会破坏以外的其他代码的类型的成员，应设计类型。</span><span class="sxs-lookup"><span data-stu-id="8997d-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="8997d-106">此解释立即意味着所有字段必须都是私有的。</span><span class="sxs-lookup"><span data-stu-id="8997d-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="8997d-107">因为此类字段，几乎根据定义，永远不会需要更改，我们会从此严格限制，排除常数和静态只读字段。</span><span class="sxs-lookup"><span data-stu-id="8997d-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="8997d-108">**X DO NOT** 提供公共或受保护的实例字段。</span><span class="sxs-lookup"><span data-stu-id="8997d-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="8997d-109">你应提供用于访问而不是进行这些公共或受保护的字段的属性。</span><span class="sxs-lookup"><span data-stu-id="8997d-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="8997d-110">**✓ DO** 常量字段用于将永远不会更改的常量。</span><span class="sxs-lookup"><span data-stu-id="8997d-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="8997d-111">编译器在直接到调用代码之前完成剩余的 const 字段的值。</span><span class="sxs-lookup"><span data-stu-id="8997d-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="8997d-112">因此，常量值永远不会更改就不会破坏兼容性的风险。</span><span class="sxs-lookup"><span data-stu-id="8997d-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="8997d-113">**✓ DO** 使用公共静态`readonly`预定义的对象实例的字段。</span><span class="sxs-lookup"><span data-stu-id="8997d-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="8997d-114">如果没有预定义的类型实例，请将它们声明为公共只读的静态字段的类型本身。</span><span class="sxs-lookup"><span data-stu-id="8997d-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="8997d-115">**X DO NOT** 分配到的可变类型的实例`readonly`字段。</span><span class="sxs-lookup"><span data-stu-id="8997d-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="8997d-116">可变类型是可在于实例化之后进行修改的实例的类型。</span><span class="sxs-lookup"><span data-stu-id="8997d-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="8997d-117">例如，数组、 大多数集合和流是可变类型，但<xref:System.Int32?displayProperty=nameWithType>， <xref:System.Uri?displayProperty=nameWithType>，和<xref:System.String?displayProperty=nameWithType>是所有不可变。</span><span class="sxs-lookup"><span data-stu-id="8997d-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="8997d-118">引用类型字段上的只读修饰符可防止在从被替换，字段中存储的实例，但不会阻止该字段的实例数据被修改通过更改实例的调用成员。</span><span class="sxs-lookup"><span data-stu-id="8997d-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="8997d-119">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="8997d-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8997d-120">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="8997d-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8997d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="8997d-121">See Also</span></span>  
 [<span data-ttu-id="8997d-122">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="8997d-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="8997d-123">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="8997d-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
