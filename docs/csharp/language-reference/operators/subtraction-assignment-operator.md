---
title: -= 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 33aba2e944c8d0589949e7bdc77aadd4f213da28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
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
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
