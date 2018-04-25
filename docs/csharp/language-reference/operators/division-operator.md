---
title: / 运算符（C# 参考）
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5b17d122e3e3f75012e084903b6f8975fb53d46c
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
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
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
