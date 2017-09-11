---
title: "可访问性级别（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 796802a407c486c1df5332d5b4920467f3a1171b
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="01adb-102">可访问性级别（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="01adb-102">Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="01adb-103">使用访问修饰符 [public](../../../csharp/language-reference/keywords/public.md)、[protected](../../../csharp/language-reference/keywords/protected.md)、[internal](../../../csharp/language-reference/keywords/internal.md) 或 [private](../../../csharp/language-reference/keywords/private.md)，以为成员指定以下声明的可访问性级别之一。</span><span class="sxs-lookup"><span data-stu-id="01adb-103">Use the access modifiers, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md), to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="01adb-104">声明的可访问性</span><span class="sxs-lookup"><span data-stu-id="01adb-104">Declared accessibility</span></span>|<span data-ttu-id="01adb-105">含义</span><span class="sxs-lookup"><span data-stu-id="01adb-105">Meaning</span></span>|  
|----------------------------|-------------|  
|`public`|<span data-ttu-id="01adb-106">访问不受限制。</span><span class="sxs-lookup"><span data-stu-id="01adb-106">Access is not restricted.</span></span>|  
|`protected`|<span data-ttu-id="01adb-107">访问限于包含类或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="01adb-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|`internal`|<span data-ttu-id="01adb-108">访问限于当前程序集。</span><span class="sxs-lookup"><span data-stu-id="01adb-108">Access is limited to the current assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="01adb-109">访问限于当前程序集或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="01adb-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|`private`|<span data-ttu-id="01adb-110">访问限于包含类。</span><span class="sxs-lookup"><span data-stu-id="01adb-110">Access is limited to the containing type.</span></span>|  
  
 <span data-ttu-id="01adb-111">除使用 `protected internal` 组合的情况外，一个成员或类型仅允许一个访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="01adb-111">Only one access modifier is allowed for a member or type, except when you use the `protected internal` combination.</span></span>  
  
 <span data-ttu-id="01adb-112">命名空间中不允许出现访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="01adb-112">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="01adb-113">命名空间没有任何访问限制。</span><span class="sxs-lookup"><span data-stu-id="01adb-113">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="01adb-114">根据出现成员声明的上下文，仅允许某些声明的可访问性。</span><span class="sxs-lookup"><span data-stu-id="01adb-114">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="01adb-115">如果未在成员声明中指定访问修饰符，则将使用默认可访问性。</span><span class="sxs-lookup"><span data-stu-id="01adb-115">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="01adb-116">未嵌套在其他类型中的顶级类型只能具有 `internal` 或 `public` 可访问性。</span><span class="sxs-lookup"><span data-stu-id="01adb-116">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="01adb-117">这些类型的默认可访问性为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="01adb-117">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="01adb-118">作为其他类型的成员的嵌套类型可以具有如下表所示的声明的可访问性。</span><span class="sxs-lookup"><span data-stu-id="01adb-118">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="01adb-119">成员</span><span class="sxs-lookup"><span data-stu-id="01adb-119">Members of</span></span>|<span data-ttu-id="01adb-120">默认成员可访问性</span><span class="sxs-lookup"><span data-stu-id="01adb-120">Default member accessibility</span></span>|<span data-ttu-id="01adb-121">允许的成员的声明的可访问性</span><span class="sxs-lookup"><span data-stu-id="01adb-121">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="01adb-122">无</span><span class="sxs-lookup"><span data-stu-id="01adb-122">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal`|  
|`interface`|`public`|<span data-ttu-id="01adb-123">无</span><span class="sxs-lookup"><span data-stu-id="01adb-123">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="01adb-124">嵌套类型的可访问性依赖于它的[可访问域](../../../csharp/language-reference/keywords/accessibility-domain.md)，该域是由已声明的成员可访问性和直接包含类型的可访问域这二者共同确定的。</span><span class="sxs-lookup"><span data-stu-id="01adb-124">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="01adb-125">但是，嵌套类型的可访问域不能超出包含类型的可访问域。</span><span class="sxs-lookup"><span data-stu-id="01adb-125">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="01adb-126">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="01adb-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="01adb-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="01adb-127">See Also</span></span>  
 <span data-ttu-id="01adb-128">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="01adb-128">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="01adb-129">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="01adb-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="01adb-130">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="01adb-130">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="01adb-131">[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="01adb-131">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="01adb-132">[可访问域](../../../csharp/language-reference/keywords/accessibility-domain.md) </span><span class="sxs-lookup"><span data-stu-id="01adb-132">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md) </span></span>  
 <span data-ttu-id="01adb-133">[可访问性级别的使用限制](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="01adb-133">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span></span>  
 <span data-ttu-id="01adb-134">[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="01adb-134">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="01adb-135">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="01adb-135">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="01adb-136">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="01adb-136">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="01adb-137">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="01adb-137">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="01adb-138">内部</span><span class="sxs-lookup"><span data-stu-id="01adb-138">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

