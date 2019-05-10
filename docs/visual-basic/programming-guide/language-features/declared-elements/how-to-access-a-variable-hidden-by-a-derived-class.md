---
title: 如何：访问被派生类 (Visual Basic) 隐藏的变量
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 43f7af1a1b540dd630cc2f228f1e5a6018d7c5d7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610461"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="4b2fb-102">如何：访问被派生类 (Visual Basic) 隐藏的变量</span><span class="sxs-lookup"><span data-stu-id="4b2fb-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>
<span data-ttu-id="4b2fb-103">当在派生类中的代码访问的变量时，编译器通常解析到最接近的可访问版本，它是可访问的版本引用派生步骤最少向后访问类中。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="4b2fb-104">如果在派生类中定义的变量，则代码通常会访问该定义。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>  
  
 <span data-ttu-id="4b2fb-105">如果派生的类变量隐藏基类中的变量，它会隐藏基类版本。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="4b2fb-106">但是，可以通过限定其与访问基类变量`MyBase`关键字。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="4b2fb-107">若要访问被派生类隐藏的基类变量</span><span class="sxs-lookup"><span data-stu-id="4b2fb-107">To access a base class variable hidden by a derived class</span></span>  
  
- <span data-ttu-id="4b2fb-108">在表达式或赋值语句中，变量名称前面加`MyBase`关键字和一个句点 (`.`)。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>  
  
     <span data-ttu-id="4b2fb-109">编译器解析对变量的基类版本的引用。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-109">The compiler resolves the reference to the base class version of the variable.</span></span>  
  
     <span data-ttu-id="4b2fb-110">下面的示例说明了通过继承进行隐藏。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="4b2fb-111">它使两个引用，用来访问隐藏的变量和一个绕开隐藏。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
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
  
     <span data-ttu-id="4b2fb-112">前面的示例中声明变量`shadowString`中类的基类和派生类中隐藏它。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="4b2fb-113">该过程`showStrings`派生类中显示字符串的隐藏版本时名称`shadowString`未限定。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="4b2fb-114">然后，它显示隐藏的版本时`shadowString`是使用限定`MyBase`关键字。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4b2fb-115">可靠编程</span><span class="sxs-lookup"><span data-stu-id="4b2fb-115">Robust Programming</span></span>  
 <span data-ttu-id="4b2fb-116">减少风险的引用被隐藏变量的意外版本，则可以完全限定对隐藏变量的所有引用。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="4b2fb-117">隐藏引入了多个版本具有相同名称的变量。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="4b2fb-118">当代码语句引用的变量名称时，编译器将该引用解析的版本取决于代码语句的位置和限定字符串存在等因素。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="4b2fb-119">这可能会增加引用了错误版本的变量的风险。</span><span class="sxs-lookup"><span data-stu-id="4b2fb-119">This can increase the risk of referring to the wrong version of the variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b2fb-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b2fb-120">See also</span></span>

- [<span data-ttu-id="4b2fb-121">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="4b2fb-121">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="4b2fb-122">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="4b2fb-122">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="4b2fb-123">隐藏和重写之间的差异</span><span class="sxs-lookup"><span data-stu-id="4b2fb-123">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="4b2fb-124">如何：隐藏与您的变量同名的变量</span><span class="sxs-lookup"><span data-stu-id="4b2fb-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="4b2fb-125">如何：隐藏继承的变量</span><span class="sxs-lookup"><span data-stu-id="4b2fb-125">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="4b2fb-126">Shadows</span><span class="sxs-lookup"><span data-stu-id="4b2fb-126">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="4b2fb-127">Overrides</span><span class="sxs-lookup"><span data-stu-id="4b2fb-127">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="4b2fb-128">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="4b2fb-128">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="4b2fb-129">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="4b2fb-129">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
