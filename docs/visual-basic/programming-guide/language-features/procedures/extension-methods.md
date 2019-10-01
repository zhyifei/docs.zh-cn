---
title: 扩展方法 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: b5ad066fe9ec40d715702ed99537f45b21c558cf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701057"
---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="5f786-102">扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f786-102">Extension Methods (Visual Basic)</span></span>

<span data-ttu-id="5f786-103">通过扩展方法，开发人员可以向已定义的数据类型添加自定义功能，而无需创建新的派生类型。</span><span class="sxs-lookup"><span data-stu-id="5f786-103">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="5f786-104">通过扩展方法，可以编写一个方法，该方法可以像调用现有类型的实例方法一样进行调用。</span><span class="sxs-lookup"><span data-stu-id="5f786-104">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5f786-105">备注</span><span class="sxs-lookup"><span data-stu-id="5f786-105">Remarks</span></span>

<span data-ttu-id="5f786-106">扩展方法只能是 @no__t 或 @no__t 的过程。</span><span class="sxs-lookup"><span data-stu-id="5f786-106">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="5f786-107">不能定义扩展属性、字段或事件。</span><span class="sxs-lookup"><span data-stu-id="5f786-107">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="5f786-108">所有扩展方法都必须使用 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 命名空间中的扩展属性 `<Extension>` 进行标记，且必须在[模块](../../../language-reference/statements/module-statement.md)中定义。</span><span class="sxs-lookup"><span data-stu-id="5f786-108">All extension methods must be marked with the extension attribute `<Extension>` from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace and must be defined in a [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="5f786-109">如果在模块之外定义扩展方法，则 Visual Basic 编译器将生成错误[BC36551](../../../misc/bc36551.md)"只能在模块中定义扩展方法"。</span><span class="sxs-lookup"><span data-stu-id="5f786-109">If an extension method is defined outside a module, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules".</span></span>

<span data-ttu-id="5f786-110">扩展方法定义中的第一个参数指定该方法扩展的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5f786-110">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="5f786-111">当方法运行时，第一个参数绑定到调用方法的数据类型的实例。</span><span class="sxs-lookup"><span data-stu-id="5f786-111">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>

<span data-ttu-id="5f786-112">@No__t-0 属性只能应用于 Visual Basic [`Module`](../../../language-reference/statements/module-statement.md)、 [`Sub`](../../../language-reference/statements/sub-statement.md)或[@no__t](../../../language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="5f786-112">The `Extension` attribute can only be applied to a Visual Basic [`Module`](../../../language-reference/statements/module-statement.md), [`Sub`](../../../language-reference/statements/sub-statement.md), or [`Function`](../../../language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="5f786-113">如果将它应用于 @no__t 0 或 `Structure`，Visual Basic 编译器将生成错误[BC36550](../../../language-reference/error-messages/extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations.md)，"Extension" 特性只能应用于 "Module"、"Sub" 或 "Function" 声明。</span><span class="sxs-lookup"><span data-stu-id="5f786-113">If you apply it to a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36550](../../../language-reference/error-messages/extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations.md), "'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations".</span></span>

## <a name="example"></a><span data-ttu-id="5f786-114">示例</span><span class="sxs-lookup"><span data-stu-id="5f786-114">Example</span></span>

<span data-ttu-id="5f786-115">下面的示例定义了 <xref:System.String> 数据类型的 @no__t 的扩展。</span><span class="sxs-lookup"><span data-stu-id="5f786-115">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="5f786-116">方法使用 `Console.WriteLine` 来显示字符串。</span><span class="sxs-lookup"><span data-stu-id="5f786-116">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="5f786-117">@No__t-1 @no__t 方法的参数确定方法扩展了 @no__t 2 类。</span><span class="sxs-lookup"><span data-stu-id="5f786-117">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>
  
[!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]

<span data-ttu-id="5f786-118">请注意，扩展方法定义标记有扩展属性 `<Extension()>`。</span><span class="sxs-lookup"><span data-stu-id="5f786-118">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="5f786-119">标记定义方法的模块是可选的，但必须标记每个扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-119">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="5f786-120">必须导入 <xref:System.Runtime.CompilerServices> 才能访问扩展属性。</span><span class="sxs-lookup"><span data-stu-id="5f786-120"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>

<span data-ttu-id="5f786-121">扩展方法只能在模块中声明。</span><span class="sxs-lookup"><span data-stu-id="5f786-121">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="5f786-122">通常，在其中定义扩展方法的模块与在其中调用扩展方法的模块不同。</span><span class="sxs-lookup"><span data-stu-id="5f786-122">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="5f786-123">如果需要，将导入包含扩展方法的模块，使其进入范围。</span><span class="sxs-lookup"><span data-stu-id="5f786-123">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="5f786-124">在包含 `Print` 的模块位于范围内后，可以调用方法，就像它是一个不采用任何参数的普通实例方法，如 `ToUpper`：</span><span class="sxs-lookup"><span data-stu-id="5f786-124">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>

[!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]

<span data-ttu-id="5f786-125">下一个示例 `PrintAndPunctuate`，也是 <xref:System.String> 的扩展，这一次使用两个参数定义。</span><span class="sxs-lookup"><span data-stu-id="5f786-125">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="5f786-126">第一个参数 `aString` 确定扩展方法扩展 @no__t。</span><span class="sxs-lookup"><span data-stu-id="5f786-126">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="5f786-127">第二个参数 `punc`，旨在作为在调用方法时作为参数传入的标点符号的字符串。</span><span class="sxs-lookup"><span data-stu-id="5f786-127">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="5f786-128">方法显示后跟标点符号的字符串。</span><span class="sxs-lookup"><span data-stu-id="5f786-128">The method displays the string followed by the punctuation marks.</span></span>

[!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]

<span data-ttu-id="5f786-129">通过在 `punc` 的字符串参数中发送来调用方法： `example.PrintAndPunctuate(".")`</span><span class="sxs-lookup"><span data-stu-id="5f786-129">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>

<span data-ttu-id="5f786-130">下面的示例演示如何定义和调用 @no__t 0 和 @no__t。</span><span class="sxs-lookup"><span data-stu-id="5f786-130">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="5f786-131">在定义模块中导入 <xref:System.Runtime.CompilerServices>，以便能够访问扩展属性。</span><span class="sxs-lookup"><span data-stu-id="5f786-131"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>


```vb
Imports System.Runtime.CompilerServices

Module StringExtensions

    <Extension()>
    Public Sub Print(aString As String)
        Console.WriteLine(aString)
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module
```

<span data-ttu-id="5f786-132">接下来，扩展方法将进入范围并被调用：</span><span class="sxs-lookup"><span data-stu-id="5f786-132">Next, the extension methods are brought into scope and called:</span></span>

```vb
Imports ConsoleApplication2.StringExtensions

Module Module1

    Sub Main()
        Dim example As String = "Example string"
        example.Print()

        example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")
    End Sub
End Module
```

<span data-ttu-id="5f786-133">运行这些或类似扩展方法所需的全部都是在范围内。</span><span class="sxs-lookup"><span data-stu-id="5f786-133">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="5f786-134">如果包含扩展方法的模块位于范围内，则它将显示在 IntelliSense 中，并可作为普通的实例方法调用。</span><span class="sxs-lookup"><span data-stu-id="5f786-134">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>

<span data-ttu-id="5f786-135">请注意，当调用方法时，不会在中为第一个参数发送参数。</span><span class="sxs-lookup"><span data-stu-id="5f786-135">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="5f786-136">前面方法定义中的参数 `aString` 绑定到 `example`，它是调用它们的 @no__t 的实例。</span><span class="sxs-lookup"><span data-stu-id="5f786-136">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="5f786-137">编译器将使用 `example` 作为要发送到第一个参数的参数。</span><span class="sxs-lookup"><span data-stu-id="5f786-137">The compiler will use `example` as the argument sent to the first parameter.</span></span>

<span data-ttu-id="5f786-138">如果为设置为 `Nothing` 的对象调用扩展方法，则扩展方法会执行。</span><span class="sxs-lookup"><span data-stu-id="5f786-138">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="5f786-139">这不适用于普通实例方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-139">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="5f786-140">可以在扩展方法中显式检查 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="5f786-140">You can explicitly check for `Nothing` in the extension method.</span></span>

## <a name="types-that-can-be-extended"></a><span data-ttu-id="5f786-141">可扩展的类型</span><span class="sxs-lookup"><span data-stu-id="5f786-141">Types that can be extended</span></span>

<span data-ttu-id="5f786-142">可以在可在 Visual Basic 参数列表中表示的大多数类型上定义扩展方法，其中包括：</span><span class="sxs-lookup"><span data-stu-id="5f786-142">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>

- <span data-ttu-id="5f786-143">类（引用类型）</span><span class="sxs-lookup"><span data-stu-id="5f786-143">Classes (reference types)</span></span>
- <span data-ttu-id="5f786-144">结构（值类型）</span><span class="sxs-lookup"><span data-stu-id="5f786-144">Structures (value types)</span></span>
- <span data-ttu-id="5f786-145">接口</span><span class="sxs-lookup"><span data-stu-id="5f786-145">Interfaces</span></span>
- <span data-ttu-id="5f786-146">委托</span><span class="sxs-lookup"><span data-stu-id="5f786-146">Delegates</span></span>
- <span data-ttu-id="5f786-147">ByRef 和 ByVal 参数</span><span class="sxs-lookup"><span data-stu-id="5f786-147">ByRef and ByVal arguments</span></span>
- <span data-ttu-id="5f786-148">泛型方法参数</span><span class="sxs-lookup"><span data-stu-id="5f786-148">Generic method parameters</span></span>
- <span data-ttu-id="5f786-149">数组</span><span class="sxs-lookup"><span data-stu-id="5f786-149">Arrays</span></span>

<span data-ttu-id="5f786-150">因为第一个参数指定扩展方法扩展的数据类型，所以它是必需的，并且不能是可选的。</span><span class="sxs-lookup"><span data-stu-id="5f786-150">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="5f786-151">出于此原因，@no__t 参数和 @no__t 1 参数不能是参数列表中的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="5f786-151">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>

<span data-ttu-id="5f786-152">在后期绑定中不考虑扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-152">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="5f786-153">在下面的示例中，语句 `anObject.PrintMe()` 引发了 @no__t 的异常，如果已删除第二个 @no__t 2 扩展方法定义，则会看到相同的异常。</span><span class="sxs-lookup"><span data-stu-id="5f786-153">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>

[!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]

## <a name="best-practices"></a><span data-ttu-id="5f786-154">最佳实践</span><span class="sxs-lookup"><span data-stu-id="5f786-154">Best practices</span></span>

<span data-ttu-id="5f786-155">扩展方法提供了一种方便且功能强大的方法来扩展现有类型。</span><span class="sxs-lookup"><span data-stu-id="5f786-155">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="5f786-156">但是，若要成功使用它们，需要考虑一些要点。</span><span class="sxs-lookup"><span data-stu-id="5f786-156">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="5f786-157">这些注意事项主要适用于类库的作者，但它们可能会影响任何使用扩展方法的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5f786-157">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>

<span data-ttu-id="5f786-158">最常见的情况是，您添加到不属于您的类型的扩展方法比添加到您控制的类型的扩展方法更易受到攻击。</span><span class="sxs-lookup"><span data-stu-id="5f786-158">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="5f786-159">您不拥有的类可能会干扰您的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-159">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>

- <span data-ttu-id="5f786-160">如果存在一个签名与调用语句中的参数兼容的可访问实例成员，并且不需要将自变量转换为参数，则将优先使用该实例方法来处理任何扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-160">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="5f786-161">因此，如果在某个时间点向类添加了相应的实例方法，则您依赖的现有扩展成员可能会变得不可访问。</span><span class="sxs-lookup"><span data-stu-id="5f786-161">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>

- <span data-ttu-id="5f786-162">扩展方法的作者无法阻止其他程序员编写可能优先于原始扩展的冲突扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-162">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>

- <span data-ttu-id="5f786-163">您可以通过将扩展方法置于其自己的命名空间中来提高可靠性。</span><span class="sxs-lookup"><span data-stu-id="5f786-163">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="5f786-164">然后，你的库的使用者可以包括命名空间或排除命名空间，或在命名空间中进行选择，与库的其余部分分开。</span><span class="sxs-lookup"><span data-stu-id="5f786-164">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>

- <span data-ttu-id="5f786-165">扩展接口可能比扩展类更安全，特别是在你不拥有接口或类时。</span><span class="sxs-lookup"><span data-stu-id="5f786-165">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="5f786-166">接口的更改将影响实现它的每个类。</span><span class="sxs-lookup"><span data-stu-id="5f786-166">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="5f786-167">因此，作者在接口中添加或更改方法可能会降低。</span><span class="sxs-lookup"><span data-stu-id="5f786-167">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="5f786-168">但是，如果某个类实现了两个具有相同签名的扩展方法的接口，则这两个扩展方法都不可见。</span><span class="sxs-lookup"><span data-stu-id="5f786-168">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>

- <span data-ttu-id="5f786-169">扩展您可以的最特定类型。</span><span class="sxs-lookup"><span data-stu-id="5f786-169">Extend the most specific type you can.</span></span> <span data-ttu-id="5f786-170">在类型的层次结构中，如果你选择派生了许多其他类型的类型，则引入实例方法或其他可能会干扰你的方法的扩展方法可能有一些层。</span><span class="sxs-lookup"><span data-stu-id="5f786-170">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>

## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="5f786-171">扩展方法、实例方法和属性</span><span class="sxs-lookup"><span data-stu-id="5f786-171">Extension methods, instance methods, and properties</span></span>

<span data-ttu-id="5f786-172">如果范围内实例方法的签名与调用语句的参数兼容，则将优先选择该实例方法作为任何扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-172">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="5f786-173">即使扩展方法更匹配，实例方法也具有优先权。</span><span class="sxs-lookup"><span data-stu-id="5f786-173">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="5f786-174">在下面的示例中，`ExampleClass` 包含一个名为 `ExampleMethod` 的实例方法，该方法具有一个类型为 `Integer` 的参数。</span><span class="sxs-lookup"><span data-stu-id="5f786-174">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="5f786-175">扩展方法 `ExampleMethod` 扩展 `ExampleClass`，并且有一个类型为 `Long` 的参数。</span><span class="sxs-lookup"><span data-stu-id="5f786-175">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>

[!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]

<span data-ttu-id="5f786-176">在以下代码中对 `ExampleMethod` 的第一次调用将调用扩展方法，因为 `arg1` @no__t 为-2，并且仅与扩展方法中的 `Long` 参数兼容。</span><span class="sxs-lookup"><span data-stu-id="5f786-176">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="5f786-177">对 @no__t 的第二次调用具有 @no__t 1 参数，@no__t 为-2，并调用实例方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-177">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>

[!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]

<span data-ttu-id="5f786-178">现在反转两种方法中参数的数据类型：</span><span class="sxs-lookup"><span data-stu-id="5f786-178">Now reverse the data types of the parameters in the two methods:</span></span>

[!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]

<span data-ttu-id="5f786-179">这次 `Main` 中的代码同时调用实例方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-179">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="5f786-180">这是因为 `arg1` 和 @no__t 都具有到 `Long` 的扩大转换，并且在这两种情况下，实例方法优先于扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-180">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>

[!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]

<span data-ttu-id="5f786-181">因此，扩展方法不能替换现有的实例方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-181">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="5f786-182">但是，当扩展方法与实例方法同名但签名不冲突时，这两种方法都可以访问。</span><span class="sxs-lookup"><span data-stu-id="5f786-182">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="5f786-183">例如，如果类 `ExampleClass` 包含不采用任何参数的名为 @no__t 的方法，则允许具有相同名称但具有不同签名的扩展方法，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="5f786-183">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>

[!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]

<span data-ttu-id="5f786-184">此代码的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="5f786-184">The output from this code is as follows:</span></span>

```console
Extension method
Instance method
```

<span data-ttu-id="5f786-185">对于属性，这种情况更简单：如果扩展方法与它所扩展的类的属性具有相同的名称，则扩展方法不可见且无法访问。</span><span class="sxs-lookup"><span data-stu-id="5f786-185">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>

## <a name="extension-method-precedence"></a><span data-ttu-id="5f786-186">扩展方法的优先级</span><span class="sxs-lookup"><span data-stu-id="5f786-186">Extension method precedence</span></span>

<span data-ttu-id="5f786-187">如果两个具有相同签名的扩展方法处于范围内并且可访问，则将调用优先级较高的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-187">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="5f786-188">扩展方法的优先级基于用于使方法进入范围的机制。</span><span class="sxs-lookup"><span data-stu-id="5f786-188">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="5f786-189">以下列表显示优先层次结构（从高到低）。</span><span class="sxs-lookup"><span data-stu-id="5f786-189">The following list shows the precedence hierarchy, from highest to lowest.</span></span>

1. <span data-ttu-id="5f786-190">在当前模块内定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-190">Extension methods defined inside the current module.</span></span>

2. <span data-ttu-id="5f786-191">在当前命名空间中的数据类型或其父命名空间中定义的扩展方法，其优先级高于父命名空间的子命名空间。</span><span class="sxs-lookup"><span data-stu-id="5f786-191">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>

3. <span data-ttu-id="5f786-192">在当前文件的任何类型导入中定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-192">Extension methods defined inside any type imports in the current file.</span></span>

4. <span data-ttu-id="5f786-193">在当前文件中的任何命名空间导入中定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-193">Extension methods defined inside any namespace imports in the current file.</span></span>

5. <span data-ttu-id="5f786-194">在任何项目级类型导入中定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-194">Extension methods defined inside any project-level type imports.</span></span>

6. <span data-ttu-id="5f786-195">在任何项目级命名空间导入中定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-195">Extension methods defined inside any project-level namespace imports.</span></span>

<span data-ttu-id="5f786-196">如果优先顺序不能解析多义性，则可以使用完全限定名称来指定要调用的方法。</span><span class="sxs-lookup"><span data-stu-id="5f786-196">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="5f786-197">如果前面的示例中的 @no__t 0 方法是在名为 `StringExtensions` 的模块中定义的，则完全限定名称 `StringExtensions.Print(example)` 而不是 `example.Print()`。</span><span class="sxs-lookup"><span data-stu-id="5f786-197">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f786-198">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f786-198">See also</span></span>

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="5f786-199">扩展方法</span><span class="sxs-lookup"><span data-stu-id="5f786-199">Extension Methods</span></span>](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [<span data-ttu-id="5f786-200">Module 语句</span><span class="sxs-lookup"><span data-stu-id="5f786-200">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="5f786-201">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="5f786-201">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5f786-202">可选参数</span><span class="sxs-lookup"><span data-stu-id="5f786-202">Optional Parameters</span></span>](optional-parameters.md)
- [<span data-ttu-id="5f786-203">参数数组</span><span class="sxs-lookup"><span data-stu-id="5f786-203">Parameter Arrays</span></span>](parameter-arrays.md)
- [<span data-ttu-id="5f786-204">属性概述</span><span class="sxs-lookup"><span data-stu-id="5f786-204">Attributes overview</span></span>](../../concepts/attributes/index.md)
- [<span data-ttu-id="5f786-205">范围 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f786-205">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
