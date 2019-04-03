---
title: 如何：控制变量 (Visual Basic 中) 的作用域
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
ms.openlocfilehash: ef7957a991718112fe01c4fa3a85f29b9226abd3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818718"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="94d07-102">如何：控制变量 (Visual Basic 中) 的作用域</span><span class="sxs-lookup"><span data-stu-id="94d07-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="94d07-103">通常情况下，变量位于*作用域*，或作为参考，整个声明它的区域可见。</span><span class="sxs-lookup"><span data-stu-id="94d07-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="94d07-104">在某些情况下，该变量的*访问级别*可能会影响其作用域。</span><span class="sxs-lookup"><span data-stu-id="94d07-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="94d07-105">有关详细信息，请参阅 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)。</span><span class="sxs-lookup"><span data-stu-id="94d07-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="94d07-106">在块或过程级别的作用域</span><span class="sxs-lookup"><span data-stu-id="94d07-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="94d07-107">若要使变量仅在一个块中可见</span><span class="sxs-lookup"><span data-stu-id="94d07-107">To make a variable visible only within a block</span></span>  
  
-   <span data-ttu-id="94d07-108">位置[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)变量之间的起始和终止声明语句的该块中，例如之间`For`并`Next`语句的`For`循环。</span><span class="sxs-lookup"><span data-stu-id="94d07-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="94d07-109">您可以引用该变量只能在块中。</span><span class="sxs-lookup"><span data-stu-id="94d07-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="94d07-110">若要使变量仅在一个过程中可见</span><span class="sxs-lookup"><span data-stu-id="94d07-110">To make a variable visible only within a procedure</span></span>  
  
-   <span data-ttu-id="94d07-111">位置`Dim`在过程内但在任何块外部变量的语句 (如`With`...`End With`块)。</span><span class="sxs-lookup"><span data-stu-id="94d07-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="94d07-112">您可以参考中的过程，包括在过程中包含的所有块内仅从变量。</span><span class="sxs-lookup"><span data-stu-id="94d07-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="94d07-113">在模块或 Namespace 级别的作用域</span><span class="sxs-lookup"><span data-stu-id="94d07-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="94d07-114">为方便起见，单个字词*模块级别*同样适用于模块、 类和结构。</span><span class="sxs-lookup"><span data-stu-id="94d07-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="94d07-115">模块级变量的访问级别确定其作用域。</span><span class="sxs-lookup"><span data-stu-id="94d07-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="94d07-116">包含模块、 类或结构的命名空间还会影响作用域。</span><span class="sxs-lookup"><span data-stu-id="94d07-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="94d07-117">若要使变量在整个模块、 类或结构可见</span><span class="sxs-lookup"><span data-stu-id="94d07-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1.  <span data-ttu-id="94d07-118">位置`Dim`内部模块、 类或结构，但在任何过程外部变量的语句。</span><span class="sxs-lookup"><span data-stu-id="94d07-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="94d07-119">包括[私有](../../../../visual-basic/language-reference/modifiers/private.md)中的关键字`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="94d07-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3.  <span data-ttu-id="94d07-120">您可以参考中的变量中的模块、 类或结构的任意位置，但不能从其外部。</span><span class="sxs-lookup"><span data-stu-id="94d07-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="94d07-121">若要使变量在整个命名空间内可见</span><span class="sxs-lookup"><span data-stu-id="94d07-121">To make a variable visible throughout a namespace</span></span>  
  
1.  <span data-ttu-id="94d07-122">位置`Dim`内部模块、 类或结构，但在任何过程外部变量的语句。</span><span class="sxs-lookup"><span data-stu-id="94d07-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="94d07-123">包括[友元](../../../../visual-basic/language-reference/modifiers/friend.md)或[公共](../../../../visual-basic/language-reference/modifiers/public.md)中的关键字`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="94d07-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3.  <span data-ttu-id="94d07-124">可以引用从任何位置的变量中包含模块、 类或结构的命名空间。</span><span class="sxs-lookup"><span data-stu-id="94d07-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94d07-125">示例</span><span class="sxs-lookup"><span data-stu-id="94d07-125">Example</span></span>  
 <span data-ttu-id="94d07-126">以下示例声明在模块级别的变量，并限制其对模块中的代码的可见性。</span><span class="sxs-lookup"><span data-stu-id="94d07-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```  
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
  
 <span data-ttu-id="94d07-127">在前面的示例中，在模块中定义的所有过程`demonstrateScope`可以指`String`变量`strMsg`。</span><span class="sxs-lookup"><span data-stu-id="94d07-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="94d07-128">当`usePrivateVariable`调用过程，它显示的字符串变量内容`strMsg`对话框框中。</span><span class="sxs-lookup"><span data-stu-id="94d07-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="94d07-129">与前面的示例中，字符串变量进行如下更改`strMsg`可以由其声明的命名空间中的任意位置的代码引用。</span><span class="sxs-lookup"><span data-stu-id="94d07-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="94d07-130">可靠编程</span><span class="sxs-lookup"><span data-stu-id="94d07-130">Robust Programming</span></span>  
 <span data-ttu-id="94d07-131">变量，减少了必须为意外引用它来替换具有相同名称的另一个变量的范围越窄。</span><span class="sxs-lookup"><span data-stu-id="94d07-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="94d07-132">此外可以尽量减少引用匹配的问题。</span><span class="sxs-lookup"><span data-stu-id="94d07-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="94d07-133">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="94d07-133">.NET Framework Security</span></span>  
 <span data-ttu-id="94d07-134">变量的范围越窄，它使用恶意代码可以进行不正确的较小的可能性。</span><span class="sxs-lookup"><span data-stu-id="94d07-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94d07-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="94d07-135">See also</span></span>

- [<span data-ttu-id="94d07-136">在 Visual Basic 中的作用域</span><span class="sxs-lookup"><span data-stu-id="94d07-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="94d07-137">在 Visual Basic 中的生存期</span><span class="sxs-lookup"><span data-stu-id="94d07-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="94d07-138">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="94d07-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="94d07-139">变量</span><span class="sxs-lookup"><span data-stu-id="94d07-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="94d07-140">变量声明</span><span class="sxs-lookup"><span data-stu-id="94d07-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="94d07-141">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="94d07-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
