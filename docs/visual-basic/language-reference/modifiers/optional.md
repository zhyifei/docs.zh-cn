---
title: Optional (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3aa01c2c1ae731c8fe00fdee24521760db69e624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="optional-visual-basic"></a><span data-ttu-id="34b67-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34b67-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="34b67-103">指定调用该过程时，可以省略过程自变量。</span><span class="sxs-lookup"><span data-stu-id="34b67-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34b67-104">备注</span><span class="sxs-lookup"><span data-stu-id="34b67-104">Remarks</span></span>  
 <span data-ttu-id="34b67-105">对于每个可选参数，你必须作为该参数的默认值指定的常量表达式。</span><span class="sxs-lookup"><span data-stu-id="34b67-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="34b67-106">如果表达式计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)，值数据类型的默认值用作参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="34b67-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="34b67-107">如果参数列表包含一个可选参数，则它后面的每个参数还必须是可选的。</span><span class="sxs-lookup"><span data-stu-id="34b67-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="34b67-108">`Optional` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="34b67-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="34b67-109">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="34b67-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="34b67-110">Function 语句</span><span class="sxs-lookup"><span data-stu-id="34b67-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="34b67-111">Property 语句</span><span class="sxs-lookup"><span data-stu-id="34b67-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="34b67-112">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="34b67-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="34b67-113">当调用过程使用或不带可选参数，您可以按位置或按名称传递自变量。</span><span class="sxs-lookup"><span data-stu-id="34b67-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="34b67-114">有关详细信息，请参阅[按位置和按名称传递自变量](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)。</span><span class="sxs-lookup"><span data-stu-id="34b67-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34b67-115">你还可以通过使用重载定义带可选参数的过程。</span><span class="sxs-lookup"><span data-stu-id="34b67-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="34b67-116">如果你有一个可选参数，你可以定义过程，一个接受参数，一个不的两个重载的的版本。</span><span class="sxs-lookup"><span data-stu-id="34b67-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="34b67-117">有关详细信息，请参阅[过程重载](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="34b67-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34b67-118">示例</span><span class="sxs-lookup"><span data-stu-id="34b67-118">Example</span></span>  
 <span data-ttu-id="34b67-119">下面的示例定义了具有一个可选参数的过程。</span><span class="sxs-lookup"><span data-stu-id="34b67-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="34b67-120">示例</span><span class="sxs-lookup"><span data-stu-id="34b67-120">Example</span></span>  
 <span data-ttu-id="34b67-121">下面的示例演示如何调用按位置传递自变量和自变量按名称传递过程。</span><span class="sxs-lookup"><span data-stu-id="34b67-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="34b67-122">过程有两个可选参数。</span><span class="sxs-lookup"><span data-stu-id="34b67-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="34b67-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34b67-123">See Also</span></span>  
 [<span data-ttu-id="34b67-124">参数列表</span><span class="sxs-lookup"><span data-stu-id="34b67-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="34b67-125">可选参数</span><span class="sxs-lookup"><span data-stu-id="34b67-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="34b67-126">关键字</span><span class="sxs-lookup"><span data-stu-id="34b67-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
