---
title: "可访问性级别（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 77124554d7a0b38414e154e024aceddbfffcfbd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="ec2da-102">可访问性级别（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ec2da-102">Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="ec2da-103">使用访问修饰符 [public](../../../csharp/language-reference/keywords/public.md)、[protected](../../../csharp/language-reference/keywords/protected.md)、[internal](../../../csharp/language-reference/keywords/internal.md) 或 [private](../../../csharp/language-reference/keywords/private.md)，以为成员指定以下声明的可访问性级别之一。</span><span class="sxs-lookup"><span data-stu-id="ec2da-103">Use the access modifiers, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md), to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="ec2da-104">声明的可访问性</span><span class="sxs-lookup"><span data-stu-id="ec2da-104">Declared accessibility</span></span>|<span data-ttu-id="ec2da-105">含义</span><span class="sxs-lookup"><span data-stu-id="ec2da-105">Meaning</span></span>|  
|----------------------------|-------------|  
|`public`|<span data-ttu-id="ec2da-106">访问不受限制。</span><span class="sxs-lookup"><span data-stu-id="ec2da-106">Access is not restricted.</span></span>|  
|`protected`|<span data-ttu-id="ec2da-107">访问限于包含类或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="ec2da-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|`internal`|<span data-ttu-id="ec2da-108">访问限于当前程序集。</span><span class="sxs-lookup"><span data-stu-id="ec2da-108">Access is limited to the current assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="ec2da-109">访问限于当前程序集或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="ec2da-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|`private`|<span data-ttu-id="ec2da-110">访问限于包含类。</span><span class="sxs-lookup"><span data-stu-id="ec2da-110">Access is limited to the containing type.</span></span>|  
|`private protected`|<span data-ttu-id="ec2da-111">访问被限制为包含的类或从包含当前程序集中的类派生的类型。</span><span class="sxs-lookup"><span data-stu-id="ec2da-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>|  
  
 <span data-ttu-id="ec2da-112">只能有一个访问修饰符时，允许成员或类型，除非你使用`protected internal`或`private protected`组合。</span><span class="sxs-lookup"><span data-stu-id="ec2da-112">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="ec2da-113">命名空间中不允许出现访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="ec2da-113">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="ec2da-114">命名空间没有任何访问限制。</span><span class="sxs-lookup"><span data-stu-id="ec2da-114">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="ec2da-115">根据出现成员声明的上下文，仅允许某些声明的可访问性。</span><span class="sxs-lookup"><span data-stu-id="ec2da-115">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="ec2da-116">如果未在成员声明中指定访问修饰符，则将使用默认可访问性。</span><span class="sxs-lookup"><span data-stu-id="ec2da-116">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="ec2da-117">未嵌套在其他类型中的顶级类型只能具有 `internal` 或 `public` 可访问性。</span><span class="sxs-lookup"><span data-stu-id="ec2da-117">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="ec2da-118">这些类型的默认可访问性为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="ec2da-118">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="ec2da-119">作为其他类型的成员的嵌套类型可以具有如下表所示的声明的可访问性。</span><span class="sxs-lookup"><span data-stu-id="ec2da-119">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="ec2da-120">成员</span><span class="sxs-lookup"><span data-stu-id="ec2da-120">Members of</span></span>|<span data-ttu-id="ec2da-121">默认成员可访问性</span><span class="sxs-lookup"><span data-stu-id="ec2da-121">Default member accessibility</span></span>|<span data-ttu-id="ec2da-122">允许的成员的声明的可访问性</span><span class="sxs-lookup"><span data-stu-id="ec2da-122">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="ec2da-123">无</span><span class="sxs-lookup"><span data-stu-id="ec2da-123">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="ec2da-124">无</span><span class="sxs-lookup"><span data-stu-id="ec2da-124">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="ec2da-125">嵌套类型的可访问性依赖于它的[可访问域](../../../csharp/language-reference/keywords/accessibility-domain.md)，该域是由已声明的成员可访问性和直接包含类型的可访问域这二者共同确定的。</span><span class="sxs-lookup"><span data-stu-id="ec2da-125">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="ec2da-126">但是，嵌套类型的可访问域不能超出包含类型的可访问域。</span><span class="sxs-lookup"><span data-stu-id="ec2da-126">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ec2da-127">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ec2da-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ec2da-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec2da-128">See Also</span></span>  
 [<span data-ttu-id="ec2da-129">C# 参考</span><span class="sxs-lookup"><span data-stu-id="ec2da-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ec2da-130">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ec2da-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ec2da-131">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="ec2da-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ec2da-132">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="ec2da-132">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="ec2da-133">可访问域</span><span class="sxs-lookup"><span data-stu-id="ec2da-133">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [<span data-ttu-id="ec2da-134">对使用可访问性级别的限制</span><span class="sxs-lookup"><span data-stu-id="ec2da-134">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [<span data-ttu-id="ec2da-135">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="ec2da-135">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="ec2da-136">公用</span><span class="sxs-lookup"><span data-stu-id="ec2da-136">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="ec2da-137">专用</span><span class="sxs-lookup"><span data-stu-id="ec2da-137">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="ec2da-138">受保护</span><span class="sxs-lookup"><span data-stu-id="ec2da-138">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="ec2da-139">内部</span><span class="sxs-lookup"><span data-stu-id="ec2da-139">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
