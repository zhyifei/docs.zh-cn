---
title: sizeof 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 4852e1166a975b1a45c5bd905123a35fc846aa28
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513121"
---
# <a name="sizeof-operator-c-reference"></a>sizeof 运算符（C# 参考）

`sizeof` 运算符返回给定类型的变量所占用的字节数。 `sizeof` 运算符的参数必须是一个[非托管类型](../builtin-types/unmanaged-types.md)的名称，或是一个[限定为](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)非托管类型的类型参数。

`sizeof` 运算符需要[不安全](../keywords/unsafe.md)上下文。 但下表中的表达式在编译时被计算为相应的常数值，并不需要“不安全”的上下文：

|表达式|常量值|
|---------|---------------|
|`sizeof(sbyte)`|1|
|`sizeof(byte)`|1|
|`sizeof(short)`|2|
|`sizeof(ushort)`|2|
|`sizeof(int)`|4|
|`sizeof(uint)`|4|
|`sizeof(long)`|8|
|`sizeof(ulong)`|8|
|`sizeof(char)`|2|
|`sizeof(float)`|4|
|`sizeof(double)`|8|
|`sizeof(decimal)`|16|
|`sizeof(bool)`|1|

下列情况也不需要使用不安全的上下文：`sizeof` 运算符的操作数是[枚举](../keywords/enum.md)类型的名称。

下面的示例演示 `sizeof` 运算符的用法：

[!code-csharp[sizeof examples](~/samples/csharp/language-reference/operators/SizeOfOperator.cs)]

`sizeof` 运算符返回公共语言运行时将在托管内存中分配的字节数。 对于[结构](../keywords/struct.md)类型，该值包括了填充（如有），如前例所示。 `sizeof` 运算符的结果可能异于 <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 方法的结果，该方法返回某个类型在*非托管*内存中的大小。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的 [sizeof 运算符](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
- [指针相关的运算符](pointer-related-operators.md)
- [指针类型](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [内存和跨度相关类型](../../../standard/memory-and-spans/index.md)
