---
title: Double 数据类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 5d2d84f298b9cf6138e84ef287f6ea9212da2960
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734807"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="9d289-102">Double 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d289-102">Double Data Type (Visual Basic)</span></span>
<span data-ttu-id="9d289-103">保存有符号 IEEE 64 位 （8 字节） 双精度浮点数，范围为从-1.79769313486231570 e + 308 到-4.94065645841246544 e-324 负值，从 4.94065645841246544 e-324 1.79769313486231570 e + 308 到正值。</span><span class="sxs-lookup"><span data-stu-id="9d289-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="9d289-104">双精度的数字存储一个实数的近似值。</span><span class="sxs-lookup"><span data-stu-id="9d289-104">Double-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d289-105">备注</span><span class="sxs-lookup"><span data-stu-id="9d289-105">Remarks</span></span>  
 <span data-ttu-id="9d289-106">`Double`数据类型提供一个数字量最大和最小可能值。</span><span class="sxs-lookup"><span data-stu-id="9d289-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>  
  
 <span data-ttu-id="9d289-107">`Double` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="9d289-107">The default value of `Double` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="9d289-108">编程提示</span><span class="sxs-lookup"><span data-stu-id="9d289-108">Programming Tips</span></span>  
  
-   <span data-ttu-id="9d289-109">**精度。**</span><span class="sxs-lookup"><span data-stu-id="9d289-109">**Precision.**</span></span> <span data-ttu-id="9d289-110">当使用浮点数时，请记住在内存中不一定有精确的表示形式。</span><span class="sxs-lookup"><span data-stu-id="9d289-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="9d289-111">这可能导致意外的结果从某些操作，如值比较和`Mod`运算符。</span><span class="sxs-lookup"><span data-stu-id="9d289-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="9d289-112">有关详细信息，请参阅[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="9d289-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="9d289-113">**尾随零。**</span><span class="sxs-lookup"><span data-stu-id="9d289-113">**Trailing Zeros.**</span></span> <span data-ttu-id="9d289-114">浮点数据类型不具有尾随零个字符的任何内部表示形式。</span><span class="sxs-lookup"><span data-stu-id="9d289-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="9d289-115">例如，它们不区分 4.2000 和 4.2。</span><span class="sxs-lookup"><span data-stu-id="9d289-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="9d289-116">因此，尾随零个字符不会出现时显示或打印的浮点值。</span><span class="sxs-lookup"><span data-stu-id="9d289-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="9d289-117">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="9d289-117">**Type Characters.**</span></span> <span data-ttu-id="9d289-118">将文本类型字符 `R` 追加到文本会将其强制转换为 `Double` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="9d289-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="9d289-119">例如，如果一个整数后, 跟`R`的值更改为`Double`。</span><span class="sxs-lookup"><span data-stu-id="9d289-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     <span data-ttu-id="9d289-120">将标识符类型字符 `#` 追加到任何标识符会将其强制转换为 `Double`。</span><span class="sxs-lookup"><span data-stu-id="9d289-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="9d289-121">在下面的示例中，变量`num`被类型化为`Double`:</span><span class="sxs-lookup"><span data-stu-id="9d289-121">In the following example, the variable `num` is typed as a `Double`:</span></span>  
  
    ```  
    Dim num# = 3  
    ```  
  
-   <span data-ttu-id="9d289-122">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="9d289-122">**Framework Type.**</span></span> <span data-ttu-id="9d289-123">.NET Framework 中的对应类型是 <xref:System.Double?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="9d289-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d289-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d289-124">See Also</span></span>  
 <xref:System.Double?displayProperty=nameWithType>  
 [<span data-ttu-id="9d289-125">数据类型</span><span class="sxs-lookup"><span data-stu-id="9d289-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="9d289-126">Decimal 数据类型</span><span class="sxs-lookup"><span data-stu-id="9d289-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [<span data-ttu-id="9d289-127">Single 数据类型</span><span class="sxs-lookup"><span data-stu-id="9d289-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [<span data-ttu-id="9d289-128">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="9d289-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="9d289-129">转换摘要</span><span class="sxs-lookup"><span data-stu-id="9d289-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="9d289-130">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="9d289-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="9d289-131">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="9d289-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="9d289-132">类型字符</span><span class="sxs-lookup"><span data-stu-id="9d289-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
