---
title: 如何：隐藏与您的变量 (Visual Basic 中) 同名的变量
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
ms.openlocfilehash: 3230dac924e9c22231494bfc8b81cd74e356bca3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610320"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="09700-102">如何：隐藏与您的变量 (Visual Basic 中) 同名的变量</span><span class="sxs-lookup"><span data-stu-id="09700-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>
<span data-ttu-id="09700-103">可以隐藏的变量*隐藏*即，它通过将它重新定义具有相同名称的变量。</span><span class="sxs-lookup"><span data-stu-id="09700-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="09700-104">可以隐藏你想要在两种方法中隐藏的变量：</span><span class="sxs-lookup"><span data-stu-id="09700-104">You can shadow the variable you want to hide in two ways:</span></span>  
  
- <span data-ttu-id="09700-105">**通过范围进行隐藏。**</span><span class="sxs-lookup"><span data-stu-id="09700-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="09700-106">您可以通过范围隐藏变量包含你想要隐藏的变量的区域子区域内重新声明变量。</span><span class="sxs-lookup"><span data-stu-id="09700-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>  
  
- <span data-ttu-id="09700-107">**通过继承进行隐藏。**</span><span class="sxs-lookup"><span data-stu-id="09700-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="09700-108">如果在类级别定义你想要隐藏的变量，您可以隐藏它通过继承隐藏其与[Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)派生类中的关键字。</span><span class="sxs-lookup"><span data-stu-id="09700-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>  
  
## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="09700-109">若要隐藏的变量的两种方法</span><span class="sxs-lookup"><span data-stu-id="09700-109">Two Ways to Hide a Variable</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="09700-110">若要通过范围进行隐藏隐藏变量</span><span class="sxs-lookup"><span data-stu-id="09700-110">To hide a variable by shadowing it through scope</span></span>  
  
1. <span data-ttu-id="09700-111">确定定义你想要隐藏的变量的区域，并确定要重新定义它与您的变量在其中一个子区域。</span><span class="sxs-lookup"><span data-stu-id="09700-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>  
  
    |<span data-ttu-id="09700-112">变量的区域</span><span class="sxs-lookup"><span data-stu-id="09700-112">Variable's region</span></span>|<span data-ttu-id="09700-113">允许为重新定义它的子区域</span><span class="sxs-lookup"><span data-stu-id="09700-113">Allowable subregion for redefining it</span></span>|  
    |-----------------------|-------------------------------------------|  
    |<span data-ttu-id="09700-114">模块</span><span class="sxs-lookup"><span data-stu-id="09700-114">Module</span></span>|<span data-ttu-id="09700-115">该模块中的类</span><span class="sxs-lookup"><span data-stu-id="09700-115">A class within the module</span></span>|  
    |<span data-ttu-id="09700-116">类</span><span class="sxs-lookup"><span data-stu-id="09700-116">Class</span></span>|<span data-ttu-id="09700-117">中的类的子类</span><span class="sxs-lookup"><span data-stu-id="09700-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="09700-118">在类内的一个过程</span><span class="sxs-lookup"><span data-stu-id="09700-118">A procedure within the class</span></span>|  
  
     <span data-ttu-id="09700-119">不能为例重新在该过程中，块中的过程变量定义中`If`...`End If`构造或`For`循环。</span><span class="sxs-lookup"><span data-stu-id="09700-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>  
  
2. <span data-ttu-id="09700-120">如果尚不存在，请创建子区域。</span><span class="sxs-lookup"><span data-stu-id="09700-120">Create the subregion if it does not already exist.</span></span>  
  
3. <span data-ttu-id="09700-121">子区域，在编写[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)声明隐藏变量。</span><span class="sxs-lookup"><span data-stu-id="09700-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>  
  
     <span data-ttu-id="09700-122">当子区域内的代码引用的变量名称时，编译器将解析为隐藏变量的引用。</span><span class="sxs-lookup"><span data-stu-id="09700-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>  
  
     <span data-ttu-id="09700-123">下面的示例说明了通过作用域，以及一个引用，它会绕开隐藏进行隐藏。</span><span class="sxs-lookup"><span data-stu-id="09700-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>  
  
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
  
     <span data-ttu-id="09700-124">前面的示例中声明变量`num`在模块级别和在过程级别 (在过程`show`)。</span><span class="sxs-lookup"><span data-stu-id="09700-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="09700-125">本地变量`num`隐藏模块级变量`num`内`show`，因此本地变量设置为 2。</span><span class="sxs-lookup"><span data-stu-id="09700-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="09700-126">但是，没有本地变量为卷影`num`在`useModuleLevelNum`过程。</span><span class="sxs-lookup"><span data-stu-id="09700-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="09700-127">因此，`useModuleLevelNum`模块级变量的值设置为 1。</span><span class="sxs-lookup"><span data-stu-id="09700-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>  
  
     <span data-ttu-id="09700-128">`MsgBox`内调用`show`通过符合条件的可忽略隐藏机制`num`模块名称。</span><span class="sxs-lookup"><span data-stu-id="09700-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="09700-129">因此，它将显示而不是本地变量的模块级变量。</span><span class="sxs-lookup"><span data-stu-id="09700-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="09700-130">若要通过隐藏通过继承隐藏的变量</span><span class="sxs-lookup"><span data-stu-id="09700-130">To hide a variable by shadowing it through inheritance</span></span>  
  
1. <span data-ttu-id="09700-131">请确保你想要隐藏的变量声明在类中，并在类级别 （任何过程之外）。</span><span class="sxs-lookup"><span data-stu-id="09700-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="09700-132">否则不能通过继承隐藏它。</span><span class="sxs-lookup"><span data-stu-id="09700-132">Otherwise you cannot shadow it through inheritance.</span></span>  
  
2. <span data-ttu-id="09700-133">定义派生自变量的类，如果尚不存在的类。</span><span class="sxs-lookup"><span data-stu-id="09700-133">Define a class derived from the variable's class if one does not already exist.</span></span>  
  
3. <span data-ttu-id="09700-134">在派生类中，编写`Dim`声明您的变量的语句。</span><span class="sxs-lookup"><span data-stu-id="09700-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="09700-135">包括[Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="09700-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="09700-136">当在派生类中的代码引用的变量名称时，编译器将解析到您的变量引用。</span><span class="sxs-lookup"><span data-stu-id="09700-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="09700-137">下面的示例说明了通过继承进行隐藏。</span><span class="sxs-lookup"><span data-stu-id="09700-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="09700-138">它使两个引用，用来访问隐藏的变量和一个绕开隐藏。</span><span class="sxs-lookup"><span data-stu-id="09700-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
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
  
     <span data-ttu-id="09700-139">前面的示例中声明变量`shadowString`中类的基类和派生类中隐藏它。</span><span class="sxs-lookup"><span data-stu-id="09700-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="09700-140">该过程`showStrings`派生类中显示字符串的隐藏版本时名称`shadowString`未限定。</span><span class="sxs-lookup"><span data-stu-id="09700-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="09700-141">然后，它显示隐藏的版本时`shadowString`是使用限定`MyBase`关键字。</span><span class="sxs-lookup"><span data-stu-id="09700-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="09700-142">可靠编程</span><span class="sxs-lookup"><span data-stu-id="09700-142">Robust Programming</span></span>  
 <span data-ttu-id="09700-143">隐藏引入了多个版本具有相同名称的变量。</span><span class="sxs-lookup"><span data-stu-id="09700-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="09700-144">当代码语句引用的变量名称时，编译器将该引用解析的版本取决于代码语句的位置和限定字符串存在等因素。</span><span class="sxs-lookup"><span data-stu-id="09700-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="09700-145">这可能会增加被隐藏变量的意外版本中引用的风险。</span><span class="sxs-lookup"><span data-stu-id="09700-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="09700-146">通过完全限定对隐藏变量的所有引用，可以降低该风险。</span><span class="sxs-lookup"><span data-stu-id="09700-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09700-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="09700-147">See also</span></span>

- [<span data-ttu-id="09700-148">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="09700-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="09700-149">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="09700-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="09700-150">隐藏和重写之间的差异</span><span class="sxs-lookup"><span data-stu-id="09700-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="09700-151">如何：隐藏继承的变量</span><span class="sxs-lookup"><span data-stu-id="09700-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="09700-152">如何：访问被派生类隐藏的变量</span><span class="sxs-lookup"><span data-stu-id="09700-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="09700-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="09700-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="09700-154">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="09700-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="09700-155">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="09700-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
