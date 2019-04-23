---
title: 可访问性级别 - C# 参考
ms.custom: seodec18
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: da49c6f0b44ab0eefbd338963a744a11502f75da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130463"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="37c23-102">可访问性级别（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="37c23-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="37c23-103">使用访问修饰符 `public`、`protected`、`internal` 或 `private`，为成员指定以下声明的可访问性级别之一。</span><span class="sxs-lookup"><span data-stu-id="37c23-103">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="37c23-104">声明的可访问性</span><span class="sxs-lookup"><span data-stu-id="37c23-104">Declared accessibility</span></span>|<span data-ttu-id="37c23-105">含义</span><span class="sxs-lookup"><span data-stu-id="37c23-105">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="37c23-106">访问不受限制。</span><span class="sxs-lookup"><span data-stu-id="37c23-106">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="37c23-107">访问限于包含类或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="37c23-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="37c23-108">访问限于当前程序集。</span><span class="sxs-lookup"><span data-stu-id="37c23-108">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="37c23-109">访问限于当前程序集或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="37c23-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="37c23-110">访问限于包含类。</span><span class="sxs-lookup"><span data-stu-id="37c23-110">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="37c23-111">访问限于包含类或当前程序集中派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="37c23-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="37c23-112">自 C# 7.2 之后可用。</span><span class="sxs-lookup"><span data-stu-id="37c23-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="37c23-113">除使用 `protected internal` 或`private protected` 组合的情况外，一个成员或类型仅允许一个访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="37c23-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="37c23-114">命名空间中不允许出现访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="37c23-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="37c23-115">命名空间没有任何访问限制。</span><span class="sxs-lookup"><span data-stu-id="37c23-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="37c23-116">根据出现成员声明的上下文，仅允许某些声明的可访问性。</span><span class="sxs-lookup"><span data-stu-id="37c23-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="37c23-117">如果未在成员声明中指定访问修饰符，则将使用默认可访问性。</span><span class="sxs-lookup"><span data-stu-id="37c23-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="37c23-118">未嵌套在其他类型中的顶级类型只能具有 `internal` 或 `public` 可访问性。</span><span class="sxs-lookup"><span data-stu-id="37c23-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="37c23-119">这些类型的默认可访问性为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="37c23-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="37c23-120">作为其他类型的成员的嵌套类型可以具有如下表所示的声明的可访问性。</span><span class="sxs-lookup"><span data-stu-id="37c23-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="37c23-121">成员</span><span class="sxs-lookup"><span data-stu-id="37c23-121">Members of</span></span>|<span data-ttu-id="37c23-122">默认成员可访问性</span><span class="sxs-lookup"><span data-stu-id="37c23-122">Default member accessibility</span></span>|<span data-ttu-id="37c23-123">允许的成员的声明的可访问性</span><span class="sxs-lookup"><span data-stu-id="37c23-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="37c23-124">None</span><span class="sxs-lookup"><span data-stu-id="37c23-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="37c23-125">None</span><span class="sxs-lookup"><span data-stu-id="37c23-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="37c23-126">嵌套类型的可访问性依赖于它的[可访问域](../../../csharp/language-reference/keywords/accessibility-domain.md)，该域是由已声明的成员可访问性和直接包含类型的可访问域这二者共同确定的。</span><span class="sxs-lookup"><span data-stu-id="37c23-126">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="37c23-127">但是，嵌套类型的可访问域不能超出包含类型的可访问域。</span><span class="sxs-lookup"><span data-stu-id="37c23-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="37c23-128">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="37c23-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37c23-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="37c23-129">See also</span></span>

- [<span data-ttu-id="37c23-130">C# 参考</span><span class="sxs-lookup"><span data-stu-id="37c23-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="37c23-131">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="37c23-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="37c23-132">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="37c23-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="37c23-133">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="37c23-133">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="37c23-134">可访问域</span><span class="sxs-lookup"><span data-stu-id="37c23-134">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)
- [<span data-ttu-id="37c23-135">对使用可访问性级别的限制</span><span class="sxs-lookup"><span data-stu-id="37c23-135">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="37c23-136">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="37c23-136">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="37c23-137">public</span><span class="sxs-lookup"><span data-stu-id="37c23-137">public</span></span>](../../../csharp/language-reference/keywords/public.md)
- [<span data-ttu-id="37c23-138">专用</span><span class="sxs-lookup"><span data-stu-id="37c23-138">private</span></span>](../../../csharp/language-reference/keywords/private.md)
- [<span data-ttu-id="37c23-139">受保护</span><span class="sxs-lookup"><span data-stu-id="37c23-139">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
- [<span data-ttu-id="37c23-140">internal</span><span class="sxs-lookup"><span data-stu-id="37c23-140">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
