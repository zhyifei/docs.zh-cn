---
title: ::运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2e456be075f3487676228244e0119ff46ed9a538
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243473"
---
# <a name="-operator-c-reference"></a>::运算符（C# 参考）
命名空间别名限定符（`::`）用于查找标识符。 它始终位于两个标识符之间，如本示例所示：  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  

`::` 运算符也可以用于 using alias 指令：

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a>备注  
 命名空间别名限定符可以为 `global`。 这将调用全局命名空间（而不是别名命名空间）中的查找。  
  
## <a name="for-more-information"></a>更多信息  
 有关如何使用 `::` 运算符的示例，请参阅以下部分：  
  
-   [如何：使用全局命名空间别名](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)  
- [命名空间关键字](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [。运算符](../../../csharp/language-reference/operators/member-access-operator.md)  
- [外部别名](../../../csharp/language-reference/keywords/extern-alias.md)
