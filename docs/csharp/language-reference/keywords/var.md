---
title: var（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: ab49a4f4fcbc990a1fd21139397d70fa9fbf5dd8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44088058"
---
# <a name="var-c-reference"></a>var（C# 参考）
从 Visual C# 3.0 开始，在方法范围内声明的变量可以具有隐式“类型”`var`。 隐式类型本地变量为强类型，就像用户已经自行声明该类型，但编译器决定类型一样。 `i` 的以下两个声明在功能上是等效的：  
  
```csharp  
var i = 10; // Implicitly typed. 
int i = 10; // Explicitly typed. 
```  
  
 有关详细信息，请参阅[隐式类型的局部变量](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)和 [LINQ 查询操作中的类型关系](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示两个查询表达式。 在第一个表达式中，`var` 的使用是允许的，但不是必需的，因为查询结果的类型可以明确表述为 `IEnumerable<string>`。 不过，在第二个表达式中，`var` 允许结果是一系列匿名类型，且相应类型的名称只可供编译器本身访问。 如果使用 `var`，便无法为结果新建类。 请注意，在示例 #2 中，`foreach` 迭代变量 `item` 必须也为隐式类型。  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [隐式类型的局部变量](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
