---
title: 如何：隐藏与您的变量同名的变量 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: a7ebc4eb44592800decd5ef943750f0cd845afb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653113"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="4e2db-102">如何：隐藏与您的变量同名的变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e2db-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>
<span data-ttu-id="4e2db-103">可以隐藏由变量*隐藏*也就是说，它通过将它重新定义具有相同名称的变量。</span><span class="sxs-lookup"><span data-stu-id="4e2db-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="4e2db-104">你可以隐藏你想要在两种方式中隐藏的变量：</span><span class="sxs-lookup"><span data-stu-id="4e2db-104">You can shadow the variable you want to hide in two ways:</span></span>  
  
-   <span data-ttu-id="4e2db-105">**通过范围进行隐藏。**</span><span class="sxs-lookup"><span data-stu-id="4e2db-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="4e2db-106">你可以通过范围隐藏隐藏包含你想要隐藏的变量的区域的子区域内。</span><span class="sxs-lookup"><span data-stu-id="4e2db-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>  
  
-   <span data-ttu-id="4e2db-107">**通过继承进行隐藏。**</span><span class="sxs-lookup"><span data-stu-id="4e2db-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="4e2db-108">如果你想要隐藏的变量在类级别定义的可以隐藏它通过继承隐藏其与[阴影](../../../../visual-basic/language-reference/modifiers/shadows.md)派生类中的关键字。</span><span class="sxs-lookup"><span data-stu-id="4e2db-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>  
  
## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="4e2db-109">两种方法来隐藏的变量</span><span class="sxs-lookup"><span data-stu-id="4e2db-109">Two Ways to Hide a Variable</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="4e2db-110">若要隐藏变量通过范围进行隐藏</span><span class="sxs-lookup"><span data-stu-id="4e2db-110">To hide a variable by shadowing it through scope</span></span>  
  
1.  <span data-ttu-id="4e2db-111">确定定义你想要隐藏，的变量的区域，并确定要对其重新定义与你的变量在其中一个子区域。</span><span class="sxs-lookup"><span data-stu-id="4e2db-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>  
  
    |<span data-ttu-id="4e2db-112">变量的区域</span><span class="sxs-lookup"><span data-stu-id="4e2db-112">Variable's region</span></span>|<span data-ttu-id="4e2db-113">为重新定义它的允许子区域</span><span class="sxs-lookup"><span data-stu-id="4e2db-113">Allowable subregion for redefining it</span></span>|  
    |-----------------------|-------------------------------------------|  
    |<span data-ttu-id="4e2db-114">模块</span><span class="sxs-lookup"><span data-stu-id="4e2db-114">Module</span></span>|<span data-ttu-id="4e2db-115">该模块中的类</span><span class="sxs-lookup"><span data-stu-id="4e2db-115">A class within the module</span></span>|  
    |<span data-ttu-id="4e2db-116">类</span><span class="sxs-lookup"><span data-stu-id="4e2db-116">Class</span></span>|<span data-ttu-id="4e2db-117">中的类的子类</span><span class="sxs-lookup"><span data-stu-id="4e2db-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="4e2db-118">一个类中的过程</span><span class="sxs-lookup"><span data-stu-id="4e2db-118">A procedure within the class</span></span>|  
  
     <span data-ttu-id="4e2db-119">不能例如重新在该过程中，块中的过程变量定义在`If`...`End If`构造或`For`循环。</span><span class="sxs-lookup"><span data-stu-id="4e2db-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>  
  
2.  <span data-ttu-id="4e2db-120">如果不存在，请创建子区域。</span><span class="sxs-lookup"><span data-stu-id="4e2db-120">Create the subregion if it does not already exist.</span></span>  
  
3.  <span data-ttu-id="4e2db-121">在子区域内，编写[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)声明隐藏的变量。</span><span class="sxs-lookup"><span data-stu-id="4e2db-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>  
  
     <span data-ttu-id="4e2db-122">当子区域内的代码引用的变量的名称时，编译器将解析对隐藏的变量的引用。</span><span class="sxs-lookup"><span data-stu-id="4e2db-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>  
  
     <span data-ttu-id="4e2db-123">下面的示例演示通过作用域，以及绕开隐藏的引用进行隐藏。</span><span class="sxs-lookup"><span data-stu-id="4e2db-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>  
  
    ```  
    Module shadowByScope  
        ' The following statement declares num as a module-level variable.  
        Public num As Integer  
        Sub show()  
            ' The following statement declares num as a local variable.  
            Dim num As Integer  
            ' The following statement sets the value of the local variable.  
            num = 2  
            ' The following statement displays the module-level variable.  
            MsgBox(CStr(shadowByScope.num))  
        End Sub  
        Sub useModuleLevelNum()  
            ' The following statement sets the value of the module-level variable.  
            num = 1  
            show()  
        End Sub  
    End Module  
    ```  
  
     <span data-ttu-id="4e2db-124">前面的示例声明了变量`num`在模块级别和过程级别 (在过程中`show`)。</span><span class="sxs-lookup"><span data-stu-id="4e2db-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="4e2db-125">本地变量`num`隐藏模块级变量`num`内`show`，因此本地变量设置为 2。</span><span class="sxs-lookup"><span data-stu-id="4e2db-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="4e2db-126">但是，没有任何局部变量为卷影`num`中`useModuleLevelNum`过程。</span><span class="sxs-lookup"><span data-stu-id="4e2db-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="4e2db-127">因此，`useModuleLevelNum`模块级变量的值设置为 1。</span><span class="sxs-lookup"><span data-stu-id="4e2db-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>  
  
     <span data-ttu-id="4e2db-128">`MsgBox`内调用`show`隐藏机制将绕过通过限定`num`使用模块名称。</span><span class="sxs-lookup"><span data-stu-id="4e2db-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="4e2db-129">因此，它显示模块级变量，而不是本地的变量。</span><span class="sxs-lookup"><span data-stu-id="4e2db-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="4e2db-130">若要通过隐藏通过继承隐藏的变量</span><span class="sxs-lookup"><span data-stu-id="4e2db-130">To hide a variable by shadowing it through inheritance</span></span>  
  
1.  <span data-ttu-id="4e2db-131">请确保你想要隐藏的变量声明在类中，并在类级别 （之外任何过程）。</span><span class="sxs-lookup"><span data-stu-id="4e2db-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="4e2db-132">否则不能通过继承隐藏它。</span><span class="sxs-lookup"><span data-stu-id="4e2db-132">Otherwise you cannot shadow it through inheritance.</span></span>  
  
2.  <span data-ttu-id="4e2db-133">定义派生自变量的类，如果尚不存在的类。</span><span class="sxs-lookup"><span data-stu-id="4e2db-133">Define a class derived from the variable's class if one does not already exist.</span></span>  
  
3.  <span data-ttu-id="4e2db-134">在派生类中，编写`Dim`语句声明您的变量。</span><span class="sxs-lookup"><span data-stu-id="4e2db-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="4e2db-135">包括[阴影](../../../../visual-basic/language-reference/modifiers/shadows.md)声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="4e2db-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="4e2db-136">当在派生类中的代码引用的变量的名称时，编译器将解析对你的变量的引用。</span><span class="sxs-lookup"><span data-stu-id="4e2db-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="4e2db-137">下面的示例演示通过继承进行隐藏。</span><span class="sxs-lookup"><span data-stu-id="4e2db-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="4e2db-138">它使两个引用，一个访问隐藏的变量，一个绕开隐藏。</span><span class="sxs-lookup"><span data-stu-id="4e2db-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
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
  
     <span data-ttu-id="4e2db-139">前面的示例声明了变量`shadowString`中的基类和派生类中隐藏它。</span><span class="sxs-lookup"><span data-stu-id="4e2db-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="4e2db-140">该过程`showStrings`派生类中显示隐藏版本的字符串时名称`shadowString`未限定。</span><span class="sxs-lookup"><span data-stu-id="4e2db-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="4e2db-141">然后，它显示隐藏的版本时`shadowString`是用限定`MyBase`关键字。</span><span class="sxs-lookup"><span data-stu-id="4e2db-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4e2db-142">可靠编程</span><span class="sxs-lookup"><span data-stu-id="4e2db-142">Robust Programming</span></span>  
 <span data-ttu-id="4e2db-143">隐藏引入了多个版本具有相同名称的变量。</span><span class="sxs-lookup"><span data-stu-id="4e2db-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="4e2db-144">当代码语句引用的变量的名称时，编译器将该引用解析的版本取决于因素，如代码语句的位置和限定字符串的状态。</span><span class="sxs-lookup"><span data-stu-id="4e2db-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="4e2db-145">这会增加引用隐藏的变量的非预期版本的风险。</span><span class="sxs-lookup"><span data-stu-id="4e2db-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="4e2db-146">你可以通过完全限定到隐藏的变量的所有引用来降低该风险。</span><span class="sxs-lookup"><span data-stu-id="4e2db-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2db-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e2db-147">See Also</span></span>  
 [<span data-ttu-id="4e2db-148">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="4e2db-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="4e2db-149">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="4e2db-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="4e2db-150">隐藏和重写之间的差异</span><span class="sxs-lookup"><span data-stu-id="4e2db-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [<span data-ttu-id="4e2db-151">如何：隐藏继承的变量</span><span class="sxs-lookup"><span data-stu-id="4e2db-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [<span data-ttu-id="4e2db-152">如何：访问被派生类隐藏的变量</span><span class="sxs-lookup"><span data-stu-id="4e2db-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [<span data-ttu-id="4e2db-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="4e2db-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="4e2db-154">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="4e2db-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="4e2db-155">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="4e2db-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
