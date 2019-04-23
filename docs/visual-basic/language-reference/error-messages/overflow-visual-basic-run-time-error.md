---
title: 溢出（Visual Basic 运行时错误）
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 63223a815e1c4ff8d4e0afbb6c732fff90aad465
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59345542"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="3c75b-102">溢出（Visual Basic 运行时错误）</span><span class="sxs-lookup"><span data-stu-id="3c75b-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="3c75b-103">当你尝试赋值超出分配的目标的限制时，将导致溢出。</span><span class="sxs-lookup"><span data-stu-id="3c75b-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3c75b-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3c75b-104">To correct this error</span></span>  
  
1. <span data-ttu-id="3c75b-105">请确保分配、 计算和数据类型的转换不是太大而无法表示允许的值，该类型的变量的范围内，并将值分配给类型的变量的结果可以容纳更大的值范围如有必要。</span><span class="sxs-lookup"><span data-stu-id="3c75b-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2. <span data-ttu-id="3c75b-106">请确保对属性分配符合它们所做的属性的范围。</span><span class="sxs-lookup"><span data-stu-id="3c75b-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3. <span data-ttu-id="3c75b-107">请确保在强制转换为整数的计算中使用的数字不具有大于整数的结果。</span><span class="sxs-lookup"><span data-stu-id="3c75b-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c75b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c75b-108">See also</span></span>

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="3c75b-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="3c75b-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="3c75b-110">错误类型</span><span class="sxs-lookup"><span data-stu-id="3c75b-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
