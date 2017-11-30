---
title: "访问修饰符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23f99d0925aefde7ef43888d16e888a0943dfc21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="093ad-102">访问修饰符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="093ad-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="093ad-103">访问修饰符是关键字，用于指定成员或类型已声明的可访问性。</span><span class="sxs-lookup"><span data-stu-id="093ad-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="093ad-104">本部分介绍四个访问修饰符：</span><span class="sxs-lookup"><span data-stu-id="093ad-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="093ad-105">公用</span><span class="sxs-lookup"><span data-stu-id="093ad-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="093ad-106">受保护</span><span class="sxs-lookup"><span data-stu-id="093ad-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="093ad-107">内部</span><span class="sxs-lookup"><span data-stu-id="093ad-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="093ad-108">专用</span><span class="sxs-lookup"><span data-stu-id="093ad-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="093ad-109">可以使用访问修饰符指定以下六个可访问性级别：</span><span class="sxs-lookup"><span data-stu-id="093ad-109">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="093ad-110">`public`：访问不受限制。</span><span class="sxs-lookup"><span data-stu-id="093ad-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="093ad-111">`protected`：访问限于包含类或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="093ad-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="093ad-112">`internal`：访问限于当前程序集。</span><span class="sxs-lookup"><span data-stu-id="093ad-112">`internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="093ad-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md)： 访问仅限于当前程序集或从包含类派生的类型。</span><span class="sxs-lookup"><span data-stu-id="093ad-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="093ad-114">`private`：访问限于包含类。</span><span class="sxs-lookup"><span data-stu-id="093ad-114">`private`: Access is limited to the containing type.</span></span>  

 <span data-ttu-id="093ad-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md)： 访问被限制为包含的类或从包含当前程序集中的类派生的类型。</span><span class="sxs-lookup"><span data-stu-id="093ad-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="093ad-116">本部分还介绍以下内容：</span><span class="sxs-lookup"><span data-stu-id="093ad-116">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="093ad-117">[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)： 使用四个访问修饰符声明的可访问性的六个级别。</span><span class="sxs-lookup"><span data-stu-id="093ad-117">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="093ad-118">[可访问性域](../../../csharp/language-reference/keywords/accessibility-domain.md)：指定可在程序段中的何处引用成员。</span><span class="sxs-lookup"><span data-stu-id="093ad-118">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="093ad-119">[对使用可访问性级别的限制](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)：概括对使用已声明的可访问性级别的限制。</span><span class="sxs-lookup"><span data-stu-id="093ad-119">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="093ad-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="093ad-120">See Also</span></span>  
 [<span data-ttu-id="093ad-121">C# 参考</span><span class="sxs-lookup"><span data-stu-id="093ad-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="093ad-122">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="093ad-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="093ad-123">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="093ad-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="093ad-124">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="093ad-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="093ad-125">访问关键字</span><span class="sxs-lookup"><span data-stu-id="093ad-125">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
 [<span data-ttu-id="093ad-126">修饰符</span><span class="sxs-lookup"><span data-stu-id="093ad-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
