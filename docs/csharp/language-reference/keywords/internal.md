---
title: "internal（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- internal_CSharpKeyword
- internal
dev_langs:
- CSharp
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: 23
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
ms.openlocfilehash: 5674a78e2c317357c31d9e2661a25ce86cbf4f6a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="internal-c-reference"></a><span data-ttu-id="b32a7-102">internal（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b32a7-102">internal (C# Reference)</span></span>
<span data-ttu-id="b32a7-103">`internal` 关键字是类型和类型成员的[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="b32a7-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> <span data-ttu-id="b32a7-104">只有在同一程序集的文件中，内部类型或成员才可访问，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="b32a7-104">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  
  
 <span data-ttu-id="b32a7-105">可从当前程序集或从包含类派生的类型访问具有访问修饰符 `protected internal` 的类型或成员。</span><span class="sxs-lookup"><span data-stu-id="b32a7-105">Types or members that have access modifier `protected internal` can be accessed from the current assembly or from types that are derived from the containing class.</span></span>  
  
 <span data-ttu-id="b32a7-106">有关 `internal` 和其他访问修饰符的比较，请参阅[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)和[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="b32a7-106">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="b32a7-107">有关程序集的详细信息，请参阅[程序集和全局程序集缓存](../../../csharp/programming-guide/concepts/assemblies-gac/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b32a7-107">For more information about assemblies, see [Assemblies and the Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
 <span data-ttu-id="b32a7-108">内部访问通常用于基于组件的开发，因为它可使一组组件以私有方式进行协作，而不必向应用程序代码的其余部分公开。</span><span class="sxs-lookup"><span data-stu-id="b32a7-108">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="b32a7-109">例如，用于生成图形用户界面的框架可以提供 `Control` 和 `Form` 类，这两个类通过使用具有内部访问权限的成员进行协作。</span><span class="sxs-lookup"><span data-stu-id="b32a7-109">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="b32a7-110">由于这些成员是内部的，因此不会向正在使用框架的代码公开。</span><span class="sxs-lookup"><span data-stu-id="b32a7-110">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="b32a7-111">从定义具有内部访问权限的类型或成员的程序集外部引用该类型或成员是错误的。</span><span class="sxs-lookup"><span data-stu-id="b32a7-111">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b32a7-112">示例</span><span class="sxs-lookup"><span data-stu-id="b32a7-112">Example</span></span>  
 <span data-ttu-id="b32a7-113">此示例包含两个文件，即 `Assembly1.cs` 和 `Assembly1_a.cs`。</span><span class="sxs-lookup"><span data-stu-id="b32a7-113">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="b32a7-114">第一个文件包含内部基类 `BaseClass`。</span><span class="sxs-lookup"><span data-stu-id="b32a7-114">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="b32a7-115">在第二个文件中，尝试实例化 `BaseClass` 会产生错误。</span><span class="sxs-lookup"><span data-stu-id="b32a7-115">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
```  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```  
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
  
## <a name="example"></a><span data-ttu-id="b32a7-116">示例</span><span class="sxs-lookup"><span data-stu-id="b32a7-116">Example</span></span>  
 <span data-ttu-id="b32a7-117">在此示例中，使用在示例 1 中所用的相同文件，并将 `BaseClass` 的可访问性级别更改为 `public`。</span><span class="sxs-lookup"><span data-stu-id="b32a7-117">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="b32a7-118">另将成员 `IntM` 的可访问性级别更改为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="b32a7-118">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="b32a7-119">在此例中，可以实例化类，但不能访问内部成员。</span><span class="sxs-lookup"><span data-stu-id="b32a7-119">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
```  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```  
// Assembly2_a.cs  
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="b32a7-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b32a7-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b32a7-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="b32a7-121">See Also</span></span>  
 <span data-ttu-id="b32a7-122">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b32a7-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b32a7-123">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b32a7-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b32a7-124">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="b32a7-124">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="b32a7-125">[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="b32a7-125">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="b32a7-126">[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="b32a7-126">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="b32a7-127">[修饰符](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="b32a7-127">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="b32a7-128">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="b32a7-128">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="b32a7-129">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="b32a7-129">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 [<span data-ttu-id="b32a7-130">受保护</span><span class="sxs-lookup"><span data-stu-id="b32a7-130">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)

