---
title: "byte（C# 参考）"
ms.date: 03/14/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 231a491914071b1d43b5a8938e677be531726e75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="byte-c-reference"></a>byte（C# 参考）

`byte` 表示存储下表所示值的整型类型。
  
|类型|范围|大小|.NET Framework 类型|  
|----------|-----------|----------|-------------------------|  
|`byte`|0 到 255|无符号的 8 位整数|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a>文本  

 可以通过为其分配十进制文本、十六进制文本或（从 C# 7 开始）二进制文本来声明和初始化 `byte` 变量。 如果整数文本在 `byte` 范围之外（即，如果它小于 <xref:System.Byte.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Byte.MaxValue?displayProperty=nameWithType>），会发生编译错误。

在以下示例中，等于 201、表示为十进制、十六进制和二进制文本的整数从 [int](../../../csharp/language-reference/keywords/int.md) 隐式转换为 `byte` 值。    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> 使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。 十进制文本没有前缀。

C# 从 7 开始，已添加几个功能以增强可读性。 
 - C# 7.0 允许使用下划线字符， `_`，作为数字分隔符。
 - C# 7.2 允许`_`前缀后要使用作为二进制或十六进制文本中，数字分隔符。 十进制文本不允许具有前导下划线。

下面显示了一些示例。

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a>转换  
 存在从 `byte` 到 [short](../../../csharp/language-reference/keywords/short.md)、[ushort](../../../csharp/language-reference/keywords/ushort.md)、[int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md)、[ulong](../../../csharp/language-reference/keywords/ulong.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。  

你不能将较大存储大小的非字面数字类型隐式转换为 `byte`。有关整数类型存储大小的详细信息，请参阅[整数类型表](../../../csharp/language-reference/keywords/integral-types-table.md)。

以下面两个 `byte` 变量 `x` 和 `y` 为例：  

```  
byte x = 10, y = 20;  
```  
  
 以下赋值语句将产生一个编译器错误，原因是赋值运算符右侧的算术表达式在默认情况下的计算结果为 `int` 类型。  
  
```  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 若要解决此问题，请使用强制转换：  
  
```  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 但是，在目标变量具有相同或更大的存储大小时，也可以使用下列语句：  
  
```  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 此外，不存在从浮点类型到 `byte` 类型的隐式转换。 例如，除非使用显式强制转换，否则以下语句将生成编译器错误：  
  
```  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 在调用重载方法时，必须使用转换。 以下面使用 `byte` 和 [int](../../../csharp/language-reference/keywords/int.md) 参数的重载方法为例：  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 使用 `byte` 强制转换可保证调用正确的类型，例如：  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。
  
 有关隐式数值转换规则的详细信息，请参阅[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)。  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Byte>  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [整型表](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [显式数值转换表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
