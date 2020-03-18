---
title: 访问修饰符 - C# 参考
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: 754949e42771de30cc2dce7e4e610f70ada6dfd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713845"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="d2ef4-102">访问修饰符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d2ef4-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="d2ef4-103">访问修饰符是关键字，用于指定成员或类型已声明的可访问性。</span><span class="sxs-lookup"><span data-stu-id="d2ef4-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="d2ef4-104">本部分介绍四个访问修饰符：</span><span class="sxs-lookup"><span data-stu-id="d2ef4-104">This section introduces the four access modifiers:</span></span>  
  
- `public`
- `protected`
- `internal`
- `private`
  
 <span data-ttu-id="d2ef4-105">可使用访问修饰符指定以下六个可访问性级别：</span><span class="sxs-lookup"><span data-stu-id="d2ef4-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="d2ef4-106">[`public`](public.md)：访问不受限制。</span><span class="sxs-lookup"><span data-stu-id="d2ef4-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="d2ef4-107">[`protected`](protected.md)：访问限于包含类或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="d2ef4-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="d2ef4-108">[`internal`](internal.md)：访问限于当前程序集。</span><span class="sxs-lookup"><span data-stu-id="d2ef4-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="d2ef4-109">[`protected internal`](protected-internal.md)：访问限于当前程序集或派生自包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="d2ef4-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="d2ef4-110">[`private`](private.md)：访问限于包含类型。</span><span class="sxs-lookup"><span data-stu-id="d2ef4-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="d2ef4-111">[`private protected`](private-protected.md)：访问限于包含类或派生自当前程序集中包含类的类型。</span><span class="sxs-lookup"><span data-stu-id="d2ef4-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="d2ef4-112">本部分还介绍以下内容：</span><span class="sxs-lookup"><span data-stu-id="d2ef4-112">This section also introduces the following:</span></span>  
  
- <span data-ttu-id="d2ef4-113">[可访问性级别](./accessibility-levels.md)：使用四种访问修饰符，声明六个可访问性级别。</span><span class="sxs-lookup"><span data-stu-id="d2ef4-113">[Accessibility Levels](./accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
- <span data-ttu-id="d2ef4-114">[可访问性域](./accessibility-domain.md)：指定可在程序段中的何处引用成员。</span><span class="sxs-lookup"><span data-stu-id="d2ef4-114">[Accessibility Domain](./accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
- <span data-ttu-id="d2ef4-115">[对使用可访问性级别的限制](./restrictions-on-using-accessibility-levels.md)：概括对使用已声明的可访问性级别的限制。</span><span class="sxs-lookup"><span data-stu-id="d2ef4-115">[Restrictions on Using Accessibility Levels](./restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2ef4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2ef4-116">See also</span></span>

- [<span data-ttu-id="d2ef4-117">C# 参考</span><span class="sxs-lookup"><span data-stu-id="d2ef4-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d2ef4-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d2ef4-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d2ef4-119">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="d2ef4-119">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="d2ef4-120">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="d2ef4-120">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="d2ef4-121">访问关键字</span><span class="sxs-lookup"><span data-stu-id="d2ef4-121">Access Keywords</span></span>](base.md)
- [<span data-ttu-id="d2ef4-122">修饰符</span><span class="sxs-lookup"><span data-stu-id="d2ef4-122">Modifiers</span></span>](index.md)
