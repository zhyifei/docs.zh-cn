---
title: "扩展方法（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- methods [C#], adding to existing types
- extension methods [C#]
- methods [C#], extension
ms.assetid: 175ce3ff-9bbf-4e64-8421-faeb81a0bb51
caps.latest.revision: 35
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
ms.sourcegitcommit: d74c1d0760d4e776c2cf4c7dea1dac060c85a83c
ms.openlocfilehash: 657f9ebfba5d6f49d3a88cb1cf790e4a0134a007
ms.contentlocale: zh-cn
ms.lasthandoff: 09/05/2017

---
# <a name="extension-methods-c-programming-guide"></a><span data-ttu-id="297e5-102">扩展方法（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="297e5-102">Extension Methods (C# Programming Guide)</span></span>
<span data-ttu-id="297e5-103">扩展方法使你能够向现有类型“添加”方法，而无需创建新的派生类型、重新编译或以其他方式修改原始类型。</span><span class="sxs-lookup"><span data-stu-id="297e5-103">Extension methods enable you to "add" methods to existing types without creating a new derived type, recompiling, or otherwise modifying the original type.</span></span> <span data-ttu-id="297e5-104">扩展方法是一种特殊的静态方法，但可以像扩展类型上的实例方法一样进行调用。</span><span class="sxs-lookup"><span data-stu-id="297e5-104">Extension methods are a special kind of static method, but they are called as if they were instance methods on the extended type.</span></span> <span data-ttu-id="297e5-105">对于用 C#、F# 和 Visual Basic 编写的客户端代码，调用扩展方法与调用在类型中实际定义的方法没有明显区别。</span><span class="sxs-lookup"><span data-stu-id="297e5-105">For client code written in C#, F# and Visual Basic, there is no apparent difference between calling an extension method and the methods that are actually defined in a type.</span></span>  
  
 <span data-ttu-id="297e5-106">最常见的扩展方法是 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 标准查询运算符，它将查询功能添加到现有的 <xref:System.Collections.IEnumerable?displayProperty=fullName> 和 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 类型。</span><span class="sxs-lookup"><span data-stu-id="297e5-106">The most common extension methods are the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] standard query operators that add query functionality to the existing <xref:System.Collections.IEnumerable?displayProperty=fullName> and <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> types.</span></span> <span data-ttu-id="297e5-107">若要使用标准查询运算符，请先使用 `using System.Linq` 指令将它们置于范围中。</span><span class="sxs-lookup"><span data-stu-id="297e5-107">To use the standard query operators, first bring them into scope with a `using System.Linq` directive.</span></span> <span data-ttu-id="297e5-108">然后，任何实现了 <xref:System.Collections.Generic.IEnumerable%601> 的类型看起来都具有 <xref:System.Linq.Enumerable.GroupBy%2A>、<xref:System.Linq.Enumerable.OrderBy%2A>、<xref:System.Linq.Enumerable.Average%2A> 等实例方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-108">Then any type that implements <xref:System.Collections.Generic.IEnumerable%601> appears to have instance methods such as <xref:System.Linq.Enumerable.GroupBy%2A>, <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="297e5-109">在 <xref:System.Collections.Generic.IEnumerable%601> 类型的实例（如 <xref:System.Collections.Generic.List%601> 或 <xref:System.Array>）后键入“dot”时，可以在 IntelliSense 语句完成中看到这些附加方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-109">You can see these additional methods in IntelliSense statement completion when you type "dot" after an instance of an <xref:System.Collections.Generic.IEnumerable%601> type such as <xref:System.Collections.Generic.List%601> or <xref:System.Array>.</span></span>  
  
 <span data-ttu-id="297e5-110">下面的示例演示如何对一个整数数组调用标准查询运算符 `OrderBy` 方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-110">The following example shows how to call the standard query operator `OrderBy` method on an array of integers.</span></span> <span data-ttu-id="297e5-111">括号里面的表达式是一个 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="297e5-111">The expression in parentheses is a lambda expression.</span></span> <span data-ttu-id="297e5-112">很多标准查询运算符采用 Lambda 表达式作为参数，但这不是扩展方法的必要条件。</span><span class="sxs-lookup"><span data-stu-id="297e5-112">Many standard query operators take lambda expressions as parameters, but this is not a requirement for extension methods.</span></span> <span data-ttu-id="297e5-113">有关详细信息，请参阅 [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="297e5-113">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="297e5-114">[!code-cs[csProgGuideExtensionMethods#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="297e5-114">[!code-cs[csProgGuideExtensionMethods#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="297e5-115">扩展方法被定义为静态方法，但它们是通过实例方法语法进行调用的。</span><span class="sxs-lookup"><span data-stu-id="297e5-115">Extension methods are defined as static methods but are called by using instance method syntax.</span></span> <span data-ttu-id="297e5-116">它们的第一个参数指定该方法作用于哪个类型，并且该参数以 [this](../../../csharp/language-reference/keywords/this.md) 修饰符为前缀。</span><span class="sxs-lookup"><span data-stu-id="297e5-116">Their first parameter specifies which type the method operates on, and the parameter is preceded by the [this](../../../csharp/language-reference/keywords/this.md) modifier.</span></span> <span data-ttu-id="297e5-117">仅当你使用 `using` 指令将命名空间显式导入到源代码中之后，扩展方法才位于范围中。</span><span class="sxs-lookup"><span data-stu-id="297e5-117">Extension methods are only in scope when you explicitly import the namespace into your source code with a `using` directive.</span></span>  
  
 <span data-ttu-id="297e5-118">下面的示例演示为 <xref:System.String?displayProperty=fullName> 类定义的一个扩展方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-118">The following example shows an extension method defined for the <xref:System.String?displayProperty=fullName> class.</span></span> <span data-ttu-id="297e5-119">请注意，它是在非嵌套的、非泛型静态类内部定义的：</span><span class="sxs-lookup"><span data-stu-id="297e5-119">Note that it is defined inside a non-nested, non-generic static class:</span></span>  
  
 <span data-ttu-id="297e5-120">[!code-cs[csProgGuideExtensionMethods#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="297e5-120">[!code-cs[csProgGuideExtensionMethods#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="297e5-121">可使用此 `WordCount` 指令将 `using` 扩展方法置于范围中：</span><span class="sxs-lookup"><span data-stu-id="297e5-121">The `WordCount` extension method can be brought into scope with this `using` directive:</span></span>  
  
```  
using ExtensionMethods;  
```  
  
 <span data-ttu-id="297e5-122">而且，可以使用以下语法从应用程序中调用该扩展方法：</span><span class="sxs-lookup"><span data-stu-id="297e5-122">And it can be called from an application by using this syntax:</span></span>  
  
```  
string s = "Hello Extension Methods";  
int i = s.WordCount();  
```  
  
 <span data-ttu-id="297e5-123">在代码中，可以使用实例方法语法调用该扩展方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-123">In your code you invoke the extension method with instance method syntax.</span></span> <span data-ttu-id="297e5-124">但是，编译器生成的中间语言 (IL) 会将代码转换为对静态方法的调用。</span><span class="sxs-lookup"><span data-stu-id="297e5-124">However, the intermediate language (IL) generated by the compiler translates your code into a call on the static method.</span></span> <span data-ttu-id="297e5-125">因此，并未真正违反封装原则。</span><span class="sxs-lookup"><span data-stu-id="297e5-125">Therefore, the principle of encapsulation is not really being violated.</span></span> <span data-ttu-id="297e5-126">实际上，扩展方法无法访问它们所扩展的类型中的私有变量。</span><span class="sxs-lookup"><span data-stu-id="297e5-126">In fact, extension methods cannot access private variables in the type they are extending.</span></span>  
  
 <span data-ttu-id="297e5-127">有关详细信息，请参阅[如何：实现和调用自定义扩展方法](../../../csharp/programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md)。</span><span class="sxs-lookup"><span data-stu-id="297e5-127">For more information, see [How to: Implement and Call a Custom  Extension Method](../../../csharp/programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md).</span></span>  
  
 <span data-ttu-id="297e5-128">通常，你更多时候是调用扩展方法而不是实现你自己的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-128">In general, you will probably be calling extension methods far more often than implementing your own.</span></span> <span data-ttu-id="297e5-129">由于扩展方法是使用实例方法语法调用的，因此不需要任何特殊知识即可从客户端代码中使用它们。</span><span class="sxs-lookup"><span data-stu-id="297e5-129">Because extension methods are called by using instance method syntax, no special knowledge is required to use them from client code.</span></span> <span data-ttu-id="297e5-130">若要为特定类型启用扩展方法，只需为在其中定义这些方法的命名空间添加 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="297e5-130">To enable extension methods for a particular type, just add a `using` directive for the namespace in which the methods are defined.</span></span> <span data-ttu-id="297e5-131">例如，若要使用标准查询运算符，请将此 `using` 指令添加到代码中：</span><span class="sxs-lookup"><span data-stu-id="297e5-131">For example, to use the standard query operators, add this `using` directive to your code:</span></span>  
  
```  
using System.Linq;  
```  
  
 <span data-ttu-id="297e5-132">（你可能还必须添加对 System.Core.dll 的引用。）你将注意到，标准查询运算符现在作为可供大多数 <xref:System.Collections.Generic.IEnumerable%601> 类型使用的附加方法显示在 IntelliSense 中。</span><span class="sxs-lookup"><span data-stu-id="297e5-132">(You may also have to add a reference to System.Core.dll.) You will notice that the standard query operators now appear in IntelliSense as additional methods available for most <xref:System.Collections.Generic.IEnumerable%601> types.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="297e5-133">尽管标准查询运算符没有显示在 <xref:System.String> 的 IntelliSense 中，但它们仍然可用。</span><span class="sxs-lookup"><span data-stu-id="297e5-133">Although standard query operators do not appear in IntelliSense for <xref:System.String>, they are still available.</span></span>  
  
## <a name="binding-extension-methods-at-compile-time"></a><span data-ttu-id="297e5-134">在编译时绑定扩展方法</span><span class="sxs-lookup"><span data-stu-id="297e5-134">Binding Extension Methods at Compile Time</span></span>  
 <span data-ttu-id="297e5-135">可以使用扩展方法来扩展类或接口，但不能重写扩展方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-135">You can use extension methods to extend a class or interface, but not to override them.</span></span> <span data-ttu-id="297e5-136">与接口或类方法具有相同名称和签名的扩展方法永远不会被调用。</span><span class="sxs-lookup"><span data-stu-id="297e5-136">An extension method with the same name and signature as an interface or class method will never be called.</span></span> <span data-ttu-id="297e5-137">编译时，扩展方法的优先级总是比类型本身中定义的实例方法低。</span><span class="sxs-lookup"><span data-stu-id="297e5-137">At compile time, extension methods always have lower priority than instance methods defined in the type itself.</span></span> <span data-ttu-id="297e5-138">换句话说，如果某个类型具有一个名为 `Process(int i)` 的方法，而你有一个具有相同签名的扩展方法，则编译器总是绑定到该实例方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-138">In other words, if a type has a method named `Process(int i)`, and you have an extension method with the same signature, the compiler will always bind to the instance method.</span></span> <span data-ttu-id="297e5-139">当编译器遇到方法调用时，它首先在该类型的实例方法中寻找匹配的方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-139">When the compiler encounters a method invocation, it first looks for a match in the type's instance methods.</span></span> <span data-ttu-id="297e5-140">如果未找到任何匹配方法，编译器将搜索为该类型定义的任何扩展方法，并且绑定到它找到的第一个扩展方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-140">If no match is found, it will search for any extension methods that are defined for the type, and bind to the first extension method that it finds.</span></span> <span data-ttu-id="297e5-141">下面的示例演示编译器如何确定要绑定到哪个扩展方法或实例方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-141">The following example demonstrates how the compiler determines which extension method or instance method to bind to.</span></span>  
  
## <a name="example"></a><span data-ttu-id="297e5-142">示例</span><span class="sxs-lookup"><span data-stu-id="297e5-142">Example</span></span>  
 <span data-ttu-id="297e5-143">下面的示例演示 C# 编译器在确定是将方法调用绑定到类型上的实例方法还是绑定到扩展方法时所遵循的规则。</span><span class="sxs-lookup"><span data-stu-id="297e5-143">The following example demonstrates the rules that the C# compiler follows in determining whether to bind a method call to an instance method on the type, or to an extension method.</span></span> <span data-ttu-id="297e5-144">静态类 `Extensions` 包含为任何实现了 `IMyInterface` 的类型定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-144">The static class `Extensions` contains extension methods defined for any type that implements `IMyInterface`.</span></span> <span data-ttu-id="297e5-145">类 `A`、`B` 和 `C` 都实现了该接口。</span><span class="sxs-lookup"><span data-stu-id="297e5-145">Classes `A`, `B`, and `C` all implement the interface.</span></span>  
  
 <span data-ttu-id="297e5-146">`MethodB` 扩展方法永远不会被调用，因为它的名称和签名与这些类已经实现的方法完全匹配。</span><span class="sxs-lookup"><span data-stu-id="297e5-146">The `MethodB` extension method is never called because its name and signature exactly match methods already implemented by the classes.</span></span>  
  
 <span data-ttu-id="297e5-147">如果编译器找不到具有匹配签名的实例方法，它会绑定到匹配的扩展方法（如果存在这样的方法）。</span><span class="sxs-lookup"><span data-stu-id="297e5-147">When the compiler cannot find an instance method with a matching signature, it will bind to a matching extension method if one exists.</span></span>  
  
 <span data-ttu-id="297e5-148">[!code-cs[csProgGuideExtensionMethods#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="297e5-148">[!code-cs[csProgGuideExtensionMethods#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_3.cs)]</span></span>  
  
## <a name="general-guidelines"></a><span data-ttu-id="297e5-149">通用准则</span><span class="sxs-lookup"><span data-stu-id="297e5-149">General Guidelines</span></span>  
 <span data-ttu-id="297e5-150">通常，建议你只在不得已的情况下才实现扩展方法，并谨慎地实现。</span><span class="sxs-lookup"><span data-stu-id="297e5-150">In general, we recommend that you implement extension methods sparingly and only when you have to.</span></span> <span data-ttu-id="297e5-151">只要有可能，必须扩展现有类型的客户端代码都应该通过创建从现有类型派生的新类型来达到这一目的。</span><span class="sxs-lookup"><span data-stu-id="297e5-151">Whenever possible, client code that must extend an existing type should do so by creating a new type derived from the existing type.</span></span> <span data-ttu-id="297e5-152">有关详细信息，请参阅[继承](../../../csharp/programming-guide/classes-and-structs/inheritance.md)。</span><span class="sxs-lookup"><span data-stu-id="297e5-152">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="297e5-153">在使用扩展方法来扩展你无法更改其源代码的类型时，你需要承受该类型实现中的更改会导致扩展方法失效的风险。</span><span class="sxs-lookup"><span data-stu-id="297e5-153">When using an extension method to extend a type whose source code you cannot change, you run the risk that a change in the implementation of the type will cause your extension method to break.</span></span>  
  
 <span data-ttu-id="297e5-154">如果确实为给定类型实现了扩展方法，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="297e5-154">If you do implement extension methods for a given type, remember the following points:</span></span>  
  
-   <span data-ttu-id="297e5-155">如果扩展方法与该类型中定义的方法具有相同的签名，则扩展方法永远不会被调用。</span><span class="sxs-lookup"><span data-stu-id="297e5-155">An extension method will never be called if it has the same signature as a method defined in the type.</span></span>  
  
-   <span data-ttu-id="297e5-156">在命名空间级别将扩展方法置于范围中。</span><span class="sxs-lookup"><span data-stu-id="297e5-156">Extension methods are brought into scope at the namespace level.</span></span> <span data-ttu-id="297e5-157">例如，如果你在一个名为 `Extensions` 的命名空间中具有多个包含扩展方法的静态类，则这些扩展方法将全部由 `using Extensions;` 指令置于范围中。</span><span class="sxs-lookup"><span data-stu-id="297e5-157">For example, if you have multiple static classes that contain extension methods in a single namespace named `Extensions`, they will all be brought into scope by the `using Extensions;` directive.</span></span>  
  
 <span data-ttu-id="297e5-158">针对已实现的类库，不应为了避免程序集的版本号递增而使用扩展方法。</span><span class="sxs-lookup"><span data-stu-id="297e5-158">For a class library that you implemented, you shouldn't use extension methods to avoid incrementing the version number of an assembly.</span></span> <span data-ttu-id="297e5-159">如果要向你拥有源代码的库中添加重要功能，应遵循适用于程序集版本控制的标准 .NET Framework 准则。</span><span class="sxs-lookup"><span data-stu-id="297e5-159">If you want to add significant functionality to a library for which you own the source code, you should follow the standard .NET Framework guidelines for assembly versioning.</span></span> <span data-ttu-id="297e5-160">有关详细信息，请参阅[程序集版本控制](https://msdn.microsoft.com/library/51ket42z)。</span><span class="sxs-lookup"><span data-stu-id="297e5-160">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="297e5-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="297e5-161">See Also</span></span>  
 <span data-ttu-id="297e5-162">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="297e5-162">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="297e5-163">[并行编程示例（这些示例包括许多示例扩展方法）](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364) </span><span class="sxs-lookup"><span data-stu-id="297e5-163">[Parallel Programming Samples (these include many example extension methods)](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364) </span></span>  
 <span data-ttu-id="297e5-164">[Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="297e5-164">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 <span data-ttu-id="297e5-165">[Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2) （标准查询运算符概述）</span><span class="sxs-lookup"><span data-stu-id="297e5-165">[Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2) </span></span>  
 <span data-ttu-id="297e5-166">[Conversion rules for Instance parameters and their impact](http://go.microsoft.com/fwlink/?LinkId=112385) （实例参数及其影响的转换规则）</span><span class="sxs-lookup"><span data-stu-id="297e5-166">[Conversion rules for Instance parameters and their impact](http://go.microsoft.com/fwlink/?LinkId=112385) </span></span>  
 <span data-ttu-id="297e5-167">[Extension methods Interoperability between languages](http://go.microsoft.com/fwlink/?LinkId=112386) （语言间扩展方法的互操作性）</span><span class="sxs-lookup"><span data-stu-id="297e5-167">[Extension methods Interoperability between languages](http://go.microsoft.com/fwlink/?LinkId=112386) </span></span>  
 <span data-ttu-id="297e5-168">[Extension methods and Curried Delegates](http://go.microsoft.com/fwlink/?LinkId=112387) （扩展方法和扩充委托）</span><span class="sxs-lookup"><span data-stu-id="297e5-168">[Extension methods and Curried Delegates](http://go.microsoft.com/fwlink/?LinkId=112387) </span></span>  
 <span data-ttu-id="297e5-169">[Extension method Binding and Error reporting](http://go.microsoft.com/fwlink/?LinkId=112388)（扩展方法绑定和错误报告）</span><span class="sxs-lookup"><span data-stu-id="297e5-169">[Extension method Binding and Error reporting](http://go.microsoft.com/fwlink/?LinkId=112388)</span></span>

