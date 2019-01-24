---
title: 函数&#39;&lt;过程名称&gt;&#39;没有&#39;t 上的所有代码路径都返回值
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: b6cc5143aafb6c2554b183a1fc5fb3b1331ec5d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552185"
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="26f63-102">函数&#39;&lt;过程名称&gt;&#39;没有&#39;t 上的所有代码路径都返回值</span><span class="sxs-lookup"><span data-stu-id="26f63-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="26f63-103">函数\<过程名称 > 没有在所有代码路径上返回一个值。</span><span class="sxs-lookup"><span data-stu-id="26f63-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="26f63-104">是否缺少 Return 语句？</span><span class="sxs-lookup"><span data-stu-id="26f63-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="26f63-105">一个`Function`过程包含至少一个可能不会返回一个值的代码路径。</span><span class="sxs-lookup"><span data-stu-id="26f63-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="26f63-106">可以返回一个介于`Function`处于以下任一过程：</span><span class="sxs-lookup"><span data-stu-id="26f63-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="26f63-107">包括中的值[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="26f63-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="26f63-108">向其分配值`Function`过程名，然后执行`Exit Function`语句。</span><span class="sxs-lookup"><span data-stu-id="26f63-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="26f63-109">向其分配值`Function`过程名，然后执行`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="26f63-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="26f63-110">控制权将传递给`Exit Function`或`End Function`和没有分配到过程名称的任何值，该过程返回的返回数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="26f63-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="26f63-111">详细信息，请参阅"行为"中[Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="26f63-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="26f63-112">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="26f63-112">By default, this message is a warning.</span></span> <span data-ttu-id="26f63-113">有关隐藏警告或将警告视为错误的详细信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="26f63-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="26f63-114">**错误 ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="26f63-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="26f63-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="26f63-115">To correct this error</span></span>  
  
-   <span data-ttu-id="26f63-116">检查控制流逻辑，并确保分配导致返回每个语句前的值。</span><span class="sxs-lookup"><span data-stu-id="26f63-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="26f63-117">它是更轻松地保证每个返回从过程返回一个值，如果始终使用`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="26f63-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="26f63-118">如果之前的最后一个语句执行此操作，`End Function`应为`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="26f63-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26f63-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="26f63-119">See also</span></span>
- [<span data-ttu-id="26f63-120">Function 过程</span><span class="sxs-lookup"><span data-stu-id="26f63-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="26f63-121">Function 语句</span><span class="sxs-lookup"><span data-stu-id="26f63-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="26f63-122">“项目设计器”->“编译”页 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26f63-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
