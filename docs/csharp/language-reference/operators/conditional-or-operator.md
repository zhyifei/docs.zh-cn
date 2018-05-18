---
title: '|| 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: ce0834874f9c5b4c5154a798492600d6ac45a4c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>|| 运算符（C# 参考）
条件 OR 运算符 (`||`) 执行其 `bool` 操作数的逻辑 OR。 如果第一个操作数的计算结果为 `true`，则不计算第二个操作数。 如果第一个操作数的计算结果为 `false`，则第二个运算符决定 OR 表达式整体的计算结果是 `true` 还是 `false`。  
  
## <a name="remarks"></a>备注  
 操作  
  
```  
x || y  
```  
  
 对应于该操作  
  
```  
x | y  
```  
  
 除非，如果 `x` 为 `true`，不计算 `y`，因为不管 `y` 的值是什么，OR 运算的结果都是 `true`。 此概念即“短路”计算。  
  
 不能重载条件 OR 运算符，但常规逻辑运算符以及运算符 [true](../../../csharp/language-reference/keywords/true.md) 和 [false](../../../csharp/language-reference/keywords/false.md) 的重载在某些限制条件下也被视为条件逻辑运算符的重载。  
  
## <a name="example"></a>示例  
 在以下示例中，使用 `||` 的表达式仅计算第一个操作数。 使用 `|` 的表达式计算两个操作数。 在第二个示例中，如果计算两个操作数，则会出现运行时异常。  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
