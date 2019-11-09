---
title: Protobuf 标量数据类型-WCF 开发人员 gRPC
description: 了解 .NET Core 中的 Protobuf 和 gRPC 支持的基本数据类型和熟知数据类型。
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: cae9cc483ffb791a9b53e6a2d9d7c0924d725a67
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841455"
---
# <a name="protobuf-scalar-data-types"></a>Protobuf 标量数据类型

Protobuf 支持一系列本机标量值类型。 下表列出了它们的等效C#类型：

| Protobuf 类型 | C# 类型      | 注意 |
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

## <a name="notes"></a>注意

1. 使用有符号值时，`int32` 和 `int64` 的标准编码会效率低下。 如果您的字段可能包含负数，请改用 `sint32` 或 `sint64`。 这两种类型分别C#映射到 `int` 和 `long` 类型。
2. 无论值是什么，`fixed` 字段始终使用相同的字节数。 此行为可以更快地对较大的值进行序列化和反序列化。
3. Protobuf 字符串是编码的 UTF-8 （或7位 ASCII），并且编码的长度不能大于 2<sup>32</sup>。
4. Protobuf 运行时提供了一种 `ByteString` 类型，该类型与C# `byte[]` 数组进行轻松映射。

## <a name="other-net-primitive-types"></a>其他 .NET 基元类型

### <a name="dates-and-times"></a>日期和时间

本机标量类型不提供日期和时间值，等效于C#的 <xref:System.DateTimeOffset>、<xref:System.DateTime>和 <xref:System.TimeSpan>。 可以使用某些 Google 的 "已知类型" 扩展来指定这些类型，这些扩展在支持的平台上提供对更复杂的字段类型的代码生成和运行时支持。 下表显示了日期和时间类型：

| C# 类型 | Protobuf 已知类型 |
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

C#类中生成的属性不是 .net 日期和时间类型。 这些属性使用 `Google.Protobuf.WellKnownTypes` 命名空间中的 `Timestamp` 和 `Duration` 类，这些类提供用于转换为 `DateTimeOffset`、`DateTime`和 `TimeSpan`的方法。

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
> `Timestamp` 类型适用于 UTC 时间;`DateTimeOffset` 值始终为零的偏移量，并且 `DateTime.Kind` 属性将始终 `DateTimeKind.Utc`。

### <a name="systemguid"></a>System.Guid

<xref:System.Guid> 类型（在其他平台上称为 `UUID`）在 Protobuf 中不受支持，并且没有已知的类型。 最佳方法是使用标准 `8-4-4-4-12` 十六进制格式（例如 `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`）处理 `Guid` 值 `string` 字段，该格式可由所有语言和平台进行分析。 不要对 `Guid` 值使用 `bytes` 字段，因为在与其他平台（如 Java）进行交互时，endian 的问题可能导致不稳定的行为。

### <a name="nullable-types"></a>可以为 null 的类型

的 Protobuf 代码生成C#使用本机类型，如 `int32``int`。 这意味着值始终包括在内且不能为 null。 对于需要显式 null 的值（例如，在C#代码中使用 `int?`），Protobuf 的 "已知类型" 包括编译为可以为 null C#的类型的包装。 若要使用它们，请将 `wrappers.proto` 导入到 `.proto` 文件中，如下所示：

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

对于生成的消息属性，Protobuf 将使用简单 `T?` （例如，`int?`）。

下表显示了具有等效C#类型的包装器类型的完整列表：

| C# 类型   | 众所周知的类型包装       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

众所周知的类型 `Timestamp` 和 `Duration` 以 .NET 形式表示为类，因此不需要可为 null 的版本，但在转换为 `DateTimeOffset` 或 `TimeSpan`时，必须检查这些类型的属性是否为 null。

## <a name="decimals"></a>数位

Protobuf 不支持 .NET `decimal` 类型，只需 `double` 和 `float`。 Protobuf 项目中提供了有关将标准 `Decimal` 类型添加到已知类型的可能，其中包含对支持它的语言和框架的平台支持，但尚未实现任何内容。

可以创建消息定义来表示将在 .NET 客户端和服务器之间进行安全序列化的 `decimal` 类型，但其他平台上的开发人员必须了解所使用的格式并实现其自己的处理。

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>为 Protobuf 创建自定义 Decimal 类型

非常简单的实现可能与某些 Google Api 使用的非标准 `Money` 类型相似，无 `currency` 字段。

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

"`nanos`" 字段表示从 `0.999_999_999` 到 `-0.999_999_999`的值。 例如，`1.5m` 的 `decimal` 值将表示为 `{ units = 1, nanos = 500_000_000 }` （这就是此示例中的 `nanos` 字段使用 `sfixed32` 类型的原因，该类型的编码比 `int32` 的值更有效）。 如果 `units` 字段为负数，则 `nanos` 字段也应为负数。

> [!NOTE]
> 有多个其他算法用于将 `decimal` 值编码为字节字符串，但此消息比其中任何一个更易于理解，并且这些值在不同的平台上不受 *[endian](https://en.wikipedia.org/wiki/Endianness)* 的影响。

此类型与 BCL `decimal` 类型之间的转换可C#像下面这样实现。

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
> 无论何时使用自定义实用工具消息类型（如此类消息类型），都**必须**记录 `.proto` 中的注释，以便其他开发人员可以在其自己的语言或框架中实现与等效类型的转换。

>[!div class="step-by-step"]
>[上一页](protobuf-messages.md)
>[下一页](protobuf-nested-types.md)
