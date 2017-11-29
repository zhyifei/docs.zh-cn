---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06770f05aabedcf13cc9af1970a2c511a30c73b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="0a0c2-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a0c2-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="0a0c2-103">指定过程参数是一个指定类型的元素的可选数组。</span><span class="sxs-lookup"><span data-stu-id="0a0c2-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="0a0c2-104">`ParamArray`可以仅在参数列表的最后一个参数上使用。</span><span class="sxs-lookup"><span data-stu-id="0a0c2-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a0c2-105">备注</span><span class="sxs-lookup"><span data-stu-id="0a0c2-105">Remarks</span></span>  
 <span data-ttu-id="0a0c2-106">`ParamArray`可以将任意数量的参数传递给过程。</span><span class="sxs-lookup"><span data-stu-id="0a0c2-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="0a0c2-107">A`ParamArray`始终使用声明参数[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="0a0c2-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="0a0c2-108">你可以提供一个或多个自变量`ParamArray`参数传递的适当的数据的数组类型，则以逗号分隔列表的值，或执行任何操作根本。</span><span class="sxs-lookup"><span data-stu-id="0a0c2-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="0a0c2-109">有关详细信息，请参阅"调用 ParamArray"[参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="0a0c2-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0a0c2-110">每当你处理数组可以是无限期地大型，没有无限大某种内部容量的你的应用程序的风险。</span><span class="sxs-lookup"><span data-stu-id="0a0c2-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="0a0c2-111">如果你接受从调用代码的参数数组，应测试它的长度，并采取适当的措施，如果你的应用程序太大。</span><span class="sxs-lookup"><span data-stu-id="0a0c2-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="0a0c2-112">`ParamArray` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="0a0c2-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="0a0c2-113">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="0a0c2-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="0a0c2-114">Function 语句</span><span class="sxs-lookup"><span data-stu-id="0a0c2-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="0a0c2-115">Property 语句</span><span class="sxs-lookup"><span data-stu-id="0a0c2-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="0a0c2-116">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="0a0c2-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0a0c2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a0c2-117">See Also</span></span>  
 [<span data-ttu-id="0a0c2-118">关键字</span><span class="sxs-lookup"><span data-stu-id="0a0c2-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="0a0c2-119">参数数组</span><span class="sxs-lookup"><span data-stu-id="0a0c2-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
