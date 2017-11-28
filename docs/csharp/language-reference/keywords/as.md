---
title: "as（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a4f2964f32a4139ffeb6d51b761f1176a57c5be6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="as-c-reference"></a>as（C# 参考）
可以使用 `as` 运算符在符合的引用类型或[可以为 null 的类型](../../../csharp/programming-guide/nullable-types/index.md)之间执行某些类型的转换。 以下代码显示一个示例。  
  
 [!code-csharp[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]  
  
## <a name="remarks"></a>备注  
 `as` 运算符类似于转换运算。 但是，如果无法进行转换，则 `as` 会返回 `null`，而不是引发异常。 请看下面的示例：  
  
```  
expression as type  
```  
  
 该代码等效于以下表达式，但 `expression` 变量仅进行一次计算。  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 请注意，`as` 运算符仅执行引用转换、可以为 null 的转换和装箱转换。 `as` 运算符无法执行其他转换，例如用户定义的转换，应使用转换表达式执行此转换。  
  
## <a name="example"></a>示例  
 [!code-csharp[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [is](../../../csharp/language-reference/keywords/is.md)  
 [?: 运算符](../../../csharp/language-reference/operators/conditional-operator.md)  
 [运算符关键字](../../../csharp/language-reference/keywords/operator-keywords.md)
