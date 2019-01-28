---
title: internal - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: 8d787f8deb8f3b7d1e59d99e71662960a5c04e15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652080"
---
# <a name="internal-c-reference"></a><span data-ttu-id="dd7ce-102">internal（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="dd7ce-102">internal (C# Reference)</span></span>
<span data-ttu-id="dd7ce-103">`internal` 关键字是类型和类型成员的[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> 
  
 > <span data-ttu-id="dd7ce-104">本页涵盖 `internal` 访问。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-104">This page covers `internal` access.</span></span> <span data-ttu-id="dd7ce-105">`internal` 关键字也是 [`protected internal`](./protected-internal.md) 访问修饰符的一部分。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-105">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="dd7ce-106">只有在同一程序集的文件中，内部类型或成员才可访问，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="dd7ce-106">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```csharp  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  

 <span data-ttu-id="dd7ce-107">有关 `internal` 和其他访问修饰符的比较，请参阅[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)和[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-107">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="dd7ce-108">有关程序集的详细信息，请参阅[程序集和全局程序集缓存](../../../csharp/programming-guide/concepts/assemblies-gac/index.md)。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-108">For more information about assemblies, see [Assemblies and the Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
 <span data-ttu-id="dd7ce-109">内部访问通常用于基于组件的开发，因为它可使一组组件以私有方式进行协作，而不必向应用程序代码的其余部分公开。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-109">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="dd7ce-110">例如，用于生成图形用户界面的框架可以提供 `Control` 和 `Form` 类，这两个类通过使用具有内部访问权限的成员进行协作。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-110">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="dd7ce-111">由于这些成员是内部的，因此不会向正在使用框架的代码公开。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-111">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="dd7ce-112">从定义具有内部访问权限的类型或成员的程序集外部引用该类型或成员是错误的。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-112">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd7ce-113">示例</span><span class="sxs-lookup"><span data-stu-id="dd7ce-113">Example</span></span>  
 <span data-ttu-id="dd7ce-114">此示例包含两个文件，即 `Assembly1.cs` 和 `Assembly1_a.cs`。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-114">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="dd7ce-115">第一个文件包含内部基类 `BaseClass`。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-115">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="dd7ce-116">在第二个文件中，尝试实例化 `BaseClass` 会产生错误。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-116">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
```csharp  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```csharp  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="dd7ce-117">示例</span><span class="sxs-lookup"><span data-stu-id="dd7ce-117">Example</span></span>  
 <span data-ttu-id="dd7ce-118">在此示例中，使用在示例 1 中所用的相同文件，并将 `BaseClass` 的可访问性级别更改为 `public`。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-118">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="dd7ce-119">另将成员 `IntM` 的可访问性级别更改为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-119">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="dd7ce-120">在此例中，可以实例化类，但不能访问内部成员。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-120">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
```csharp  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```csharp  
// Assembly2_a.cs  
// Compile with: /reference:Assembly2.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="dd7ce-121">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="dd7ce-121">C# Language Specification</span></span>  

<span data-ttu-id="dd7ce-122">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[声明的可访问性](~/_csharplang/spec/basic-concepts.md#declared-accessibility)。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-122">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="dd7ce-123">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="dd7ce-123">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dd7ce-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd7ce-124">See also</span></span>

- [<span data-ttu-id="dd7ce-125">C# 参考</span><span class="sxs-lookup"><span data-stu-id="dd7ce-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="dd7ce-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="dd7ce-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="dd7ce-127">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="dd7ce-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="dd7ce-128">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="dd7ce-128">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="dd7ce-129">可访问性级别</span><span class="sxs-lookup"><span data-stu-id="dd7ce-129">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)
- [<span data-ttu-id="dd7ce-130">修饰符</span><span class="sxs-lookup"><span data-stu-id="dd7ce-130">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
- [<span data-ttu-id="dd7ce-131">public</span><span class="sxs-lookup"><span data-stu-id="dd7ce-131">public</span></span>](../../../csharp/language-reference/keywords/public.md)
- [<span data-ttu-id="dd7ce-132">专用</span><span class="sxs-lookup"><span data-stu-id="dd7ce-132">private</span></span>](../../../csharp/language-reference/keywords/private.md)
- [<span data-ttu-id="dd7ce-133">受保护</span><span class="sxs-lookup"><span data-stu-id="dd7ce-133">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
