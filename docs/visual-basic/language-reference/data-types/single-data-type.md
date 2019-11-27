---
title: Single 数据类型
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: 60a688c510f6e36dca5809566b37a388429e18c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343921"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="63473-102">Single 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63473-102">Single Data Type (Visual Basic)</span></span>

<span data-ttu-id="63473-103">为负值，保留已签名的 IEEE 32 位（4字节）单精度浮点数，介于-3.4028235 E + 38 到-1.401298 E-45 之间，对于正值，为正值，从 1.401298 E-45 到 3.4028235 E + 38。</span><span class="sxs-lookup"><span data-stu-id="63473-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="63473-104">单精度数字存储实数的近似值。</span><span class="sxs-lookup"><span data-stu-id="63473-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63473-105">备注</span><span class="sxs-lookup"><span data-stu-id="63473-105">Remarks</span></span>  

 <span data-ttu-id="63473-106">使用 `Single` 数据类型包含不需要 `Double`的完整数据宽度的浮点值。</span><span class="sxs-lookup"><span data-stu-id="63473-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="63473-107">在某些情况下，公共语言运行时可以将 `Single` 的变量紧密地打包在一起，从而节省内存消耗。</span><span class="sxs-lookup"><span data-stu-id="63473-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="63473-108">`Single` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="63473-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="63473-109">编程提示</span><span class="sxs-lookup"><span data-stu-id="63473-109">Programming Tips</span></span>  
  
- <span data-ttu-id="63473-110">**Precision.**</span><span class="sxs-lookup"><span data-stu-id="63473-110">**Precision.**</span></span> <span data-ttu-id="63473-111">使用浮点数时，请记住，它们在内存中不一定有精确的表示形式。</span><span class="sxs-lookup"><span data-stu-id="63473-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="63473-112">这可能会导致某些操作产生意外结果，如值比较和 `Mod` 运算符。</span><span class="sxs-lookup"><span data-stu-id="63473-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="63473-113">有关详细信息，请参阅[数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="63473-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="63473-114">**扩大.**</span><span class="sxs-lookup"><span data-stu-id="63473-114">**Widening.**</span></span> <span data-ttu-id="63473-115">`Single` 的数据类型扩大到 `Double`。</span><span class="sxs-lookup"><span data-stu-id="63473-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="63473-116">这意味着，可以将 `Single` 转换为 `Double`，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。</span><span class="sxs-lookup"><span data-stu-id="63473-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="63473-117">**尾随零。**</span><span class="sxs-lookup"><span data-stu-id="63473-117">**Trailing Zeros.**</span></span> <span data-ttu-id="63473-118">浮点数据类型不包含尾随0字符的任何内部表示形式。</span><span class="sxs-lookup"><span data-stu-id="63473-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="63473-119">例如，它们不区分4.2000 和4.2。</span><span class="sxs-lookup"><span data-stu-id="63473-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="63473-120">因此，在显示或打印浮点值时，不会出现尾随0字符。</span><span class="sxs-lookup"><span data-stu-id="63473-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="63473-121">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="63473-121">**Type Characters.**</span></span> <span data-ttu-id="63473-122">将文本类型字符 `F` 追加到文本会将其强制转换为 `Single` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="63473-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="63473-123">将标识符类型字符 `!` 追加到任何标识符会将其强制转换为 `Single`。</span><span class="sxs-lookup"><span data-stu-id="63473-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="63473-124">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="63473-124">**Framework Type.**</span></span> <span data-ttu-id="63473-125">.NET Framework 中的对应类型是 <xref:System.Single?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="63473-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63473-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63473-126">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="63473-127">数据类型</span><span class="sxs-lookup"><span data-stu-id="63473-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="63473-128">Decimal 数据类型</span><span class="sxs-lookup"><span data-stu-id="63473-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="63473-129">Double 数据类型</span><span class="sxs-lookup"><span data-stu-id="63473-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="63473-130">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="63473-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="63473-131">转换摘要</span><span class="sxs-lookup"><span data-stu-id="63473-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="63473-132">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="63473-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="63473-133">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="63473-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
