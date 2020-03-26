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
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="26401-103">Protobuf 标量数据类型</span><span class="sxs-lookup"><span data-stu-id="26401-103">Protobuf scalar data types</span></span>

<span data-ttu-id="26401-104">协议缓冲区（Protobuf）支持一系列本机标量值类型。</span><span class="sxs-lookup"><span data-stu-id="26401-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="26401-105">下表列出了它们与等效的 C# 类型：</span><span class="sxs-lookup"><span data-stu-id="26401-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="26401-106">原型</span><span class="sxs-lookup"><span data-stu-id="26401-106">Protobuf type</span></span> | <span data-ttu-id="26401-107">C# 类型</span><span class="sxs-lookup"><span data-stu-id="26401-107">C# type</span></span>      | <span data-ttu-id="26401-108">说明</span><span class="sxs-lookup"><span data-stu-id="26401-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="26401-109">1</span><span class="sxs-lookup"><span data-stu-id="26401-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="26401-110">1</span><span class="sxs-lookup"><span data-stu-id="26401-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="26401-111">1</span><span class="sxs-lookup"><span data-stu-id="26401-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="26401-112">1</span><span class="sxs-lookup"><span data-stu-id="26401-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="26401-113">2</span><span class="sxs-lookup"><span data-stu-id="26401-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="26401-114">2</span><span class="sxs-lookup"><span data-stu-id="26401-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="26401-115">2</span><span class="sxs-lookup"><span data-stu-id="26401-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="26401-116">2</span><span class="sxs-lookup"><span data-stu-id="26401-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="26401-117">3</span><span class="sxs-lookup"><span data-stu-id="26401-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="26401-118">4</span><span class="sxs-lookup"><span data-stu-id="26401-118">4</span></span>     |

<span data-ttu-id="26401-119">说明：</span><span class="sxs-lookup"><span data-stu-id="26401-119">Notes:</span></span>

1. <span data-ttu-id="26401-120">使用已签名值`int32`时`int64`，和 的标准编码效率很低。</span><span class="sxs-lookup"><span data-stu-id="26401-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="26401-121">如果字段可能包含负数，请使用`sint32`或`sint64`改为。</span><span class="sxs-lookup"><span data-stu-id="26401-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="26401-122">这些类型分别映射到 C# `int` `long`和类型。</span><span class="sxs-lookup"><span data-stu-id="26401-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="26401-123">无论`fixed`值是什么，字段始终使用相同的字节数。</span><span class="sxs-lookup"><span data-stu-id="26401-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="26401-124">此行为使较大值的序列化和反序列化更快。</span><span class="sxs-lookup"><span data-stu-id="26401-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="26401-125">Protobuf 字符串是 UTF-8（或 7 位 ASCII）编码的。</span><span class="sxs-lookup"><span data-stu-id="26401-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="26401-126">编码的长度不能大于2<sup>32</sup>。</span><span class="sxs-lookup"><span data-stu-id="26401-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="26401-127">Protobuf 运行时提供了一种`ByteString`易于映射到 C# 数组和从`byte[]`C# 数组的类型。</span><span class="sxs-lookup"><span data-stu-id="26401-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="26401-128">其他 .NET 基元类型</span><span class="sxs-lookup"><span data-stu-id="26401-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="26401-129">日期和时间</span><span class="sxs-lookup"><span data-stu-id="26401-129">Dates and times</span></span>

<span data-ttu-id="26401-130">本机标量类型不提供日期和时间值，等效于 C# <xref:System.DateTimeOffset><xref:System.DateTime>和 。 <xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="26401-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="26401-131">您可以使用 Google 的一些"已知类型"扩展来指定这些类型。</span><span class="sxs-lookup"><span data-stu-id="26401-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="26401-132">这些扩展为受支持的平台的复杂字段类型提供代码生成和运行时支持。</span><span class="sxs-lookup"><span data-stu-id="26401-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span>

<span data-ttu-id="26401-133">下表显示了日期和时间类型：</span><span class="sxs-lookup"><span data-stu-id="26401-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="26401-134">C# 类型</span><span class="sxs-lookup"><span data-stu-id="26401-134">C# type</span></span> | <span data-ttu-id="26401-135">原型公司知名类型</span><span class="sxs-lookup"><span data-stu-id="26401-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="26401-136">C# 类中生成的属性不是 .NET 日期和时间类型。</span><span class="sxs-lookup"><span data-stu-id="26401-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="26401-137">属性在`Google.Protobuf.WellKnownTypes`命名空间`Timestamp`中使用`Duration`和 类。</span><span class="sxs-lookup"><span data-stu-id="26401-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="26401-138">这些类提供转换 到 和`DateTimeOffset``DateTime`和 的方法。 `TimeSpan`</span><span class="sxs-lookup"><span data-stu-id="26401-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="26401-139">该`Timestamp`类型适用于 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="26401-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="26401-140">`DateTimeOffset`值的偏移量始终为零，`DateTime.Kind`属性始终`DateTimeKind.Utc`为 。</span><span class="sxs-lookup"><span data-stu-id="26401-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="26401-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="26401-141">System.Guid</span></span>

<span data-ttu-id="26401-142">Protobuf 并不直接支持<xref:System.Guid>该类型，这`UUID`称为其他平台。</span><span class="sxs-lookup"><span data-stu-id="26401-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="26401-143">没有众所周知的类型。</span><span class="sxs-lookup"><span data-stu-id="26401-143">There's no well-known type for it.</span></span>

<span data-ttu-id="26401-144">最好的`Guid`方法是使用标准的`string``8-4-4-4-12`十六进制格式（例如， `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`） 将值作为字段处理。</span><span class="sxs-lookup"><span data-stu-id="26401-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="26401-145">所有语言和平台都可以解析该格式。</span><span class="sxs-lookup"><span data-stu-id="26401-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="26401-146">不要对`bytes``Guid`值使用字段。</span><span class="sxs-lookup"><span data-stu-id="26401-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="26401-147">当Protobuf与其他平台（如Java）交互时，*内皮性*问题（[维基百科定义](https://en.wikipedia.org/wiki/Endianness)）可能会导致行为不稳定。</span><span class="sxs-lookup"><span data-stu-id="26401-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="26401-148">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="26401-148">Nullable types</span></span>

<span data-ttu-id="26401-149">C# 的 Protobuf 代码生成使用本机类型，例如`int` `int32`。</span><span class="sxs-lookup"><span data-stu-id="26401-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="26401-150">因此，这些值始终包含，不能为空。</span><span class="sxs-lookup"><span data-stu-id="26401-150">So the values are always included and can't be null.</span></span>

<span data-ttu-id="26401-151">对于需要显式 null 的值（如`int?`在 C# 代码中使用），Protobuf 的"已知类型"包括编译为空 C# 类型的包装。</span><span class="sxs-lookup"><span data-stu-id="26401-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="26401-152">要使用它们，请导入`wrappers.proto`到文件中`.proto`，如下所示：</span><span class="sxs-lookup"><span data-stu-id="26401-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="26401-153">Protobuf 将使用生成的消息`T?`属性的简单 （`int?`例如 ， ） 。</span><span class="sxs-lookup"><span data-stu-id="26401-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="26401-154">下表显示了具有等效 C# 类型的包装类型的完整列表：</span><span class="sxs-lookup"><span data-stu-id="26401-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="26401-155">C# 类型</span><span class="sxs-lookup"><span data-stu-id="26401-155">C# type</span></span>   | <span data-ttu-id="26401-156">众所周知的类型包装器</span><span class="sxs-lookup"><span data-stu-id="26401-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="26401-157">已知类型`Timestamp`，并在`Duration`.NET 中表示为类。</span><span class="sxs-lookup"><span data-stu-id="26401-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes.</span></span> <span data-ttu-id="26401-158">在 C# 8 及以后，可以使用可无引用类型。</span><span class="sxs-lookup"><span data-stu-id="26401-158">In C# 8 and beyond, you can use nullable reference types.</span></span> <span data-ttu-id="26401-159">但是，在转换为`DateTimeOffset`或`TimeSpan`时，请务必检查这些类型的属性的 null。</span><span class="sxs-lookup"><span data-stu-id="26401-159">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="26401-160">小数</span><span class="sxs-lookup"><span data-stu-id="26401-160">Decimals</span></span>

<span data-ttu-id="26401-161">Protobuf 不本机支持 .NET`decimal`类型，只是`double`和`float`。</span><span class="sxs-lookup"><span data-stu-id="26401-161">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="26401-162">Protobuf 项目中正在进行讨论，讨论向已知类型添加标准`Decimal`类型的可能性，以及支持它的语言和框架的平台支持。</span><span class="sxs-lookup"><span data-stu-id="26401-162">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="26401-163">尚未实施任何措施。</span><span class="sxs-lookup"><span data-stu-id="26401-163">Nothing has been implemented yet.</span></span>

<span data-ttu-id="26401-164">可以创建消息定义来表示适用于 .NET 客户端`decimal`和服务器之间安全序列化的类型。</span><span class="sxs-lookup"><span data-stu-id="26401-164">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="26401-165">但是，其他平台上的开发人员必须了解所使用的格式，并实现自己的处理。</span><span class="sxs-lookup"><span data-stu-id="26401-165">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="26401-166">为 Protobuf 创建自定义十进制类型</span><span class="sxs-lookup"><span data-stu-id="26401-166">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="26401-167">简单实现可能与某些 Google API 在没有`Money``currency`字段的情况下使用的非标准类型类似。</span><span class="sxs-lookup"><span data-stu-id="26401-167">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="26401-168">此字段`nanos`表示从`0.999_999_999`到`-0.999_999_999`的值。</span><span class="sxs-lookup"><span data-stu-id="26401-168">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="26401-169">例如，`decimal`该值`1.5m`将表示为`{ units = 1, nanos = 500_000_000 }`。</span><span class="sxs-lookup"><span data-stu-id="26401-169">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="26401-170">这就是为什么此示例中的`nanos`字段使用`sfixed32`类型，该类型编码的效率高于`int32`对较大值的编码。</span><span class="sxs-lookup"><span data-stu-id="26401-170">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="26401-171">如果`units`字段为负，则`nanos`该字段也应为负数。</span><span class="sxs-lookup"><span data-stu-id="26401-171">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="26401-172">将值编码`decimal`为字节字符串还有其他多个算法，但此消息比其中任何算法更易于理解。</span><span class="sxs-lookup"><span data-stu-id="26401-172">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="26401-173">值不受不同平台上的内端性的影响。</span><span class="sxs-lookup"><span data-stu-id="26401-173">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="26401-174">此类型和 BCL`decimal`类型之间的转换可能在 C# 中实现，如下所示：</span><span class="sxs-lookup"><span data-stu-id="26401-174">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="26401-175">每当使用此类自定义消息类型时，*都必须*在 中`.proto`使用 注释来记录它们。</span><span class="sxs-lookup"><span data-stu-id="26401-175">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="26401-176">然后，其他开发人员可以使用他们自己的语言或框架实现从等效类型转换。</span><span class="sxs-lookup"><span data-stu-id="26401-176">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="26401-177">[上一个](protobuf-messages.md)
>[下一个](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="26401-177">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
