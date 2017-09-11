---
title: "类型参数的约束（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.assetid: 141b003e-1ddb-4e1c-bcb2-e1c3870e6a51
caps.latest.revision: 41
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
ms.openlocfilehash: e91ae026bd89a6dd30b4c9233da4dd897928291e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="constraints-on-type-parameters-c-programming-guide"></a><span data-ttu-id="12a28-102">类型参数的约束（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="12a28-102">Constraints on Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="12a28-103">定义泛型类时，可以对客户端代码能够在实例化类时用于类型参数的几种类型施加限制。</span><span class="sxs-lookup"><span data-stu-id="12a28-103">When you define a generic class, you can apply restrictions to the kinds of types that client code can use for type arguments when it instantiates your class.</span></span> <span data-ttu-id="12a28-104">如果客户端代码尝试使用约束所不允许的类型来实例化类，则会产生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="12a28-104">If client code tries to instantiate your class by using a type that is not allowed by a constraint, the result is a compile-time error.</span></span> <span data-ttu-id="12a28-105">这些限制称为约束。</span><span class="sxs-lookup"><span data-stu-id="12a28-105">These restrictions are called constraints.</span></span> <span data-ttu-id="12a28-106">通过使用 `where` 上下文关键字指定约束。</span><span class="sxs-lookup"><span data-stu-id="12a28-106">Constraints are specified by using the `where` contextual keyword.</span></span> <span data-ttu-id="12a28-107">下表列出了六种类型的约束：</span><span class="sxs-lookup"><span data-stu-id="12a28-107">The following table lists the six types of constraints:</span></span>  
  
|<span data-ttu-id="12a28-108">约束</span><span class="sxs-lookup"><span data-stu-id="12a28-108">Constraint</span></span>|<span data-ttu-id="12a28-109">描述</span><span class="sxs-lookup"><span data-stu-id="12a28-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="12a28-110">where T：结构</span><span class="sxs-lookup"><span data-stu-id="12a28-110">where T: struct</span></span>|<span data-ttu-id="12a28-111">类型参数必须是值类型。</span><span class="sxs-lookup"><span data-stu-id="12a28-111">The type argument must be a value type.</span></span> <span data-ttu-id="12a28-112">可以指定除 <xref:System.Nullable> 以外的任何值类型。</span><span class="sxs-lookup"><span data-stu-id="12a28-112">Any value type except <xref:System.Nullable> can be specified.</span></span> <span data-ttu-id="12a28-113">有关详细信息，请参阅[使用可以为 null 的类型](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)。</span><span class="sxs-lookup"><span data-stu-id="12a28-113">See [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md) for more information.</span></span>|  
|<span data-ttu-id="12a28-114">where T：类</span><span class="sxs-lookup"><span data-stu-id="12a28-114">where T : class</span></span>|<span data-ttu-id="12a28-115">类型参数必须是引用类型；这同样适用于所有类、接口、委托或数组类型。</span><span class="sxs-lookup"><span data-stu-id="12a28-115">The type argument must be a reference type; this applies also to any class, interface, delegate, or array type.</span></span>|  
|<span data-ttu-id="12a28-116">where T：new()</span><span class="sxs-lookup"><span data-stu-id="12a28-116">where T : new()</span></span>|<span data-ttu-id="12a28-117">类型参数必须具有公共无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="12a28-117">The type argument must have a public parameterless constructor.</span></span> <span data-ttu-id="12a28-118">与其他约束一起使用时，`new()` 约束必须最后指定。</span><span class="sxs-lookup"><span data-stu-id="12a28-118">When used together with other constraints, the `new()` constraint must be specified last.</span></span>|  
|<span data-ttu-id="12a28-119">where T：\<基类名称></span><span class="sxs-lookup"><span data-stu-id="12a28-119">where T : \<base class name></span></span>|<span data-ttu-id="12a28-120">类型参数必须是指定的基类或派生自指定的基类。</span><span class="sxs-lookup"><span data-stu-id="12a28-120">The type argument must be or derive from the specified base class.</span></span>|  
|<span data-ttu-id="12a28-121">where T：\<接口名称></span><span class="sxs-lookup"><span data-stu-id="12a28-121">where T : \<interface name></span></span>|<span data-ttu-id="12a28-122">类型参数必须是指定的接口或实现指定的接口。</span><span class="sxs-lookup"><span data-stu-id="12a28-122">The type argument must be or implement the specified interface.</span></span> <span data-ttu-id="12a28-123">可指定多个接口约束。</span><span class="sxs-lookup"><span data-stu-id="12a28-123">Multiple interface constraints can be specified.</span></span> <span data-ttu-id="12a28-124">约束接口也可以是泛型。</span><span class="sxs-lookup"><span data-stu-id="12a28-124">The constraining interface can also be generic.</span></span>|  
|<span data-ttu-id="12a28-125">where T：U</span><span class="sxs-lookup"><span data-stu-id="12a28-125">where T : U</span></span>|<span data-ttu-id="12a28-126">为 T 提供的类型参数必须是为 U 提供的参数或派生自为 U 提供的参数。</span><span class="sxs-lookup"><span data-stu-id="12a28-126">The type argument supplied for T must be or derive from the argument supplied for U.</span></span>|  
  
## <a name="why-use-constraints"></a><span data-ttu-id="12a28-127">使用约束的原因</span><span class="sxs-lookup"><span data-stu-id="12a28-127">Why Use Constraints</span></span>  
 <span data-ttu-id="12a28-128">如果要检查泛型列表中的某个项，确定它是否有效，或者将它与其他某个项进行比较，则编译器必须保证它需要调用的运算符或方法将受到客户端代码可能指定的任何类型参数的支持。</span><span class="sxs-lookup"><span data-stu-id="12a28-128">If you want to examine an item in a generic list to determine whether it is valid or to compare it to some other item, the compiler must have some guarantee that the operator or method it has to call will be supported by any type argument that might be specified by client code.</span></span> <span data-ttu-id="12a28-129">通过对泛型类定义应用一个或多个约束获得这种保证。</span><span class="sxs-lookup"><span data-stu-id="12a28-129">This guarantee is obtained by applying one or more constraints to your generic class definition.</span></span> <span data-ttu-id="12a28-130">例如，基类约束告诉编译器，仅此类型的对象或派生自此类型的对象可用作类型参数。</span><span class="sxs-lookup"><span data-stu-id="12a28-130">For example, the base class constraint tells the compiler that only objects of this type or derived from this type will be used as type arguments.</span></span> <span data-ttu-id="12a28-131">编译器有了此保证后，就能够允许在泛型类中调用该类型的方法。</span><span class="sxs-lookup"><span data-stu-id="12a28-131">Once the compiler has this guarantee, it can allow methods of that type to be called in the generic class.</span></span> <span data-ttu-id="12a28-132">通过使用 `where` 上下文关键字应用约束。</span><span class="sxs-lookup"><span data-stu-id="12a28-132">Constraints are applied by using the contextual keyword `where`.</span></span> <span data-ttu-id="12a28-133">以下代码示例演示可通过应用基类约束添加到（[泛型介绍](../../../csharp/programming-guide/generics/introduction-to-generics.md)中的）`GenericList<T>` 类的功能。</span><span class="sxs-lookup"><span data-stu-id="12a28-133">The following code example demonstrates the functionality we can add to the `GenericList<T>` class (in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md)) by applying a base class constraint.</span></span>  
  
 <span data-ttu-id="12a28-134">[!code-cs[csProgGuideGenerics#11](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="12a28-134">[!code-cs[csProgGuideGenerics#11](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="12a28-135">约束使得泛型类能够使用 `Employee.Name` 属性，因为类型 T 的所有项都保证是 `Employee` 对象或是从 `Employee` 继承的对象。</span><span class="sxs-lookup"><span data-stu-id="12a28-135">The constraint enables the generic class to use the `Employee.Name` property because all items of type T are guaranteed to be either an `Employee` object or an object that inherits from `Employee`.</span></span>  
  
 <span data-ttu-id="12a28-136">可以对同一类型参数应用多个约束，并且约束自身可以是泛型类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="12a28-136">Multiple constraints can be applied to the same type parameter, and the constraints themselves can be generic types, as follows:</span></span>  
  
 <span data-ttu-id="12a28-137">[!code-cs[csProgGuideGenerics#12](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="12a28-137">[!code-cs[csProgGuideGenerics#12](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_2.cs)]</span></span>  
  
 <span data-ttu-id="12a28-138">通过约束类型参数，可以增加约束类型及其继承层次结构中的所有类型所支持的允许操作和方法调用的数量。</span><span class="sxs-lookup"><span data-stu-id="12a28-138">By constraining the type parameter, you increase the number of allowable operations and method calls to those supported by the constraining type and all types in its inheritance hierarchy.</span></span> <span data-ttu-id="12a28-139">因此，在设计泛型类或方法时，如果要对泛型成员执行除简单赋值之外的任何操作或调用 `System.Object` 不支持的任何方法，则必须对该类型参数应用约束。</span><span class="sxs-lookup"><span data-stu-id="12a28-139">Therefore, when you design generic classes or methods, if you will be performing any operation on the generic members beyond simple assignment or calling any methods not supported by `System.Object`, you will have to apply constraints to the type parameter.</span></span>  
  
 <span data-ttu-id="12a28-140">在应用 `where T : class` 约束时，请避免对类型参数使用 `==` 和 `!=` 运算符，因为这些运算符仅测试引用标识而不测试值相等性。</span><span class="sxs-lookup"><span data-stu-id="12a28-140">When applying the `where T : class` constraint, avoid the `==` and `!=` operators on the type parameter because these operators will test for reference identity only, not for value equality.</span></span> <span data-ttu-id="12a28-141">即使在用作参数的类型中重载这些运算符也是如此。</span><span class="sxs-lookup"><span data-stu-id="12a28-141">This is the case even if these operators are overloaded in a type that is used as an argument.</span></span> <span data-ttu-id="12a28-142">下面的代码说明了这一点；即使 <xref:System.String> 类重载 `==` 运算符，输出也为 false。</span><span class="sxs-lookup"><span data-stu-id="12a28-142">The following code illustrates this point; the output is false even though the <xref:System.String> class overloads the `==` operator.</span></span>  
  
 <span data-ttu-id="12a28-143">[!code-cs[csProgGuideGenerics#13](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="12a28-143">[!code-cs[csProgGuideGenerics#13](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_3.cs)]</span></span>  
  
 <span data-ttu-id="12a28-144">出现这种情况是因为，编译器在编译时仅知道 T 是引用类型，因此必须使用对所有引用类型都有效的默认运算符。</span><span class="sxs-lookup"><span data-stu-id="12a28-144">The reason for this behavior is that, at compile time, the compiler only knows that T is a reference type, and therefore must use the default operators that are valid for all reference types.</span></span> <span data-ttu-id="12a28-145">如果必须测试值相等性，建议的方法是同时应用 `where T : IComparable<T>` 约束，并在将用于构造泛型类的任何类中实现该接口。</span><span class="sxs-lookup"><span data-stu-id="12a28-145">If you must test for value equality, the recommended way is to also apply the `where T : IComparable<T>` constraint and implement that interface in any class that will be used to construct the generic class.</span></span>  
  
## <a name="constraining-multiple-parameters"></a><span data-ttu-id="12a28-146">约束多个参数</span><span class="sxs-lookup"><span data-stu-id="12a28-146">Constraining Multiple Parameters</span></span>  
 <span data-ttu-id="12a28-147">可以对多个参数应用多个约束，对一个参数应用多个约束，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="12a28-147">You can apply constraints to multiple parameters, and multiple constraints to a single parameter, as shown in the following example:</span></span>  
  
 <span data-ttu-id="12a28-148">[!code-cs[csProgGuideGenerics#64](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="12a28-148">[!code-cs[csProgGuideGenerics#64](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_4.cs)]</span></span>  
  
## <a name="unbounded-type-parameters"></a><span data-ttu-id="12a28-149">未绑定的类型参数</span><span class="sxs-lookup"><span data-stu-id="12a28-149">Unbounded Type Parameters</span></span>  
 <span data-ttu-id="12a28-150">没有约束的类型参数（如公共类 `SampleClass<T>{}` 中的 T）称为未绑定的类型参数。</span><span class="sxs-lookup"><span data-stu-id="12a28-150">Type parameters that have no constraints, such as T in public class `SampleClass<T>{}`, are called unbounded type parameters.</span></span> <span data-ttu-id="12a28-151">未绑定的类型参数具有以下规则：</span><span class="sxs-lookup"><span data-stu-id="12a28-151">Unbounded type parameters have the following rules:</span></span>  
  
-   <span data-ttu-id="12a28-152">不能使用 `!=` 和 `==` 运算符，因为无法保证具体的类型参数能支持这些运算符。</span><span class="sxs-lookup"><span data-stu-id="12a28-152">The `!=` and `==` operators cannot be used because there is no guarantee that the concrete type argument will support these operators.</span></span>  
  
-   <span data-ttu-id="12a28-153">可以在它们与 `System.Object` 之间来回转换，或将它们显式转换为任何接口类型。</span><span class="sxs-lookup"><span data-stu-id="12a28-153">They can be converted to and from `System.Object` or explicitly converted to any interface type.</span></span>  
  
-   <span data-ttu-id="12a28-154">可以将它们与 [null](../../../csharp/language-reference/keywords/null.md) 进行比较。</span><span class="sxs-lookup"><span data-stu-id="12a28-154">You can compare to [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="12a28-155">将未绑定的参数与 `null` 进行比较时，如果类型参数为值类型，则该比较将始终返回 false。</span><span class="sxs-lookup"><span data-stu-id="12a28-155">If an unbounded parameter is compared to `null`, the comparison will always return false if the type argument is a value type.</span></span>  
  
## <a name="type-parameters-as-constraints"></a><span data-ttu-id="12a28-156">类型参数作为约束</span><span class="sxs-lookup"><span data-stu-id="12a28-156">Type Parameters as Constraints</span></span>  
 <span data-ttu-id="12a28-157">在具有自己类型参数的成员函数必须将该参数约束为包含类型的类型参数时，将泛型类型参数用作约束非常有用，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="12a28-157">The use of a generic type parameter as a constraint is useful when a member function with its own type parameter has to constrain that parameter to the type parameter of the containing type, as shown in the following example:</span></span>  
  
 <span data-ttu-id="12a28-158">[!code-cs[csProgGuideGenerics#14](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="12a28-158">[!code-cs[csProgGuideGenerics#14](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_5.cs)]</span></span>  
  
 <span data-ttu-id="12a28-159">在上述示例中，`T` 在 `Add` 方法的上下文中是一个类型约束，而在 `List` 类的上下文中是一个未绑定的类型参数。</span><span class="sxs-lookup"><span data-stu-id="12a28-159">In the previous example, `T` is a type constraint in the context of the `Add` method, and an unbounded type parameter in the context of the `List` class.</span></span>  
  
 <span data-ttu-id="12a28-160">类型参数还可在泛型类定义中用作约束。</span><span class="sxs-lookup"><span data-stu-id="12a28-160">Type parameters can also be used as constraints in generic class definitions.</span></span> <span data-ttu-id="12a28-161">请注意，必须在尖括号中声明此类型参数以及任何其他类型参数：</span><span class="sxs-lookup"><span data-stu-id="12a28-161">Note that the type parameter must be declared within the angle brackets together with any other type parameters:</span></span>  
  
 <span data-ttu-id="12a28-162">[!code-cs[csProgGuideGenerics#15](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="12a28-162">[!code-cs[csProgGuideGenerics#15](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_6.cs)]</span></span>  
  
 <span data-ttu-id="12a28-163">类型参数作为泛型类的约束的作用非常有限，因为编译器除了假设类型参数派生自 `System.Object` 以外，不会做其他任何假设。</span><span class="sxs-lookup"><span data-stu-id="12a28-163">The usefulness of type parameters as constraints with generic classes is very limited because the compiler can assume nothing about the type parameter except that it derives from `System.Object`.</span></span> <span data-ttu-id="12a28-164">如果要在两个类型参数之间强制继承关系，可以将类型参数用作泛型类的约束。</span><span class="sxs-lookup"><span data-stu-id="12a28-164">Use type parameters as constraints on generic classes in scenarios in which you want to enforce an inheritance relationship between two type parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12a28-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12a28-165">See Also</span></span>  
 <span data-ttu-id="12a28-166"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="12a28-166"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="12a28-167">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="12a28-167">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="12a28-168">[泛型简介](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="12a28-168">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="12a28-169">[泛型类](../../../csharp/programming-guide/generics/generic-classes.md) </span><span class="sxs-lookup"><span data-stu-id="12a28-169">[Generic Classes](../../../csharp/programming-guide/generics/generic-classes.md) </span></span>  
 [<span data-ttu-id="12a28-170">new 约束</span><span class="sxs-lookup"><span data-stu-id="12a28-170">new Constraint</span></span>](../../../csharp/language-reference/keywords/new-constraint.md)

