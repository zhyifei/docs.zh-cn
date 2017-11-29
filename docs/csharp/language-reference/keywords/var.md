---
title: "var（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords: var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2be56243f9c4ddafb3903d14fa6d6f9cb0e2f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="var-c-reference"></a>var（C# 参考）
从 Visual C# 3.0 开始，在方法范围内声明的变量可以具有隐式“类型”`var`。 隐式类型本地变量为强类型，就像用户已经自行声明该类型，但编译器决定类型一样。 `i` 的以下两个声明在功能上是等效的：  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 有关详细信息，请参阅[隐式类型的局部变量](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)和 [LINQ 查询操作中的类型关系](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示两个查询表达式。 在第一个表达式中，`var` 的使用是允许的，但不是必需的，因为查询结果的类型可以明确表述为 `IEnumerable<string>`。 但是，在第二个表达式中，必须使用 `var`，因为结果是匿名类型的集合，并且该类型的名称只有编译器本身才可访问。 请注意，在示例 #2 中，`foreach` 迭代变量 `item` 必须也为隐式类型。  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [隐式类型的局部变量](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
