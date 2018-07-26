---
title: new 约束（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 77c955102ba9cede831c85838a6a7e57025ad35b
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199453"
---
# <a name="new-constraint-c-reference"></a>new 约束（C# 参考）
`new` 约束指定泛型类声明中的任何类型实参都必须有公共的无形参构造函数。 若要使用 new 约束，则该类型不能为抽象类型。  
  
## <a name="example"></a>示例  
 当泛型类创建类型的新实例时，请将 `new` 约束应用于类型参数，如下面的示例所示：  
  
 [!code-csharp[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a>示例  
 当与其他约束一起使用时，`new()` 约束必须最后指定：  
  
 [!code-csharp[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 有关详细信息，请参阅[类型参数的约束](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)。  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Collections.Generic>  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [运算符关键字](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [泛型](../../../csharp/programming-guide/generics/index.md)
