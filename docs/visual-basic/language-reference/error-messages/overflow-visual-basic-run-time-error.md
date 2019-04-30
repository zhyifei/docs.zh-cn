---
title: 溢出（Visual Basic 运行时错误）
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 63223a815e1c4ff8d4e0afbb6c732fff90aad465
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946544"
---
# <a name="overflow-visual-basic-run-time-error"></a>溢出（Visual Basic 运行时错误）
当你尝试赋值超出分配的目标的限制时，将导致溢出。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 请确保分配、 计算和数据类型的转换不是太大而无法表示允许的值，该类型的变量的范围内，并将值分配给类型的变量的结果可以容纳更大的值范围如有必要。  
  
2. 请确保对属性分配符合它们所做的属性的范围。  
  
3. 请确保在强制转换为整数的计算中使用的数字不具有大于整数的结果。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)
