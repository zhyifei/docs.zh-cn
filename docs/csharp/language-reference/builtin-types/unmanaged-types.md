---
title: 非托管类型 - C# 参考
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512074"
---
# <a name="unmanaged-types-c-reference"></a>非托管类型（C# 参考）

**非托管类型**指任何不是引用类型或构造类型（包含至少一个类型参数）的类型，且在任何级别的嵌套中不含引用类型或构造类型字段。 换言之，非托管类型即为以下类型之一：

- `sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float`、`double`、`decimal` 或 `bool`
- 任何[枚举](../keywords/enum.md)类型
- 任何[指针](../../programming-guide/unsafe-code-pointers/pointer-types.md)类型
- 任何不是[构造](../keywords/struct.md)类型且仅包含非托管类型字段的用户定义的类型

从 C# 7.3 开始，可使用 [`unmanaged` 约束](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)指定：类型参数为“非指针非托管类型”。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[指针类型](~/_csharplang/spec/unsafe-code.md#pointer-types)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [指针类型](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [内存和跨度相关类型](../../../standard/memory-and-spans/index.md)
- [sizeof 运算符](../operators/sizeof.md)
- [stackalloc 运算符](../operators/stackalloc.md)
