---
title: 默认值表 - C# 参考
ms.custom: seodec18
description: 了解 C# 值类型的默认值。
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- parameterless constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], parameterless constructor
- types [C#], parameterless constructor return values
ms.openlocfilehash: dfab5107d4a0ad14c3ffbfc6a5f3c4317b44d17c
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424225"
---
# <a name="default-values-table-c-reference"></a>默认值表（C# 参考）

下表显示[值类型](value-types.md)的默认值。

|值类型|默认值|
|----------------|-------------------|
|[bool](bool.md)|`false`|
|[byte](../builtin-types/integral-numeric-types.md)|0|
|[char](char.md)|'\0'|
|[decimal](decimal.md)|0M|
|[double](double.md)|0.0D|
|[enum](enum.md)|表达式 `(E)0` 生成的值，其中 `E` 是枚举标识符。|
|[float](float.md)|0.0F|
|[int](../builtin-types/integral-numeric-types.md)|0|
|[long](../builtin-types/integral-numeric-types.md)|0L|
|[sbyte](../builtin-types/integral-numeric-types.md)|0|
|[short](../builtin-types/integral-numeric-types.md)|0|
|[struct](struct.md)|通过如下设置生成的值：将所有值类型的字段设置为其默认值，将所有引用类型的字段设置为 `null`。|
|[uint](../builtin-types/integral-numeric-types.md)|0|
|[ulong](../builtin-types/integral-numeric-types.md)|0|
|[ushort](../builtin-types/integral-numeric-types.md)|0|

## <a name="remarks"></a>备注

无法在 C# 中使用未初始化的变量。 可以使用变量类型的默认值对变量进行初始化。 还可使用类型的默认值来指定方法的[可选参数](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments)的默认值。

使用[默认值表达式](../../programming-guide/statements-expressions-operators/default-value-expressions.md)生成类型的默认值，如以下示例所示：

```csharp
int a = default(int);
```

从 C# 7.1 开始，可使用[`default`文本](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference)来初始化变量，使其具有其类型的默认值：

```csharp
int a = default;
```

还可使用无参数构造函数或隐式无参数构造函数来生成值类型的默认值，如以下示例所示。 有关构造函数的详细信息，请参阅[构造函数](../../programming-guide/classes-and-structs/constructors.md)一文。

```csharp
int a = new int();
```

任何[引用类型](reference-types.md)的默认值为 `null`。 [可以为 null 的类型](../../programming-guide/nullable-types/index.md)的默认值是 <xref:System.Nullable%601.HasValue%2A> 属性为 `false` 且未定义 <xref:System.Nullable%601.Value%2A> 属性的实例。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](index.md)
- [值类型](value-types.md)
- [值类型表](value-types-table.md)
- [内置类型表](built-in-types-table.md)
