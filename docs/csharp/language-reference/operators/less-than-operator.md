---
title: "&lt; 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 76d53d4c943c886f6b8c8a68e2b8bb12bc9a9d6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lt-operator-c-reference"></a>&lt; 运算符（C# 参考）
所有数值和枚举类型定义“小于”关系运算符 (`<`)，如果第一个操作数小于第二个操作数，此运算符返回 `true`，否则返回 `false`。  
  
## <a name="remarks"></a>备注  
 用户定义的类型可以重载 `<` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 如果已重载 `<`，则必须同时重载 [>](../../../csharp/language-reference/operators/greater-than-operator.md)。 重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
