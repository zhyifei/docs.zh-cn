---
title: 值类型表 - C# 参考
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 98829f30c2c25c0710cf3fe044359d3c7538fe76
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424040"
---
# <a name="value-types-table-c-reference"></a>值类型表（C# 参考）

下表显示 C# 值类型：

|值类型|类别|类型后缀|
|----------------|--------------|-----------------|
|[bool](bool.md)|Boolean||
|[byte](../builtin-types/integral-numeric-types.md)|无符号、数字、[整型](../builtin-types/integral-numeric-types.md)||
|[char](char.md)|无符号、数字、[整型](../builtin-types/integral-numeric-types.md)
)||
|[decimal](decimal.md)|数字、[浮点](floating-point-types-table.md)|M 或 m|
|[double](double.md)|数字、[浮点](floating-point-types-table.md)|D 或 d|
|[enum](enum.md)|枚举||
|[float](float.md)|数字、[浮点](floating-point-types-table.md)|F 或 f|
|[int](../builtin-types/integral-numeric-types.md)|带符号、数字、[整型](../builtin-types/integral-numeric-types.md)||
|[long](../builtin-types/integral-numeric-types.md)|带符号、数字、[整型](../builtin-types/integral-numeric-types.md)|L 或 l|
|[sbyte](../builtin-types/integral-numeric-types.md)|带符号、数字、[整型](../builtin-types/integral-numeric-types.md)||
|[short](../builtin-types/integral-numeric-types.md)|带符号、数字、[整型](../builtin-types/integral-numeric-types.md)||
|[struct](struct.md)|用户定义的结构||
|[uint](../builtin-types/integral-numeric-types.md)|无符号、数字、[整型](../builtin-types/integral-numeric-types.md)|U 或 u|
|[ulong](../builtin-types/integral-numeric-types.md)|无符号、数字、[整型](../builtin-types/integral-numeric-types.md)|UL、Ul、uL、ul、LU、Lu、lU 或 lu|
|[ushort](../builtin-types/integral-numeric-types.md)|无符号、数字、[整型](../builtin-types/integral-numeric-types.md)||

## <a name="remarks"></a>备注

使用类型后缀指定数字文字的类型。 例如:

```csharp
decimal a = 0.1M;
```

如果[整数数值型字面量](~/_csharplang/spec/lexical-structure.md#integer-literals)没有后缀，则它具有以下类型中的第一个类型，其值可以通过这种类型表示：`int`、`uint`、`long`、`ulong`。

如果[实际数值字面量](~/_csharplang/spec/lexical-structure.md#real-literals)没有后缀，则其类型为 `double`。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [默认值表](default-values-table.md)
- [值类型](value-types.md)
- [设置数值结果表的格式](formatting-numeric-results-table.md)
