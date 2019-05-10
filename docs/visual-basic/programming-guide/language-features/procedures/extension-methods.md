---
title: 扩展方法 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: 48a2609a1931e55d24d98cd2b336fc16c520c948
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649638"
---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="5fb63-102">扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fb63-102">Extension Methods (Visual Basic)</span></span>
<span data-ttu-id="5fb63-103">扩展方法使开发人员能够将自定义功能添加到已定义而无需创建新的派生的类型的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5fb63-103">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="5fb63-104">扩展方法使其可以编写可以像调用现有类型的实例方法那样调用的方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-104">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fb63-105">备注</span><span class="sxs-lookup"><span data-stu-id="5fb63-105">Remarks</span></span>  
 <span data-ttu-id="5fb63-106">扩展方法只能`Sub`过程或`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="5fb63-106">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="5fb63-107">不能定义扩展属性、 字段或事件。</span><span class="sxs-lookup"><span data-stu-id="5fb63-107">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="5fb63-108">必须使用扩展属性标记所有扩展方法`<Extension()>`从<xref:System.Runtime.CompilerServices?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="5fb63-108">All extension methods must be marked with the extension attribute `<Extension()>` from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="5fb63-109">扩展方法定义中的第一个参数指定该方法所扩展的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5fb63-109">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="5fb63-110">运行方法时，第一个参数是绑定到调用方法的数据类型的实例。</span><span class="sxs-lookup"><span data-stu-id="5fb63-110">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fb63-111">示例</span><span class="sxs-lookup"><span data-stu-id="5fb63-111">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="5fb63-112">描述</span><span class="sxs-lookup"><span data-stu-id="5fb63-112">Description</span></span>  
 <span data-ttu-id="5fb63-113">下面的示例定义`Print`扩展<xref:System.String>数据类型。</span><span class="sxs-lookup"><span data-stu-id="5fb63-113">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="5fb63-114">该方法使用`Console.WriteLine`显示字符串。</span><span class="sxs-lookup"><span data-stu-id="5fb63-114">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="5fb63-115">参数`Print`方法， `aString`，确保方法扩展<xref:System.String>类。</span><span class="sxs-lookup"><span data-stu-id="5fb63-115">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]  
  
 <span data-ttu-id="5fb63-116">请注意，扩展方法定义用扩展特性标记`<Extension()>`。</span><span class="sxs-lookup"><span data-stu-id="5fb63-116">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="5fb63-117">将标记在其中定义该方法的模块是可选的但必须标记每个扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-117">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="5fb63-118"><xref:System.Runtime.CompilerServices> 必须导入才能访问扩展属性。</span><span class="sxs-lookup"><span data-stu-id="5fb63-118"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>  
  
 <span data-ttu-id="5fb63-119">扩展方法可以声明只能在模块中。</span><span class="sxs-lookup"><span data-stu-id="5fb63-119">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="5fb63-120">通常情况下，在其中定义扩展方法的模块不调用它的一个相同的模块。</span><span class="sxs-lookup"><span data-stu-id="5fb63-120">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="5fb63-121">相反，包含扩展方法是导入的模块，如果它必须是以使其进入作用域。</span><span class="sxs-lookup"><span data-stu-id="5fb63-121">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="5fb63-122">包含该模块后`Print`是在作用域，就像普通实例方法，如不采用任何参数，可以调用该方法`ToUpper`:</span><span class="sxs-lookup"><span data-stu-id="5fb63-122">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]  
  
 <span data-ttu-id="5fb63-123">下一步的示例中， `PrintAndPunctuate`，也是一个扩展<xref:System.String>，这次使用两个参数定义。</span><span class="sxs-lookup"><span data-stu-id="5fb63-123">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="5fb63-124">第一个参数， `aString`，确保扩展方法扩展<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="5fb63-124">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="5fb63-125">第二个参数， `punc`，它要用作标点符号的字符串，它在作为参数传递时调用的方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-125">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="5fb63-126">该方法显示跟标点符号的字符串。</span><span class="sxs-lookup"><span data-stu-id="5fb63-126">The method displays the string followed by the punctuation marks.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]  
  
 <span data-ttu-id="5fb63-127">该方法调用中的字符串参数发送`punc`: `example.PrintAndPunctuate(".")`</span><span class="sxs-lookup"><span data-stu-id="5fb63-127">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>  
  
 <span data-ttu-id="5fb63-128">下面的示例演示`Print`和`PrintAndPunctuate`定义和调用。</span><span class="sxs-lookup"><span data-stu-id="5fb63-128">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="5fb63-129"><xref:System.Runtime.CompilerServices> 将以导入定义模块以启用扩展属性的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5fb63-129"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5fb63-130">代码</span><span class="sxs-lookup"><span data-stu-id="5fb63-130">Code</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
  
    <Extension()>   
    Public Sub Print(ByVal aString As String)  
        Console.WriteLine(aString)  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="5fb63-131">接下来，扩展方法引入作用域，名为。</span><span class="sxs-lookup"><span data-stu-id="5fb63-131">Next, the extension methods are brought into scope and called.</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="5fb63-132">注释</span><span class="sxs-lookup"><span data-stu-id="5fb63-132">Comments</span></span>  
 <span data-ttu-id="5fb63-133">所有所需能够运行这些或类似的扩展方法是，它们是在作用域中。</span><span class="sxs-lookup"><span data-stu-id="5fb63-133">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="5fb63-134">如果包含扩展方法的模块在作用域，它在 IntelliSense 中可见，并可以像调用普通实例方法那样调用。</span><span class="sxs-lookup"><span data-stu-id="5fb63-134">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>  
  
 <span data-ttu-id="5fb63-135">请注意，调用方法时, 未发送任何参数第一个参数。</span><span class="sxs-lookup"><span data-stu-id="5fb63-135">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="5fb63-136">参数`aString`前一种方法中定义绑定到`example`，实例`String`调用它们。</span><span class="sxs-lookup"><span data-stu-id="5fb63-136">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="5fb63-137">编译器将使用`example`作为参数发送到第一个参数。</span><span class="sxs-lookup"><span data-stu-id="5fb63-137">The compiler will use `example` as the argument sent to the first parameter.</span></span>  
  
 <span data-ttu-id="5fb63-138">如果设置为某个对象调用扩展方法`Nothing`，执行该扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-138">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="5fb63-139">这不适用于普通实例方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-139">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="5fb63-140">您可以显式检查`Nothing`扩展方法中。</span><span class="sxs-lookup"><span data-stu-id="5fb63-140">You can explicitly check for `Nothing` in the extension method.</span></span>  
  
## <a name="types-that-can-be-extended"></a><span data-ttu-id="5fb63-141">可以扩展的类型</span><span class="sxs-lookup"><span data-stu-id="5fb63-141">Types That Can Be Extended</span></span>  
 <span data-ttu-id="5fb63-142">您可以定义可以出现在 Visual Basic 参数列表，其中包括的大多数类型的扩展方法：</span><span class="sxs-lookup"><span data-stu-id="5fb63-142">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>  
  
- <span data-ttu-id="5fb63-143">类 （引用类型）</span><span class="sxs-lookup"><span data-stu-id="5fb63-143">Classes (reference types)</span></span>  
  
- <span data-ttu-id="5fb63-144">结构 （值类型）</span><span class="sxs-lookup"><span data-stu-id="5fb63-144">Structures (value types)</span></span>  
  
- <span data-ttu-id="5fb63-145">接口</span><span class="sxs-lookup"><span data-stu-id="5fb63-145">Interfaces</span></span>  
  
- <span data-ttu-id="5fb63-146">委托</span><span class="sxs-lookup"><span data-stu-id="5fb63-146">Delegates</span></span>  
  
- <span data-ttu-id="5fb63-147">ByRef 和 ByVal 参数</span><span class="sxs-lookup"><span data-stu-id="5fb63-147">ByRef and ByVal arguments</span></span>  
  
- <span data-ttu-id="5fb63-148">泛型方法参数</span><span class="sxs-lookup"><span data-stu-id="5fb63-148">Generic method parameters</span></span>  
  
- <span data-ttu-id="5fb63-149">数组</span><span class="sxs-lookup"><span data-stu-id="5fb63-149">Arrays</span></span>  
  
 <span data-ttu-id="5fb63-150">第一个参数指定的数据类型的扩展方法扩展，因为它是必需的且不能为可选。</span><span class="sxs-lookup"><span data-stu-id="5fb63-150">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="5fb63-151">因此，`Optional`参数和`ParamArray`参数不能是参数列表中的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="5fb63-151">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="5fb63-152">在后期绑定中不考虑扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-152">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="5fb63-153">在下面的示例中，该语句`anObject.PrintMe()`将引发<xref:System.MissingMemberException>异常，相同的异常时将看到第二个`PrintMe`扩展方法定义已删除。</span><span class="sxs-lookup"><span data-stu-id="5fb63-153">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]  
  
## <a name="best-practices"></a><span data-ttu-id="5fb63-154">最佳做法</span><span class="sxs-lookup"><span data-stu-id="5fb63-154">Best Practices</span></span>  
 <span data-ttu-id="5fb63-155">扩展方法提供一种方便功能强大的方式来扩展现有类型。</span><span class="sxs-lookup"><span data-stu-id="5fb63-155">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="5fb63-156">但是，若要成功使用，还是有要考虑的一些要点。</span><span class="sxs-lookup"><span data-stu-id="5fb63-156">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="5fb63-157">这些注意事项主要适用于作者的类库，但它们可能会影响任何使用扩展方法的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5fb63-157">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>  
  
 <span data-ttu-id="5fb63-158">大多数情况下，您将添加到不属于您的类型的扩展方法是添加到您控制的类型的扩展方法相比更易受到攻击。</span><span class="sxs-lookup"><span data-stu-id="5fb63-158">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="5fb63-159">许多因素可能不属于您的类中可能会干扰你的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-159">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>  
  
- <span data-ttu-id="5fb63-160">如果存在任何可访问的实例成员具有与需要从实参向参数没有收缩转换与调用语句中的参数兼容的签名，将优先于任何扩展方法使用实例方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-160">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="5fb63-161">因此，如果相应的实例方法添加到类在某些时候，你依赖的现有扩展成员变得不可访问。</span><span class="sxs-lookup"><span data-stu-id="5fb63-161">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>  
  
- <span data-ttu-id="5fb63-162">扩展方法作者无法阻止其他程序员编写可能优先于原来的扩展名的冲突扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-162">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>  
  
- <span data-ttu-id="5fb63-163">可以通过将扩展方法放置在自己的命名空间中来提高可靠性。</span><span class="sxs-lookup"><span data-stu-id="5fb63-163">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="5fb63-164">你的库的使用者可以包含的命名空间或排除它，或选择多个命名空间，独立于库的其余部分。</span><span class="sxs-lookup"><span data-stu-id="5fb63-164">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>  
  
- <span data-ttu-id="5fb63-165">它可能是更为安全的做法比扩展类，尤其是如果您不拥有该接口或类扩展接口。</span><span class="sxs-lookup"><span data-stu-id="5fb63-165">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="5fb63-166">在接口中的更改会影响每个类来实现它。</span><span class="sxs-lookup"><span data-stu-id="5fb63-166">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="5fb63-167">因此，作者可能不太可能要添加或更改在接口中的方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-167">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="5fb63-168">但是，如果一个类实现两个具有相同签名的扩展方法的接口，扩展方法都不可见。</span><span class="sxs-lookup"><span data-stu-id="5fb63-168">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>  
  
- <span data-ttu-id="5fb63-169">扩展可以最具体的类型。</span><span class="sxs-lookup"><span data-stu-id="5fb63-169">Extend the most specific type you can.</span></span> <span data-ttu-id="5fb63-170">在类型的层次结构，如果您选择从其派生许多其他类型，类型有可能将引入实例方法或其他可能会影响您的扩展方法的层。</span><span class="sxs-lookup"><span data-stu-id="5fb63-170">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>  
  
## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="5fb63-171">扩展方法、 实例方法和属性</span><span class="sxs-lookup"><span data-stu-id="5fb63-171">Extension Methods, Instance Methods, and Properties</span></span>  
 <span data-ttu-id="5fb63-172">当范围内实例方法具有与调用语句的实参兼容的签名时，将任何扩展方法优先选择的实例方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-172">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="5fb63-173">实例方法具有优先权，即使扩展方法是更好的匹配项。</span><span class="sxs-lookup"><span data-stu-id="5fb63-173">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="5fb63-174">在以下示例中，`ExampleClass`包含名为的实例方法`ExampleMethod`它具有一个参数类型的`Integer`。</span><span class="sxs-lookup"><span data-stu-id="5fb63-174">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="5fb63-175">扩展方法`ExampleMethod`扩展`ExampleClass`，并具有一个类型参数`Long`。</span><span class="sxs-lookup"><span data-stu-id="5fb63-175">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]  
  
 <span data-ttu-id="5fb63-176">首次调用`ExampleMethod`下面的代码中调用扩展方法，因为`arg1`是`Long`并且仅与兼容`Long`扩展方法中的参数。</span><span class="sxs-lookup"><span data-stu-id="5fb63-176">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="5fb63-177">第二次调用`ExampleMethod`已`Integer`自变量， `arg2`，它将调用实例方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-177">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]  
  
 <span data-ttu-id="5fb63-178">现在反转这两种方法中的参数的数据类型：</span><span class="sxs-lookup"><span data-stu-id="5fb63-178">Now reverse the data types of the parameters in the two methods:</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]  
  
 <span data-ttu-id="5fb63-179">这一次中的代码`Main`两次都调用实例方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-179">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="5fb63-180">这是因为两者`arg1`并`arg2`有扩大转换为`Long`，和实例方法优先于这两种情况中的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-180">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]  
  
 <span data-ttu-id="5fb63-181">因此，扩展方法不能替换现有的实例方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-181">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="5fb63-182">但是，如果扩展方法具有相同的名称作为实例方法，但签名不冲突，则可以访问这两种方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-182">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="5fb63-183">例如，如果类`ExampleClass`包含一个名为方法`ExampleMethod`不采用任何参数，具有相同名称的扩展方法，但允许不同的签名，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="5fb63-183">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]  
  
 <span data-ttu-id="5fb63-184">此代码的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="5fb63-184">The output from this code is as follows:</span></span>  
  
 `Extension method`  
  
 `Instance method`  
  
 <span data-ttu-id="5fb63-185">这种情况是使用属性更简单： 如果扩展方法具有与它所扩展的类的属性相同的名称，该扩展方法不可见，且无法访问。</span><span class="sxs-lookup"><span data-stu-id="5fb63-185">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>  
  
## <a name="extension-method-precedence"></a><span data-ttu-id="5fb63-186">扩展方法优先级</span><span class="sxs-lookup"><span data-stu-id="5fb63-186">Extension Method Precedence</span></span>  
 <span data-ttu-id="5fb63-187">作用域中并且可以访问两个具有相同签名的扩展方法时，将调用具有较高的优先级。</span><span class="sxs-lookup"><span data-stu-id="5fb63-187">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="5fb63-188">扩展方法的优先级基于用于将方法引入作用域的机制。</span><span class="sxs-lookup"><span data-stu-id="5fb63-188">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="5fb63-189">以下列表显示了优先级层次结构中的，从最高到最低。</span><span class="sxs-lookup"><span data-stu-id="5fb63-189">The following list shows the precedence hierarchy, from highest to lowest.</span></span>  
  
1. <span data-ttu-id="5fb63-190">在当前模块内定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-190">Extension methods defined inside the current module.</span></span>  
  
2. <span data-ttu-id="5fb63-191">扩展方法内定义数据类型在当前命名空间或其任何一个其父项，其中子命名空间具有更高的优先级比父命名空间。</span><span class="sxs-lookup"><span data-stu-id="5fb63-191">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>  
  
3. <span data-ttu-id="5fb63-192">当前文件中的任何类型导入内定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-192">Extension methods defined inside any type imports in the current file.</span></span>  
  
4. <span data-ttu-id="5fb63-193">当前文件中任何命名空间导入内定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-193">Extension methods defined inside any namespace imports in the current file.</span></span>  
  
5. <span data-ttu-id="5fb63-194">任何项目级类型导入内定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-194">Extension methods defined inside any project-level type imports.</span></span>  
  
6. <span data-ttu-id="5fb63-195">任何项目级命名空间导入内定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-195">Extension methods defined inside any project-level namespace imports.</span></span>  
  
 <span data-ttu-id="5fb63-196">如果优先级不能解决多义性问题，可以使用完全限定的名称来指定要调用的方法。</span><span class="sxs-lookup"><span data-stu-id="5fb63-196">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="5fb63-197">如果`Print`前面的示例中的方法定义一个名为模块中`StringExtensions`，完全限定的名是`StringExtensions.Print(example)`而不是`example.Print()`。</span><span class="sxs-lookup"><span data-stu-id="5fb63-197">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb63-198">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fb63-198">See also</span></span>

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="5fb63-199">扩展方法</span><span class="sxs-lookup"><span data-stu-id="5fb63-199">Extension Methods</span></span>](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [<span data-ttu-id="5fb63-200">Module 语句</span><span class="sxs-lookup"><span data-stu-id="5fb63-200">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="5fb63-201">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="5fb63-201">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5fb63-202">可选参数</span><span class="sxs-lookup"><span data-stu-id="5fb63-202">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="5fb63-203">参数数组</span><span class="sxs-lookup"><span data-stu-id="5fb63-203">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="5fb63-204">属性概述</span><span class="sxs-lookup"><span data-stu-id="5fb63-204">Attributes overview</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="5fb63-205">在 Visual Basic 中的作用域</span><span class="sxs-lookup"><span data-stu-id="5fb63-205">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
