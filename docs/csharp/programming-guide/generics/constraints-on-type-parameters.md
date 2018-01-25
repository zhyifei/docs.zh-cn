---
title: "类型参数的约束（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.assetid: 141b003e-1ddb-4e1c-bcb2-e1c3870e6a51
caps.latest.revision: "41"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6f7c80acdb3815af4b5d545297894778029a9104
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2018
---
# <a name="constraints-on-type-parameters-c-programming-guide"></a><span data-ttu-id="669f6-102">类型参数的约束（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="669f6-102">Constraints on Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="669f6-103">定义泛型类时，可以对客户端代码能够在实例化类时用于类型参数的几种类型施加限制。</span><span class="sxs-lookup"><span data-stu-id="669f6-103">When you define a generic class, you can apply restrictions to the kinds of types that client code can use for type arguments when it instantiates your class.</span></span> <span data-ttu-id="669f6-104">如果客户端代码尝试使用约束所不允许的类型来实例化类，则会产生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="669f6-104">If client code tries to instantiate your class by using a type that is not allowed by a constraint, the result is a compile-time error.</span></span> <span data-ttu-id="669f6-105">这些限制称为约束。</span><span class="sxs-lookup"><span data-stu-id="669f6-105">These restrictions are called constraints.</span></span> <span data-ttu-id="669f6-106">通过使用 `where` 上下文关键字指定约束。</span><span class="sxs-lookup"><span data-stu-id="669f6-106">Constraints are specified by using the `where` contextual keyword.</span></span> <span data-ttu-id="669f6-107">下表列出了六种类型的约束：</span><span class="sxs-lookup"><span data-stu-id="669f6-107">The following table lists the six types of constraints:</span></span>  
  
|<span data-ttu-id="669f6-108">约束</span><span class="sxs-lookup"><span data-stu-id="669f6-108">Constraint</span></span>|<span data-ttu-id="669f6-109">描述</span><span class="sxs-lookup"><span data-stu-id="669f6-109">Description</span></span>|  
|----------------|-----------------|  
|`where T: struct`|<span data-ttu-id="669f6-110">类型参数必须是值类型。</span><span class="sxs-lookup"><span data-stu-id="669f6-110">The type argument must be a value type.</span></span> <span data-ttu-id="669f6-111">可以指定除 <xref:System.Nullable> 以外的任何值类型。</span><span class="sxs-lookup"><span data-stu-id="669f6-111">Any value type except <xref:System.Nullable> can be specified.</span></span> <span data-ttu-id="669f6-112">有关详细信息，请参阅[使用可以为 null 的类型](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)。</span><span class="sxs-lookup"><span data-stu-id="669f6-112">See [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md) for more information.</span></span>|  
|`where T : class`|<span data-ttu-id="669f6-113">类型参数必须是引用类型；这同样适用于所有类、接口、委托或数组类型。</span><span class="sxs-lookup"><span data-stu-id="669f6-113">The type argument must be a reference type; this applies also to any class, interface, delegate, or array type.</span></span>|  
|`where T : new()`|<span data-ttu-id="669f6-114">类型参数必须具有公共无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="669f6-114">The type argument must have a public parameterless constructor.</span></span> <span data-ttu-id="669f6-115">与其他约束一起使用时，`new()` 约束必须最后指定。</span><span class="sxs-lookup"><span data-stu-id="669f6-115">When used together with other constraints, the `new()` constraint must be specified last.</span></span>|  
|<span data-ttu-id="669f6-116">`where T : `*\<基类名>*</span><span class="sxs-lookup"><span data-stu-id="669f6-116">`where T : `*\<base class name>*</span></span>|<span data-ttu-id="669f6-117">类型参数必须是指定的基类或派生自指定的基类。</span><span class="sxs-lookup"><span data-stu-id="669f6-117">The type argument must be or derive from the specified base class.</span></span>|  
|<span data-ttu-id="669f6-118">`where T : `*\<接口名称>*</span><span class="sxs-lookup"><span data-stu-id="669f6-118">`where T : `*\<interface name>*</span></span>|<span data-ttu-id="669f6-119">类型参数必须是指定的接口或实现指定的接口。</span><span class="sxs-lookup"><span data-stu-id="669f6-119">The type argument must be or implement the specified interface.</span></span> <span data-ttu-id="669f6-120">可指定多个接口约束。</span><span class="sxs-lookup"><span data-stu-id="669f6-120">Multiple interface constraints can be specified.</span></span> <span data-ttu-id="669f6-121">约束接口也可以是泛型。</span><span class="sxs-lookup"><span data-stu-id="669f6-121">The constraining interface can also be generic.</span></span>|  
|`where T : U`|<span data-ttu-id="669f6-122">为 T 提供的类型参数必须是为 U 提供的参数或派生自为 U 提供的参数。</span><span class="sxs-lookup"><span data-stu-id="669f6-122">The type argument supplied for T must be or derive from the argument supplied for U.</span></span>|  
  
## <a name="why-use-constraints"></a><span data-ttu-id="669f6-123">使用约束的原因</span><span class="sxs-lookup"><span data-stu-id="669f6-123">Why Use Constraints</span></span>  
 <span data-ttu-id="669f6-124">如果要检查泛型列表中的某个项，确定它是否有效，或者将它与其他某个项进行比较，则编译器必须保证它需要调用的运算符或方法将受到客户端代码可能指定的任何类型参数的支持。</span><span class="sxs-lookup"><span data-stu-id="669f6-124">If you want to examine an item in a generic list to determine whether it is valid or to compare it to some other item, the compiler must have some guarantee that the operator or method it has to call will be supported by any type argument that might be specified by client code.</span></span> <span data-ttu-id="669f6-125">通过对泛型类定义应用一个或多个约束获得这种保证。</span><span class="sxs-lookup"><span data-stu-id="669f6-125">This guarantee is obtained by applying one or more constraints to your generic class definition.</span></span> <span data-ttu-id="669f6-126">例如，基类约束告诉编译器，仅此类型的对象或派生自此类型的对象可用作类型参数。</span><span class="sxs-lookup"><span data-stu-id="669f6-126">For example, the base class constraint tells the compiler that only objects of this type or derived from this type will be used as type arguments.</span></span> <span data-ttu-id="669f6-127">编译器有了此保证后，就能够允许在泛型类中调用该类型的方法。</span><span class="sxs-lookup"><span data-stu-id="669f6-127">Once the compiler has this guarantee, it can allow methods of that type to be called in the generic class.</span></span> <span data-ttu-id="669f6-128">通过使用 `where` 上下文关键字应用约束。</span><span class="sxs-lookup"><span data-stu-id="669f6-128">Constraints are applied by using the contextual keyword `where`.</span></span> <span data-ttu-id="669f6-129">以下代码示例演示可通过应用基类约束添加到（[泛型介绍](../../../csharp/programming-guide/generics/introduction-to-generics.md)中的）`GenericList<T>` 类的功能。</span><span class="sxs-lookup"><span data-stu-id="669f6-129">The following code example demonstrates the functionality we can add to the `GenericList<T>` class (in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md)) by applying a base class constraint.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#11](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_1.cs)]  
  
 <span data-ttu-id="669f6-130">约束使得泛型类能够使用 `Employee.Name` 属性，因为类型 T 的所有项都保证是 `Employee` 对象或是从 `Employee` 继承的对象。</span><span class="sxs-lookup"><span data-stu-id="669f6-130">The constraint enables the generic class to use the `Employee.Name` property because all items of type T are guaranteed to be either an `Employee` object or an object that inherits from `Employee`.</span></span>  
  
 <span data-ttu-id="669f6-131">可以对同一类型参数应用多个约束，并且约束自身可以是泛型类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="669f6-131">Multiple constraints can be applied to the same type parameter, and the constraints themselves can be generic types, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#12](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_2.cs)]  
  
 <span data-ttu-id="669f6-132">通过约束类型参数，可以增加约束类型及其继承层次结构中的所有类型所支持的允许操作和方法调用的数量。</span><span class="sxs-lookup"><span data-stu-id="669f6-132">By constraining the type parameter, you increase the number of allowable operations and method calls to those supported by the constraining type and all types in its inheritance hierarchy.</span></span> <span data-ttu-id="669f6-133">因此，在设计泛型类或方法时，如果要对泛型成员执行除简单赋值之外的任何操作或调用 `System.Object` 不支持的任何方法，则必须对该类型参数应用约束。</span><span class="sxs-lookup"><span data-stu-id="669f6-133">Therefore, when you design generic classes or methods, if you will be performing any operation on the generic members beyond simple assignment or calling any methods not supported by `System.Object`, you will have to apply constraints to the type parameter.</span></span>  
  
 <span data-ttu-id="669f6-134">在应用 `where T : class` 约束时，请避免对类型参数使用 `==` 和 `!=` 运算符，因为这些运算符仅测试引用标识而不测试值相等性。</span><span class="sxs-lookup"><span data-stu-id="669f6-134">When applying the `where T : class` constraint, avoid the `==` and `!=` operators on the type parameter because these operators will test for reference identity only, not for value equality.</span></span> <span data-ttu-id="669f6-135">即使在用作参数的类型中重载这些运算符也是如此。</span><span class="sxs-lookup"><span data-stu-id="669f6-135">This is the case even if these operators are overloaded in a type that is used as an argument.</span></span> <span data-ttu-id="669f6-136">下面的代码说明了这一点；即使 <xref:System.String> 类重载 `==` 运算符，输出也为 false。</span><span class="sxs-lookup"><span data-stu-id="669f6-136">The following code illustrates this point; the output is false even though the <xref:System.String> class overloads the `==` operator.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#13](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_3.cs)]  
  
 <span data-ttu-id="669f6-137">出现这种情况是因为，编译器在编译时仅知道 T 是引用类型，因此必须使用对所有引用类型都有效的默认运算符。</span><span class="sxs-lookup"><span data-stu-id="669f6-137">The reason for this behavior is that, at compile time, the compiler only knows that T is a reference type, and therefore must use the default operators that are valid for all reference types.</span></span> <span data-ttu-id="669f6-138">如果必须测试值相等性，建议的方法是同时应用 `where T : IComparable<T>` 约束，并在将用于构造泛型类的任何类中实现该接口。</span><span class="sxs-lookup"><span data-stu-id="669f6-138">If you must test for value equality, the recommended way is to also apply the `where T : IComparable<T>` constraint and implement that interface in any class that will be used to construct the generic class.</span></span>  
  
## <a name="constraining-multiple-parameters"></a><span data-ttu-id="669f6-139">约束多个参数</span><span class="sxs-lookup"><span data-stu-id="669f6-139">Constraining Multiple Parameters</span></span>  
 <span data-ttu-id="669f6-140">可以对多个参数应用多个约束，对一个参数应用多个约束，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="669f6-140">You can apply constraints to multiple parameters, and multiple constraints to a single parameter, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#64](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_4.cs)]  
  
## <a name="unbounded-type-parameters"></a><span data-ttu-id="669f6-141">未绑定的类型参数</span><span class="sxs-lookup"><span data-stu-id="669f6-141">Unbounded Type Parameters</span></span>  
 <span data-ttu-id="669f6-142">没有约束的类型参数（如公共类 `SampleClass<T>{}` 中的 T）称为未绑定的类型参数。</span><span class="sxs-lookup"><span data-stu-id="669f6-142">Type parameters that have no constraints, such as T in public class `SampleClass<T>{}`, are called unbounded type parameters.</span></span> <span data-ttu-id="669f6-143">未绑定的类型参数具有以下规则：</span><span class="sxs-lookup"><span data-stu-id="669f6-143">Unbounded type parameters have the following rules:</span></span>  
  
-   <span data-ttu-id="669f6-144">不能使用 `!=` 和 `==` 运算符，因为无法保证具体的类型参数能支持这些运算符。</span><span class="sxs-lookup"><span data-stu-id="669f6-144">The `!=` and `==` operators cannot be used because there is no guarantee that the concrete type argument will support these operators.</span></span>  
  
-   <span data-ttu-id="669f6-145">可以在它们与 `System.Object` 之间来回转换，或将它们显式转换为任何接口类型。</span><span class="sxs-lookup"><span data-stu-id="669f6-145">They can be converted to and from `System.Object` or explicitly converted to any interface type.</span></span>  
  
-   <span data-ttu-id="669f6-146">可以将它们与 [null](../../../csharp/language-reference/keywords/null.md) 进行比较。</span><span class="sxs-lookup"><span data-stu-id="669f6-146">You can compare to [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="669f6-147">将未绑定的参数与 `null` 进行比较时，如果类型参数为值类型，则该比较将始终返回 false。</span><span class="sxs-lookup"><span data-stu-id="669f6-147">If an unbounded parameter is compared to `null`, the comparison will always return false if the type argument is a value type.</span></span>  
  
## <a name="type-parameters-as-constraints"></a><span data-ttu-id="669f6-148">类型参数作为约束</span><span class="sxs-lookup"><span data-stu-id="669f6-148">Type Parameters as Constraints</span></span>  
 <span data-ttu-id="669f6-149">在具有自己类型参数的成员函数必须将该参数约束为包含类型的类型参数时，将泛型类型参数用作约束非常有用，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="669f6-149">The use of a generic type parameter as a constraint is useful when a member function with its own type parameter has to constrain that parameter to the type parameter of the containing type, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#14](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_5.cs)]  
  
 <span data-ttu-id="669f6-150">在上述示例中，`T` 在 `Add` 方法的上下文中是一个类型约束，而在 `List` 类的上下文中是一个未绑定的类型参数。</span><span class="sxs-lookup"><span data-stu-id="669f6-150">In the previous example, `T` is a type constraint in the context of the `Add` method, and an unbounded type parameter in the context of the `List` class.</span></span>  
  
 <span data-ttu-id="669f6-151">类型参数还可在泛型类定义中用作约束。</span><span class="sxs-lookup"><span data-stu-id="669f6-151">Type parameters can also be used as constraints in generic class definitions.</span></span> <span data-ttu-id="669f6-152">请注意，必须在尖括号中声明此类型参数以及任何其他类型参数：</span><span class="sxs-lookup"><span data-stu-id="669f6-152">Note that the type parameter must be declared within the angle brackets together with any other type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#15](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_6.cs)]  
  
 <span data-ttu-id="669f6-153">类型参数作为泛型类的约束的作用非常有限，因为编译器除了假设类型参数派生自 `System.Object` 以外，不会做其他任何假设。</span><span class="sxs-lookup"><span data-stu-id="669f6-153">The usefulness of type parameters as constraints with generic classes is very limited because the compiler can assume nothing about the type parameter except that it derives from `System.Object`.</span></span> <span data-ttu-id="669f6-154">如果要在两个类型参数之间强制继承关系，可以将类型参数用作泛型类的约束。</span><span class="sxs-lookup"><span data-stu-id="669f6-154">Use type parameters as constraints on generic classes in scenarios in which you want to enforce an inheritance relationship between two type parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="669f6-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="669f6-155">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="669f6-156">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="669f6-156">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="669f6-157">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="669f6-157">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="669f6-158">泛型类</span><span class="sxs-lookup"><span data-stu-id="669f6-158">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
 [<span data-ttu-id="669f6-159">new 约束</span><span class="sxs-lookup"><span data-stu-id="669f6-159">new Constraint</span></span>](../../../csharp/language-reference/keywords/new-constraint.md)
