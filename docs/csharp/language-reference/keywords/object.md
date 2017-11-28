---
title: "object（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords: object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0fcced75d3a86fd700e642e48b7e325e554cae53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="object-c-reference"></a>object（C# 参考）
`object` 类型是 .NET Framework 中 <xref:System.Object> 的别名。 在 C# 的统一类型系统中，所有类型（预定义类型、用户定义类型、引用类型和值类型）都是直接或间接从 <xref:System.Object> 继承的。 可以将任何类型的值赋给 `object` 类型的变量。 将值类型的变量转换为对象的过程称为*装箱*。 将对象类型的变量转换为值类型的过程称为*取消装箱*。 有关详细信息，请参阅[装箱和取消装箱](../../../csharp/programming-guide/types/boxing-and-unboxing.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示 `object` 类型的变量如何接受任何数据类型的值，以及 `object` 类型的变量如何在 .NET Framework 中使用 <xref:System.Object> 的方法。  
  
 [!code-csharp[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [引用类型](../../../csharp/language-reference/keywords/reference-types.md)  
 [值类型](../../../csharp/language-reference/keywords/value-types.md)
