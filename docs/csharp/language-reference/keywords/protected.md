---
title: protected（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: 2da8211ac21a5016478e7b881e7f2f9925b49cef
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001329"
---
# <a name="protected-c-reference"></a><span data-ttu-id="902ce-102">protected（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="902ce-102">protected (C# Reference)</span></span>
<span data-ttu-id="902ce-103">`protected` 关键字是一个成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="902ce-103">The `protected` keyword is a member access modifier.</span></span> 

 > <span data-ttu-id="902ce-104">本页涵盖 `protected` 访问。</span><span class="sxs-lookup"><span data-stu-id="902ce-104">This page covers `protected` access.</span></span> <span data-ttu-id="902ce-105">`protected` 关键字也属于 [`protected internal`](./protected-internal.md) 和 [`private protected`](./private-protected.md) 访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="902ce-105">The `protected` keyword is also part of the [`protected internal`](./protected-internal.md) and [`private protected`](./private-protected.md) access modifiers.</span></span> 

<span data-ttu-id="902ce-106">受保护成员在其所在的类中可由派生类实例访问。</span><span class="sxs-lookup"><span data-stu-id="902ce-106">A protected member is accessible within its class and by derived class instances.</span></span> 

<span data-ttu-id="902ce-107">有关 `protected` 和其他访问修饰符的比较，请参阅[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="902ce-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
  
## <a name="example"></a><span data-ttu-id="902ce-108">示例</span><span class="sxs-lookup"><span data-stu-id="902ce-108">Example</span></span>  
 <span data-ttu-id="902ce-109">只有在通过派生类类型进行访问时，基类的受保护成员在派生类中才是可访问的。</span><span class="sxs-lookup"><span data-stu-id="902ce-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="902ce-110">以下面的代码段为例：</span><span class="sxs-lookup"><span data-stu-id="902ce-110">For example, consider the following code segment:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 <span data-ttu-id="902ce-111">语句 `a.x = 10` 生成错误，因为它是在静态方法 Main 中生成的，而不是类 B 的实例。</span><span class="sxs-lookup"><span data-stu-id="902ce-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>  
  
 <span data-ttu-id="902ce-112">无法保护结构成员，因为无法继承结构。</span><span class="sxs-lookup"><span data-stu-id="902ce-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="902ce-113">示例</span><span class="sxs-lookup"><span data-stu-id="902ce-113">Example</span></span>  
 <span data-ttu-id="902ce-114">在此示例中，`DerivedPoint` 类是从 `Point` 派生的。</span><span class="sxs-lookup"><span data-stu-id="902ce-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="902ce-115">因此，可以从派生类直接访问基类的受保护成员。</span><span class="sxs-lookup"><span data-stu-id="902ce-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 <span data-ttu-id="902ce-116">如果将 `x` 和 `y` 的访问级别更改为 [private](../../../csharp/language-reference/keywords/private.md)，编译器将发出错误消息：</span><span class="sxs-lookup"><span data-stu-id="902ce-116">If you change the access levels of `x` and `y` to [private](../../../csharp/language-reference/keywords/private.md), the compiler will issue the error messages:</span></span>  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="902ce-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="902ce-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## 

- [<span data-ttu-id="902ce-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="902ce-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="902ce-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="902ce-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="902ce-120">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="902ce-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="902ce-121">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="902ce-121">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [<span data-ttu-id="902ce-122">可访问性级别</span><span class="sxs-lookup"><span data-stu-id="902ce-122">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
- [<span data-ttu-id="902ce-123">修饰符</span><span class="sxs-lookup"><span data-stu-id="902ce-123">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
- [<span data-ttu-id="902ce-124">public</span><span class="sxs-lookup"><span data-stu-id="902ce-124">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
- [<span data-ttu-id="902ce-125">private</span><span class="sxs-lookup"><span data-stu-id="902ce-125">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="902ce-126">internal</span><span class="sxs-lookup"><span data-stu-id="902ce-126">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
- <span data-ttu-id="902ce-127">[Internal Virtual 关键字的安全问题](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="902ce-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>