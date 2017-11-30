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
# <a name="overflow-visual-basic-run-time-error"></a>溢出（Visual Basic 运行时错误）
当你尝试赋值，则超出分配的目标的限制时，将导致溢出。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  请确保转换不太大而无法表示变量的值，类型所允许的范围内，并将值分配给类型的变量的分配、 计算和数据类型的结果可以容纳更大的值范围如有必要。  
  
2.  请确保对属性分配符合他们所做的属性的范围。  
  
3.  请确保在强制转换为整数的计算中使用的数字不具有大于整数的结果。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)
