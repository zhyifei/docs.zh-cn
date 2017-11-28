---
title: "() 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6d62e6c93dcc69c892d4ca96ace3806cb1c8d989
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>() 运算符（C# 参考）
除了用于指定表达式中的运算顺序外，圆括号还用于执行以下任务：  
  
1.  指定强制转换或类型转换。  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  调用方法或委托。  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a>备注  
 强制转换显式调用从一种类型到另一种类型的转换运算符；如果未定义这样的转换运算符，则强制转换失败。 若要定义转换运算符，请参阅 [explicit](../../../csharp/language-reference/keywords/explicit.md) 和 [implicit](../../../csharp/language-reference/keywords/implicit.md)。  
  
 不能重载 `()` 运算符。  
  
 有关详细信息，请参阅[强制转换和类型转换](../../../csharp/programming-guide/types/casting-and-type-conversions.md)。  
  
 强制转换表达式可能会使语法发生歧义。 例如，表达式 `(x)–y` 既可以解释为强制转换表达式（将 –y 强制转换为类型 x），也可以解释为结合了带括号表达式的相加表达式（计算 x – y 的值）。  
  
 有关方法调用的详细信息，请参阅[方法](../../../csharp/programming-guide/classes-and-structs/methods.md)。  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
