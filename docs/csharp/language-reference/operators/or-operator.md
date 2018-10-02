---
title: '| 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: d95fe29aa7ffab9938e8edc57999445268fe41a8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085700"
---
# <a name="-operator-c-reference"></a>| 运算符（C# 参考）
针对整型类型和 `bool` 预定义了二元 `|` 运算符。 对于整型类型，`|` 会计算其操作数的按位 OR。 对于 `bool` 操作数，`|` 会计算其操作数的逻辑 OR；即，当且仅当其两个操作数皆为 `false` 时，结果才为 `false`。  
  
## <a name="remarks"></a>备注  
 二元 `|` 运算符计算两个操作数，无论第一个操作数的值是什么。这与 [conditional-OR operator] (conditional-or-operator.md) `||` 相反。
 
 用户定义的类型可以重载 `|` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)
