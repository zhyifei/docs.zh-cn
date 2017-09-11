---
title: "一个实例; 通过共享成员访问将不计算限定表达式 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42025
- BC42025
dev_langs:
- VB
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 49dc785131e257b19d0d1d57627ccb6cf8a3c63e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a><span data-ttu-id="e5924-102">通过实例访问共享成员；将不计算限定表达式</span><span class="sxs-lookup"><span data-stu-id="e5924-102">Access of shared member through an instance; qualifying expression will not be evaluated</span></span>
<span data-ttu-id="e5924-103">使用类或结构的实例变量访问`Shared`变量、 属性、 过程中或在该类或结构中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="e5924-103">An instance variable of a class or structure is used to access a `Shared` variable, property, procedure, or event defined in that class or structure.</span></span> <span data-ttu-id="e5924-104">如果实例变量用于访问类或结构，例如常量或枚举中，或一个嵌套的类或结构的隐式共享的成员，也可能发生此警告。</span><span class="sxs-lookup"><span data-stu-id="e5924-104">This warning can also occur if an instance variable is used to access an implicitly shared member of a class or structure, such as a constant or enumeration, or a nested class or structure.</span></span>  
  
 <span data-ttu-id="e5924-105">共享某个成员的目的是创建仅该成员的单个副本并将该单一副本提供给类或结构声明它的每个实例。</span><span class="sxs-lookup"><span data-stu-id="e5924-105">The purpose of sharing a member is to create only a single copy of that member and make that single copy available to every instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="e5924-106">它具有一致性具有访问该目的`Shared`通过其类或结构的名称而不是通过变量包含的单独实例，该类或结构的成员。</span><span class="sxs-lookup"><span data-stu-id="e5924-106">It is consistent with this purpose to access a `Shared` member through the name of its class or structure, rather than through a variable that holds an individual instance of that class or structure.</span></span>  
  
 <span data-ttu-id="e5924-107">访问`Shared`通过实例变量的成员可以使代码更加难以理解通过隐藏该成员是事实`Shared`。</span><span class="sxs-lookup"><span data-stu-id="e5924-107">Accessing a `Shared` member through an instance variable can make your code more difficult to understand by obscuring the fact that the member is `Shared`.</span></span> <span data-ttu-id="e5924-108">此外，如果此类访问是表达式的一部分执行其他操作，如`Function`返回共享成员实例的过程[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]绕过表达式，否则，它会执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="e5924-108">Furthermore, if such access is part of an expression that performs other actions, such as a `Function` procedure that returns an instance of the shared member, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] bypasses the expression and any other actions it would otherwise perform.</span></span>  
  
 <span data-ttu-id="e5924-109">有关详细信息和示例，请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="e5924-109">For more information and an example, see [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
 <span data-ttu-id="e5924-110">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="e5924-110">By default, this message is a warning.</span></span> <span data-ttu-id="e5924-111">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="e5924-111">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e5924-112">**错误 ID:** BC42025</span><span class="sxs-lookup"><span data-stu-id="e5924-112">**Error ID:** BC42025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e5924-113">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e5924-113">To correct this error</span></span>  
  
-   <span data-ttu-id="e5924-114">使用类或结构，它定义的名称`Shared`成员来访问它，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="e5924-114">Use the name of the class or structure that defines the `Shared` member to access it, as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="e5924-115">当两个编程元素具有相同的名称，则发出警报的作用域的效果。</span><span class="sxs-lookup"><span data-stu-id="e5924-115">Be alert for the effects of scope when two programming elements have the same name.</span></span> <span data-ttu-id="e5924-116">在上一示例中，如果通过使用声明实例`Dim testClass as testClass = Nothing`，则编译器将调用`testClass.sayHello()`发生时通过类名，并不会出现警告的方法的访问。</span><span class="sxs-lookup"><span data-stu-id="e5924-116">In the previous example, if you declare an instance by using `Dim testClass as testClass = Nothing`, the compiler treats a call to `testClass.sayHello()` as an access of the method through the class name, and no warning occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5924-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5924-117">See Also</span></span>  
 <span data-ttu-id="e5924-118">[共享](../../../visual-basic/language-reference/modifiers/shared.md) </span><span class="sxs-lookup"><span data-stu-id="e5924-118">[Shared](../../../visual-basic/language-reference/modifiers/shared.md) </span></span>  
<span data-ttu-id="e5924-119"> [在 Visual Basic 中的作用域](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)</span><span class="sxs-lookup"><span data-stu-id="e5924-119"> [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)</span></span>
