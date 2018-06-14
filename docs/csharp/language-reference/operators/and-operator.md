---
title: '&amp; 运算符（C# 参考）'
ms.date: 04/04/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 59813b4bc5781776c9f9741c3e49e660c684bff9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267875"
---
# <a name="amp-operator-c-reference"></a>&amp; 运算符（C# 参考）
`&` 运算符既可作为一元运算符也可作为二元运算符。  
  
## <a name="remarks"></a>备注  
 一元 `&` 运算符返回操作数的地址（需要 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 上下文）。  
  
 针对整型类型和 `bool` 预定义了二元 `&` 运算符。 对于整型类型，& 计算其操作数的逻辑按位 AND。 对于 `bool` 操作数，& 计算其操作数的逻辑 AND；即，当且仅当其两个操作数皆为 `true` 时，结果才为 `true`。  
  
 二元 `&` 运算符计算两个运算符，无论第一个运算符的值是什么。这与[条件 AND 运算符](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&` 相反。 例如:  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 用户定义的类型可以重载二元 `&` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 对整数类型的操作通常可用于枚举。 重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
