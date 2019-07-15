---
title: 隐式数值转换表 - C# 参考
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 516505ccacfd2a8a5c275b0de033e1316fa06d3a
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661344"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>隐式数值转换表（C# 参考）

下表显示 .NET 数值类型之间的预定义隐式转换。
  
|From|到|  
|----------|--------|  
|[sbyte](../builtin-types/integral-numeric-types.md)|`short`、`int`、`long`、`float`、`double` 或 `decimal`|  
|[byte](../builtin-types/integral-numeric-types.md)|`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`|  
|[char](char.md)|`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`|  
|[short](../builtin-types/integral-numeric-types.md)|`int`、`long`、`float`、`double` 或 `decimal`|  
|[ushort](../builtin-types/integral-numeric-types.md)|`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`。|  
|[int](../builtin-types/integral-numeric-types.md)|`long`、`float`、`double` 或 `decimal`|  
|[uint](../builtin-types/integral-numeric-types.md)|`long`、`ulong`、`float`、`double` 或 `decimal`|  
|[long](../builtin-types/integral-numeric-types.md)|`float`、`double` 或 `decimal`|  
|[ulong](../builtin-types/integral-numeric-types.md)|`float`、`double` 或 `decimal`|  
|[float](../builtin-types/floating-point-numeric-types.md)|`double`|  
  
## <a name="remarks"></a>备注  

- 任何[整型类型](../builtin-types/integral-numeric-types.md)都可以隐式转换为任何[浮点类型](../builtin-types/floating-point-numeric-types.md)。

- 在从 `int`、`uint`、`long` 或 `ulong` 转换为 `float`，以及从 `long` 或 `ulong` 转换为 `double` 时，可能会丢失精度，但不会丢失量值。  
  
- 不存在针对 `char`、`byte` 和 `sbyte` 类型的隐式转换。  

- 不存在从 `double` 和 `decimal` 类型的隐式转换。
  
- `decimal` 类型和 `float` 或 `double` 类型之间不存在隐式转换。  
  
- 类型 `int` 的常量表达式的值（例如，由整数型字面量表示的值）可以转换为 `sbyte`、`byte`、`short`、`ushort`、`uint` 或 `ulong`，前提是它在目标类型的范围内：

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

有关隐式转换的详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[隐式转换](~/_csharplang/spec/conversions.md#implicit-conversions)章节。
  
## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [整型类型](../builtin-types/integral-numeric-types.md)
- [浮点型表](../builtin-types/floating-point-numeric-types.md)
- [内置类型表](built-in-types-table.md)
- [显式数值转换表](explicit-numeric-conversions-table.md)
- [强制转换和类型转换](../../programming-guide/types/casting-and-type-conversions.md)
