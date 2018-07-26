---
title: 访问修饰符（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
ms.openlocfilehash: ec275d4782fee047b16fd114c4d22ceb03eecb11
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199209"
---
# <a name="access-modifiers-c-programming-guide"></a><span data-ttu-id="426f8-102">访问修饰符（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="426f8-102">Access Modifiers (C# Programming Guide)</span></span>
<span data-ttu-id="426f8-103">所有类型和类型成员都具有可访问性级别，该级别可以控制是否可以从你的程序集或其他程序集中的其他代码中使用它们。</span><span class="sxs-lookup"><span data-stu-id="426f8-103">All types and type members have an accessibility level, which controls whether they can be used from other code in your assembly or other assemblies.</span></span> <span data-ttu-id="426f8-104">可以使用以下访问修饰符在进行声明时指定类型或成员的可访问性：</span><span class="sxs-lookup"><span data-stu-id="426f8-104">You can use the following access modifiers to specify the accessibility of a type or member when you declare it:</span></span>  
  
 [<span data-ttu-id="426f8-105">public</span><span class="sxs-lookup"><span data-stu-id="426f8-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 <span data-ttu-id="426f8-106">同一程序集中的任何其他代码或引用该程序集的其他程序集都可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="426f8-106">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span> 
  
 [<span data-ttu-id="426f8-107">private</span><span class="sxs-lookup"><span data-stu-id="426f8-107">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 <span data-ttu-id="426f8-108">只有同一类或结构中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="426f8-108">The type or member can be accessed only by code in the same class or struct.</span></span>  
  
 [<span data-ttu-id="426f8-109">protected</span><span class="sxs-lookup"><span data-stu-id="426f8-109">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 <span data-ttu-id="426f8-110">只有同一类或者从该类派生的类中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="426f8-110">The type or member can be accessed only by code in the same class, or in a class that is derived from that class.</span></span>  
 [<span data-ttu-id="426f8-111">internal</span><span class="sxs-lookup"><span data-stu-id="426f8-111">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="426f8-112">同一程序集中的任何代码都可以访问该类型或成员，但其他程序集中的代码不可以。</span><span class="sxs-lookup"><span data-stu-id="426f8-112">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>  
  
 <span data-ttu-id="426f8-113">[受保护的内部](../../../csharp/language-reference/keywords/protected-internal.md) 该类型或成员可由对其进行声明的程序集或另一程序集中的派生类中的任何代码访问。</span><span class="sxs-lookup"><span data-stu-id="426f8-113">[protected internal](../../../csharp/language-reference/keywords/protected-internal.md) The type or member can be accessed by any code in the assembly in which it is declared, or from within a derived class in another assembly.</span></span> 

 <span data-ttu-id="426f8-114">[专用受保护](../../../csharp/language-reference/keywords/private-protected.md)只有在其声明程序集内，通过相同类中的代码或派生自该类的类型，才能访问类型或成员。</span><span class="sxs-lookup"><span data-stu-id="426f8-114">[private protected](../../../csharp/language-reference/keywords/private-protected.md) The type or member can be accessed only within its declaring assembly, by code in the same class or in a type that is derived from that class.</span></span>
  
 <span data-ttu-id="426f8-115">下面的示例演示如何在类型和成员上指定访问修饰符：</span><span class="sxs-lookup"><span data-stu-id="426f8-115">The following examples demonstrate how to specify access modifiers on a type and member:</span></span>  
  
 [!code-csharp[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]  
  
 <span data-ttu-id="426f8-116">并非所有的访问修饰符都可以由所有上下文中的所有类型或成员使用，并且在某些情况下，类型成员的可访问性受其包含类型的可访问性限制。</span><span class="sxs-lookup"><span data-stu-id="426f8-116">Not all access modifiers can be used by all types or members in all contexts, and in some cases the accessibility of a type member is constrained by the accessibility of its containing type.</span></span> <span data-ttu-id="426f8-117">以下各节提供了有关可访问性的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="426f8-117">The following sections provide more details about accessibility.</span></span>  
  
## <a name="class-and-struct-accessibility"></a><span data-ttu-id="426f8-118">类和结构可访问性</span><span class="sxs-lookup"><span data-stu-id="426f8-118">Class and Struct Accessibility</span></span>  
 <span data-ttu-id="426f8-119">在命名空间内直接声明（换句话说，不嵌套在其他类或结构中）的类和结构可以为公共或内部。</span><span class="sxs-lookup"><span data-stu-id="426f8-119">Classes and structs that are declared directly within a namespace (in other words, that are not nested within other classes or structs) can be either public or internal.</span></span> <span data-ttu-id="426f8-120">如果未指定任何访问修饰符，则默认设置为内部。</span><span class="sxs-lookup"><span data-stu-id="426f8-120">Internal is the default if no access modifier is specified.</span></span>  
  
 <span data-ttu-id="426f8-121">结构成员（包括嵌套的类和结构）可以声明为公共、内部或私有。</span><span class="sxs-lookup"><span data-stu-id="426f8-121">Struct members, including nested classes and structs, can be declared as public, internal, or private.</span></span> <span data-ttu-id="426f8-122">类成员（包括嵌套的类和结构）可以为公共、受保护的内部、受保护、内部、专用受保护或专用。</span><span class="sxs-lookup"><span data-stu-id="426f8-122">Class members, including nested classes and structs, can be public, protected internal, protected, internal, private protected or private.</span></span> <span data-ttu-id="426f8-123">默认情况下，类成员和结构成员（包括嵌套的类和结构）的访问级别为私有。</span><span class="sxs-lookup"><span data-stu-id="426f8-123">The access level for class members and struct members, including nested classes and structs, is private by default.</span></span> <span data-ttu-id="426f8-124">不能从包含类型的外部访问私有嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="426f8-124">Private nested types are not accessible from outside the containing type.</span></span>  
  
 <span data-ttu-id="426f8-125">派生类不能具有高于其基类型的可访问性。</span><span class="sxs-lookup"><span data-stu-id="426f8-125">Derived classes cannot have greater accessibility than their base types.</span></span> <span data-ttu-id="426f8-126">换而言之，不能具有派生自内部类 `A` 的公共类 `B`。</span><span class="sxs-lookup"><span data-stu-id="426f8-126">In other words, you cannot have a public class `B` that derives from an internal class `A`.</span></span> <span data-ttu-id="426f8-127">如果允许这样，则它将具有使 `A` 公开的效果，因为可从派生类访问 `A` 的所有受保护的或内部成员。</span><span class="sxs-lookup"><span data-stu-id="426f8-127">If this were allowed, it would have the effect of making `A` public, because all protected or internal members of `A` are accessible from the derived class.</span></span>  
  
 <span data-ttu-id="426f8-128">可以通过使用 InternalsVisibleToAttribute 启用特定的其他程序集访问内部类型。</span><span class="sxs-lookup"><span data-stu-id="426f8-128">You can enable specific other assemblies to access your internal types by using the InternalsVisibleToAttribute.</span></span> <span data-ttu-id="426f8-129">有关详细信息，请参阅[友元程序集](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)。</span><span class="sxs-lookup"><span data-stu-id="426f8-129">For more information, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
## <a name="class-and-struct-member-accessibility"></a><span data-ttu-id="426f8-130">类和结构成员可访问性</span><span class="sxs-lookup"><span data-stu-id="426f8-130">Class and Struct Member Accessibility</span></span>  
 <span data-ttu-id="426f8-131">可以使用六种访问类型中的任意一种声明类成员（包括嵌套的类和结构）。</span><span class="sxs-lookup"><span data-stu-id="426f8-131">Class members (including nested classes and structs) can be declared with any of the six types of access.</span></span> <span data-ttu-id="426f8-132">结构成员无法声明为受保护，因为结构不支持继承。</span><span class="sxs-lookup"><span data-stu-id="426f8-132">Struct members cannot be declared as protected because structs do not support inheritance.</span></span>  
  
 <span data-ttu-id="426f8-133">通常情况下，成员的可访问性不大于包含该成员的类型的可访问性。</span><span class="sxs-lookup"><span data-stu-id="426f8-133">Normally, the accessibility of a member is not greater than the accessibility of the type that contains it.</span></span> <span data-ttu-id="426f8-134">但是，如果内部类的公共成员实现了接口方法或替代了在公共基类中定义的虚拟方法，则可从该程序集的外部访问该成员。</span><span class="sxs-lookup"><span data-stu-id="426f8-134">However, a public member of an internal class might be accessible from outside the assembly if the member implements interface methods or overrides virtual methods that are defined in a public base class.</span></span>  
  
 <span data-ttu-id="426f8-135">为字段、属性或事件的任何成员的类型必须至少与该成员本身具有相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="426f8-135">The type of any member that is a field, property, or event must be at least as accessible as the member itself.</span></span> <span data-ttu-id="426f8-136">同样，为方法、索引器或委托的任何成员的返回类型和参数类型必须至少与该成员本身具有相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="426f8-136">Similarly, the return type and the parameter types of any member that is a method, indexer, or delegate must be at least as accessible as the member itself.</span></span> <span data-ttu-id="426f8-137">例如，不能具有返回类 `C` 的公共方法 `M`，除非 `C` 也是公共的。</span><span class="sxs-lookup"><span data-stu-id="426f8-137">For example, you cannot have a public method `M` that returns a class `C` unless `C` is also public.</span></span> <span data-ttu-id="426f8-138">同样，如果 `A` 声明为私有，则不能具有类型 `A` 的受保护的属性。</span><span class="sxs-lookup"><span data-stu-id="426f8-138">Likewise, you cannot have a protected property of type `A` if `A` is declared as private.</span></span>  
  
 <span data-ttu-id="426f8-139">用户定义的运算符始终必须声明为公共。</span><span class="sxs-lookup"><span data-stu-id="426f8-139">User-defined operators must always be declared as public.</span></span> <span data-ttu-id="426f8-140">有关详细信息，请参阅[运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="426f8-140">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
 <span data-ttu-id="426f8-141">终结器不能具有可访问性修饰符。</span><span class="sxs-lookup"><span data-stu-id="426f8-141">Finalizers cannot have accessibility modifiers.</span></span>  
  
 <span data-ttu-id="426f8-142">若要设置类或结构成员的访问级别，向成员声明添加适当的关键字，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="426f8-142">To set the access level for a class or struct member, add the appropriate keyword to the member declaration, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="426f8-143">受保护的内部可访问性级别意味着受保护或内部，而非受保护和内部。</span><span class="sxs-lookup"><span data-stu-id="426f8-143">The protected internal accessibility level means protected OR internal, not protected AND internal.</span></span> <span data-ttu-id="426f8-144">换而言之，可以从同一程序集中的任何类（包括派生类）访问受保护的内部成员。</span><span class="sxs-lookup"><span data-stu-id="426f8-144">In other words, a protected internal member can be accessed from any class in the same assembly, including derived classes.</span></span> <span data-ttu-id="426f8-145">若要将同一程序集中的可访问性限制为仅派生类，请声明类本身为内部，并声明其成员为受保护。</span><span class="sxs-lookup"><span data-stu-id="426f8-145">To limit accessibility to only derived classes in the same assembly, declare the class itself internal, and declare its members as protected.</span></span> <span data-ttu-id="426f8-146">此外，从 C# 7.2 开始，可以使用专用受保护的访问修饰符实现相同的效果，而无需使包含的类属于内部。</span><span class="sxs-lookup"><span data-stu-id="426f8-146">Also, starting with C# 7.2, you can use the private protected access modifier to achieve the same result without need to make the containing class internal.</span></span>  
  
## <a name="other-types"></a><span data-ttu-id="426f8-147">其他类型</span><span class="sxs-lookup"><span data-stu-id="426f8-147">Other Types</span></span>  
 <span data-ttu-id="426f8-148">在命名空间内直接声明的接口可以声明为公共或内部，就像类和结构一样，接口默认设置为内部访问。</span><span class="sxs-lookup"><span data-stu-id="426f8-148">Interfaces declared directly within a namespace can be declared as public or internal and, just like classes and structs, interfaces default to internal access.</span></span> <span data-ttu-id="426f8-149">接口成员始终为公共的，因为接口的用途是启用其他类型以访问类或结构。</span><span class="sxs-lookup"><span data-stu-id="426f8-149">Interface members are always public because the purpose of an interface is to enable other types to access a class or struct.</span></span> <span data-ttu-id="426f8-150">没有访问修饰符可以应用于接口成员。</span><span class="sxs-lookup"><span data-stu-id="426f8-150">No access modifiers can be applied to interface members.</span></span>  
  
 <span data-ttu-id="426f8-151">枚举成员始终为公共的，并且不应用任何访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="426f8-151">Enumeration members are always public, and no access modifiers can be applied.</span></span>  
  
 <span data-ttu-id="426f8-152">委托类似于类和结构。</span><span class="sxs-lookup"><span data-stu-id="426f8-152">Delegates behave like classes and structs.</span></span> <span data-ttu-id="426f8-153">默认情况下，当在命名空间内直接声明它们时，它们具有内部访问，当将它们嵌套在命名空间内时，它们具有私有访问。</span><span class="sxs-lookup"><span data-stu-id="426f8-153">By default, they have internal access when declared directly within a namespace, and private access when nested.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="426f8-154">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="426f8-154">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="426f8-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="426f8-155">See Also</span></span>  
 [<span data-ttu-id="426f8-156">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="426f8-156">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="426f8-157">类和结构</span><span class="sxs-lookup"><span data-stu-id="426f8-157">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="426f8-158">接口</span><span class="sxs-lookup"><span data-stu-id="426f8-158">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="426f8-159">private</span><span class="sxs-lookup"><span data-stu-id="426f8-159">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="426f8-160">public</span><span class="sxs-lookup"><span data-stu-id="426f8-160">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="426f8-161">internal</span><span class="sxs-lookup"><span data-stu-id="426f8-161">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 [<span data-ttu-id="426f8-162">protected</span><span class="sxs-lookup"><span data-stu-id="426f8-162">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="426f8-163">受保护的内部</span><span class="sxs-lookup"><span data-stu-id="426f8-163">protected internal</span></span>](../../../csharp/language-reference/keywords/protected-internal.md)  
 [<span data-ttu-id="426f8-164">专用受保护</span><span class="sxs-lookup"><span data-stu-id="426f8-164">private protected</span></span>](../../../csharp/language-reference/keywords/private-protected.md)  
 [<span data-ttu-id="426f8-165">class</span><span class="sxs-lookup"><span data-stu-id="426f8-165">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="426f8-166">struct</span><span class="sxs-lookup"><span data-stu-id="426f8-166">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
 [<span data-ttu-id="426f8-167">interface</span><span class="sxs-lookup"><span data-stu-id="426f8-167">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)
