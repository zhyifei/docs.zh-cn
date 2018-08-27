---
title: 访问修饰符（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: ff313df9683dbc76bab684ff484b746ad05e065a
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935556"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="9574a-102">访问修饰符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="9574a-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="9574a-103">访问修饰符是关键字，用于指定成员或类型已声明的可访问性。</span><span class="sxs-lookup"><span data-stu-id="9574a-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="9574a-104">本部分介绍四个访问修饰符：</span><span class="sxs-lookup"><span data-stu-id="9574a-104">This section introduces the four access modifiers:</span></span>  
  
-   `public`
-   `protected`
-   `internal`
-   `private`
  
 <span data-ttu-id="9574a-105">可使用访问修饰符指定以下六个可访问性级别：</span><span class="sxs-lookup"><span data-stu-id="9574a-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="9574a-106">[`public`](public.md)：访问不受限制。</span><span class="sxs-lookup"><span data-stu-id="9574a-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="9574a-107">[`protected`](protected.md)：访问限于包含类或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="9574a-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="9574a-108">[`internal`](internal.md)：访问限于当前程序集。</span><span class="sxs-lookup"><span data-stu-id="9574a-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="9574a-109">[`protected internal`](protected-internal.md)：访问限于当前程序集或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="9574a-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="9574a-110">[`private`](private.md)：访问限于包含类型。</span><span class="sxs-lookup"><span data-stu-id="9574a-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="9574a-111">[`private protected`](private-protected.md)：访问限于包含类或派生自当前程序集中包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="9574a-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="9574a-112">本部分还介绍以下内容：</span><span class="sxs-lookup"><span data-stu-id="9574a-112">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="9574a-113">[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)：使用四种访问修饰符，声明六个可访问性级别。</span><span class="sxs-lookup"><span data-stu-id="9574a-113">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="9574a-114">[可访问性域](../../../csharp/language-reference/keywords/accessibility-domain.md)：指定可在程序段中的何处引用成员。</span><span class="sxs-lookup"><span data-stu-id="9574a-114">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="9574a-115">[对使用可访问性级别的限制](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)：概括对使用已声明的可访问性级别的限制。</span><span class="sxs-lookup"><span data-stu-id="9574a-115">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9574a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9574a-116">See Also</span></span>  
- [<span data-ttu-id="9574a-117">C# 参考</span><span class="sxs-lookup"><span data-stu-id="9574a-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="9574a-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="9574a-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9574a-119">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="9574a-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="9574a-120">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="9574a-120">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [<span data-ttu-id="9574a-121">访问关键字</span><span class="sxs-lookup"><span data-stu-id="9574a-121">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
- [<span data-ttu-id="9574a-122">修饰符</span><span class="sxs-lookup"><span data-stu-id="9574a-122">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
