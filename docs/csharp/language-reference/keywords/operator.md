---
title: "运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords: operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8fae5487d5daa5ada52d45919598d1abd217aee9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="operator-c-reference"></a>运算符（C# 参考）
使用 `operator` 关键字重载内置运算符，或在类或结构声明中提供用户定义的转换。  
  
## <a name="example"></a>示例  
 下面是针对分数的一个非常简单的类。 此类重载 + 和 * 运算符以执行分数加法和乘法，并提供转换运算符将分数类型转换为双精度类型。  
  
 [!code-csharp[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [implicit](../../../csharp/language-reference/keywords/implicit.md)  
 [explicit](../../../csharp/language-reference/keywords/explicit.md)  
 [如何：在结构之间实现用户定义的转换](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
