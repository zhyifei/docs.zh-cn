---
title: "访问修饰符（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
caps.latest.revision: 32
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
ms.openlocfilehash: 38b259b4d85d54467cd15cd49e5987f6198e8d99
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-programming-guide"></a><span data-ttu-id="66c83-102">访问修饰符（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="66c83-102">Access Modifiers (C# Programming Guide)</span></span>
<span data-ttu-id="66c83-103">所有类型和类型成员都具有可访问性级别，该级别可以控制是否可以从你的程序集或其他程序集中的其他代码中使用它们。</span><span class="sxs-lookup"><span data-stu-id="66c83-103">All types and type members have an accessibility level, which controls whether they can be used from other code in your assembly or other assemblies.</span></span> <span data-ttu-id="66c83-104">可以使用以下访问修饰符在进行声明时指定类型或成员的可访问性：</span><span class="sxs-lookup"><span data-stu-id="66c83-104">You can use the following access modifiers to specify the accessibility of a type or member when you declare it:</span></span>  
  
 [<span data-ttu-id="66c83-105">公用</span><span class="sxs-lookup"><span data-stu-id="66c83-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 <span data-ttu-id="66c83-106">同一程序集中的任何其他代码或引用该程序集的其他程序集都可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="66c83-106">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>  
  
 [<span data-ttu-id="66c83-107">专用</span><span class="sxs-lookup"><span data-stu-id="66c83-107">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 <span data-ttu-id="66c83-108">只有同一类或结构中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="66c83-108">The type or member can be accessed only by code in the same class or struct.</span></span>  
  
 [<span data-ttu-id="66c83-109">受保护</span><span class="sxs-lookup"><span data-stu-id="66c83-109">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 <span data-ttu-id="66c83-110">只有同一类或结构或者从该类派生的类中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="66c83-110">The type or member can be accessed only by code in the same class or struct, or in a class that is derived from that class.</span></span>  
  
 [<span data-ttu-id="66c83-111">内部</span><span class="sxs-lookup"><span data-stu-id="66c83-111">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="66c83-112">同一程序集中的任何代码都可以访问该类型或成员，但其他程序集中的代码不可以。</span><span class="sxs-lookup"><span data-stu-id="66c83-112">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>  
  
 `protected internal`  
 <span data-ttu-id="66c83-113">该类型或成员可由对其进行声明的程序集或另一程序集中的派生类中的任何代码访问。</span><span class="sxs-lookup"><span data-stu-id="66c83-113">The type or member can be accessed by any code in the assembly in which it is declared, or from within a derived class in another assembly.</span></span> <span data-ttu-id="66c83-114">从另一程序集进行访问必须发生在从此类（其中已声明受保护的内部元素）派生的类声明中，且必须通过派生类类型的实例发生。</span><span class="sxs-lookup"><span data-stu-id="66c83-114">Access from another assembly must take place within a class declaration that derives from the class in which the protected internal element is declared, and it must take place through an instance of the derived class type.</span></span>  
  
 <span data-ttu-id="66c83-115">下面的示例演示如何在类型和成员上指定访问修饰符：</span><span class="sxs-lookup"><span data-stu-id="66c83-115">The following examples demonstrate how to specify access modifiers on a type and member:</span></span>  
  
 <span data-ttu-id="66c83-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="66c83-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span></span>  
  
 <span data-ttu-id="66c83-117">并非所有的访问修饰符都可以由所有上下文中的所有类型或成员使用，并且在某些情况下，类型成员的可访问性受其包含类型的可访问性限制。</span><span class="sxs-lookup"><span data-stu-id="66c83-117">Not all access modifiers can be used by all types or members in all contexts, and in some cases the accessibility of a type member is constrained by the accessibility of its containing type.</span></span> <span data-ttu-id="66c83-118">以下各节提供了有关可访问性的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="66c83-118">The following sections provide more details about accessibility.</span></span>  
  
## <a name="class-and-struct-accessibility"></a><span data-ttu-id="66c83-119">类和结构可访问性</span><span class="sxs-lookup"><span data-stu-id="66c83-119">Class and Struct Accessibility</span></span>  
 <span data-ttu-id="66c83-120">在命名空间内直接声明（换句话说，不嵌套在其他类或结构中）的类和结构可以为公共或内部。</span><span class="sxs-lookup"><span data-stu-id="66c83-120">Classes and structs that are declared directly within a namespace (in other words, that are not nested within other classes or structs) can be either public or internal.</span></span> <span data-ttu-id="66c83-121">如果未指定任何访问修饰符，则默认设置为内部。</span><span class="sxs-lookup"><span data-stu-id="66c83-121">Internal is the default if no access modifier is specified.</span></span>  
  
 <span data-ttu-id="66c83-122">结构成员（包括嵌套的类和结构）可以声明为公共、内部或私有。</span><span class="sxs-lookup"><span data-stu-id="66c83-122">Struct members, including nested classes and structs, can be declared as public, internal, or private.</span></span> <span data-ttu-id="66c83-123">类成员（包括嵌套的类和结构）可以为公共、受保护的内部、受保护、内部或私有。</span><span class="sxs-lookup"><span data-stu-id="66c83-123">Class members, including nested classes and structs, can be public, protected internal, protected, internal, or private.</span></span> <span data-ttu-id="66c83-124">默认情况下，类成员和结构成员（包括嵌套的类和结构）的访问级别为私有。</span><span class="sxs-lookup"><span data-stu-id="66c83-124">The access level for class members and struct members, including nested classes and structs, is private by default.</span></span> <span data-ttu-id="66c83-125">不能从包含类型的外部访问私有嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="66c83-125">Private nested types are not accessible from outside the containing type.</span></span>  
  
 <span data-ttu-id="66c83-126">派生类不能具有高于其基类型的可访问性。</span><span class="sxs-lookup"><span data-stu-id="66c83-126">Derived classes cannot have greater accessibility than their base types.</span></span> <span data-ttu-id="66c83-127">换而言之，不能具有派生自内部类 `A` 的公共类 `B`。</span><span class="sxs-lookup"><span data-stu-id="66c83-127">In other words, you cannot have a public class `B` that derives from an internal class `A`.</span></span> <span data-ttu-id="66c83-128">如果允许这样，则它将具有使 `A` 公开的效果，因为可从派生类访问 `A` 的所有受保护的或内部成员。</span><span class="sxs-lookup"><span data-stu-id="66c83-128">If this were allowed, it would have the effect of making `A` public, because all protected or internal members of `A` are accessible from the derived class.</span></span>  
  
 <span data-ttu-id="66c83-129">可以通过使用 InternalsVisibleToAttribute 启用特定的其他程序集访问内部类型。</span><span class="sxs-lookup"><span data-stu-id="66c83-129">You can enable specific other assemblies to access your internal types by using the InternalsVisibleToAttribute.</span></span> <span data-ttu-id="66c83-130">有关详细信息，请参阅[友元程序集](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)。</span><span class="sxs-lookup"><span data-stu-id="66c83-130">For more information, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
## <a name="class-and-struct-member-accessibility"></a><span data-ttu-id="66c83-131">类和结构成员可访问性</span><span class="sxs-lookup"><span data-stu-id="66c83-131">Class and Struct Member Accessibility</span></span>  
 <span data-ttu-id="66c83-132">可以使用任何五种访问类型声明类成员（包括嵌套的类和结构）。</span><span class="sxs-lookup"><span data-stu-id="66c83-132">Class members (including nested classes and structs) can be declared with any of the five types of access.</span></span> <span data-ttu-id="66c83-133">结构成员无法声明为受保护，因为结构不支持继承。</span><span class="sxs-lookup"><span data-stu-id="66c83-133">Struct members cannot be declared as protected because structs do not support inheritance.</span></span>  
  
 <span data-ttu-id="66c83-134">通常情况下，成员的可访问性不大于包含该成员的类型的可访问性。</span><span class="sxs-lookup"><span data-stu-id="66c83-134">Normally, the accessibility of a member is not greater than the accessibility of the type that contains it.</span></span> <span data-ttu-id="66c83-135">但是，如果内部类的公共成员实现了接口方法或替代了在公共基类中定义的虚拟方法，则可从该程序集的外部访问该成员。</span><span class="sxs-lookup"><span data-stu-id="66c83-135">However, a public member of an internal class might be accessible from outside the assembly if the member implements interface methods or overrides virtual methods that are defined in a public base class.</span></span>  
  
 <span data-ttu-id="66c83-136">为字段、属性或事件的任何成员的类型必须至少与该成员本身具有相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="66c83-136">The type of any member that is a field, property, or event must be at least as accessible as the member itself.</span></span> <span data-ttu-id="66c83-137">同样，为方法、索引器或委托的任何成员的返回类型和参数类型必须至少与该成员本身具有相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="66c83-137">Similarly, the return type and the parameter types of any member that is a method, indexer, or delegate must be at least as accessible as the member itself.</span></span> <span data-ttu-id="66c83-138">例如，不能具有返回类 `C` 的公共方法 `M`，除非 `C` 也是公共的。</span><span class="sxs-lookup"><span data-stu-id="66c83-138">For example, you cannot have a public method `M` that returns a class `C` unless `C` is also public.</span></span> <span data-ttu-id="66c83-139">同样，如果 `A` 声明为私有，则不能具有类型 `A` 的受保护的属性。</span><span class="sxs-lookup"><span data-stu-id="66c83-139">Likewise, you cannot have a protected property of type `A` if `A` is declared as private.</span></span>  
  
 <span data-ttu-id="66c83-140">用户定义的运算符始终必须声明为公共。</span><span class="sxs-lookup"><span data-stu-id="66c83-140">User-defined operators must always be declared as public.</span></span> <span data-ttu-id="66c83-141">有关详细信息，请参阅[运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="66c83-141">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
 <span data-ttu-id="66c83-142">终结器不能具有可访问性修饰符。</span><span class="sxs-lookup"><span data-stu-id="66c83-142">Finalizers cannot have accessibility modifiers.</span></span>  
  
 <span data-ttu-id="66c83-143">若要设置类或结构成员的访问级别，向成员声明添加适当的关键字，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="66c83-143">To set the access level for a class or struct member, add the appropriate keyword to the member declaration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="66c83-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="66c83-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66c83-145">受保护的内部可访问性级别意味着受保护或内部，而非受保护和内部。</span><span class="sxs-lookup"><span data-stu-id="66c83-145">The protected internal accessibility level means protected OR internal, not protected AND internal.</span></span> <span data-ttu-id="66c83-146">换而言之，可以从同一程序集中的任何类（包括派生类）访问受保护的内部成员。</span><span class="sxs-lookup"><span data-stu-id="66c83-146">In other words, a protected internal member can be accessed from any class in the same assembly, including derived classes.</span></span> <span data-ttu-id="66c83-147">若要将同一程序集中的可访问性限制为仅派生类，请声明类本身为内部，并声明其成员为受保护。</span><span class="sxs-lookup"><span data-stu-id="66c83-147">To limit accessibility to only derived classes in the same assembly, declare the class itself internal, and declare its members as protected.</span></span>  
  
## <a name="other-types"></a><span data-ttu-id="66c83-148">其他类型</span><span class="sxs-lookup"><span data-stu-id="66c83-148">Other Types</span></span>  
 <span data-ttu-id="66c83-149">在命名空间内直接声明的接口可以声明为公共或内部，就像类和结构一样，接口默认设置为内部访问。</span><span class="sxs-lookup"><span data-stu-id="66c83-149">Interfaces declared directly within a namespace can be declared as public or internal and, just like classes and structs, interfaces default to internal access.</span></span> <span data-ttu-id="66c83-150">接口成员始终为公共的，因为接口的用途是启用其他类型以访问类或结构。</span><span class="sxs-lookup"><span data-stu-id="66c83-150">Interface members are always public because the purpose of an interface is to enable other types to access a class or struct.</span></span> <span data-ttu-id="66c83-151">没有访问修饰符可以应用于接口成员。</span><span class="sxs-lookup"><span data-stu-id="66c83-151">No access modifiers can be applied to interface members.</span></span>  
  
 <span data-ttu-id="66c83-152">枚举成员始终为公共的，并且不应用任何访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="66c83-152">Enumeration members are always public, and no access modifiers can be applied.</span></span>  
  
 <span data-ttu-id="66c83-153">委托类似于类和结构。</span><span class="sxs-lookup"><span data-stu-id="66c83-153">Delegates behave like classes and structs.</span></span> <span data-ttu-id="66c83-154">默认情况下，当在命名空间内直接声明它们时，它们具有内部访问，当将它们嵌套在命名空间内时，它们具有私有访问。</span><span class="sxs-lookup"><span data-stu-id="66c83-154">By default, they have internal access when declared directly within a namespace, and private access when nested.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="66c83-155">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="66c83-155">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66c83-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="66c83-156">See Also</span></span>  
 <span data-ttu-id="66c83-157">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="66c83-157">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="66c83-158">[类和结构](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="66c83-158">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="66c83-159">[接口](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="66c83-159">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 <span data-ttu-id="66c83-160">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="66c83-160">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="66c83-161">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="66c83-161">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="66c83-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="66c83-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="66c83-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="66c83-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 <span data-ttu-id="66c83-164">[类](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="66c83-164">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="66c83-165">[结构](../../../csharp/language-reference/keywords/struct.md) </span><span class="sxs-lookup"><span data-stu-id="66c83-165">[struct](../../../csharp/language-reference/keywords/struct.md) </span></span>  
 [<span data-ttu-id="66c83-166">接口</span><span class="sxs-lookup"><span data-stu-id="66c83-166">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)

