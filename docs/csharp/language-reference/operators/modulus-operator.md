---
title: "% 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '%_CSharpKeyword'
helpviewer_keywords:
- modulus operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cea4aa03424e93f3ec144126d73c63931a737b54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>% 运算符（C# 参考）
`%` 运算符计算第一个操作数除以第二个操作数后的余数。 所有数值类型都已预定义余数运算符。  
  
## <a name="remarks"></a>备注  
 用户定义的类型可以重载 `%` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]  
  
## <a name="comments"></a>注释  
 请注意与双精度类型关联的舍入误差。  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
