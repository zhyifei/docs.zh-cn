---
title: "如何：隐藏继承的变量 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d2059da873f8b9ec9ea51191139c652a9e01d92b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="8b806-102">如何：隐藏继承的变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b806-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>
<span data-ttu-id="8b806-103">派生的类继承其基类的所有定义。</span><span class="sxs-lookup"><span data-stu-id="8b806-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="8b806-104">如果你想要定义变量使用相同的名称与某一元素的基类，则可以隐藏，或*卷影*，该基类元素，当在派生类中定义你的变量。</span><span class="sxs-lookup"><span data-stu-id="8b806-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="8b806-105">如果这样做，派生类中的代码可访问你的变量，除非显式绕过隐藏的机制。</span><span class="sxs-lookup"><span data-stu-id="8b806-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>  
  
 <span data-ttu-id="8b806-106">你可能想要隐藏继承的变量的另一个原因是为了防止基类修订版本。</span><span class="sxs-lookup"><span data-stu-id="8b806-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="8b806-107">基类可能会经历更改继承的元素的更改。</span><span class="sxs-lookup"><span data-stu-id="8b806-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="8b806-108">如果发生这种情况，`Shadows`修饰符强制从派生类，以解析为你的变量，而不是基类元素的引用。</span><span class="sxs-lookup"><span data-stu-id="8b806-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>  
  
### <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="8b806-109">若要隐藏继承的变量</span><span class="sxs-lookup"><span data-stu-id="8b806-109">To hide an inherited variable</span></span>  
  
1.  <span data-ttu-id="8b806-110">请确保你想要隐藏的变量声明在类级别 （之外任何过程）。</span><span class="sxs-lookup"><span data-stu-id="8b806-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="8b806-111">否则不需要隐藏它。</span><span class="sxs-lookup"><span data-stu-id="8b806-111">Otherwise you do not need to hide it.</span></span>  
  
2.  <span data-ttu-id="8b806-112">在派生类中，编写[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)声明您的变量。</span><span class="sxs-lookup"><span data-stu-id="8b806-112">Inside your derived class, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="8b806-113">与继承的变量使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="8b806-113">Use the same name as that of the inherited variable.</span></span>  
  
3.  <span data-ttu-id="8b806-114">包括[阴影](../../../../visual-basic/language-reference/modifiers/shadows.md)声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="8b806-114">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="8b806-115">当在派生类中的代码引用的变量的名称时，编译器将解析对你的变量的引用。</span><span class="sxs-lookup"><span data-stu-id="8b806-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="8b806-116">下面的示例演示如何隐藏被继承的变量。</span><span class="sxs-lookup"><span data-stu-id="8b806-116">The following example illustrates shadowing of an inherited variable.</span></span>  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="8b806-117">前面的示例声明了变量`shadowString`中的基类和派生类中隐藏它。</span><span class="sxs-lookup"><span data-stu-id="8b806-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="8b806-118">该过程`showStrings`派生类中显示隐藏版本的字符串时名称`shadowString`未限定。</span><span class="sxs-lookup"><span data-stu-id="8b806-118">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="8b806-119">然后，它显示隐藏的版本时`shadowString`是用限定`MyBase`关键字。</span><span class="sxs-lookup"><span data-stu-id="8b806-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8b806-120">可靠编程</span><span class="sxs-lookup"><span data-stu-id="8b806-120">Robust Programming</span></span>  
 <span data-ttu-id="8b806-121">隐藏引入了多个版本具有相同名称的变量。</span><span class="sxs-lookup"><span data-stu-id="8b806-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="8b806-122">当代码语句引用的变量的名称时，编译器将该引用解析的版本取决于因素，如代码语句的位置和限定字符串的状态。</span><span class="sxs-lookup"><span data-stu-id="8b806-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="8b806-123">这会增加引用隐藏的变量的非预期版本的风险。</span><span class="sxs-lookup"><span data-stu-id="8b806-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="8b806-124">你可以通过完全限定到隐藏的变量的所有引用来降低该风险。</span><span class="sxs-lookup"><span data-stu-id="8b806-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b806-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b806-125">See Also</span></span>  
 [<span data-ttu-id="8b806-126">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="8b806-126">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="8b806-127">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="8b806-127">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="8b806-128">隐藏和重写之间的差异</span><span class="sxs-lookup"><span data-stu-id="8b806-128">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [<span data-ttu-id="8b806-129">如何：隐藏与你的变量同名的变量</span><span class="sxs-lookup"><span data-stu-id="8b806-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [<span data-ttu-id="8b806-130">如何：访问被派生类隐藏的变量</span><span class="sxs-lookup"><span data-stu-id="8b806-130">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [<span data-ttu-id="8b806-131">Overrides</span><span class="sxs-lookup"><span data-stu-id="8b806-131">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="8b806-132">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="8b806-132">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="8b806-133">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="8b806-133">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
