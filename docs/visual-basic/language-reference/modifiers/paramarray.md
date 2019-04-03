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
ms.openlocfilehash: b9dee0fc876c6e7a02d085db7db4bf1c5dd2c68d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816650"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="368c9-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="368c9-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="368c9-103">指定过程参数采用一个可选的指定类型的元素的数组。</span><span class="sxs-lookup"><span data-stu-id="368c9-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="368c9-104">`ParamArray` 可以使用仅在参数列表的最后一个参数上。</span><span class="sxs-lookup"><span data-stu-id="368c9-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="368c9-105">备注</span><span class="sxs-lookup"><span data-stu-id="368c9-105">Remarks</span></span>  
 <span data-ttu-id="368c9-106">`ParamArray` 可以将任意数量的参数传递给该过程。</span><span class="sxs-lookup"><span data-stu-id="368c9-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="368c9-107">一个`ParamArray`始终使用声明参数[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="368c9-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="368c9-108">您可以提供一个或多个参数`ParamArray`通过传递相应的数据数组的参数类型，则一列以逗号分隔的值或执行任何操作根本。</span><span class="sxs-lookup"><span data-stu-id="368c9-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="368c9-109">详细信息，请参阅"调用 ParamArray"中[参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="368c9-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="368c9-110">每当处理数组可以是无限期较大，则存在无限大的某种内部容量的应用程序的风险。</span><span class="sxs-lookup"><span data-stu-id="368c9-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="368c9-111">如果接受从调用代码的参数数组，应测试它的长度，并采取相应措施，如果你的应用程序太大。</span><span class="sxs-lookup"><span data-stu-id="368c9-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="368c9-112">`ParamArray` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="368c9-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="368c9-113">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="368c9-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="368c9-114">Function 语句</span><span class="sxs-lookup"><span data-stu-id="368c9-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="368c9-115">Property 语句</span><span class="sxs-lookup"><span data-stu-id="368c9-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="368c9-116">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="368c9-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="368c9-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="368c9-117">See also</span></span>

- [<span data-ttu-id="368c9-118">关键字</span><span class="sxs-lookup"><span data-stu-id="368c9-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="368c9-119">参数数组</span><span class="sxs-lookup"><span data-stu-id="368c9-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
