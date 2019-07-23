---
title: nameof 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 965b3e96a20906187df4c8693f050c550a747091
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331433"
---
# <a name="nameof-operator-c-reference"></a>nameof 运算符 -（C# 参考）

`nameof` 运算符获取变量、类型或成员的名称作为字符串常量：

[!code-csharp-interactive[nameof operator](~/samples/csharp/language-reference/operators/NameOfOperator.cs#Examples)]

如前面的示例所示，对于类型和命名空间，生成的名称通常不是[完全限定的](~/_csharplang/spec/basic-concepts.md#fully-qualified-names)名称。

`nameof` 运算符在编译时进行求值，在运行时无效。

可以使用 `nameof` 运算符使参数检查代码更易于维护：

[!code-csharp[nameof and argument check](~/samples/csharp/language-reference/operators/NameOfOperator.cs#ExceptionMessage)]

`nameof` 运算符在 C# 6 及更高版本中提供。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的 [Nameof 表达式](~/_csharplang/spec/expressions.md#nameof-expressions)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
