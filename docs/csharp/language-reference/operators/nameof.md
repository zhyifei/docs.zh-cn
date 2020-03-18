---
title: nameof 运算符 - C# 参考
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: ffbc801acf61bf72db1c88912dc2142a478fa280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846267"
---
# <a name="nameof-operator-c-reference"></a>nameof 运算符 -（C# 参考）

`nameof` 运算符获取变量、类型或成员的名称作为字符串常量：

[!code-csharp-interactive[nameof operator](snippets/NameOfOperator.cs#Examples)]

如前面的示例所示，对于类型和命名空间，生成的名称通常不是[完全限定的](~/_csharplang/spec/basic-concepts.md#fully-qualified-names)名称。

`nameof` 运算符在编译时进行求值，在运行时无效。

可以使用 `nameof` 运算符使参数检查代码更易于维护：

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

`nameof` 运算符在 C# 6 及更高版本中提供。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/expressions.md#nameof-expressions)中的 [Nameof 表达式](~/_csharplang/spec/introduction.md)部分。

## <a name="see-also"></a>另请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
