---
title: 通过实例访问共享成员；将不计算限定表达式
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9bbec233435ab728657c1b99e26ab157d4657093
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a><span data-ttu-id="b38d2-102">通过实例访问共享成员；将不计算限定表达式</span><span class="sxs-lookup"><span data-stu-id="b38d2-102">Access of shared member through an instance; qualifying expression will not be evaluated</span></span>
<span data-ttu-id="b38d2-103">使用类或结构的一个实例变量访问`Shared`变量、 属性、 过程或在该类或结构中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="b38d2-103">An instance variable of a class or structure is used to access a `Shared` variable, property, procedure, or event defined in that class or structure.</span></span> <span data-ttu-id="b38d2-104">如果使用实例变量访问的类或结构，例如常量或枚举，或一个嵌套的类或结构的隐式共享的成员，也会发生此警告。</span><span class="sxs-lookup"><span data-stu-id="b38d2-104">This warning can also occur if an instance variable is used to access an implicitly shared member of a class or structure, such as a constant or enumeration, or a nested class or structure.</span></span>  
  
 <span data-ttu-id="b38d2-105">共享成员的目的是创建仅该成员的单个副本并将该单个副本提供的类或结构声明它的每个实例。</span><span class="sxs-lookup"><span data-stu-id="b38d2-105">The purpose of sharing a member is to create only a single copy of that member and make that single copy available to every instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="b38d2-106">它是与此目的访问一致`Shared`成员通过其类或结构的名称而不是包含的单独实例，该类或结构的变量。</span><span class="sxs-lookup"><span data-stu-id="b38d2-106">It is consistent with this purpose to access a `Shared` member through the name of its class or structure, rather than through a variable that holds an individual instance of that class or structure.</span></span>  
  
 <span data-ttu-id="b38d2-107">访问`Shared`成员通过实例变量会导致代码更难理解通过隐藏该成员是事实`Shared`。</span><span class="sxs-lookup"><span data-stu-id="b38d2-107">Accessing a `Shared` member through an instance variable can make your code more difficult to understand by obscuring the fact that the member is `Shared`.</span></span> <span data-ttu-id="b38d2-108">此外，如果表达式的一部分进行访问时，将执行其他操作，如`Function`返回共享的成员的实例的过程，Visual Basic 将忽略表达式以及它将执行的任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="b38d2-108">Furthermore, if such access is part of an expression that performs other actions, such as a `Function` procedure that returns an instance of the shared member, Visual Basic bypasses the expression and any other actions it would otherwise perform.</span></span>  
  
 <span data-ttu-id="b38d2-109">有关详细信息及示例，请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="b38d2-109">For more information and an example, see [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
 <span data-ttu-id="b38d2-110">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="b38d2-110">By default, this message is a warning.</span></span> <span data-ttu-id="b38d2-111">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="b38d2-111">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="b38d2-112">**错误 ID:** BC42025</span><span class="sxs-lookup"><span data-stu-id="b38d2-112">**Error ID:** BC42025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b38d2-113">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b38d2-113">To correct this error</span></span>  
  
-   <span data-ttu-id="b38d2-114">使用的类或结构，它定义名称`Shared`成员来访问它，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="b38d2-114">Use the name of the class or structure that defines the `Shared` member to access it, as shown in the following example.</span></span>  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
>  <span data-ttu-id="b38d2-115">当两个编程元素具有相同名称时，则发出警报的作用域的效果。</span><span class="sxs-lookup"><span data-stu-id="b38d2-115">Be alert for the effects of scope when two programming elements have the same name.</span></span> <span data-ttu-id="b38d2-116">在上一示例中，如果你使用声明实例`Dim testClass as testClass = Nothing`，编译器将调用`testClass.sayHello()`通过类名称和任何警告的方法的访问权限发生时。</span><span class="sxs-lookup"><span data-stu-id="b38d2-116">In the previous example, if you declare an instance by using `Dim testClass as testClass = Nothing`, the compiler treats a call to `testClass.sayHello()` as an access of the method through the class name, and no warning occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b38d2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b38d2-117">See Also</span></span>  
 [<span data-ttu-id="b38d2-118">Shared</span><span class="sxs-lookup"><span data-stu-id="b38d2-118">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="b38d2-119">在 Visual Basic 中的作用域</span><span class="sxs-lookup"><span data-stu-id="b38d2-119">Scope in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
