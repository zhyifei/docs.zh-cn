---
title: "访问修饰符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: 15
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
ms.openlocfilehash: a3ad46580561500d9f011da4997007023a3bc844
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="bc4f8-102">访问修饰符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="bc4f8-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="bc4f8-103">访问修饰符是关键字，用于指定成员或类型已声明的可访问性。</span><span class="sxs-lookup"><span data-stu-id="bc4f8-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="bc4f8-104">本部分介绍四个访问修饰符：</span><span class="sxs-lookup"><span data-stu-id="bc4f8-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="bc4f8-105">公用</span><span class="sxs-lookup"><span data-stu-id="bc4f8-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="bc4f8-106">受保护</span><span class="sxs-lookup"><span data-stu-id="bc4f8-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="bc4f8-107">内部</span><span class="sxs-lookup"><span data-stu-id="bc4f8-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="bc4f8-108">专用</span><span class="sxs-lookup"><span data-stu-id="bc4f8-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="bc4f8-109">可使用访问修饰符指定以下五个可访问性级别：</span><span class="sxs-lookup"><span data-stu-id="bc4f8-109">The following five accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="bc4f8-110">`public`：访问不受限制。</span><span class="sxs-lookup"><span data-stu-id="bc4f8-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="bc4f8-111">`protected`：访问限于包含类或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="bc4f8-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="bc4f8-112">`Internal`：访问限于当前程序集。</span><span class="sxs-lookup"><span data-stu-id="bc4f8-112">`Internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="bc4f8-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)：访问限于当前程序集或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="bc4f8-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="bc4f8-114">`private`：访问限于包含类。</span><span class="sxs-lookup"><span data-stu-id="bc4f8-114">`private`: Access is limited to the containing type.</span></span>  
  
 <span data-ttu-id="bc4f8-115">本部分还介绍以下内容：</span><span class="sxs-lookup"><span data-stu-id="bc4f8-115">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="bc4f8-116">[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)：使用四种访问修饰符声明五个可访问性级别。</span><span class="sxs-lookup"><span data-stu-id="bc4f8-116">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare five levels of accessibility.</span></span>  
  
-   <span data-ttu-id="bc4f8-117">[可访问性域](../../../csharp/language-reference/keywords/accessibility-domain.md)：指定可在程序段中的何处引用成员。</span><span class="sxs-lookup"><span data-stu-id="bc4f8-117">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="bc4f8-118">[对使用可访问性级别的限制](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)：概括对使用已声明的可访问性级别的限制。</span><span class="sxs-lookup"><span data-stu-id="bc4f8-118">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc4f8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc4f8-119">See Also</span></span>  
 <span data-ttu-id="bc4f8-120">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bc4f8-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bc4f8-121">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bc4f8-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bc4f8-122">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="bc4f8-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="bc4f8-123">[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="bc4f8-123">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="bc4f8-124">[访问关键字](../../../csharp/language-reference/keywords/access-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="bc4f8-124">[Access Keywords](../../../csharp/language-reference/keywords/access-keywords.md) </span></span>  
 [<span data-ttu-id="bc4f8-125">修饰符</span><span class="sxs-lookup"><span data-stu-id="bc4f8-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

