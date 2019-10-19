---
title: 如何：控制变量的范围 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 23a10bd2d6c0c9f3a13bff864559460c48927e01
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582603"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="f961f-102">如何：控制变量的范围 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f961f-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="f961f-103">通常，变量在声明它的整个区域内处于*范围*内，或者在引用中可见。</span><span class="sxs-lookup"><span data-stu-id="f961f-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="f961f-104">在某些情况下，变量的*访问级别*会影响其作用域。</span><span class="sxs-lookup"><span data-stu-id="f961f-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="f961f-105">有关详细信息，请参阅 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)。</span><span class="sxs-lookup"><span data-stu-id="f961f-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="f961f-106">块或过程级别的作用域</span><span class="sxs-lookup"><span data-stu-id="f961f-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="f961f-107">使变量仅在块中可见</span><span class="sxs-lookup"><span data-stu-id="f961f-107">To make a variable visible only within a block</span></span>  
  
- <span data-ttu-id="f961f-108">将变量的[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)置于该块的起始和终止声明语句之间，例如，在 `For` 循环的 `For` 和 `Next` 语句之间。</span><span class="sxs-lookup"><span data-stu-id="f961f-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="f961f-109">只能从块内引用该变量。</span><span class="sxs-lookup"><span data-stu-id="f961f-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="f961f-110">使变量仅在过程中可见</span><span class="sxs-lookup"><span data-stu-id="f961f-110">To make a variable visible only within a procedure</span></span>  
  
- <span data-ttu-id="f961f-111">将变量的 `Dim` 语句放置在过程中，但在任何块（如 `With` ... `End With` 块）的外部。</span><span class="sxs-lookup"><span data-stu-id="f961f-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="f961f-112">您只能从过程内引用变量，包括过程中包含的任何块。</span><span class="sxs-lookup"><span data-stu-id="f961f-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="f961f-113">模块或命名空间级别的作用域</span><span class="sxs-lookup"><span data-stu-id="f961f-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="f961f-114">为方便起见，单术语*模块级别*同样适用于模块、类和结构。</span><span class="sxs-lookup"><span data-stu-id="f961f-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="f961f-115">模块级别变量的访问级别确定其作用域。</span><span class="sxs-lookup"><span data-stu-id="f961f-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="f961f-116">包含模块、类或结构的命名空间还会影响范围。</span><span class="sxs-lookup"><span data-stu-id="f961f-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="f961f-117">使变量在整个模块、类或结构中可见</span><span class="sxs-lookup"><span data-stu-id="f961f-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="f961f-118">将变量的 `Dim` 语句放入模块、类或结构中，但在任何过程之外。</span><span class="sxs-lookup"><span data-stu-id="f961f-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f961f-119">在 `Dim` 语句中包含[Private](../../../../visual-basic/language-reference/modifiers/private.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="f961f-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="f961f-120">可以从模块、类或结构中的任何位置引用该变量，而不能从外部引用。</span><span class="sxs-lookup"><span data-stu-id="f961f-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="f961f-121">使变量在整个命名空间中可见</span><span class="sxs-lookup"><span data-stu-id="f961f-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="f961f-122">将变量的 `Dim` 语句放入模块、类或结构中，但在任何过程之外。</span><span class="sxs-lookup"><span data-stu-id="f961f-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f961f-123">在 `Dim` 语句中包含[Friend](../../../../visual-basic/language-reference/modifiers/friend.md)或[Public](../../../../visual-basic/language-reference/modifiers/public.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="f961f-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="f961f-124">可以从包含模块、类或结构的命名空间中的任何位置引用该变量。</span><span class="sxs-lookup"><span data-stu-id="f961f-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f961f-125">示例</span><span class="sxs-lookup"><span data-stu-id="f961f-125">Example</span></span>  
 <span data-ttu-id="f961f-126">下面的示例在模块级别声明一个变量，并将其可见性限制为模块中的代码。</span><span class="sxs-lookup"><span data-stu-id="f961f-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```vb  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="f961f-127">在前面的示例中，模块 `demonstrateScope` 中定义的所有过程都可以引用 `strMsg` 的 `String` 变量。</span><span class="sxs-lookup"><span data-stu-id="f961f-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="f961f-128">调用 `usePrivateVariable` 过程时，它将在对话框中显示字符串变量 `strMsg` 的内容。</span><span class="sxs-lookup"><span data-stu-id="f961f-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="f961f-129">对于前面的示例的以下更改，字符串变量 `strMsg` 可以在其声明的命名空间中的任何位置通过代码引用。</span><span class="sxs-lookup"><span data-stu-id="f961f-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="f961f-130">可靠编程</span><span class="sxs-lookup"><span data-stu-id="f961f-130">Robust Programming</span></span>  
 <span data-ttu-id="f961f-131">变量的作用域越窄，使用同一名称的另一个变量无意引用它就越少机会。</span><span class="sxs-lookup"><span data-stu-id="f961f-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="f961f-132">你还可以最大程度地减少引用匹配的问题。</span><span class="sxs-lookup"><span data-stu-id="f961f-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f961f-133">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="f961f-133">.NET Framework Security</span></span>  
 <span data-ttu-id="f961f-134">变量的范围越窄，恶意代码使用它的机会就越小。</span><span class="sxs-lookup"><span data-stu-id="f961f-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f961f-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="f961f-135">See also</span></span>

- [<span data-ttu-id="f961f-136">范围 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f961f-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="f961f-137">生存期（Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f961f-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="f961f-138">Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="f961f-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="f961f-139">变量</span><span class="sxs-lookup"><span data-stu-id="f961f-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="f961f-140">变量声明</span><span class="sxs-lookup"><span data-stu-id="f961f-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="f961f-141">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="f961f-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
