---
title: 通过实例访问共享成员；将不计算限定表达式
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 311f4c025072162e0cfb6b87587f8602d33fcd19
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646871"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a><span data-ttu-id="ea28a-102">通过实例访问共享成员；将不计算限定表达式</span><span class="sxs-lookup"><span data-stu-id="ea28a-102">Access of shared member through an instance; qualifying expression will not be evaluated</span></span>
<span data-ttu-id="ea28a-103">使用类或结构的实例变量访问`Shared`变量、 属性、 过程或在该类或结构中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="ea28a-103">An instance variable of a class or structure is used to access a `Shared` variable, property, procedure, or event defined in that class or structure.</span></span> <span data-ttu-id="ea28a-104">如果使用实例变量访问类或结构，例如常量或枚举，或一个嵌套的类或结构的隐式共享的成员，也可能发生此警告。</span><span class="sxs-lookup"><span data-stu-id="ea28a-104">This warning can also occur if an instance variable is used to access an implicitly shared member of a class or structure, such as a constant or enumeration, or a nested class or structure.</span></span>  
  
 <span data-ttu-id="ea28a-105">共享某个成员的目的是创建仅该成员的一个副本并使该单个副本可供类或结构声明它的每个实例。</span><span class="sxs-lookup"><span data-stu-id="ea28a-105">The purpose of sharing a member is to create only a single copy of that member and make that single copy available to every instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="ea28a-106">为此目的，若要访问与一致`Shared`成员通过其类或结构的名称而不是包含的单独实例，该类或结构的变量。</span><span class="sxs-lookup"><span data-stu-id="ea28a-106">It is consistent with this purpose to access a `Shared` member through the name of its class or structure, rather than through a variable that holds an individual instance of that class or structure.</span></span>  
  
 <span data-ttu-id="ea28a-107">访问`Shared`通过实例变量的成员可以使代码更难以理解通过隐藏该成员是这一事实`Shared`。</span><span class="sxs-lookup"><span data-stu-id="ea28a-107">Accessing a `Shared` member through an instance variable can make your code more difficult to understand by obscuring the fact that the member is `Shared`.</span></span> <span data-ttu-id="ea28a-108">此外，如果此类访问是表达式的一部分执行其他操作，如`Function`返回的共享成员实例的过程，Visual Basic 将忽略表达式以及它将执行的任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="ea28a-108">Furthermore, if such access is part of an expression that performs other actions, such as a `Function` procedure that returns an instance of the shared member, Visual Basic bypasses the expression and any other actions it would otherwise perform.</span></span>  
  
 <span data-ttu-id="ea28a-109">有关详细信息和示例，请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="ea28a-109">For more information and an example, see [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
 <span data-ttu-id="ea28a-110">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="ea28a-110">By default, this message is a warning.</span></span> <span data-ttu-id="ea28a-111">若要深入了解如何隐藏警告或将警告视为错误，请参阅 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="ea28a-111">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ea28a-112">**错误 ID:** BC42025</span><span class="sxs-lookup"><span data-stu-id="ea28a-112">**Error ID:** BC42025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea28a-113">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ea28a-113">To correct this error</span></span>  
  
- <span data-ttu-id="ea28a-114">使用类或结构，它定义的名称`Shared`成员来访问它，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="ea28a-114">Use the name of the class or structure that defines the `Shared` member to access it, as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="ea28a-115">当两个编程元素具有相同名称时，警报是作用域的影响。</span><span class="sxs-lookup"><span data-stu-id="ea28a-115">Be alert for the effects of scope when two programming elements have the same name.</span></span> <span data-ttu-id="ea28a-116">在上一示例中，如果通过使用声明的实例`Dim testClass as testClass = Nothing`，则编译器将调用`testClass.sayHello()`发生时通过类名，并不会出现警告的方法的访问。</span><span class="sxs-lookup"><span data-stu-id="ea28a-116">In the previous example, if you declare an instance by using `Dim testClass as testClass = Nothing`, the compiler treats a call to `testClass.sayHello()` as an access of the method through the class name, and no warning occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea28a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea28a-117">See also</span></span>

- [<span data-ttu-id="ea28a-118">Shared</span><span class="sxs-lookup"><span data-stu-id="ea28a-118">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="ea28a-119">在 Visual Basic 中的作用域</span><span class="sxs-lookup"><span data-stu-id="ea28a-119">Scope in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
