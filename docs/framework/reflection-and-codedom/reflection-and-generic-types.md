---
title: 反射类型和泛型类型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- reflection emit, generic types
- reflection, generic types
- type arguments
- generics [.NET Framework], reflection
- viewing type information
- type information, viewing
- types, generic
- type parameters
ms.assetid: f7180fc5-dd41-42d4-8a8e-1b34288e06de
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a45ef91eba38223270a04cff2f00c30decb019f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399699"
---
# <a name="reflection-and-generic-types"></a><span data-ttu-id="a41d2-102">反射类型和泛型类型</span><span class="sxs-lookup"><span data-stu-id="a41d2-102">Reflection and Generic Types</span></span>
<a name="top"></a> <span data-ttu-id="a41d2-103">从反射的角度来说，泛型类型和普通类型之间的区别在于泛型类型具有与之关联的一组类型形参（若是泛型类型定义）或类型实参（若是构造类型）。</span><span class="sxs-lookup"><span data-stu-id="a41d2-103">From the point of view of reflection, the difference between a generic type and an ordinary type is that a generic type has associated with it a set of type parameters (if it is a generic type definition) or type arguments (if it is a constructed type).</span></span> <span data-ttu-id="a41d2-104">泛型方法和普通方法以相同方式互不相同。</span><span class="sxs-lookup"><span data-stu-id="a41d2-104">A generic method differs from an ordinary method in the same way.</span></span>  
  
 <span data-ttu-id="a41d2-105">有两个关键点可了解反射如何处理泛型类型和方法：</span><span class="sxs-lookup"><span data-stu-id="a41d2-105">There are two keys to understanding how reflection handles generic types and methods:</span></span>  
  
-   <span data-ttu-id="a41d2-106">泛型类型定义和泛型方法定义的类型参数由 <xref:System.Type> 类的实例表示。</span><span class="sxs-lookup"><span data-stu-id="a41d2-106">The type parameters of generic type definitions and generic method definitions are represented by instances of the <xref:System.Type> class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a41d2-107"><xref:System.Type> 对象表示泛型类型参数时， <xref:System.Type> 的很多属性和方法具有不同的行为。</span><span class="sxs-lookup"><span data-stu-id="a41d2-107">Many properties and methods of <xref:System.Type> have different behavior when a <xref:System.Type> object represents a generic type parameter.</span></span> <span data-ttu-id="a41d2-108">这些差异记录在属性和方法主题中。</span><span class="sxs-lookup"><span data-stu-id="a41d2-108">These differences are documented in the property and method topics.</span></span> <span data-ttu-id="a41d2-109">有关示例，请参阅 <xref:System.Type.IsAutoClass%2A> 和 <xref:System.Type.DeclaringType%2A>。</span><span class="sxs-lookup"><span data-stu-id="a41d2-109">For example, see <xref:System.Type.IsAutoClass%2A> and <xref:System.Type.DeclaringType%2A>.</span></span> <span data-ttu-id="a41d2-110">此外，某些成员仅在 <xref:System.Type> 对象表示泛型类型参数时有效。</span><span class="sxs-lookup"><span data-stu-id="a41d2-110">In addition, some members are valid only when a <xref:System.Type> object represents a generic type parameter.</span></span> <span data-ttu-id="a41d2-111">有关示例，请参阅 <xref:System.Type.GetGenericTypeDefinition%2A>。</span><span class="sxs-lookup"><span data-stu-id="a41d2-111">For example, see <xref:System.Type.GetGenericTypeDefinition%2A>.</span></span>  
  
-   <span data-ttu-id="a41d2-112">如果 <xref:System.Type> 的实例表示泛型类型，则它包含表示类型形参（对于泛型类型定义）或类型实参（对于构造类型）的类型数组。</span><span class="sxs-lookup"><span data-stu-id="a41d2-112">If an instance of <xref:System.Type> represents a generic type, then it includes an array of types that represent the type parameters (for generic type definitions) or the type arguments (for constructed types).</span></span> <span data-ttu-id="a41d2-113">这同样适用于表示泛型方法的 <xref:System.Reflection.MethodInfo> 的类的实例。</span><span class="sxs-lookup"><span data-stu-id="a41d2-113">The same is true of an instance of the <xref:System.Reflection.MethodInfo> class that represents a generic method.</span></span>  
  
 <span data-ttu-id="a41d2-114">反射提供 <xref:System.Type> 和 <xref:System.Reflection.MethodInfo> 的方法，它允许你访问类型形参的数组并确定 <xref:System.Type> 的实例是表示类型形参还是表示实际类型。</span><span class="sxs-lookup"><span data-stu-id="a41d2-114">Reflection provides methods of <xref:System.Type> and <xref:System.Reflection.MethodInfo> that allow you to access the array of type parameters, and to determine whether an instance of <xref:System.Type> represents a type parameter or an actual type.</span></span>  
  
 <span data-ttu-id="a41d2-115">若要深入了解此处讨论的方法的示例代码演示，请参阅[如何：使用反射检查和实例化泛型类型](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md)。</span><span class="sxs-lookup"><span data-stu-id="a41d2-115">For example code demonstrating the methods discussed here, see [How to: Examine and Instantiate Generic Types with Reflection](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md).</span></span>  
  
 <span data-ttu-id="a41d2-116">以下讨论假定熟悉泛型的术语，例如类型形参和实参之间的差异以及开放式或封闭式构造类型之间的差异。</span><span class="sxs-lookup"><span data-stu-id="a41d2-116">The following discussion assumes familiarity with the terminology of generics, such as the difference between type parameters and arguments and open or closed constructed types.</span></span> <span data-ttu-id="a41d2-117">有关详细信息，请参阅[泛型](../../../docs/standard/generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a41d2-117">For more information, see [Generics](../../../docs/standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="a41d2-118">本概述包含以下几节：</span><span class="sxs-lookup"><span data-stu-id="a41d2-118">This overview consists of the following sections:</span></span>  
  
-   [<span data-ttu-id="a41d2-119">这是泛型类型还是泛型方法？</span><span class="sxs-lookup"><span data-stu-id="a41d2-119">Is This a Generic Type or Method?</span></span>](#is_this_a_generic_type_or_method)  
  
-   [<span data-ttu-id="a41d2-120">生成封闭式泛型类型</span><span class="sxs-lookup"><span data-stu-id="a41d2-120">Generating Closed Generic Types</span></span>](#generating_closed_generic_types)  
  
-   [<span data-ttu-id="a41d2-121">检查类型实参和类型形参</span><span class="sxs-lookup"><span data-stu-id="a41d2-121">Examining Type Arguments and Type Parameters</span></span>](#examining_type_arguments)  
  
-   [<span data-ttu-id="a41d2-122">固定协定</span><span class="sxs-lookup"><span data-stu-id="a41d2-122">Invariants</span></span>](#invariants)  
  
-   [<span data-ttu-id="a41d2-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="a41d2-123">Related Topics</span></span>](#related_topics)  
  
<a name="is_this_a_generic_type_or_method"></a>   
## <a name="is-this-a-generic-type-or-method"></a><span data-ttu-id="a41d2-124">这是泛型类型还是泛型方法？</span><span class="sxs-lookup"><span data-stu-id="a41d2-124">Is This a Generic Type or Method?</span></span>  
 <span data-ttu-id="a41d2-125">当使用反射来检查未知类型（由 <xref:System.Type>的实例表示）时，请使用 <xref:System.Type.IsGenericType%2A> 属性来确定未知类型是否为泛型。</span><span class="sxs-lookup"><span data-stu-id="a41d2-125">When you use reflection to examine an unknown type, represented by an instance of <xref:System.Type>, use the <xref:System.Type.IsGenericType%2A> property to determine whether the unknown type is generic.</span></span> <span data-ttu-id="a41d2-126">如果类型是泛型，它会返回 `true` 。</span><span class="sxs-lookup"><span data-stu-id="a41d2-126">It returns `true` if the type is generic.</span></span> <span data-ttu-id="a41d2-127">同样，当检查未知方法（由 <xref:System.Reflection.MethodInfo> 类的实例表示）时，请使用 <xref:System.Reflection.MethodBase.IsGenericMethod%2A> 属性来确定此方法是否为泛型。</span><span class="sxs-lookup"><span data-stu-id="a41d2-127">Similarly, when you examine an unknown method, represented by an instance of the <xref:System.Reflection.MethodInfo> class, use the <xref:System.Reflection.MethodBase.IsGenericMethod%2A> property to determine whether the method is generic.</span></span>  
  
### <a name="is-this-a-generic-type-or-method-definition"></a><span data-ttu-id="a41d2-128">这是泛型类型定义还是泛型方法定义？</span><span class="sxs-lookup"><span data-stu-id="a41d2-128">Is This a Generic Type or Method Definition?</span></span>  
 <span data-ttu-id="a41d2-129">使用 <xref:System.Type.IsGenericTypeDefinition%2A> 属性来确定 <xref:System.Type> 对象是否表示泛型类型定义，并使用 <xref:System.Reflection.MethodBase.IsGenericMethodDefinition%2A> 方法来确定 <xref:System.Reflection.MethodInfo> 是否表示泛型方法定义。</span><span class="sxs-lookup"><span data-stu-id="a41d2-129">Use the <xref:System.Type.IsGenericTypeDefinition%2A> property to determine whether a <xref:System.Type> object represents a generic type definition, and use the <xref:System.Reflection.MethodBase.IsGenericMethodDefinition%2A> method to determine whether a <xref:System.Reflection.MethodInfo> represents a generic method definition.</span></span>  
  
 <span data-ttu-id="a41d2-130">泛型类型定义和泛型方法定义是一些从中创建可实例化类型的模板。</span><span class="sxs-lookup"><span data-stu-id="a41d2-130">Generic type and method definitions are the templates from which instantiable types are created.</span></span> <span data-ttu-id="a41d2-131">.NET Framework 类库中的泛型类型（如 <xref:System.Collections.Generic.Dictionary%602>）是泛型类型定义。</span><span class="sxs-lookup"><span data-stu-id="a41d2-131">Generic types in the .NET Framework class library, such as <xref:System.Collections.Generic.Dictionary%602>, are generic type definitions.</span></span>  
  
### <a name="is-the-type-or-method-open-or-closed"></a><span data-ttu-id="a41d2-132">类型或方法是开放式还是封闭式的？</span><span class="sxs-lookup"><span data-stu-id="a41d2-132">Is the Type or Method Open or Closed?</span></span>  
 <span data-ttu-id="a41d2-133">如果可实例化类型都已替换为所有类型形参（包括所有封闭类型的所有类型形参），则泛型类型或方法是封闭式的。</span><span class="sxs-lookup"><span data-stu-id="a41d2-133">A generic type or method is closed if instantiable types have been substituted for all its type parameters, including all the type parameters of all enclosing types.</span></span> <span data-ttu-id="a41d2-134">若为封闭式，则只能创建泛型类型的实例。</span><span class="sxs-lookup"><span data-stu-id="a41d2-134">You can only create an instance of a generic type if it is closed.</span></span> <span data-ttu-id="a41d2-135">如果类型为开放式， <xref:System.Type.ContainsGenericParameters%2A?displayProperty=nameWithType> 属性将返回 `true` 。</span><span class="sxs-lookup"><span data-stu-id="a41d2-135">The <xref:System.Type.ContainsGenericParameters%2A?displayProperty=nameWithType> property returns `true` if a type is open.</span></span> <span data-ttu-id="a41d2-136">对于方法， <xref:System.Reflection.MethodBase.ContainsGenericParameters%2A?displayProperty=nameWithType> 方法执行相同的功能。</span><span class="sxs-lookup"><span data-stu-id="a41d2-136">For methods, the <xref:System.Reflection.MethodBase.ContainsGenericParameters%2A?displayProperty=nameWithType> method performs the same function.</span></span>  
  
 [<span data-ttu-id="a41d2-137">返回页首</span><span class="sxs-lookup"><span data-stu-id="a41d2-137">Back to top</span></span>](#top)  
  
<a name="generating_closed_generic_types"></a>   
## <a name="generating-closed-generic-types"></a><span data-ttu-id="a41d2-138">生成封闭式泛型类型</span><span class="sxs-lookup"><span data-stu-id="a41d2-138">Generating Closed Generic Types</span></span>  
 <span data-ttu-id="a41d2-139">在具有泛型类型或方法定义之后，请使用 <xref:System.Type.MakeGenericType%2A> 方法来创建封闭式泛型类型或者使用 <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> 方法来为封闭式泛型方法创建 <xref:System.Reflection.MethodInfo> 。</span><span class="sxs-lookup"><span data-stu-id="a41d2-139">Once you have a generic type or method definition, use the <xref:System.Type.MakeGenericType%2A> method to create a closed generic type or the <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> method to create a <xref:System.Reflection.MethodInfo> for a closed generic method.</span></span>  
  
### <a name="getting-the-generic-type-or-method-definition"></a><span data-ttu-id="a41d2-140">获取泛型类型或方法定义</span><span class="sxs-lookup"><span data-stu-id="a41d2-140">Getting the Generic Type or Method Definition</span></span>  
 <span data-ttu-id="a41d2-141">如果你具有开放式泛型类型或方法（非泛型类型或方法定义），则不能创建它的实例，也不能提供缺少的类型形参。</span><span class="sxs-lookup"><span data-stu-id="a41d2-141">If you have an open generic type or method that is not a generic type or method definition, you cannot create instances of it and you cannot supply the type parameters that are missing.</span></span> <span data-ttu-id="a41d2-142">必须具有泛型类型或方法定义。</span><span class="sxs-lookup"><span data-stu-id="a41d2-142">You must have a generic type or method definition.</span></span> <span data-ttu-id="a41d2-143">使用 <xref:System.Type.GetGenericTypeDefinition%2A> 方法来获取泛型类型定义或使用 <xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A> 方法来获取泛型方法定义。</span><span class="sxs-lookup"><span data-stu-id="a41d2-143">Use the <xref:System.Type.GetGenericTypeDefinition%2A> method to obtain the generic type definition or the <xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A> method to obtain the generic method definition.</span></span>  
  
 <span data-ttu-id="a41d2-144">例如，如果你有一个表示 <xref:System.Type> 的 `Dictionary<int, string>` 对象（在 Visual Basic 中为`Dictionary(Of Integer, String)` ）且想创建类型 `Dictionary<string, MyClass>`，则可以使用 <xref:System.Type.GetGenericTypeDefinition%2A> 方法来获取表示 <xref:System.Type> 的 `Dictionary<TKey, TValue>` ，然后使用 <xref:System.Type.MakeGenericType%2A> 方法来生成表示 <xref:System.Type> 的 `Dictionary<int, MyClass>`。</span><span class="sxs-lookup"><span data-stu-id="a41d2-144">For example, if you have a <xref:System.Type> object representing `Dictionary<int, string>` (`Dictionary(Of Integer, String)` in Visual Basic) and you want to create the type `Dictionary<string, MyClass>`, you can use the <xref:System.Type.GetGenericTypeDefinition%2A> method to get a <xref:System.Type> representing `Dictionary<TKey, TValue>` and then use the <xref:System.Type.MakeGenericType%2A> method to produce a <xref:System.Type> representing `Dictionary<int, MyClass>`.</span></span>  
  
 <span data-ttu-id="a41d2-145">有关非泛型类型的开放式泛型类型的示例，请参阅本主题稍后部分的“类型形参或类型实参”。</span><span class="sxs-lookup"><span data-stu-id="a41d2-145">For an example of an open generic type that is not a generic type, see "Type Parameter or Type Argument" later in this topic.</span></span>  
  
 [<span data-ttu-id="a41d2-146">返回页首</span><span class="sxs-lookup"><span data-stu-id="a41d2-146">Back to top</span></span>](#top)  
  
<a name="examining_type_arguments"></a>   
## <a name="examining-type-arguments-and-type-parameters"></a><span data-ttu-id="a41d2-147">检查类型实参和类型形参</span><span class="sxs-lookup"><span data-stu-id="a41d2-147">Examining Type Arguments and Type Parameters</span></span>  
 <span data-ttu-id="a41d2-148">使用 <xref:System.Type.GetGenericArguments%2A?displayProperty=nameWithType> 方法来获取 <xref:System.Type> 对象的数组（表示泛型类型的类型形参或类型实参），并使用 <xref:System.Reflection.MethodInfo.GetGenericArguments%2A?displayProperty=nameWithType> 方法为泛型方法执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="a41d2-148">Use the <xref:System.Type.GetGenericArguments%2A?displayProperty=nameWithType> method to obtain an array of <xref:System.Type> objects that represent the type parameters or type arguments of a generic type, and use the <xref:System.Reflection.MethodInfo.GetGenericArguments%2A?displayProperty=nameWithType> method to do the same for a generic method.</span></span>  
  
 <span data-ttu-id="a41d2-149">在了解 <xref:System.Type> 对象表示类型形参之后，即可借助反射来回答很多其他问题。</span><span class="sxs-lookup"><span data-stu-id="a41d2-149">Once you know that a <xref:System.Type> object represents a type parameter, there are many additional questions reflection can answer.</span></span> <span data-ttu-id="a41d2-150">可以确定类型形参的源、位置以及约束。</span><span class="sxs-lookup"><span data-stu-id="a41d2-150">You can determine the type parameter's source, its position, and its constraints.</span></span>  
  
### <a name="type-parameter-or-type-argument"></a><span data-ttu-id="a41d2-151">类型形参或类型实参</span><span class="sxs-lookup"><span data-stu-id="a41d2-151">Type Parameter or Type Argument</span></span>  
 <span data-ttu-id="a41d2-152">若要确定数组的某个特定元素是类型形参还是类型实参，请使用 <xref:System.Type.IsGenericParameter%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="a41d2-152">To determine whether a particular element of the array is a type parameter or a type argument, use the <xref:System.Type.IsGenericParameter%2A> property.</span></span> <span data-ttu-id="a41d2-153">如果元素是类型形参，则 <xref:System.Type.IsGenericParameter%2A> 属性为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="a41d2-153">The <xref:System.Type.IsGenericParameter%2A> property is `true` if the element is a type parameter.</span></span>  
  
 <span data-ttu-id="a41d2-154">在不是泛型类型定义的情况下，泛型类型也可以是开放式，此时它同时具有类型实参和类型形参。</span><span class="sxs-lookup"><span data-stu-id="a41d2-154">A generic type can be open without being a generic type definition, in which case it has a mixture of type arguments and type parameters.</span></span> <span data-ttu-id="a41d2-155">例如，在下面的代码中，类 `D` 派生自通过将 `D` 的第一个类型参数替换为 `B`的第二个类型参数来创建的类型。</span><span class="sxs-lookup"><span data-stu-id="a41d2-155">For example, in the following code, class `D` derives from a type created by substituting the first type parameter of `D` for the second type parameter of `B`.</span></span>  
  
```csharp  
class B<T, U> {}  
class D<V, W> : B<int, V> {}  
```  
  
```vb  
Class B(Of T, U)  
End Class  
Class D(Of V, W)  
    Inherits B(Of Integer, V)  
End Class  
```  
  
```cpp  
generic<typename T, typename U> ref class B {};  
generic<typename V, typename W> ref class D : B<int, V> {};  
```  
  
 <span data-ttu-id="a41d2-156">如果你获取表示 <xref:System.Type> 的 `D<V, W>` 对象，并使用 <xref:System.Type.BaseType%2A> 属性来获取其基类型，则产生的 `type B<int, V>` 是开放式的，但它不是泛型类型定义。</span><span class="sxs-lookup"><span data-stu-id="a41d2-156">If you obtain a <xref:System.Type> object representing `D<V, W>` and use the <xref:System.Type.BaseType%2A> property to obtain its base type, the resulting `type B<int, V>` is open, but it is not a generic type definition.</span></span>  
  
### <a name="source-of-a-generic-parameter"></a><span data-ttu-id="a41d2-157">泛型参数的源</span><span class="sxs-lookup"><span data-stu-id="a41d2-157">Source of a Generic Parameter</span></span>  
 <span data-ttu-id="a41d2-158">泛型类型形参可能来自要检查的类型、封闭类型或者泛型方法。</span><span class="sxs-lookup"><span data-stu-id="a41d2-158">A generic type parameter might come from the type you are examining, from an enclosing type, or from a generic method.</span></span> <span data-ttu-id="a41d2-159">可以按以下方式确定泛型类型形参的源：</span><span class="sxs-lookup"><span data-stu-id="a41d2-159">You can determine the source of the generic type parameter as follows:</span></span>  
  
-   <span data-ttu-id="a41d2-160">首先，使用 <xref:System.Type.DeclaringMethod%2A> 属性来确定类型形参是否来自泛型方法。</span><span class="sxs-lookup"><span data-stu-id="a41d2-160">First, use the <xref:System.Type.DeclaringMethod%2A> property to determine whether the type parameter comes from a generic method.</span></span> <span data-ttu-id="a41d2-161">如果属性值不是 null 引用（在 Visual Basic 中为`Nothing` ），则源是泛型方法。</span><span class="sxs-lookup"><span data-stu-id="a41d2-161">If the property value is not a null reference (`Nothing` in Visual Basic), then the source is a generic method.</span></span>  
  
-   <span data-ttu-id="a41d2-162">如果源不是泛型方法，则使用 <xref:System.Type.DeclaringType%2A> 属性来确定泛型类型形参所属的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="a41d2-162">If the source is not a generic method, use the <xref:System.Type.DeclaringType%2A> property to determine the generic type the generic type parameter belongs to.</span></span>  
  
 <span data-ttu-id="a41d2-163">如果类型形参属于泛型方法，则 <xref:System.Type.DeclaringType%2A> 属性返回声明泛型方法的类型，这是不相关的类型。</span><span class="sxs-lookup"><span data-stu-id="a41d2-163">If the type parameter belongs to a generic method, the <xref:System.Type.DeclaringType%2A> property returns the type that declared the generic method, which is irrelevant.</span></span>  
  
### <a name="position-of-a-generic-parameter"></a><span data-ttu-id="a41d2-164">泛型参数的位置</span><span class="sxs-lookup"><span data-stu-id="a41d2-164">Position of a Generic Parameter</span></span>  
 <span data-ttu-id="a41d2-165">在极少数情况下，必须确定类型形参在其声明类的类型形参列表中的位置。</span><span class="sxs-lookup"><span data-stu-id="a41d2-165">In rare situations, it is necessary to determine the position of a type parameter in the type parameter list of its declaring class.</span></span> <span data-ttu-id="a41d2-166">例如，假设你有表示上述示例中的 <xref:System.Type> 类型的 `B<int, V>` 对象。</span><span class="sxs-lookup"><span data-stu-id="a41d2-166">For example, suppose you have a <xref:System.Type> object representing the `B<int, V>` type from the preceding example.</span></span> <span data-ttu-id="a41d2-167"><xref:System.Type.GetGenericArguments%2A> 方法提供类型实参的列表，在检查 `V` 时即可使用 <xref:System.Type.DeclaringMethod%2A> 和 <xref:System.Type.DeclaringType%2A> 属性来发现它的来源位置。</span><span class="sxs-lookup"><span data-stu-id="a41d2-167">The <xref:System.Type.GetGenericArguments%2A> method gives you a list of type arguments, and when you examine `V` you can use the <xref:System.Type.DeclaringMethod%2A> and <xref:System.Type.DeclaringType%2A> properties to discover where it comes from.</span></span> <span data-ttu-id="a41d2-168">然后，可以使用 <xref:System.Type.GenericParameterPosition%2A> 属性来确定它在定义它的类型形参列表中的位置。</span><span class="sxs-lookup"><span data-stu-id="a41d2-168">You can then use the <xref:System.Type.GenericParameterPosition%2A> property to determine its position in the type parameter list where it was defined.</span></span> <span data-ttu-id="a41d2-169">在此示例中， `V` 在定义它的类型形参列表中位于位置 0（零）。</span><span class="sxs-lookup"><span data-stu-id="a41d2-169">In this example, `V` is at position 0 (zero) in the type parameter list where it was defined.</span></span>  
  
### <a name="base-type-and-interface-constraints"></a><span data-ttu-id="a41d2-170">基类型和接口约束</span><span class="sxs-lookup"><span data-stu-id="a41d2-170">Base Type and Interface Constraints</span></span>  
 <span data-ttu-id="a41d2-171">使用 <xref:System.Type.GetGenericParameterConstraints%2A> 方法来获取类型形参的基类型约束和接口约束。</span><span class="sxs-lookup"><span data-stu-id="a41d2-171">Use the <xref:System.Type.GetGenericParameterConstraints%2A> method to obtain the base type constraint and interface constraints of a type parameter.</span></span> <span data-ttu-id="a41d2-172">数组的元素顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="a41d2-172">The order of the elements of the array is not significant.</span></span> <span data-ttu-id="a41d2-173">如果元素是接口类型，则它表示接口约束。</span><span class="sxs-lookup"><span data-stu-id="a41d2-173">An element represents an interface constraint if it is an interface type.</span></span>  
  
### <a name="generic-parameter-attributes"></a><span data-ttu-id="a41d2-174">泛型参数特性</span><span class="sxs-lookup"><span data-stu-id="a41d2-174">Generic Parameter Attributes</span></span>  
 <span data-ttu-id="a41d2-175"><xref:System.Type.GenericParameterAttributes%2A> 属性获取 <xref:System.Reflection.GenericParameterAttributes> 值，该值指示类型形参的方差（协变或逆变）和特殊约束。</span><span class="sxs-lookup"><span data-stu-id="a41d2-175">The <xref:System.Type.GenericParameterAttributes%2A> property gets a <xref:System.Reflection.GenericParameterAttributes> value that indicates the variance (covariance or contravariance) and the special constraints of a type parameter.</span></span>  
  
#### <a name="covariance-and-contravariance"></a><span data-ttu-id="a41d2-176">协变和逆变</span><span class="sxs-lookup"><span data-stu-id="a41d2-176">Covariance and Contravariance</span></span>  
 <span data-ttu-id="a41d2-177">若要确定类型形参是协变还是逆变，请将 <xref:System.Reflection.GenericParameterAttributes.VarianceMask?displayProperty=nameWithType> 掩码应用到 <xref:System.Reflection.GenericParameterAttributes> 属性返回的 <xref:System.Type.GenericParameterAttributes%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="a41d2-177">To determine whether a type parameter is covariant or contravariant, apply the <xref:System.Reflection.GenericParameterAttributes.VarianceMask?displayProperty=nameWithType> mask to the <xref:System.Reflection.GenericParameterAttributes> value that is returned by the <xref:System.Type.GenericParameterAttributes%2A> property.</span></span> <span data-ttu-id="a41d2-178">如果结果为 <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>，则类型形参不变。</span><span class="sxs-lookup"><span data-stu-id="a41d2-178">If the result is <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, the type parameter is invariant.</span></span> <span data-ttu-id="a41d2-179">请参阅 [协变和逆变](../../../docs/standard/generics/covariance-and-contravariance.md)。</span><span class="sxs-lookup"><span data-stu-id="a41d2-179">See [Covariance and Contravariance](../../../docs/standard/generics/covariance-and-contravariance.md).</span></span>  
  
#### <a name="special-constraints"></a><span data-ttu-id="a41d2-180">特殊约束</span><span class="sxs-lookup"><span data-stu-id="a41d2-180">Special Constraints</span></span>  
 <span data-ttu-id="a41d2-181">若要确定类型形参的特殊约束，请将 <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> 掩码应用到 <xref:System.Reflection.GenericParameterAttributes> 属性返回的 <xref:System.Type.GenericParameterAttributes%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="a41d2-181">To determine the special constraints of a type parameter, apply the <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> mask to the <xref:System.Reflection.GenericParameterAttributes> value that is returned by the <xref:System.Type.GenericParameterAttributes%2A> property.</span></span> <span data-ttu-id="a41d2-182">如果结果为 <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>，则没有任何特殊约束。</span><span class="sxs-lookup"><span data-stu-id="a41d2-182">If the result is <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, there are no special constraints.</span></span> <span data-ttu-id="a41d2-183">可将类型形参约束为引用类型、不可以为 null 的类型以及具有默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="a41d2-183">A type parameter can be constrained to be a reference type, to be a non-nullable value type, and to have a default constructor.</span></span>  
  
 [<span data-ttu-id="a41d2-184">返回页首</span><span class="sxs-lookup"><span data-stu-id="a41d2-184">Back to top</span></span>](#top)  
  
<a name="invariants"></a>   
## <a name="invariants"></a><span data-ttu-id="a41d2-185">固定协定</span><span class="sxs-lookup"><span data-stu-id="a41d2-185">Invariants</span></span>  
 <span data-ttu-id="a41d2-186">有关泛型类型反射中常用术语的固定条件表格，请参阅 <xref:System.Type.IsGenericType%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a41d2-186">For a table of the invariant conditions for common terms in reflection for generic types, see <xref:System.Type.IsGenericType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a41d2-187">有关与泛型方法相关的其他术语，请参阅 <xref:System.Reflection.MethodBase.IsGenericMethod%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a41d2-187">For additional terms relating to generic methods, see <xref:System.Reflection.MethodBase.IsGenericMethod%2A?displayProperty=nameWithType>.</span></span>  
  
 [<span data-ttu-id="a41d2-188">返回页首</span><span class="sxs-lookup"><span data-stu-id="a41d2-188">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="a41d2-189">相关主题</span><span class="sxs-lookup"><span data-stu-id="a41d2-189">Related Topics</span></span>  
  
|<span data-ttu-id="a41d2-190">标题</span><span class="sxs-lookup"><span data-stu-id="a41d2-190">Title</span></span>|<span data-ttu-id="a41d2-191">描述</span><span class="sxs-lookup"><span data-stu-id="a41d2-191">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a41d2-192">如何：使用反射检查和实例化泛型类型</span><span class="sxs-lookup"><span data-stu-id="a41d2-192">How to: Examine and Instantiate Generic Types with Reflection</span></span>](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md)|<span data-ttu-id="a41d2-193">演示如何使用 <xref:System.Type> 和 <xref:System.Reflection.MethodInfo> 的属性和方法来检查泛型类型。</span><span class="sxs-lookup"><span data-stu-id="a41d2-193">Shows how to use the properties and methods of <xref:System.Type> and <xref:System.Reflection.MethodInfo> to examine generic types.</span></span>|  
|[<span data-ttu-id="a41d2-194">泛型</span><span class="sxs-lookup"><span data-stu-id="a41d2-194">Generics</span></span>](../../../docs/standard/generics/index.md)|<span data-ttu-id="a41d2-195">描述泛型功能以及 .NET Framework 如何支持它。</span><span class="sxs-lookup"><span data-stu-id="a41d2-195">Describes the generics feature and how it is supported in the .NET Framework.</span></span>|  
|[<span data-ttu-id="a41d2-196">如何：使用 Reflection Emit 定义泛型类型</span><span class="sxs-lookup"><span data-stu-id="a41d2-196">How to: Define a Generic Type with Reflection Emit</span></span>](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md)|<span data-ttu-id="a41d2-197">演示如何在动态程序集中使用反射发出生成泛型类型。</span><span class="sxs-lookup"><span data-stu-id="a41d2-197">Shows how to use reflection emit to generate generic types in dynamic assemblies.</span></span>|  
|[<span data-ttu-id="a41d2-198">查看类型信息</span><span class="sxs-lookup"><span data-stu-id="a41d2-198">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)|<span data-ttu-id="a41d2-199">介绍 <xref:System.Type> 类并提供演示如何使用具有各种反射类的 <xref:System.Type> 来获取有关构造函数、方法、字段、属性和事件的信息的代码示例。</span><span class="sxs-lookup"><span data-stu-id="a41d2-199">Describes the <xref:System.Type> class and provides code examples that illustrate how to use <xref:System.Type> with various reflection classes to obtain information about constructors, methods, fields, properties, and events.</span></span>|
