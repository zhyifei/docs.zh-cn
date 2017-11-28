---
title: "-= 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 443f0d717288a491838d23eaa63218150bd346d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="--operator-c-reference"></a>-= 运算符（C# 参考）
减法赋值运算符。  
  
## <a name="remarks"></a>备注  
 使用 `-=` 赋值运算符的表达式，如  
  
```  
x -= y  
```  
  
 等效于  
  
```  
x = x - y  
```  
  
 不同的是 `x` 只计算一次。 [- 运算符](../../../csharp/language-reference/operators/subtraction-operator.md)的含义取决于 `x` 和 `y` 的类型（例如，对于数值操作数，其含义为相减；对于委托操作数，其含义为移除委托）。  
  
 不能直接重载 `-=` 运算符，但用户定义的类型可重载 [- 运算符](../../../csharp/language-reference/operators/subtraction-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。  
  
 C# 中也使用 -= 运算符来取消订阅事件。 有关详细信息，请参阅[如何：订阅和取消订阅事件](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
