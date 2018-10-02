---
title: ^= 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: d6546f23ffb6dee792339a7e3863bf58ae668d58
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857227"
---
# <a name="-operator-c-reference"></a>^= 运算符（C# 参考）
异或赋值运算符。  
  
## <a name="remarks"></a>备注  
 形式如下的表达式  
  
```csharp  
x ^= y  
```  
  
 计算结果为  
  
```csharp  
x = x ^ y  
```  
  
 不同的是 `x` 只计算一次。 [^ 运算符](../../../csharp/language-reference/operators/xor-operator.md) 对整型操作数执行按位异或运算，对 [bool](../../../csharp/language-reference/keywords/bool.md) 操作数执行逻辑异或运算。  
  
 不能直接重载 ^= 运算符，但用户定义的类型可重载 [^ 运算符](../../../csharp/language-reference/operators/xor-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)
