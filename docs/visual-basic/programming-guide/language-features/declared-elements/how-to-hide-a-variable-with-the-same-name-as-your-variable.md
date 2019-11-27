---
title: 如何：隐藏与您的变量同名的变量
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
ms.openlocfilehash: 0915adbbabb778b1bdd3b6b30e56725a7e74867c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345358"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="1cc3e-102">如何：隐藏与您的变量同名的变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cc3e-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>

<span data-ttu-id="1cc3e-103">您可以通过隐藏变量来*隐藏该变量*，也就是说，使用同一名称的变量重新定义该变量即可。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="1cc3e-104">您可以通过两种方式隐藏要隐藏的变量：</span><span class="sxs-lookup"><span data-stu-id="1cc3e-104">You can shadow the variable you want to hide in two ways:</span></span>

- <span data-ttu-id="1cc3e-105">**通过范围隐藏。**</span><span class="sxs-lookup"><span data-stu-id="1cc3e-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="1cc3e-106">可以通过范围将其隐藏，方法是在包含要隐藏的变量的区域的子区域内重新声明。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>

- <span data-ttu-id="1cc3e-107">**通过继承隐藏。**</span><span class="sxs-lookup"><span data-stu-id="1cc3e-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="1cc3e-108">如果要隐藏的变量是在类级别定义的，可以通过继承将其隐藏，方法是使用派生类中的[Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)关键字对其进行重新声明。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>

## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="1cc3e-109">用于隐藏变量的两种方法</span><span class="sxs-lookup"><span data-stu-id="1cc3e-109">Two Ways to Hide a Variable</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="1cc3e-110">通过使用范围隐藏变量来隐藏变量</span><span class="sxs-lookup"><span data-stu-id="1cc3e-110">To hide a variable by shadowing it through scope</span></span>

1. <span data-ttu-id="1cc3e-111">确定定义要隐藏的变量的区域，并确定要将其与变量一起重新定义的子区域。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>

    |<span data-ttu-id="1cc3e-112">变量的区域</span><span class="sxs-lookup"><span data-stu-id="1cc3e-112">Variable's region</span></span>|<span data-ttu-id="1cc3e-113">允许用于重新定义的子区域</span><span class="sxs-lookup"><span data-stu-id="1cc3e-113">Allowable subregion for redefining it</span></span>|
    |-----------------------|-------------------------------------------|
    |<span data-ttu-id="1cc3e-114">模块</span><span class="sxs-lookup"><span data-stu-id="1cc3e-114">Module</span></span>|<span data-ttu-id="1cc3e-115">模块内的类</span><span class="sxs-lookup"><span data-stu-id="1cc3e-115">A class within the module</span></span>|
    |<span data-ttu-id="1cc3e-116">实例</span><span class="sxs-lookup"><span data-stu-id="1cc3e-116">Class</span></span>|<span data-ttu-id="1cc3e-117">类中的子类</span><span class="sxs-lookup"><span data-stu-id="1cc3e-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="1cc3e-118">类中的过程</span><span class="sxs-lookup"><span data-stu-id="1cc3e-118">A procedure within the class</span></span>|

    <span data-ttu-id="1cc3e-119">不能在该过程中的块内重新定义过程变量，例如，在 `If``End If` 构造或 `For` 循环中。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>

2. <span data-ttu-id="1cc3e-120">如果子区域尚不存在，则创建它。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-120">Create the subregion if it does not already exist.</span></span>

3. <span data-ttu-id="1cc3e-121">在子区域内，编写声明隐藏变量的[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>

    <span data-ttu-id="1cc3e-122">当子区域内的代码引用变量名时，编译器解析对隐藏变量的引用。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>

    <span data-ttu-id="1cc3e-123">下面的示例说明了通过范围进行的隐藏，以及跳过隐藏的引用。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>

    ```vb
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

    <span data-ttu-id="1cc3e-124">前面的示例在模块级和过程级别（在过程 `show`中）声明变量 `num`。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="1cc3e-125">局部变量 `num` 在 `show`内隐藏模块级变量 `num`，因此本地变量设置为2。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="1cc3e-126">但是，在 `useModuleLevelNum` 过程中，不存在用于隐藏 `num` 的本地变量。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="1cc3e-127">因此，`useModuleLevelNum` 将模块级变量的值设置为1。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>

    <span data-ttu-id="1cc3e-128">`show` 中的 `MsgBox` 调用通过使用模块名称限定 `num`，绕过隐藏机制。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="1cc3e-129">因此，它会显示模块级变量，而不是局部变量。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="1cc3e-130">通过继承隐藏变量来隐藏变量</span><span class="sxs-lookup"><span data-stu-id="1cc3e-130">To hide a variable by shadowing it through inheritance</span></span>

1. <span data-ttu-id="1cc3e-131">确保要隐藏的变量是在类中声明，在类级别（在任何过程之外）声明。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="1cc3e-132">否则，不能通过继承将其隐藏起来。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-132">Otherwise you cannot shadow it through inheritance.</span></span>

2. <span data-ttu-id="1cc3e-133">定义派生自变量的类的类（如果尚不存在）。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-133">Define a class derived from the variable's class if one does not already exist.</span></span>

3. <span data-ttu-id="1cc3e-134">在派生类中，编写声明变量的 `Dim` 语句。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="1cc3e-135">在声明中包含[Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

    <span data-ttu-id="1cc3e-136">当派生类中的代码引用变量名时，编译器会将对变量的引用解析为。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

    <span data-ttu-id="1cc3e-137">下面的示例演示通过继承进行的隐藏。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="1cc3e-138">它创建两个引用，一个用于访问隐藏变量，另一个用于绕过隐藏。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

    ```vb
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

    <span data-ttu-id="1cc3e-139">前面的示例声明了基类中 `shadowString` 的变量，并在派生类中隐藏了该变量。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="1cc3e-140">派生类中的过程 `showStrings` 在名称 `shadowString` 不限定时显示字符串的隐藏版本。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="1cc3e-141">然后，在用 `MyBase` 关键字限定 `shadowString` 时，它会显示隐藏的版本。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="1cc3e-142">可靠的编程</span><span class="sxs-lookup"><span data-stu-id="1cc3e-142">Robust Programming</span></span>

<span data-ttu-id="1cc3e-143">隐藏引入了一个具有相同名称的变量的多个版本。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="1cc3e-144">当代码语句引用变量名时，编译器解析引用的版本取决于一些因素，如代码语句的位置和符合条件的字符串的状态。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="1cc3e-145">这可能会增加引用隐藏变量的意外版本的风险。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="1cc3e-146">您可以通过完全限定对隐藏变量的所有引用来降低风险。</span><span class="sxs-lookup"><span data-stu-id="1cc3e-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="1cc3e-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cc3e-147">See also</span></span>

- [<span data-ttu-id="1cc3e-148">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="1cc3e-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="1cc3e-149">Visual Basic 中的阴影</span><span class="sxs-lookup"><span data-stu-id="1cc3e-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="1cc3e-150">隐藏和重写之间的差异</span><span class="sxs-lookup"><span data-stu-id="1cc3e-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="1cc3e-151">如何：隐藏继承的变量</span><span class="sxs-lookup"><span data-stu-id="1cc3e-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="1cc3e-152">如何：访问被派生类隐藏的变量</span><span class="sxs-lookup"><span data-stu-id="1cc3e-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="1cc3e-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="1cc3e-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="1cc3e-154">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="1cc3e-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="1cc3e-155">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="1cc3e-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
