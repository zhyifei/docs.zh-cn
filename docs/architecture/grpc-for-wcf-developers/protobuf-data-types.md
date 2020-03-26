---
title: 原型标量数据类型 - gRPC，适用于 WCF 开发人员
description: 了解 Protobuf 和 gRPC 在 .NET Core 中支持的基本和众所周知的数据类型。
ms.date: 09/09/2019
ms.openlocfilehash: ea3b53426ecf6f50f3bae22a537e227b07248508
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249430"
---
# <a name="protobuf-scalar-data-types"></a>Protobuf 标量数据类型

协议缓冲区（Protobuf）支持一系列本机标量值类型。 下表列出了它们与等效的 C# 类型：

| 原型 | C# 类型      | 说明 |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | 1     |
| `int64`       | `long`       | 1     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | 1     |
| `sint64`      | `long`       | 1     |
| `fixed32`     | `uint`       | 2     |
| `fixed64`     | `ulong`      | 2     |
| `sfixed32`    | `int`        | 2     |
| `sfixed64`    | `long`       | 2     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | 3     |
| `bytes`       | `ByteString` | 4     |

说明：

1. 使用已签名值`int32`时`int64`，和 的标准编码效率很低。 如果字段可能包含负数，请使用`sint32`或`sint64`改为。 这些类型分别映射到 C# `int` `long`和类型。
2. 无论`fixed`值是什么，字段始终使用相同的字节数。 此行为使较大值的序列化和反序列化更快。
3. Protobuf 字符串是 UTF-8（或 7 位 ASCII）编码的。 编码的长度不能大于2<sup>32</sup>。
4. Protobuf 运行时提供了一种`ByteString`易于映射到 C# 数组和从`byte[]`C# 数组的类型。

## <a name="other-net-primitive-types"></a>其他 .NET 基元类型

### <a name="dates-and-times"></a>日期和时间

本机标量类型不提供日期和时间值，等效于 C# <xref:System.DateTimeOffset><xref:System.DateTime>和 。 <xref:System.TimeSpan> 您可以使用 Google 的一些"已知类型"扩展来指定这些类型。 这些扩展为受支持的平台的复杂字段类型提供代码生成和运行时支持。

下表显示了日期和时间类型：

| C# 类型 | 原型公司知名类型 |
| ------- | ------------------------ |
| `DateTimeOffset` | `google.protobuf.Timestamp` |
| `DateTime` | `google.protobuf.Timestamp` |
| `TimeSpan` | `google.protobuf.Duration` |

```protobuf  
syntax = "proto3"

import "google/protobuf/duration.proto";  
import "google/protobuf/timestamp.proto";

message Meeting {

    string subject = 1;
    google.protobuf.Timestamp time = 2;
    google.protobuf.Duration duration = 3;

}  
```

C# 类中生成的属性不是 .NET 日期和时间类型。 属性在`Google.Protobuf.WellKnownTypes`命名空间`Timestamp`中使用`Duration`和 类。 这些类提供转换 到 和`DateTimeOffset``DateTime`和 的方法。 `TimeSpan`

```csharp
// Create Timestamp and Duration from .NET DateTimeOffset and TimeSpan
var meeting = new Meeting
{
    Time = Timestamp.FromDateTimeOffset(meetingTime), // also FromDateTime()
    Duration = Duration.FromTimeSpan(meetingLength)
};

// Convert Timestamp and Duration to .NET DateTimeOffset and TimeSpan
DateTimeOffset time = meeting.Time.ToDateTimeOffset();
TimeSpan? duration = meeting.Duration?.ToTimeSpan();
```

> [!NOTE]
> 该`Timestamp`类型适用于 UTC 时间。 `DateTimeOffset`值的偏移量始终为零，`DateTime.Kind`属性始终`DateTimeKind.Utc`为 。

### <a name="systemguid"></a>System.Guid

Protobuf 并不直接支持<xref:System.Guid>该类型，这`UUID`称为其他平台。 没有众所周知的类型。

最好的`Guid`方法是使用标准的`string``8-4-4-4-12`十六进制格式（例如， `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`） 将值作为字段处理。 所有语言和平台都可以解析该格式。

不要对`bytes``Guid`值使用字段。 当Protobuf与其他平台（如Java）交互时，*内皮性*问题（[维基百科定义](https://en.wikipedia.org/wiki/Endianness)）可能会导致行为不稳定。

### <a name="nullable-types"></a>可以为 null 的类型

C# 的 Protobuf 代码生成使用本机类型，例如`int` `int32`。 因此，这些值始终包含，不能为空。

对于需要显式 null 的值（如`int?`在 C# 代码中使用），Protobuf 的"已知类型"包括编译为空 C# 类型的包装。 要使用它们，请导入`wrappers.proto`到文件中`.proto`，如下所示：

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf 将使用生成的消息`T?`属性的简单 （`int?`例如 ， ） 。

下表显示了具有等效 C# 类型的包装类型的完整列表：

| C# 类型   | 众所周知的类型包装器       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

已知类型`Timestamp`，并在`Duration`.NET 中表示为类。 在 C# 8 及以后，可以使用可无引用类型。 但是，在转换为`DateTimeOffset`或`TimeSpan`时，请务必检查这些类型的属性的 null。

## <a name="decimals"></a>小数

Protobuf 不本机支持 .NET`decimal`类型，只是`double`和`float`。 Protobuf 项目中正在进行讨论，讨论向已知类型添加标准`Decimal`类型的可能性，以及支持它的语言和框架的平台支持。 尚未实施任何措施。

可以创建消息定义来表示适用于 .NET 客户端`decimal`和服务器之间安全序列化的类型。 但是，其他平台上的开发人员必须了解所使用的格式，并实现自己的处理。

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>为 Protobuf 创建自定义十进制类型

简单实现可能与某些 Google API 在没有`Money``currency`字段的情况下使用的非标准类型类似。

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message Decimal {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

此字段`nanos`表示从`0.999_999_999`到`-0.999_999_999`的值。 例如，`decimal`该值`1.5m`将表示为`{ units = 1, nanos = 500_000_000 }`。 这就是为什么此示例中的`nanos`字段使用`sfixed32`类型，该类型编码的效率高于`int32`对较大值的编码。 如果`units`字段为负，则`nanos`该字段也应为负数。

> [!NOTE]
> 将值编码`decimal`为字节字符串还有其他多个算法，但此消息比其中任何算法更易于理解。 值不受不同平台上的内端性的影响。

此类型和 BCL`decimal`类型之间的转换可能在 C# 中实现，如下所示：

```csharp
namespace CustomTypes
{
    public partial class GrpcDecimal
    {
        private const decimal NanoFactor = 1_000_000_000;
        public GrpcDecimal(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.Decimal grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.Decimal(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.Decimal(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> 每当使用此类自定义消息类型时，*都必须*在 中`.proto`使用 注释来记录它们。 然后，其他开发人员可以使用他们自己的语言或框架实现从等效类型转换。

>[!div class="step-by-step"]
>[上一个](protobuf-messages.md)
>[下一个](protobuf-nested-types.md)
