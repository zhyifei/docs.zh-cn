---
title: '|= 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: fe56005ce94656b5e8a075cddfb91dc0da096cf7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44194502"
---
# <a name="-operator-c-reference"></a>|= 运算符（C# 参考）
OR 赋值运算符。  
  
## <a name="remarks"></a>备注  
 使用 `|=` 赋值运算符的表达式，如  
  
```csharp  
x |= y  
```  
  
 等效于  
  
```csharp  
x = x | y  
```  
  
 不同的是 `x` 只计算一次。 [&#124; 运算符](../../../csharp/language-reference/operators/or-operator.md) 对整型操作数执行按位逻辑 OR 运算，对 bool 操作数执行逻辑 OR 运算。  
  
 不能直接重载 `|=` 运算符，但用户定义的类型可重载 [&#124; 运算符](../../../csharp/language-reference/operators/or-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)
