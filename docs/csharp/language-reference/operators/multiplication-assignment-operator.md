---
title: '*= 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 6bbf2142ca7e9e05010a29920da52e1439f6e882
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a>*= 运算符（C# 参考）
二进制乘法赋值运算符。  
  
## <a name="remarks"></a>备注  
 使用 `*=` 赋值运算符的表达式，如  
  
```csharp  
x *= y  
```  
  
 等效于  
  
```csharp  
x = x * y  
```  
  
 不同的是 `x` 只计算一次。 针对数值类型预定义了 [* 运算符](../../../csharp/language-reference/operators/multiplication-operator.md)以进行乘法运算。  
  
 不能直接重载 `*=` 运算符，但用户定义的类型可重载 [* 运算符](../../../csharp/language-reference/operators/multiplication-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
