---
title: -- 运算符（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4eb68143103d44defeac7191e7c4ce7d1ee90e9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="---operator-c-reference"></a>-- 运算符（C# 参考）
减量运算符 (`--`) 按 1 递减其操作数。 减量运算符可以在其操作数之前或之后出现：`--variable` 和 `variable--`。 第一种形式是前缀递减操作。 操作的结果是操作数递减“后”的值。 第二种形式是后缀递减操作。 操作的结果是操作数递减“前”的值。  
  
## <a name="remarks"></a>备注  
 数值和枚举类型具有预定义的减量运算符。  
  
 用户定义的类型可以重载 `--` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 对整数类型的操作通常可用于枚举。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
