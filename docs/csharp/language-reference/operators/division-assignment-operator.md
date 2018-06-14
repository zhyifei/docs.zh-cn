---
title: /= 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: c31ff374e6af4c08c329a971fdd8af169e239395
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171616"
---
# <a name="-operator-c-reference"></a>/= 运算符（C# 参考）
除法赋值运算符。  
  
## <a name="remarks"></a>备注  
 使用 `/=` 赋值运算符的表达式，如  
  
```csharp  
x /= y  
```  
  
 等效于  
  
```csharp  
x = x / y  
```  
  
 不同的是 `x` 只计算一次。 为数值类型预定义了 [/ 运算符](../../../csharp/language-reference/operators/division-operator.md)以进行除法运算。  
  
 不能直接重载 `/=` 运算符，但用户定义的类型可重载 [/ 运算符](../../../csharp/language-reference/operators/division-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 对于所有复合赋值运算符，隐式重载二元运算符会重载等效的复合赋值。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
