---
title: 访问修饰符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: d87ea1ff18c4697a2c04f22cbf67720f21cbf459
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118126"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="52523-102">访问修饰符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="52523-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="52523-103">访问修饰符是关键字，用于指定成员或类型已声明的可访问性。</span><span class="sxs-lookup"><span data-stu-id="52523-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="52523-104">本部分介绍四个访问修饰符：</span><span class="sxs-lookup"><span data-stu-id="52523-104">This section introduces the four access modifiers:</span></span>  
  
-   `public`
-   `protected`
-   `internal`
-   `private`
  
 <span data-ttu-id="52523-105">可使用访问修饰符指定以下六个可访问性级别：</span><span class="sxs-lookup"><span data-stu-id="52523-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="52523-106">[`public`](public.md)：访问不受限制。</span><span class="sxs-lookup"><span data-stu-id="52523-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="52523-107">[`protected`](protected.md)：访问限于包含类或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="52523-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="52523-108">[`internal`](internal.md)：访问限于当前程序集。</span><span class="sxs-lookup"><span data-stu-id="52523-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="52523-109">[`protected internal`](protected-internal.md)：访问限于当前程序集或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="52523-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="52523-110">[`private`](private.md)：访问限于包含类。</span><span class="sxs-lookup"><span data-stu-id="52523-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="52523-111">[`private protected`](private-protected.md)：访问限于包含类或当前程序集中派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="52523-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="52523-112">本部分还介绍以下内容：</span><span class="sxs-lookup"><span data-stu-id="52523-112">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="52523-113">[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)：使用四个访问修饰符声明六个可访问性级别。</span><span class="sxs-lookup"><span data-stu-id="52523-113">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="52523-114">[可访问性域](../../../csharp/language-reference/keywords/accessibility-domain.md)：指定可以在程序段中的何处引用成员。</span><span class="sxs-lookup"><span data-stu-id="52523-114">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="52523-115">[可访问性级别的使用限制](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)：汇总了已声明可访问性级别的使用限制。</span><span class="sxs-lookup"><span data-stu-id="52523-115">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52523-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="52523-116">See also</span></span>

- [<span data-ttu-id="52523-117">C# 参考</span><span class="sxs-lookup"><span data-stu-id="52523-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="52523-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="52523-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="52523-119">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="52523-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="52523-120">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="52523-120">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="52523-121">访问关键字</span><span class="sxs-lookup"><span data-stu-id="52523-121">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)
- [<span data-ttu-id="52523-122">修饰符</span><span class="sxs-lookup"><span data-stu-id="52523-122">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
