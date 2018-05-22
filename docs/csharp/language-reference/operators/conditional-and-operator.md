---
title: '&amp;&amp; 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 15bb3e9702f04cc805af63767c7ecbfc68160368
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
---
# <a name="ampamp-operator-c-reference"></a>&amp;&amp; 运算符（C# 参考）
条件 AND 运算符 (`&&`) 对其 `bool` 操作数执行逻辑 AND 运算，但仅在必要时才计算第二个操作数。  
  
## <a name="remarks"></a>备注  
 操作  
  
```csharp  
x && y  
```  
  
 对应于该操作  
  
```csharp  
x & y  
```  
  
 除非，如果 `x` 为 `false`，不计算 `y`，因为不管 `y` 的值是什么，AND 运算的结果都是 `false`。 这称作“短路”计算。  
  
 不能重载条件 AND 运算符，但常规逻辑运算符以及运算符 [true](../../../csharp/language-reference/keywords/true.md) 和 [false](../../../csharp/language-reference/keywords/false.md) 的重载在某些限制条件下也被视为条件逻辑运算符的重载。  
  
## <a name="example"></a>示例  
 在以下示例中，第二个 `if` 语句中的条件表达式仅计算第一个操作数，因为操作数返回 `false`。  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
