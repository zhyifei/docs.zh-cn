---
title: "泛型方法（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
caps.latest.revision: 27
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
ms.openlocfilehash: 14461773303bafc098f79c3686b1f76827f11005
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="generic-methods-c-programming-guide"></a><span data-ttu-id="caa2b-102">泛型方法（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="caa2b-102">Generic Methods (C# Programming Guide)</span></span>
<span data-ttu-id="caa2b-103">泛型方法是通过类型参数声明的方法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="caa2b-103">A generic method is a method that is declared with type parameters, as follows:</span></span>  
  
 <span data-ttu-id="caa2b-104">[!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="caa2b-104">[!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="caa2b-105">如下示例演示使用类型参数的 `int` 调用方法的一种方式：</span><span class="sxs-lookup"><span data-stu-id="caa2b-105">The following code example shows one way to call the method by using `int` for the type argument:</span></span>  
  
 <span data-ttu-id="caa2b-106">[!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="caa2b-106">[!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="caa2b-107">还可省略类型参数，编译器将推断类型参数。</span><span class="sxs-lookup"><span data-stu-id="caa2b-107">You can also omit the type argument and the compiler will infer it.</span></span> <span data-ttu-id="caa2b-108">如下 `Swap` 调用等效于之前的调用：</span><span class="sxs-lookup"><span data-stu-id="caa2b-108">The following call to `Swap` is equivalent to the previous call:</span></span>  
  
 <span data-ttu-id="caa2b-109">[!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="caa2b-109">[!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]</span></span>  
  
 <span data-ttu-id="caa2b-110">类型推理的相同规则适用于静态方法和实例方法。</span><span class="sxs-lookup"><span data-stu-id="caa2b-110">The same rules for type inference apply to static methods and instance methods.</span></span> <span data-ttu-id="caa2b-111">编译器可基于传入的方法参数推断类型参数；而无法仅根据约束或返回值推断类型参数。</span><span class="sxs-lookup"><span data-stu-id="caa2b-111">The compiler can infer the type parameters based on the method arguments you pass in; it cannot infer the type parameters only from a constraint or return value.</span></span> <span data-ttu-id="caa2b-112">因此，类型推理不适用于不具有参数的方法。</span><span class="sxs-lookup"><span data-stu-id="caa2b-112">Therefore type inference does not work with methods that have no parameters.</span></span> <span data-ttu-id="caa2b-113">类型推理发生在编译时，之后编译器尝试解析重载的方法签名。</span><span class="sxs-lookup"><span data-stu-id="caa2b-113">Type inference occurs at compile time before the compiler tries to resolve overloaded method signatures.</span></span> <span data-ttu-id="caa2b-114">编译器将类型推理逻辑应用于共用同一名称的所有泛型方法。</span><span class="sxs-lookup"><span data-stu-id="caa2b-114">The compiler applies type inference logic to all generic methods that share the same name.</span></span> <span data-ttu-id="caa2b-115">在重载解决方案步骤中，编译器仅包含在其上类型推理成功的泛型方法。</span><span class="sxs-lookup"><span data-stu-id="caa2b-115">In the overload resolution step, the compiler includes only those generic methods on which type inference succeeded.</span></span>  
  
 <span data-ttu-id="caa2b-116">在泛型类中，非泛型方法可访问类级别类型参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="caa2b-116">Within a generic class, non-generic methods can access the class-level type parameters, as follows:</span></span>  
  
 <span data-ttu-id="caa2b-117">[!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="caa2b-117">[!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]</span></span>  
  
 <span data-ttu-id="caa2b-118">如果定义一个具有与包含类相同的类型参数的泛型方法，则编译器会生成警告 CS0693，因为在该方法范围内，向内 `T` 提供的参数会隐藏向外 `T` 提供的参数。</span><span class="sxs-lookup"><span data-stu-id="caa2b-118">If you define a generic method that takes the same type parameters as the containing class, the compiler generates warning CS0693 because within the method scope, the argument supplied for the inner `T` hides the argument supplied for the outer `T`.</span></span> <span data-ttu-id="caa2b-119">如果需要使用类型参数（而不是类实例化时提供的参数）调用泛型类方法所具备的灵活性，请考虑为此方法的类型参数提供另一标识符，如下方示例中 `GenericList2<T>` 所示。</span><span class="sxs-lookup"><span data-stu-id="caa2b-119">If you require the flexibility of calling a generic class method with type arguments other than the ones provided when the class was instantiated, consider providing another identifier for the type parameter of the method, as shown in `GenericList2<T>` in the following example.</span></span>  
  
 <span data-ttu-id="caa2b-120">[!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="caa2b-120">[!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]</span></span>  
  
 <span data-ttu-id="caa2b-121">使用约束在方法中的类型参数上实现更多专用操作。</span><span class="sxs-lookup"><span data-stu-id="caa2b-121">Use constraints to enable more specialized operations on type parameters in methods.</span></span> <span data-ttu-id="caa2b-122">此版 `Swap<T>` 现名为 `SwapIfGreater<T>`，仅可用于实现 <xref:System.IComparable%601> 的类型参数。</span><span class="sxs-lookup"><span data-stu-id="caa2b-122">This version of `Swap<T>`, now named `SwapIfGreater<T>`, can only be used with type arguments that implement <xref:System.IComparable%601>.</span></span>  
  
 <span data-ttu-id="caa2b-123">[!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="caa2b-123">[!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]</span></span>  
  
 <span data-ttu-id="caa2b-124">泛型方法可重载在数个泛型参数上。</span><span class="sxs-lookup"><span data-stu-id="caa2b-124">Generic methods can be overloaded on several type parameters.</span></span> <span data-ttu-id="caa2b-125">例如，以下方法可全部位于同一类中：</span><span class="sxs-lookup"><span data-stu-id="caa2b-125">For example, the following methods can all be located in the same class:</span></span>  
  
 <span data-ttu-id="caa2b-126">[!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="caa2b-126">[!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="caa2b-127">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="caa2b-127">C# Language Specification</span></span>  
 <span data-ttu-id="caa2b-128">有关详细信息，请参阅 [C# 语言规范](../../../csharp/language-reference/language-specification/index.md)。</span><span class="sxs-lookup"><span data-stu-id="caa2b-128">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa2b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="caa2b-129">See Also</span></span>  
 <span data-ttu-id="caa2b-130"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="caa2b-130"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="caa2b-131">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="caa2b-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="caa2b-132">[泛型简介](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="caa2b-132">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 [<span data-ttu-id="caa2b-133">方法</span><span class="sxs-lookup"><span data-stu-id="caa2b-133">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

