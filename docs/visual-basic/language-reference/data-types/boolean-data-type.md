---
title: "Boolean 数据类型 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdc106f1ec874c1a2165df069d5f3485fe5b2e43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="ef9b4-102">Boolean 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef9b4-102">Boolean Data Type (Visual Basic)</span></span>
<span data-ttu-id="ef9b4-103">只能是保留值`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="ef9b4-104">关键字`True`和`False`对应的两个状态`Boolean`变量。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef9b4-105">备注</span><span class="sxs-lookup"><span data-stu-id="ef9b4-105">Remarks</span></span>  
 <span data-ttu-id="ef9b4-106">使用[布尔数据类型 (Visual Basic 中)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)以包含两个状态如 true/false 的值是/否或开/关。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-106">Use the [Boolean Data Type (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="ef9b4-107">`Boolean` 的默认值为 `False`。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="ef9b4-108">`Boolean`值不会存储为数字，并且存储的值不应为等效于数字。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="ef9b4-109">绝不应编写依赖于等效数字值的代码`True`和`False`。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="ef9b4-110">只要有可能，应限制使用`Boolean`到为其设计的逻辑值的变量。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="ef9b4-111">类型转换</span><span class="sxs-lookup"><span data-stu-id="ef9b4-111">Type Conversions</span></span>  
 <span data-ttu-id="ef9b4-112">当 Visual Basic 数值数据类型将值转换为`Boolean`，0 会变为`False`和所有其他值将成为`True`。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="ef9b4-113">当 Visual Basic 将转换`Boolean`为数字类型的值`False`变为 0 和`True`会变为-1。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="ef9b4-114">你之间进行转换时`Boolean`值和数值数据类型，请记住情况下，.NET Framework 的转换方法不始终生成 Visual Basic 转换关键字与相同的结果。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="ef9b4-115">这是因为 Visual Basic 转换可以保留与以前的版本兼容的行为。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="ef9b4-116">有关详细信息，请参阅"布尔类型不会不转换为数值类型准确地"中[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="ef9b4-117">编程提示</span><span class="sxs-lookup"><span data-stu-id="ef9b4-117">Programming Tips</span></span>  
  
-   <span data-ttu-id="ef9b4-118">**负数。**</span><span class="sxs-lookup"><span data-stu-id="ef9b4-118">**Negative Numbers.**</span></span> <span data-ttu-id="ef9b4-119">`Boolean`不是数值类型，不能表示为负值。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="ef9b4-120">在任何情况下，不应使用`Boolean`来保存数值。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="ef9b4-121">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="ef9b4-121">**Type Characters.**</span></span> <span data-ttu-id="ef9b4-122">`Boolean`不包含文本类型字符或标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="ef9b4-123">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="ef9b4-123">**Framework Type.**</span></span> <span data-ttu-id="ef9b4-124">.NET Framework 中的对应类型是 <xref:System.Boolean?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef9b4-125">示例</span><span class="sxs-lookup"><span data-stu-id="ef9b4-125">Example</span></span>  
 <span data-ttu-id="ef9b4-126">在下面的示例中，`runningVB`是`Boolean`变量不同，后者将存储是/否设置一个简单。</span><span class="sxs-lookup"><span data-stu-id="ef9b4-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef9b4-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef9b4-127">See Also</span></span>  
 <xref:System.Boolean?displayProperty=nameWithType>  
 [<span data-ttu-id="ef9b4-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="ef9b4-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="ef9b4-129">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="ef9b4-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="ef9b4-130">转换摘要</span><span class="sxs-lookup"><span data-stu-id="ef9b4-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="ef9b4-131">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="ef9b4-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="ef9b4-132">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="ef9b4-132">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="ef9b4-133">CType 函数</span><span class="sxs-lookup"><span data-stu-id="ef9b4-133">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
