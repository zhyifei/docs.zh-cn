---
title: 溢出（Visual Basic 运行时错误）
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 9db79071c4895d49680352bde2d0824a3756d941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594170"
---
# <a name="overflow-visual-basic-run-time-error"></a>溢出（Visual Basic 运行时错误）
当你尝试赋值，则超出分配的目标的限制时，将导致溢出。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  请确保转换不太大而无法表示变量的值，类型所允许的范围内，并将值分配给类型的变量的分配、 计算和数据类型的结果可以容纳更大的值范围如有必要。  
  
2.  请确保对属性分配符合他们所做的属性的范围。  
  
3.  请确保在强制转换为整数的计算中使用的数字不具有大于整数的结果。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)
