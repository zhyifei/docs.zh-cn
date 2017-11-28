---
title: "/= 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 26096d9b5dfc565c9933f1ed8ffb241dc900d9ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>/= 运算符（C# 参考）
除法赋值运算符。  
  
## <a name="remarks"></a>备注  
 使用 `/=` 赋值运算符的表达式，如  
  
```  
x /= y  
```  
  
 等效于  
  
```  
x = x / y  
```  
  
 不同的是 `x` 只计算一次。 为数值类型预定义了 [/ 运算符](../../../csharp/language-reference/operators/division-operator.md)以进行除法运算。  
  
 不能直接重载 `/=` 运算符，但用户定义的类型可重载 [/ 运算符](../../../csharp/language-reference/operators/division-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 对于所有复合赋值运算符，隐式重载二元运算符会重载等效的复合赋值。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
