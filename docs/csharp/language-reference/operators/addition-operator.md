---
title: + 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: b49694bc8937c58bd295f0f8e57c378802d0dfb9
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227982"
---
# <a name="-operator-c-reference"></a>+ 运算符（C# 参考）
`+` 运算符既可作为一元运算符也可作为二元运算符。  
  
## <a name="remarks"></a>备注  
 为所有数值类型预定义了一元 `+` 运算符。 对数值类型进行一元 `+` 运算的结果就是操作数的值。  
  
 为数值类型和字符串类型预定义了二元 `+` 运算符。 对于数值类型，+ 计算两个操作数之和。 当其中的一个操作数是字符串类型或两个操作数都是字符串类型时，+ 将操作数的字符串表示形式串联在一起。  
  
 委托类型也提供二元 `+` 运算符，该运算符执行委托串联。  
  
 用户定义的类型可重载一元 `+` 运算符和二元 `+` 运算符。 对整数类型的操作通常可用于枚举。 有关详细信息，请参阅[运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)  
- [运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)
