---
title: '基本类型 （F #）'
description: '了解 F # 语言中使用的基础的基本类型。'
ms.date: 07/09/2018
ms.openlocfilehash: fdb5e95e102fcf721569156c7fb3a32604fff1dd
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37937194"
---
# <a name="basic-types"></a>基本类型

本主题列出了在 F # 语言中定义的基本类型。 这些类型是最基本的 F # 中，几乎每个 F # 程序的基础。 它们是.NET 基元类型的一个超集。

|类型|.NET 类型|描述|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|可能的值为 `true` 和 `false`。|
|`byte`|<xref:System.Byte>|从 0 到 255 之间的值。|
|`sbyte`|<xref:System.SByte>|从-128 到 127 之间的值。|
|`int16`|<xref:System.Int16>|从-32768 到 32767 之间的值。|
|`uint16`|<xref:System.UInt16>|值的范围是从 0 到 65535。|
|`int`|<xref:System.Int32>|从-2147483648 到 2147483647 的值。|
|`uint32`|<xref:System.UInt32>|从 0 到 4294967295 之间的值。|
|`int64`|<xref:System.Int64>|从-9223372036854775808 到 9,223,372,036,854,775,807 的值。|
|`uint64`|<xref:System.UInt64>|从 0 到 18446744073709551615 之间的值。|
|`nativeint`|<xref:System.IntPtr>|一个有符号整数形式的本机指针。|
|`unativeint`|<xref:System.UIntPtr>|无符号整数形式的本机指针。|
|`char`|<xref:System.Char>|Unicode 字符值。|
|`string`|<xref:System.String>|Unicode 文本。|
|`decimal`|<xref:System.Decimal>|一个浮点数据类型的至少 28 个有效位。|
|`unit`|不适用|表示实际值不的存在。 该类型具有只有一个正式的值，该值表示`()`。 单元值， `()`，通常用作其中需要的值，但没有实际值是可用或者有意义的占位符。|
|`void`|<xref:System.Void>|指示没有类型或值。|
|`float32`, `single`|<xref:System.Single>|32 位浮点类型。|
|`float`, `double`|<xref:System.Double>|64 位浮点类型。|

>[!NOTE]
通过执行 64 位整数类型具有整数太大的计算[bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa)类型。 `bigint` 不被视为一种基本类型;是的缩写`System.Numerics.BigInteger`。

## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)
