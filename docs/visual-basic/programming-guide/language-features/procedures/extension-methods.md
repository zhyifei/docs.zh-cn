---
title: "扩展方法 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ExtensionMethods
dev_langs:
- VB
helpviewer_keywords:
- extending data types
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0705929da72bcb3001228a90bbb9d5ba7c248bf7
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="f3884-102">扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3884-102">Extension Methods (Visual Basic)</span></span>
<span data-ttu-id="f3884-103">扩展方法使开发人员能够将自定义功能添加到已定义而无需创建新的派生的类型的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f3884-103">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="f3884-104">扩展方法使您可以用来编写，就好像从现有的类型的实例方法可以调用的方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-104">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3884-105">备注</span><span class="sxs-lookup"><span data-stu-id="f3884-105">Remarks</span></span>  
 <span data-ttu-id="f3884-106">只能是一个扩展方法`Sub`过程或`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="f3884-106">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="f3884-107">不能定义扩展属性、 字段或事件。</span><span class="sxs-lookup"><span data-stu-id="f3884-107">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="f3884-108">所有扩展方法都必须都标记为扩展属性`<Extension()>`从<xref:System.Runtime.CompilerServices?displayProperty=fullName>命名空间。</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f3884-108">All extension methods must be marked with the extension attribute `<Extension()>` from the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace.</span></span>  
  
 <span data-ttu-id="f3884-109">扩展方法定义中的第一个参数指定该方法将扩展的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f3884-109">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="f3884-110">该方法运行时，第一个参数是绑定到调用方法的数据类型的实例。</span><span class="sxs-lookup"><span data-stu-id="f3884-110">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3884-111">示例</span><span class="sxs-lookup"><span data-stu-id="f3884-111">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f3884-112">描述</span><span class="sxs-lookup"><span data-stu-id="f3884-112">Description</span></span>  
 <span data-ttu-id="f3884-113">下面的示例定义`Print`扩展<xref:System.String>数据类型。</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="f3884-113">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="f3884-114">该方法使用`Console.WriteLine`来显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="f3884-114">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="f3884-115">参数`Print`方法， `aString`，建立方法扩展<xref:System.String>类。</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="f3884-115">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>  
  
 <span data-ttu-id="f3884-116">[!code-vb[VbVbalrExtensionMethods #&1;](./codesnippet/VisualBasic/extension-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3884-116">[!code-vb[VbVbalrExtensionMethods#1](./codesnippet/VisualBasic/extension-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="f3884-117">请注意，与扩展特性标记扩展方法定义`<Extension()>`。</span><span class="sxs-lookup"><span data-stu-id="f3884-117">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="f3884-118">将标记在其中定义该方法的模块是可选的但必须标记每个扩展方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-118">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="f3884-119"><xref:System.Runtime.CompilerServices>必须导入才能访问扩展属性。</xref:System.Runtime.CompilerServices></span><span class="sxs-lookup"><span data-stu-id="f3884-119"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>  
  
 <span data-ttu-id="f3884-120">可以仅在模块中声明的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-120">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="f3884-121">通常情况下，在其中定义的扩展方法的模块不可调用它的一个相同的模块。</span><span class="sxs-lookup"><span data-stu-id="f3884-121">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="f3884-122">相反，包含扩展方法是导入的模块，如果需要以使其进入作用域。</span><span class="sxs-lookup"><span data-stu-id="f3884-122">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="f3884-123">在包含该模块后`Print`是在作用域，就好像不采用参数，如的普通实例方法可以调用该方法`ToUpper`:</span><span class="sxs-lookup"><span data-stu-id="f3884-123">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>  
  
 <span data-ttu-id="f3884-124">[!code-vb[VbVbalrExtensionMethods #&2;](./codesnippet/VisualBasic/extension-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3884-124">[!code-vb[VbVbalrExtensionMethods#2](./codesnippet/VisualBasic/extension-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="f3884-125">下面的示例`PrintAndPunctuate`，也是一个扩展<xref:System.String>，这次使用两个参数定义。</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="f3884-125">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="f3884-126">第一个参数， `aString`，建立扩展方法扩展<xref:System.String>。</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="f3884-126">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="f3884-127">第二个参数， `punc`，旨在标点符号的字符串，它在作为参数传递时调用的方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-127">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="f3884-128">该方法显示跟标点符号的字符串。</span><span class="sxs-lookup"><span data-stu-id="f3884-128">The method displays the string followed by the punctuation marks.</span></span>  
  
 <span data-ttu-id="f3884-129">[!code-vb[VbVbalrExtensionMethods #&3;](./codesnippet/VisualBasic/extension-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3884-129">[!code-vb[VbVbalrExtensionMethods#3](./codesnippet/VisualBasic/extension-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="f3884-130">该方法由发送中的字符串参数调用`punc`:`example.PrintAndPunctuate(".")`</span><span class="sxs-lookup"><span data-stu-id="f3884-130">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>  
  
 <span data-ttu-id="f3884-131">下面的示例演示`Print`和`PrintAndPunctuate`定义和调用。</span><span class="sxs-lookup"><span data-stu-id="f3884-131">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="f3884-132"><xref:System.Runtime.CompilerServices>将以导入定义模块以启用扩展属性的访问权限。</xref:System.Runtime.CompilerServices></span><span class="sxs-lookup"><span data-stu-id="f3884-132"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f3884-133">代码</span><span class="sxs-lookup"><span data-stu-id="f3884-133">Code</span></span>  
  
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
  
 <span data-ttu-id="f3884-134">接下来，扩展方法置于范围中，调用。</span><span class="sxs-lookup"><span data-stu-id="f3884-134">Next, the extension methods are brought into scope and called.</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="f3884-135">注释</span><span class="sxs-lookup"><span data-stu-id="f3884-135">Comments</span></span>  
 <span data-ttu-id="f3884-136">来说，只需要能够运行这些或类似的扩展方法是，它们是在作用域中。</span><span class="sxs-lookup"><span data-stu-id="f3884-136">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="f3884-137">如果模块包含扩展方法的方法是在作用域中，它在 IntelliSense 中可见，并可以像调用的普通实例方法那样调用。</span><span class="sxs-lookup"><span data-stu-id="f3884-137">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>  
  
 <span data-ttu-id="f3884-138">请注意，这些方法调用中时，未发送任何参数第一个参数。</span><span class="sxs-lookup"><span data-stu-id="f3884-138">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="f3884-139">参数`aString`在前一种方法中定义绑定到`example`，实例`String`调用的。</span><span class="sxs-lookup"><span data-stu-id="f3884-139">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="f3884-140">编译器将使用`example`作为参数发送到第一个参数。</span><span class="sxs-lookup"><span data-stu-id="f3884-140">The compiler will use `example` as the argument sent to the first parameter.</span></span>  
  
 <span data-ttu-id="f3884-141">如果对设置为对象调用扩展方法时`Nothing`，扩展方法执行。</span><span class="sxs-lookup"><span data-stu-id="f3884-141">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="f3884-142">这不适用于普通实例方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-142">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="f3884-143">您可以显式地检查`Nothing`扩展方法中。</span><span class="sxs-lookup"><span data-stu-id="f3884-143">You can explicitly check for `Nothing` in the extension method.</span></span>  
  
## <a name="types-that-can-be-extended"></a><span data-ttu-id="f3884-144">可以扩展的类型</span><span class="sxs-lookup"><span data-stu-id="f3884-144">Types That Can Be Extended</span></span>  
 <span data-ttu-id="f3884-145">您可以针对可能出现在 Visual Basic 参数列表，其中包括以下的大多数类型定义的扩展方法︰</span><span class="sxs-lookup"><span data-stu-id="f3884-145">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>  
  
-   <span data-ttu-id="f3884-146">类 （引用类型）</span><span class="sxs-lookup"><span data-stu-id="f3884-146">Classes (reference types)</span></span>  
  
-   <span data-ttu-id="f3884-147">结构 （值类型）</span><span class="sxs-lookup"><span data-stu-id="f3884-147">Structures (value types)</span></span>  
  
-   <span data-ttu-id="f3884-148">接口</span><span class="sxs-lookup"><span data-stu-id="f3884-148">Interfaces</span></span>  
  
-   <span data-ttu-id="f3884-149">委托</span><span class="sxs-lookup"><span data-stu-id="f3884-149">Delegates</span></span>  
  
-   <span data-ttu-id="f3884-150">ByRef 和 ByVal 参数</span><span class="sxs-lookup"><span data-stu-id="f3884-150">ByRef and ByVal arguments</span></span>  
  
-   <span data-ttu-id="f3884-151">泛型方法的参数</span><span class="sxs-lookup"><span data-stu-id="f3884-151">Generic method parameters</span></span>  
  
-   <span data-ttu-id="f3884-152">数组</span><span class="sxs-lookup"><span data-stu-id="f3884-152">Arrays</span></span>  
  
 <span data-ttu-id="f3884-153">第一个参数指定的数据类型的扩展方法扩展，因为它是必需的不能是可选的。</span><span class="sxs-lookup"><span data-stu-id="f3884-153">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="f3884-154">由于这个原因，`Optional`参数和`ParamArray`参数不能是参数列表中的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="f3884-154">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="f3884-155">扩展方法不会考虑在后期绑定中。</span><span class="sxs-lookup"><span data-stu-id="f3884-155">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="f3884-156">在下面的示例中，该语句`anObject.PrintMe()`引发<xref:System.MissingMemberException>异常，而相同的异常时将看到第二个`PrintMe`扩展方法定义已删除。</xref:System.MissingMemberException></span><span class="sxs-lookup"><span data-stu-id="f3884-156">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>  
  
 <span data-ttu-id="f3884-157">[!code-vb[VbVbalrExtensionMethods #&9;](./codesnippet/VisualBasic/extension-methods_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3884-157">[!code-vb[VbVbalrExtensionMethods#9](./codesnippet/VisualBasic/extension-methods_4.vb)]</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="f3884-158">最佳做法</span><span class="sxs-lookup"><span data-stu-id="f3884-158">Best Practices</span></span>  
 <span data-ttu-id="f3884-159">扩展方法提供便利和功能强大的方式来扩展现有类型。</span><span class="sxs-lookup"><span data-stu-id="f3884-159">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="f3884-160">但是，若要成功使用，还是有一些需要考虑的要点。</span><span class="sxs-lookup"><span data-stu-id="f3884-160">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="f3884-161">这些注意事项主要适用于作者的类库，但它们可能会影响使用扩展方法的任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="f3884-161">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>  
  
 <span data-ttu-id="f3884-162">大多数情况下，您将添加到不属于您的类型的扩展方法是添加到您控制的类型的扩展方法比更易受到攻击。</span><span class="sxs-lookup"><span data-stu-id="f3884-162">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="f3884-163">多种情况可能不属于您的类中可能会影响您的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-163">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>  
  
-   <span data-ttu-id="f3884-164">如果存在任何可访问的实例成员都与从参数所需参数不收缩转换中调用的语句中，用参数兼容的签名，将优先于任何扩展方法使用实例方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-164">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="f3884-165">因此，如果相应的实例方法添加到在某一时刻的类，您依赖于某个现有扩展成员变得不可访问。</span><span class="sxs-lookup"><span data-stu-id="f3884-165">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>  
  
-   <span data-ttu-id="f3884-166">扩展方法的作者不能防止其他程序员编写冲突的扩展方法可能优先于原来的扩展名。</span><span class="sxs-lookup"><span data-stu-id="f3884-166">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>  
  
-   <span data-ttu-id="f3884-167">可以通过扩展方法置于自己的命名空间来提高可靠性。</span><span class="sxs-lookup"><span data-stu-id="f3884-167">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="f3884-168">您的库的使用者可以包含命名空间或排除它，或在命名空间，独立于库的其余部分之间选择。</span><span class="sxs-lookup"><span data-stu-id="f3884-168">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>  
  
-   <span data-ttu-id="f3884-169">它可能会比要扩展类，特别是如果您不拥有接口或类扩展接口更安全。</span><span class="sxs-lookup"><span data-stu-id="f3884-169">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="f3884-170">在接口中的更改会影响每个类来实现它。</span><span class="sxs-lookup"><span data-stu-id="f3884-170">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="f3884-171">因此，作者不大可能要添加或更改接口中的方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-171">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="f3884-172">但是，如果类实现具有相同签名的扩展方法的两个接口，扩展方法都不是可见的。</span><span class="sxs-lookup"><span data-stu-id="f3884-172">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>  
  
-   <span data-ttu-id="f3884-173">扩展可以最具体的类型。</span><span class="sxs-lookup"><span data-stu-id="f3884-173">Extend the most specific type you can.</span></span> <span data-ttu-id="f3884-174">在类型的层次结构，如果您选择从中派生的许多其他类型，类型有一些图层的实例方法或其他可能会影响您的扩展方法引入的可能性。</span><span class="sxs-lookup"><span data-stu-id="f3884-174">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>  
  
## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="f3884-175">扩展方法、 实例方法和属性</span><span class="sxs-lookup"><span data-stu-id="f3884-175">Extension Methods, Instance Methods, and Properties</span></span>  
 <span data-ttu-id="f3884-176">当范围内实例方法具有与调用的语句的参数兼容的签名时，将任何扩展方法优先选择的实例方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-176">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="f3884-177">实例方法具有优先级，即使扩展方法是更好的匹配。</span><span class="sxs-lookup"><span data-stu-id="f3884-177">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="f3884-178">在下面的示例中，`ExampleClass`包含名为实例方法`ExampleMethod`它具有一个参数类型的`Integer`。</span><span class="sxs-lookup"><span data-stu-id="f3884-178">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="f3884-179">扩展方法`ExampleMethod`扩展`ExampleClass`，并且具有一个类型的参数`Long`。</span><span class="sxs-lookup"><span data-stu-id="f3884-179">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>  
  
 <span data-ttu-id="f3884-180">[!code-vb[VbVbalrExtensionMethods #&4;](./codesnippet/VisualBasic/extension-methods_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3884-180">[!code-vb[VbVbalrExtensionMethods#4](./codesnippet/VisualBasic/extension-methods_5.vb)]</span></span>  
  
 <span data-ttu-id="f3884-181">首次调用`ExampleMethod`下面的代码中调用扩展方法，因为`arg1`是`Long`和仅与兼容`Long`扩展方法中的参数。</span><span class="sxs-lookup"><span data-stu-id="f3884-181">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="f3884-182">第二次调用`ExampleMethod`具有`Integer`参数， `arg2`，它会调用实例方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-182">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>  
  
 <span data-ttu-id="f3884-183">[!code-vb[VbVbalrExtensionMethods #&5;](./codesnippet/VisualBasic/extension-methods_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3884-183">[!code-vb[VbVbalrExtensionMethods#5](./codesnippet/VisualBasic/extension-methods_6.vb)]</span></span>  
  
 <span data-ttu-id="f3884-184">现在反转中这两种方法的参数的数据类型︰</span><span class="sxs-lookup"><span data-stu-id="f3884-184">Now reverse the data types of the parameters in the two methods:</span></span>  
  
 <span data-ttu-id="f3884-185">[!code-vb[VbVbalrExtensionMethods #&6;](./codesnippet/VisualBasic/extension-methods_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3884-185">[!code-vb[VbVbalrExtensionMethods#6](./codesnippet/VisualBasic/extension-methods_7.vb)]</span></span>  
  
 <span data-ttu-id="f3884-186">这次中的代码`Main`两次都调用实例方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-186">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="f3884-187">这是因为两者`arg1`和`arg2`都可以扩大转换为`Long`，并与实例方法优先于这两种情况中的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-187">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>  
  
 <span data-ttu-id="f3884-188">[!code-vb[VbVbalrExtensionMethods #&7;](./codesnippet/VisualBasic/extension-methods_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3884-188">[!code-vb[VbVbalrExtensionMethods#7](./codesnippet/VisualBasic/extension-methods_8.vb)]</span></span>  
  
 <span data-ttu-id="f3884-189">因此，扩展方法不能替换现有的实例方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-189">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="f3884-190">但是，如果扩展方法具有相同的名称作为实例方法，但这些签名不会发生冲突，则这两种方法可以访问。</span><span class="sxs-lookup"><span data-stu-id="f3884-190">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="f3884-191">例如，如果类`ExampleClass`包含一个名为方法`ExampleMethod`不采用任何参数、 扩展方法具有相同名称但不同的签名允许的如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="f3884-191">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>  
  
 <span data-ttu-id="f3884-192">[!code-vb[VbVbalrExtensionMethods #&8;](./codesnippet/VisualBasic/extension-methods_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3884-192">[!code-vb[VbVbalrExtensionMethods#8](./codesnippet/VisualBasic/extension-methods_9.vb)]</span></span>  
  
 <span data-ttu-id="f3884-193">此代码的输出是，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="f3884-193">The output from this code is as follows:</span></span>  
  
 `Extension method`  
  
 `Instance method`  
  
 <span data-ttu-id="f3884-194">这种情况是要简单的属性︰ 如果扩展方法具有相同的名称作为它所扩展的类的属性，扩展方法是不可见的并且不能访问。</span><span class="sxs-lookup"><span data-stu-id="f3884-194">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>  
  
## <a name="extension-method-precedence"></a><span data-ttu-id="f3884-195">扩展方法优先级</span><span class="sxs-lookup"><span data-stu-id="f3884-195">Extension Method Precedence</span></span>  
 <span data-ttu-id="f3884-196">作用域中并且可以访问两个具有相同的签名的扩展方法时，将调用一个具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="f3884-196">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="f3884-197">扩展方法的优先级取决于用来将该方法引入作用域的机制。</span><span class="sxs-lookup"><span data-stu-id="f3884-197">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="f3884-198">以下列表显示了优先级层次结构中的，从高到最低。</span><span class="sxs-lookup"><span data-stu-id="f3884-198">The following list shows the precedence hierarchy, from highest to lowest.</span></span>  
  
1.  <span data-ttu-id="f3884-199">在当前模块中定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-199">Extension methods defined inside the current module.</span></span>  
  
2.  <span data-ttu-id="f3884-200">扩展方法数据类型内定义在当前命名空间或其任何一个的父与子命名空间具有优先权要高于父命名空间。</span><span class="sxs-lookup"><span data-stu-id="f3884-200">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>  
  
3.  <span data-ttu-id="f3884-201">在任何类型的导入在当前文件中定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-201">Extension methods defined inside any type imports in the current file.</span></span>  
  
4.  <span data-ttu-id="f3884-202">在任何命名空间导入当前文件中定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-202">Extension methods defined inside any namespace imports in the current file.</span></span>  
  
5.  <span data-ttu-id="f3884-203">在任何项目级别类型 imports 语句中定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-203">Extension methods defined inside any project-level type imports.</span></span>  
  
6.  <span data-ttu-id="f3884-204">在任何项目级别命名空间导入定义的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-204">Extension methods defined inside any project-level namespace imports.</span></span>  
  
 <span data-ttu-id="f3884-205">如果优先级不能解决多义性问题，可以使用完全限定的名来指定要调用的方法。</span><span class="sxs-lookup"><span data-stu-id="f3884-205">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="f3884-206">如果`Print`在前面的示例中的方法定义一个名为模块中`StringExtensions`，完全限定的名是`StringExtensions.Print(example)`而不是`example.Print()`。</span><span class="sxs-lookup"><span data-stu-id="f3884-206">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3884-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3884-207">See Also</span></span>  
 <span data-ttu-id="f3884-208"><xref:System.Runtime.CompilerServices></xref:System.Runtime.CompilerServices></span><span class="sxs-lookup"><span data-stu-id="f3884-208"><xref:System.Runtime.CompilerServices></span></span>   
 <span data-ttu-id="f3884-209"><xref:System.Runtime.CompilerServices.ExtensionAttribute></xref:System.Runtime.CompilerServices.ExtensionAttribute></span><span class="sxs-lookup"><span data-stu-id="f3884-209"><xref:System.Runtime.CompilerServices.ExtensionAttribute></span></span>   
<span data-ttu-id="f3884-210"> [扩展方法](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="f3884-210"> [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span></span>  
<span data-ttu-id="f3884-211"> [Module 语句](../../../../visual-basic/language-reference/statements/module-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f3884-211"> [Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md) </span></span>  
<span data-ttu-id="f3884-212"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="f3884-212"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="f3884-213"> [可选参数](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="f3884-213"> [Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="f3884-214"> [参数数组](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="f3884-214"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="f3884-215"> [属性概述](../../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="f3884-215"> [Attributes overview](../../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="f3884-216"> [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)</span><span class="sxs-lookup"><span data-stu-id="f3884-216"> [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)</span></span>
