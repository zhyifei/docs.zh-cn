---
title: "函数&lt;过程名&gt;并非在所有代码路径上都返回值 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
dev_langs:
- VB
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
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
ms.openlocfilehash: cec047644bfbf82c5c3c206b23af6b0fc37f834d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="49fd4-102">函数&lt;过程名&gt;并非在所有代码路径上都返回值</span><span class="sxs-lookup"><span data-stu-id="49fd4-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="49fd4-103">函数\<过程名&1;> 并非在所有代码路径上都返回值。</span><span class="sxs-lookup"><span data-stu-id="49fd4-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="49fd4-104">是否缺少 Return 语句？</span><span class="sxs-lookup"><span data-stu-id="49fd4-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="49fd4-105">一个`Function`过程具有至少一个可能不返回值的代码路径。</span><span class="sxs-lookup"><span data-stu-id="49fd4-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="49fd4-106">您可以返回一个介于`Function`处于以下任一过程︰</span><span class="sxs-lookup"><span data-stu-id="49fd4-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="49fd4-107">中包括值[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="49fd4-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="49fd4-108">将值赋给`Function`过程名，然后执行`Exit Function`语句。</span><span class="sxs-lookup"><span data-stu-id="49fd4-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="49fd4-109">将值赋给`Function`过程名，然后执行`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="49fd4-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="49fd4-110">控制权将传递给`Exit Function`或`End Function`和您没有任何值分配到过程名称，该过程返回的返回数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="49fd4-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="49fd4-111">详细信息，请参阅"行为"中[Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="49fd4-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="49fd4-112">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="49fd4-112">By default, this message is a warning.</span></span> <span data-ttu-id="49fd4-113">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="49fd4-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="49fd4-114">**错误 ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="49fd4-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="49fd4-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="49fd4-115">To correct this error</span></span>  
  
-   <span data-ttu-id="49fd4-116">控制流逻辑检查并确保导致返回每个语句之前赋值。</span><span class="sxs-lookup"><span data-stu-id="49fd4-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="49fd4-117">很容易地保证每一次返回从过程返回一个值，如果始终使用`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="49fd4-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="49fd4-118">如果这样做时之前, 的最后一个语句`End Function`应`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="49fd4-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49fd4-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49fd4-119">See Also</span></span>  
 <span data-ttu-id="49fd4-120">[Function 过程](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="49fd4-120">[Function Procedures](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span></span>  
<span data-ttu-id="49fd4-121"> [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="49fd4-121"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="49fd4-122"> [“项目设计器”->“编译”页 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="49fd4-122"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span></span>
