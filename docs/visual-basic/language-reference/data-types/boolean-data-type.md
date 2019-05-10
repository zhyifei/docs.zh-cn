---
title: Boolean 数据类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: 03497136ec53d89ac944fdd90301a4c590be326a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622541"
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="47786-102">Boolean 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47786-102">Boolean Data Type (Visual Basic)</span></span>
<span data-ttu-id="47786-103">可以仅由值保存`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="47786-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="47786-104">关键字`True`并`False`对应的两种状态`Boolean`变量。</span><span class="sxs-lookup"><span data-stu-id="47786-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47786-105">备注</span><span class="sxs-lookup"><span data-stu-id="47786-105">Remarks</span></span>  
 <span data-ttu-id="47786-106">使用[布尔数据类型 (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)是/否或开/关包含两个状态的值，如 true/false。</span><span class="sxs-lookup"><span data-stu-id="47786-106">Use the [Boolean Data Type (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="47786-107">`Boolean` 的默认值为 `False`。</span><span class="sxs-lookup"><span data-stu-id="47786-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="47786-108">`Boolean` 值不存储为数字，并存储的值并不等同于数字。</span><span class="sxs-lookup"><span data-stu-id="47786-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="47786-109">绝不应编写依赖于等效的数值的代码`True`和`False`。</span><span class="sxs-lookup"><span data-stu-id="47786-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="47786-110">只要有可能，应限制的使用情况`Boolean`它们设计的逻辑值的变量。</span><span class="sxs-lookup"><span data-stu-id="47786-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="47786-111">类型转换</span><span class="sxs-lookup"><span data-stu-id="47786-111">Type Conversions</span></span>  
 <span data-ttu-id="47786-112">当 Visual Basic 将转换为数值数据类型值`Boolean`，将 0 变为`False`和所有其他值将成为`True`。</span><span class="sxs-lookup"><span data-stu-id="47786-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="47786-113">当 Visual Basic 转换`Boolean`值为数值类型，`False`变为 0 和`True`变得为-1。</span><span class="sxs-lookup"><span data-stu-id="47786-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="47786-114">之间转换时`Boolean`值和数值数据类型，请记住，.NET Framework 转换方法不始终生成与 Visual Basic 转换关键字相同的结果。</span><span class="sxs-lookup"><span data-stu-id="47786-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="47786-115">这是因为 Visual Basic 转换可以保留行为与早期版本兼容。</span><span class="sxs-lookup"><span data-stu-id="47786-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="47786-116">有关详细信息，请参阅"布尔值类型不会不转换到数值类型准确"中[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="47786-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="47786-117">编程提示</span><span class="sxs-lookup"><span data-stu-id="47786-117">Programming Tips</span></span>  
  
- <span data-ttu-id="47786-118">**负号。**</span><span class="sxs-lookup"><span data-stu-id="47786-118">**Negative Numbers.**</span></span> <span data-ttu-id="47786-119">`Boolean` 不是数值类型，不能表示为负值。</span><span class="sxs-lookup"><span data-stu-id="47786-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="47786-120">在任何情况下，不应使用`Boolean`来保存数值。</span><span class="sxs-lookup"><span data-stu-id="47786-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
- <span data-ttu-id="47786-121">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="47786-121">**Type Characters.**</span></span> <span data-ttu-id="47786-122">`Boolean` 不包含文本类型字符或标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="47786-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
- <span data-ttu-id="47786-123">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="47786-123">**Framework Type.**</span></span> <span data-ttu-id="47786-124">.NET Framework 中的对应类型是 <xref:System.Boolean?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="47786-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47786-125">示例</span><span class="sxs-lookup"><span data-stu-id="47786-125">Example</span></span>  
 <span data-ttu-id="47786-126">在以下示例中，`runningVB`是`Boolean`变量，其中存储一个简单的是/否设置。</span><span class="sxs-lookup"><span data-stu-id="47786-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="47786-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="47786-127">See also</span></span>

- <xref:System.Boolean?displayProperty=nameWithType>
- [<span data-ttu-id="47786-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="47786-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="47786-129">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="47786-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="47786-130">转换摘要</span><span class="sxs-lookup"><span data-stu-id="47786-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="47786-131">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="47786-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="47786-132">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="47786-132">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="47786-133">CType 函数</span><span class="sxs-lookup"><span data-stu-id="47786-133">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
