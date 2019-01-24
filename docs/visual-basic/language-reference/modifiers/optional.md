---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: 7db5f8afdfe61709aba9569bcee8c0d3aa6ee44f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527037"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="79a2b-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79a2b-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="79a2b-103">指定调用此过程时，可以省略过程自变量。</span><span class="sxs-lookup"><span data-stu-id="79a2b-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79a2b-104">备注</span><span class="sxs-lookup"><span data-stu-id="79a2b-104">Remarks</span></span>  
 <span data-ttu-id="79a2b-105">对于每个可选参数，必须为该参数的默认值指定的常量表达式。</span><span class="sxs-lookup"><span data-stu-id="79a2b-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="79a2b-106">如果表达式的计算结果[Nothing](../../../visual-basic/language-reference/nothing.md)，值数据类型的默认值用作参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="79a2b-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="79a2b-107">如果参数列表包含一个可选参数，则可以跟踪该域控制器的每个参数还必须是可选的。</span><span class="sxs-lookup"><span data-stu-id="79a2b-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="79a2b-108">`Optional` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="79a2b-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="79a2b-109">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="79a2b-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="79a2b-110">Function 语句</span><span class="sxs-lookup"><span data-stu-id="79a2b-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="79a2b-111">Property 语句</span><span class="sxs-lookup"><span data-stu-id="79a2b-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="79a2b-112">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="79a2b-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="79a2b-113">在调用时使用或不带可选参数的过程，您可以按位置或名称传递参数。</span><span class="sxs-lookup"><span data-stu-id="79a2b-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="79a2b-114">有关详细信息，请参阅[按位置和按名称传递自变量](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)。</span><span class="sxs-lookup"><span data-stu-id="79a2b-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79a2b-115">此外可以通过使用重载定义带可选参数的过程。</span><span class="sxs-lookup"><span data-stu-id="79a2b-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="79a2b-116">如果您有一个可选参数，可以定义两个重载的版本的过程，一个接受参数，一个不会。</span><span class="sxs-lookup"><span data-stu-id="79a2b-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="79a2b-117">有关更多信息，请参见 [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="79a2b-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79a2b-118">示例</span><span class="sxs-lookup"><span data-stu-id="79a2b-118">Example</span></span>  
 <span data-ttu-id="79a2b-119">下面的示例定义具有一个可选参数的过程。</span><span class="sxs-lookup"><span data-stu-id="79a2b-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="79a2b-120">示例</span><span class="sxs-lookup"><span data-stu-id="79a2b-120">Example</span></span>  
 <span data-ttu-id="79a2b-121">下面的示例演示如何使用按位置传递的参数和使用按名称传递的参数调用的过程。</span><span class="sxs-lookup"><span data-stu-id="79a2b-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="79a2b-122">该过程有两个可选参数。</span><span class="sxs-lookup"><span data-stu-id="79a2b-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="79a2b-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="79a2b-123">See also</span></span>
- [<span data-ttu-id="79a2b-124">参数列表</span><span class="sxs-lookup"><span data-stu-id="79a2b-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)
- [<span data-ttu-id="79a2b-125">可选参数</span><span class="sxs-lookup"><span data-stu-id="79a2b-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="79a2b-126">关键字</span><span class="sxs-lookup"><span data-stu-id="79a2b-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
