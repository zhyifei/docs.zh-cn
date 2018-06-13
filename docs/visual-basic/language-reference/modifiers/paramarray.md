---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: be8ddb7f9ba08535d12890d1c5c82a9b7b485f3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597355"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="20a95-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20a95-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="20a95-103">指定过程参数是一个指定类型的元素的可选数组。</span><span class="sxs-lookup"><span data-stu-id="20a95-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="20a95-104">`ParamArray` 可以仅在参数列表的最后一个参数上使用。</span><span class="sxs-lookup"><span data-stu-id="20a95-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20a95-105">备注</span><span class="sxs-lookup"><span data-stu-id="20a95-105">Remarks</span></span>  
 <span data-ttu-id="20a95-106">`ParamArray` 可以将任意数量的参数传递给过程。</span><span class="sxs-lookup"><span data-stu-id="20a95-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="20a95-107">A`ParamArray`始终使用声明参数[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="20a95-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="20a95-108">你可以提供一个或多个自变量`ParamArray`参数传递的适当的数据的数组类型，则以逗号分隔列表的值，或执行任何操作根本。</span><span class="sxs-lookup"><span data-stu-id="20a95-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="20a95-109">有关详细信息，请参阅"调用 ParamArray"[参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="20a95-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20a95-110">每当你处理数组可以是无限期地大型，没有无限大某种内部容量的你的应用程序的风险。</span><span class="sxs-lookup"><span data-stu-id="20a95-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="20a95-111">如果你接受从调用代码的参数数组，应测试它的长度，并采取适当的措施，如果你的应用程序太大。</span><span class="sxs-lookup"><span data-stu-id="20a95-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="20a95-112">`ParamArray` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="20a95-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="20a95-113">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="20a95-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="20a95-114">Function 语句</span><span class="sxs-lookup"><span data-stu-id="20a95-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="20a95-115">Property 语句</span><span class="sxs-lookup"><span data-stu-id="20a95-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="20a95-116">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="20a95-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="20a95-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="20a95-117">See Also</span></span>  
 [<span data-ttu-id="20a95-118">关键字</span><span class="sxs-lookup"><span data-stu-id="20a95-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="20a95-119">参数数组</span><span class="sxs-lookup"><span data-stu-id="20a95-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
