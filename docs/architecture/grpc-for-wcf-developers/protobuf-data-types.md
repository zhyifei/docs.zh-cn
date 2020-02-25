---
title: Protobuf 标量数据类型-WCF 开发人员 gRPC
description: 了解 .NET Core 中的 Protobuf 和 gRPC 支持的基本数据类型和熟知数据类型。
ms.date: 09/09/2019
ms.openlocfilehash: f5215550a6a2d54dfe2e859c574a34f641fdb68d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543152"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="b0ceb-103">Protobuf 标量数据类型</span><span class="sxs-lookup"><span data-stu-id="b0ceb-103">Protobuf scalar data types</span></span>

<span data-ttu-id="b0ceb-104">协议缓冲区（Protobuf）支持一系列本机标量值类型。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="b0ceb-105">下表列出了它们的等效C#类型：</span><span class="sxs-lookup"><span data-stu-id="b0ceb-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="b0ceb-106">Protobuf 类型</span><span class="sxs-lookup"><span data-stu-id="b0ceb-106">Protobuf type</span></span> | <span data-ttu-id="b0ceb-107">C# 类型</span><span class="sxs-lookup"><span data-stu-id="b0ceb-107">C# type</span></span>      | <span data-ttu-id="b0ceb-108">说明</span><span class="sxs-lookup"><span data-stu-id="b0ceb-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="b0ceb-109">1</span><span class="sxs-lookup"><span data-stu-id="b0ceb-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="b0ceb-110">1</span><span class="sxs-lookup"><span data-stu-id="b0ceb-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="b0ceb-111">1</span><span class="sxs-lookup"><span data-stu-id="b0ceb-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="b0ceb-112">1</span><span class="sxs-lookup"><span data-stu-id="b0ceb-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="b0ceb-113">2</span><span class="sxs-lookup"><span data-stu-id="b0ceb-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="b0ceb-114">2</span><span class="sxs-lookup"><span data-stu-id="b0ceb-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="b0ceb-115">2</span><span class="sxs-lookup"><span data-stu-id="b0ceb-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="b0ceb-116">2</span><span class="sxs-lookup"><span data-stu-id="b0ceb-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="b0ceb-117">3</span><span class="sxs-lookup"><span data-stu-id="b0ceb-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="b0ceb-118">4</span><span class="sxs-lookup"><span data-stu-id="b0ceb-118">4</span></span>     |

<span data-ttu-id="b0ceb-119">说明：</span><span class="sxs-lookup"><span data-stu-id="b0ceb-119">Notes:</span></span>

1. <span data-ttu-id="b0ceb-120">使用有符号值时，`int32` 和 `int64` 的标准编码会效率低下。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="b0ceb-121">如果您的字段可能包含负数，请改用 `sint32` 或 `sint64`。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="b0ceb-122">这些类型分别映射到C# `int` 和 `long` 类型。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="b0ceb-123">无论值是什么，`fixed` 字段始终使用相同的字节数。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="b0ceb-124">此行为可以更快地对较大的值进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="b0ceb-125">Protobuf 字符串是编码的 UTF-8 （或7位 ASCII）。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="b0ceb-126">编码长度不能大于 2<sup>32</sup>。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="b0ceb-127">Protobuf 运行时提供了一种 `ByteString` 类型，该类型与C# `byte[]` 数组进行轻松映射。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="b0ceb-128">其他 .NET 基元类型</span><span class="sxs-lookup"><span data-stu-id="b0ceb-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="b0ceb-129">日期和时间</span><span class="sxs-lookup"><span data-stu-id="b0ceb-129">Dates and times</span></span>

<span data-ttu-id="b0ceb-130">本机标量类型不提供日期和时间值，等效于C#的 <xref:System.DateTimeOffset>、<xref:System.DateTime>和 <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="b0ceb-131">你可以通过使用 Google 的某些 "知名类型" 扩展来指定这些类型。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="b0ceb-132">这些扩展为跨受支持平台的复杂字段类型提供代码生成和运行时支持。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span> 

<span data-ttu-id="b0ceb-133">下表显示了日期和时间类型：</span><span class="sxs-lookup"><span data-stu-id="b0ceb-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="b0ceb-134">C# 类型</span><span class="sxs-lookup"><span data-stu-id="b0ceb-134">C# type</span></span> | <span data-ttu-id="b0ceb-135">Protobuf 已知类型</span><span class="sxs-lookup"><span data-stu-id="b0ceb-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="b0ceb-136">C#类中生成的属性不是 .net 日期和时间类型。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="b0ceb-137">属性使用 `Timestamp` 和 `Duration` `Google.Protobuf.WellKnownTypes` 命名空间中的类。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="b0ceb-138">这些类提供了在 `DateTimeOffset`、`DateTime`和 `TimeSpan`之间进行转换的方法。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="b0ceb-139">`Timestamp` 类型适用于 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="b0ceb-140">`DateTimeOffset` 值始终为零偏移量，并且 `DateTime.Kind` 属性始终 `DateTimeKind.Utc`。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="b0ceb-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="b0ceb-141">System.Guid</span></span>

<span data-ttu-id="b0ceb-142">Protobuf 不直接支持在其他平台上称为 `UUID` 的 <xref:System.Guid> 类型。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="b0ceb-143">它没有已知的类型。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-143">There's no well-known type for it.</span></span> 

<span data-ttu-id="b0ceb-144">最佳方法是使用标准 `8-4-4-4-12` 十六进制格式（例如 `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`），将 `Guid` 值作为 `string` 字段处理。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="b0ceb-145">所有语言和平台都可以分析该格式。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="b0ceb-146">不要对 `Guid` 值使用 `bytes` 字段。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="b0ceb-147">当 Protobuf 与其他平台（如 Java）交互时， *endian* （[维基百科定义](https://en.wikipedia.org/wiki/Endianness)）的问题可能导致不稳定的行为。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="b0ceb-148">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="b0ceb-148">Nullable types</span></span>

<span data-ttu-id="b0ceb-149">的 Protobuf 代码生成C#使用本机类型，如 `int32``int`。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="b0ceb-150">因此，这些值始终包括在内且不能为 null。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-150">So the values are always included and can't be null.</span></span> 

<span data-ttu-id="b0ceb-151">对于需要显式 null 的值（例如，在C#代码中使用 `int?`），Protobuf 的 "已知类型" 包括编译为可以为 null C#的类型的包装。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="b0ceb-152">若要使用它们，请将 `wrappers.proto` 导入到 `.proto` 文件中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b0ceb-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="b0ceb-153">对于生成的消息属性，Protobuf 将使用简单 `T?` （例如，`int?`）。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="b0ceb-154">下表显示了具有等效C#类型的包装器类型的完整列表：</span><span class="sxs-lookup"><span data-stu-id="b0ceb-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="b0ceb-155">C# 类型</span><span class="sxs-lookup"><span data-stu-id="b0ceb-155">C# type</span></span>   | <span data-ttu-id="b0ceb-156">众所周知的类型包装</span><span class="sxs-lookup"><span data-stu-id="b0ceb-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="b0ceb-157">众所周知的类型 `Timestamp` 和 `Duration` 以 .NET 形式表示为类，因此不需要可为 null 的版本。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version.</span></span> <span data-ttu-id="b0ceb-158">但在转换为 `DateTimeOffset` 或 `TimeSpan`时，必须检查这些类型的属性是否为 null。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-158">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="b0ceb-159">小数</span><span class="sxs-lookup"><span data-stu-id="b0ceb-159">Decimals</span></span>

<span data-ttu-id="b0ceb-160">Protobuf 不支持 .NET `decimal` 类型，只需 `double` 和 `float`。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-160">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="b0ceb-161">Protobuf 项目中提供了有关将标准 `Decimal` 类型添加到已知类型的可能，其中包含对支持它的语言和框架的平台支持。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-161">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="b0ceb-162">尚未实现任何内容。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-162">Nothing has been implemented yet.</span></span>

<span data-ttu-id="b0ceb-163">可以创建消息定义来表示在 .NET 客户端和服务器之间安全序列化的 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-163">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="b0ceb-164">但其他平台上的开发人员必须了解所使用的格式并实现其自己的处理。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-164">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="b0ceb-165">为 Protobuf 创建自定义 decimal 类型</span><span class="sxs-lookup"><span data-stu-id="b0ceb-165">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="b0ceb-166">简单实现可能与某些 Google Api 使用的非标准 `Money` 类型相似，无 `currency` 字段。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-166">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="b0ceb-167">"`nanos`" 字段表示从 `0.999_999_999` 到 `-0.999_999_999`的值。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-167">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="b0ceb-168">例如，`1.5m` `decimal` 值将表示为 `{ units = 1, nanos = 500_000_000 }`。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-168">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="b0ceb-169">这就是此示例中的 `nanos` 字段使用 `sfixed32` 类型的原因，其编码比 `int32` 较大值更有效。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-169">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="b0ceb-170">如果 `units` 字段为负数，则 `nanos` 字段也应为负数。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-170">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="b0ceb-171">有多个其他算法用于将 `decimal` 值编码为字节字符串，但此消息比其中任何一个更易于理解。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-171">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="b0ceb-172">不同平台上的值不受字节序影响。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-172">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="b0ceb-173">此类型与 BCL `decimal` 类型之间的转换可能会在中C#实现，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b0ceb-173">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="b0ceb-174">无论何时使用自定义消息类型，都*必须*在 `.proto`中记录注释。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-174">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="b0ceb-175">然后，其他开发人员可在其自己的语言或框架中实现与等效类型的转换。</span><span class="sxs-lookup"><span data-stu-id="b0ceb-175">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b0ceb-176">[上一页](protobuf-messages.md)
>[下一页](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="b0ceb-176">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
