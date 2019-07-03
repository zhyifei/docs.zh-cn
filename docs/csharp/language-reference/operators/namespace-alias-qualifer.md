---
title: ':: 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: c494e8dbb18f44ce5520b21800a21d3feb03da59
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025070"
---
# <a name="-operator-c-reference"></a>:: 运算符（C# 参考）

命名空间别名限定符（`::`）用于查找标识符。 它始终位于两个标识符之间，如本示例所示：

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

`::` 运算符也可以用于 using alias 指令  ：

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a>备注

命名空间别名限定符可以为 `global`。 这将调用全局命名空间（而不是别名命名空间）中的查找。

## <a name="for-more-information"></a>更多相关信息

有关如何使用 `::` 运算符的示例，请参阅以下部分：

- [如何：使用全局命名空间别名](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a>C# 语言规范

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
- [. 运算符](member-access-operators.md#member-access-operator-)
- [外部别名](../keywords/extern-alias.md)
