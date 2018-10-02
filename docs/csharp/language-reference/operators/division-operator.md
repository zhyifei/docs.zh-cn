---
title: / 运算符（C# 参考）
ms.date: 04/04/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: bddf6d234f3536ad64f0cd876cc7ade4494916d9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43800750"
---
# <a name="-operator-c-reference"></a>/ 运算符（C# 参考）
除法运算符 (`/`) 将其第一操作数除以第二操作数。 所有数值类型都具有预定义的除法运算符。
  
## <a name="remarks"></a>备注  
 用户定义的类型可以重载 `/` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 重载 `/` 运算符将隐式地重载 [/= operator](division-assignment-operator.md)。  
  
 两个整数相除，其结果始终为整数。 例如，7 除以 3 得 2。 不要将这与 Floor 除法相混淆，因为 `/` 运算符是往 0 的方向舍入：-7 / 3 的计算结果是 -2。  
  
 若要获取有理数形式的商，请使用 `float`、`double` 或 `decimal` 类型。 切换[内置数值类型](../../../csharp/language-reference/keywords/reference-tables-for-types.md)的方法有许多种。  
  
 若要确定余数，请使用[余数运算符](../../../csharp/language-reference/operators/remainder-operator.md) `%`。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)
