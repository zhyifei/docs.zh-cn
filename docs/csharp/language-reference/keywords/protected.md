---
title: protected（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: a3115fe82b452f52ee75cf222302ece0fc67b330
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="protected-c-reference"></a><span data-ttu-id="ad05d-102">protected（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ad05d-102">protected (C# Reference)</span></span>
<span data-ttu-id="ad05d-103">`protected` 关键字是一个成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad05d-103">The `protected` keyword is a member access modifier.</span></span> 

 > <span data-ttu-id="ad05d-104">本页涵盖 `protected` 访问。</span><span class="sxs-lookup"><span data-stu-id="ad05d-104">This page covers `protected` access.</span></span> <span data-ttu-id="ad05d-105">`protected` 关键字也属于 [`protected internal`](./protected-internal.md) 和 [`private protected`](./private-protected.md) 访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad05d-105">The `protected` keyword is also part of the [`protected internal`](./protected-internal.md) and [`private protected`](./private-protected.md) access modifiers.</span></span> 

<span data-ttu-id="ad05d-106">受保护成员在其所在的类中可由派生类实例访问。</span><span class="sxs-lookup"><span data-stu-id="ad05d-106">A protected member is accessible within its class and by derived class instances.</span></span> 

<span data-ttu-id="ad05d-107">有关 `protected` 和其他访问修饰符的比较，请参阅[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="ad05d-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
  
## <a name="example"></a><span data-ttu-id="ad05d-108">示例</span><span class="sxs-lookup"><span data-stu-id="ad05d-108">Example</span></span>  
 <span data-ttu-id="ad05d-109">只有在通过派生类类型进行访问时，基类的受保护成员在派生类中才是可访问的。</span><span class="sxs-lookup"><span data-stu-id="ad05d-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="ad05d-110">以下面的代码段为例：</span><span class="sxs-lookup"><span data-stu-id="ad05d-110">For example, consider the following code segment:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 <span data-ttu-id="ad05d-111">语句 `a.x = 10` 生成错误，因为它是在静态方法 Main 中生成的，而不是类 B 的实例。</span><span class="sxs-lookup"><span data-stu-id="ad05d-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>  
  
 <span data-ttu-id="ad05d-112">无法保护结构成员，因为无法继承结构。</span><span class="sxs-lookup"><span data-stu-id="ad05d-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad05d-113">示例</span><span class="sxs-lookup"><span data-stu-id="ad05d-113">Example</span></span>  
 <span data-ttu-id="ad05d-114">在此示例中，`DerivedPoint` 类是从 `Point` 派生的。</span><span class="sxs-lookup"><span data-stu-id="ad05d-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="ad05d-115">因此，可以从派生类直接访问基类的受保护成员。</span><span class="sxs-lookup"><span data-stu-id="ad05d-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 <span data-ttu-id="ad05d-116">如果将 `x` 和 `y` 的访问级别更改为 [private](../../../csharp/language-reference/keywords/private.md)，编译器将发出错误消息：</span><span class="sxs-lookup"><span data-stu-id="ad05d-116">If you change the access levels of `x` and `y` to [private](../../../csharp/language-reference/keywords/private.md), the compiler will issue the error messages:</span></span>  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="ad05d-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ad05d-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad05d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad05d-118">See Also</span></span>  
 [<span data-ttu-id="ad05d-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="ad05d-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ad05d-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ad05d-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ad05d-121">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="ad05d-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ad05d-122">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="ad05d-122">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="ad05d-123">可访问性级别</span><span class="sxs-lookup"><span data-stu-id="ad05d-123">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="ad05d-124">修饰符</span><span class="sxs-lookup"><span data-stu-id="ad05d-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="ad05d-125">public</span><span class="sxs-lookup"><span data-stu-id="ad05d-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="ad05d-126">private</span><span class="sxs-lookup"><span data-stu-id="ad05d-126">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="ad05d-127">internal</span><span class="sxs-lookup"><span data-stu-id="ad05d-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="ad05d-128">[Internal Virtual 关键字的安全问题](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="ad05d-128">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>