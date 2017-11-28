---
title: "&gt;= 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f020c2bd8756899908681ab72cac7aa2a203c6a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="gt-operator-c-reference"></a>&gt;= 运算符（C# 参考）
所有数值和枚举类型定义“大于或等于”关系运算符 `>=`，如果第一个操作数大于或等于第二个操作数，此运算符返回 `true`，否则返回 `false`。  
  
## <a name="remarks"></a>备注  
 用户定义的类型可以重载 `>=` 运算符。 有关详细信息，请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)。 如果已重载 `>=`，则必须同时重载 [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md)。 对整数类型的操作通常可用于枚举。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
