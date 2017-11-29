---
title: "函数 &#39;&lt;过程名称&gt;&#39; 没有 &#39; 在所有代码路径上返回值的 t"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords: BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5244d97a79f2450f44fe05f63510369914375912
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="7bf3e-102">函数 &#39;&lt;过程名称&gt;&#39; 没有 &#39; 在所有代码路径上返回值的 t</span><span class="sxs-lookup"><span data-stu-id="7bf3e-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="7bf3e-103">函数\<过程名称 > 没有在所有代码路径上返回一个值。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="7bf3e-104">是否缺少 Return 语句？</span><span class="sxs-lookup"><span data-stu-id="7bf3e-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="7bf3e-105">A`Function`过程有至少一个通过其代码不会返回一个值的可能路径。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="7bf3e-106">你可以返回一个介于`Function`处于以下任一过程：</span><span class="sxs-lookup"><span data-stu-id="7bf3e-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="7bf3e-107">包括中的值[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="7bf3e-108">将值赋给`Function`过程名，然后执行`Exit Function`语句。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="7bf3e-109">将值赋给`Function`过程名，然后执行`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="7bf3e-110">如果控制权传递给`Exit Function`或`End Function`和未将任何值分配到过程名称，该过程返回的返回数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="7bf3e-111">有关详细信息，请参阅"行为" [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="7bf3e-112">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-112">By default, this message is a warning.</span></span> <span data-ttu-id="7bf3e-113">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="7bf3e-114">**错误 ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="7bf3e-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7bf3e-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7bf3e-115">To correct this error</span></span>  
  
-   <span data-ttu-id="7bf3e-116">请检查控制流逻辑并确保导致返回每个语句之前赋值。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="7bf3e-117">很容易地保证每个返回从过程返回一个值，如果始终使用`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="7bf3e-118">如果你这样做，请在之前的最后一个语句`End Function`应`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="7bf3e-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf3e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bf3e-119">See Also</span></span>  
 [<span data-ttu-id="7bf3e-120">Function 过程</span><span class="sxs-lookup"><span data-stu-id="7bf3e-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [<span data-ttu-id="7bf3e-121">Function 语句</span><span class="sxs-lookup"><span data-stu-id="7bf3e-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="7bf3e-122">“项目设计器”->“编译”页 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7bf3e-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
