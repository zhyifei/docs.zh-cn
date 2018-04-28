---
title: 基元类型 (F#)
description: '发现的基础的基元类型，F # 语言中使用。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 7832151ee211f56547ecad98fc31f1454cb18870
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="primitive-types"></a>基元类型

本主题列出了 F # 语言中使用的基础基元类型。 它还提供每种类型的相应 .NET 类型和最小和最大值。

## <a name="summary-of-primitive-types"></a>基元类型的摘要
下表总结了基元的 F # 类型的属性。

|类型|.NET 类型|描述|
|----|---------|-----------|
|`bool`|`System.Boolean`|可能的值为 `true` 和 `false`。|
|`byte`|`System.Byte`|值的范围是从 0 到 255。|
|`sbyte`|`System.SByte`|值的范围是从-128 到 127 之间。|
|`int16`|`System.Int16`|从-32768 到 32767 之间的值。|
|`uint16`|`System.UInt16`|值的范围是从 0 到 65535。|
|`int`|`System.Int32`|从-2147483648 到 2147483647 的值。|
|`uint32`|`System.UInt32`|从 0 到 4294967295 之间的值。|
|`int64`|`System.Int64`|值的范围是从-9223372036854775808 到 9223372036854775807。|
|`uint64`|`System.UInt64`|从 0 到 18446744073709551615 之间的值。|
|`nativeint`|`System.IntPtr`|一个带符号整数形式的本机指针。|
|`unativeint`|`System.UIntPtr`|本机指针作为无符号整数。|
|`char`|`System.Char`|Unicode 字符值。|
|`string`|`System.String`|Unicode 文本。|
|`decimal`|`System.Decimal`|一个浮点数据类型具有至少 28 个有效位。|
|`unit`|不适用|表示实际值的缺失。 该类型具有只有一个正式的值，表示`()`。 单元值， `()`，通常用作的占位符其中需要值但没有真正的价值可用或者有意义。|
|`void`|`System.Void`|不指示任何类型或值。|
|`float32, single`|`System.Single`|一个 32 位浮点类型。|
|`float, double`|`System.Double`|一个 64 位浮点类型。|

>[!NOTE]
可以通过使用 64 位整数类型中执行计算传递具有整数太大[bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa)类型。 `bigint` 不被视为基元的类型;它是的缩写`System.Numerics.BigInteger`。

## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)
