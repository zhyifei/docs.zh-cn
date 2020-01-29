---
title: 内置类型表 - C# 参考
description: 内置 C# 类型的关键字
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: f26da848d58426472d2c2ab755ecadfd267b096a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734480"
---
# <a name="built-in-types-table-c-reference"></a>内置类型表（C# 参考）

下表显示内置 C# 类型的关键字，即 <xref:System> 命名空间中预定义类型的别名：

|C# 类型|.NET 类型|  
|--------------|-------------------------|  
|[bool](../builtin-types/bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[byte](../builtin-types/integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[sbyte](../builtin-types/integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[char](../builtin-types/char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[decimal](../builtin-types/floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[double](../builtin-types/floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[float](../builtin-types/floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[int](../builtin-types/integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[uint](../builtin-types/integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[long](../builtin-types/integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[ulong](../builtin-types/integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[object](../builtin-types/reference-types.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[short](../builtin-types/integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[ushort](../builtin-types/integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[string](../builtin-types/reference-types.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a>备注

此表中的所有类型，除 `object` 和 `string` 外，皆被称为简单类型。

.NET 类型及其 C# 类型关键字别名可互换。 例如，可通过使用以下任意一个声明来声明整型变量：

```csharp
int x = 123;
System.Int32 y = 123;
```

使用 [typeof](../operators/type-testing-and-cast.md#typeof-operator) 运算符以获取表示指定类型的 <xref:System.Type?displayProperty=nameWithType> 实例：

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 关键字](index.md)
- [值类型](../builtin-types/value-types.md)
- [引用类型](reference-types.md)
- [C# 类型的默认值](../builtin-types/default-values.md)
- [dynamic](../builtin-types/reference-types.md#the-dynamic-type)
