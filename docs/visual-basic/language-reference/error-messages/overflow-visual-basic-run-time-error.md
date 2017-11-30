---
title: "溢出（Visual Basic 运行时错误）"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1908ad576a499e79102aff23e3e2f11d7d99d52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="001f3-102">溢出（Visual Basic 运行时错误）</span><span class="sxs-lookup"><span data-stu-id="001f3-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="001f3-103">当你尝试赋值，则超出分配的目标的限制时，将导致溢出。</span><span class="sxs-lookup"><span data-stu-id="001f3-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="001f3-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="001f3-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="001f3-105">请确保转换不太大而无法表示变量的值，类型所允许的范围内，并将值分配给类型的变量的分配、 计算和数据类型的结果可以容纳更大的值范围如有必要。</span><span class="sxs-lookup"><span data-stu-id="001f3-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2.  <span data-ttu-id="001f3-106">请确保对属性分配符合他们所做的属性的范围。</span><span class="sxs-lookup"><span data-stu-id="001f3-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3.  <span data-ttu-id="001f3-107">请确保在强制转换为整数的计算中使用的数字不具有大于整数的结果。</span><span class="sxs-lookup"><span data-stu-id="001f3-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="001f3-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="001f3-108">See Also</span></span>  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [<span data-ttu-id="001f3-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="001f3-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="001f3-110">错误类型</span><span class="sxs-lookup"><span data-stu-id="001f3-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
