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
ms.openlocfilehash: 92adb26702d94dee08e51decd845d019c797e195
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630094"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="21e7a-102">Double 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21e7a-102">Double Data Type (Visual Basic)</span></span>

<span data-ttu-id="21e7a-103">为负值以及从 4.94065645841246544 E-324 到 1.79769313486231570 E + 308 的值, 保留已签名的 IEEE 64 位 (8 字节) 双精度浮点数, 其值范围为-1.79769313486231570 E + 308 到-4.94065645841246544 E-324正值。</span><span class="sxs-lookup"><span data-stu-id="21e7a-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="21e7a-104">双精度数字存储实数的近似值。</span><span class="sxs-lookup"><span data-stu-id="21e7a-104">Double-precision numbers store an approximation of a real number.</span></span>

## <a name="remarks"></a><span data-ttu-id="21e7a-105">备注</span><span class="sxs-lookup"><span data-stu-id="21e7a-105">Remarks</span></span>

<span data-ttu-id="21e7a-106">`Double`数据类型为数字提供最大和最小的度。</span><span class="sxs-lookup"><span data-stu-id="21e7a-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>

<span data-ttu-id="21e7a-107">          `Double` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="21e7a-107">The default value of `Double` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="21e7a-108">编程提示</span><span class="sxs-lookup"><span data-stu-id="21e7a-108">Programming Tips</span></span>

- <span data-ttu-id="21e7a-109">**Precision.**</span><span class="sxs-lookup"><span data-stu-id="21e7a-109">**Precision.**</span></span> <span data-ttu-id="21e7a-110">使用浮点数时, 请记住, 它们在内存中不一定有精确的表示形式。</span><span class="sxs-lookup"><span data-stu-id="21e7a-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="21e7a-111">这可能会导致某些操作产生意外结果, 如值比较和`Mod`运算符。</span><span class="sxs-lookup"><span data-stu-id="21e7a-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="21e7a-112">有关详细信息, 请参阅[数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="21e7a-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

- <span data-ttu-id="21e7a-113">**尾随零。**</span><span class="sxs-lookup"><span data-stu-id="21e7a-113">**Trailing Zeros.**</span></span> <span data-ttu-id="21e7a-114">浮点数据类型不包含尾随零字符的任何内部表示形式。</span><span class="sxs-lookup"><span data-stu-id="21e7a-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="21e7a-115">例如, 它们不区分4.2000 和4.2。</span><span class="sxs-lookup"><span data-stu-id="21e7a-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="21e7a-116">因此, 在显示或打印浮点值时, 不会出现尾随零字符。</span><span class="sxs-lookup"><span data-stu-id="21e7a-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>

- <span data-ttu-id="21e7a-117">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="21e7a-117">**Type Characters.**</span></span> <span data-ttu-id="21e7a-118">将文本类型字符 `R` 追加到文本会将其强制转换为 `Double` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="21e7a-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="21e7a-119">例如, 如果整数值后跟`R`, 则该值将更改`Double`为。</span><span class="sxs-lookup"><span data-stu-id="21e7a-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  <span data-ttu-id="21e7a-120">将标识符类型字符 `#` 追加到任何标识符会将其强制转换为 `Double`。</span><span class="sxs-lookup"><span data-stu-id="21e7a-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="21e7a-121">在下面的示例中, 变量`num`被类型化为: `Double`</span><span class="sxs-lookup"><span data-stu-id="21e7a-121">In the following example, the variable `num` is typed as a `Double`:</span></span>

  ```vb
  Dim num# = 3
  ```

- <span data-ttu-id="21e7a-122">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="21e7a-122">**Framework Type.**</span></span> <span data-ttu-id="21e7a-123">.NET Framework 中的对应类型是 <xref:System.Double?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="21e7a-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="21e7a-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="21e7a-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="21e7a-125">数据类型</span><span class="sxs-lookup"><span data-stu-id="21e7a-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="21e7a-126">Decimal 数据类型</span><span class="sxs-lookup"><span data-stu-id="21e7a-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="21e7a-127">Single 数据类型</span><span class="sxs-lookup"><span data-stu-id="21e7a-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="21e7a-128">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="21e7a-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="21e7a-129">转换摘要</span><span class="sxs-lookup"><span data-stu-id="21e7a-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="21e7a-130">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="21e7a-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="21e7a-131">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="21e7a-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="21e7a-132">类型字符</span><span class="sxs-lookup"><span data-stu-id="21e7a-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
