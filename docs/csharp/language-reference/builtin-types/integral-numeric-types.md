---
title: 整型数值类型 - C# 参考
description: 了解每种整型数值类型的范围、存储大小和用途。
ms.date: 06/25/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: bde0b7cea52951cd72bde6cfd7d8f1c7dbcb8f46
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425592"
---
# <a name="integral-numeric-types--c-reference"></a>整型数值类型（C# 参考）

“整型数值类型”是“简单类型”的子集，可以使用[文本](#integral-literals)**进行初始化**   。 所有整型类型同时也是值类型。

所有整型数值类型都支持[算术](../operators/arithmetic-operators.md)、[位逻辑](../operators/bitwise-and-shift-operators.md)、[比较和相等](../operators/equality-operators.md)运算符。

## <a name="sizes-and-ranges"></a>大小和范围

下表显示整型类型的大小和范围：

|类型|范围|大小|  
|----------|-----------|----------|  
|`sbyte`|-128 到 127|8 位带符号整数|  
|`byte`|0 到 255|无符号的 8 位整数|  
|`short`|-32,768 到 32,767|有符号 16 位整数|  
|`ushort`|0 到 65,535|无符号 16 位整数|  
|`int`|-2,147,483,648 到 2,147,483,647|带符号的 32 位整数|  
|`uint`|0 到 4,294,967,295|无符号的 32 位整数|  
|`long`|-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807|64 位带符号整数|  
|`ulong`|0 到 18,446,744,073,709,551,615|无符号 64 位整数|  

所有整型类型的默认值都是 `0`。 每个整型类型都有名为 `MinValue` 和 `MaxValue` 的常量，且分别为该类型的最小值和最大值。

<xref:System.Numerics.BigInteger?displayProperty=nameWithType> 结构用于表示没有上限或下限的带符号整数。

## <a name="integral-literals"></a>整型文本

整型文本可以指定为十进制文本、十六进制文本或二进制文本    。 每种文本的示例如下所示：

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

十进制文本不需要任何前缀。 `x` 或 `X` 前缀表示十六进制文本  。 `b` 或 `B` 前缀表示二进制文本  。 `binaryLiteral` 的声明演示将 `_` 用作数字分隔符  。 数字分隔符可以与所有数值文本一起使用。 C# 7.0 及以后版本均支持二进制文本和数字分隔符 `_`。

## <a name="literal-suffixes"></a>文本后缀 

`l` 或 `L` 后缀指定整型文本应为 `long` 类型。 `ul` 或 `UL` 后缀指定 `ulong` 类型。 如果对大于 9,223,372,036,854,775,807（`long` 的最大值）的文本使用 `L` 后缀，则该值将转换为 `ulong` 类型。 如果由整数字面量所表示的值超出了 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>，则将出现编译器错误 [CS1021](../../misc/cs1021.md)。 

> [!NOTE]
> 也可用小写字母“l”作后缀。 但是，字母“l”容易与数字“1”混淆，因此会生成编译器警告。 为清楚起见，请使用“L”。

## <a name="type-of-an-integral-literal"></a>整型文本类型

如果整型文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：

1. `int`
1. `uint`
1. `long`
1. `ulong`

可以通过赋值或强制转换，将整型文本转换为范围小于默认值的类型：

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

可以通过赋值、强制转换或文本后缀将整型文本转换为范围大于默认值的类型：

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a>转换

任何两个整型类型之间均可进行隐式转换（称为扩大转换），在转换中，目标类型可以存储源类型的所有值  。 例如，`int` 可隐式转换为 `long`，因为 `int` 值的范围是 `long` 的真子集。 小型无符号整型类型可隐式转换为大型带符号整型类型。 任何整型类型都可隐式转换为任何浮点类型。  任何带符号整型类型无法隐式转换为任何无符号整型类型。

如果未定义源类型到目标类型的隐式转换，必须使用显式强制转换将整型类型转换为其他整型类型。 这称为收缩转换  。 由于转换可能导致数据丢失，因此必须使用显式用例。

## <a name="see-also"></a>请参阅

- [C# 语言规范 - 整型类型](~/_csharplang/spec/types.md#integral-types)
- [C# 参考](../index.md)
- [浮点型表](../keywords/floating-point-types-table.md)
- [默认值表](../keywords/default-values-table.md)
- [设置数值结果表的格式](../keywords/formatting-numeric-results-table.md)
- [内置类型表](../keywords/built-in-types-table.md)
- [.NET 中的数字](../../../standard/numerics.md)
