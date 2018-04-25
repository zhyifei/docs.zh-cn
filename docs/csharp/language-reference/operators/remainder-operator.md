---
title: '% 运算符（C# 参考）'
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 796b4a40347fc5881db27a8a8a28404c7c4e8c5b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a>% 运算符（C# 参考）
余数运算符 (`%`) 计算第一个操作数除以第二个操作数后的余数。 所有数值类型都已预定义余数运算符。 
  
## <a name="remarks"></a>备注  
 公式 `a % b` 始终返回介于 `(-b, b)` 范围（不含边界值）内的值（绝不会返回 `b` 或 `-b`），同时保留被除数的符号。 对于整数除法，余数运算符执行规则 `a % b = a - (a / b) * b`。
  
 不要将这与规范取模相混淆，后者虽然执行类似的规则，但采用 Floor 除法，并返回介于 `[0, b)` 范围内的值。 C# 没有规范取模运算符。 不过，行为与正被除数相同。
  
 用户定义的类型可以重载 `%` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a>注释  
 请注意与双精度类型关联的舍入误差。  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
