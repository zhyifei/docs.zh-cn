---
title: Protobuf 和一个字段的变量类型-gRPC for WCF 开发人员
description: 了解如何使用 Any 类型和一个关键字在消息中表示变体对象类型。
ms.date: 09/09/2019
ms.openlocfilehash: af3ba22c238aa80a8c6119f62d5d8914770cad68
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971619"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="a5028-103">Protobuf 和一个字段的变量类型</span><span class="sxs-lookup"><span data-stu-id="a5028-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="a5028-104">在 WCF 中处理动态属性类型（即，类型 `object`的属性）非常复杂。</span><span class="sxs-lookup"><span data-stu-id="a5028-104">Handling dynamic property types (that is, properties of type `object`) in WCF is complicated.</span></span> <span data-ttu-id="a5028-105">必须指定序列化程序，必须提供[KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute)特性，依此类推。</span><span class="sxs-lookup"><span data-stu-id="a5028-105">Serializers must be specified, [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes must be provided, and so on.</span></span>

<span data-ttu-id="a5028-106">Protobuf 提供了两个更简单的选项用于处理可能属于多个类型的值。</span><span class="sxs-lookup"><span data-stu-id="a5028-106">Protobuf provides two simpler options for dealing with values that may be of more than one type.</span></span> <span data-ttu-id="a5028-107">`Any` 类型可以表示任何已知的 Protobuf 消息类型，而 `oneof` 关键字可用于指定在任何给定消息中只能设置一个字段范围中的一个字段。</span><span class="sxs-lookup"><span data-stu-id="a5028-107">The `Any` type can represent any known Protobuf message type, while the `oneof` keyword allows you to specify that only one of a range of fields can be set in any given message.</span></span>

## <a name="any"></a><span data-ttu-id="a5028-108">任何</span><span class="sxs-lookup"><span data-stu-id="a5028-108">Any</span></span>

<span data-ttu-id="a5028-109">`Any` 是 Protobuf 的 "已知类型"：一系列有用的可重复使用的消息类型，具有所有支持语言的实现。</span><span class="sxs-lookup"><span data-stu-id="a5028-109">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="a5028-110">若要使用 `Any` 类型，必须导入 `google/protobuf/any.proto` 定义。</span><span class="sxs-lookup"><span data-stu-id="a5028-110">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

```protobuf
syntax "proto3"

import "google/protobuf/any.proto"

message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
    int32 id = 1;
    google.protobuf.Any instrument = 2;
}
```

<span data-ttu-id="a5028-111">在C#代码中，`Any` 类提供用于设置字段、提取消息和检查类型的方法。</span><span class="sxs-lookup"><span data-stu-id="a5028-111">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    if (change.Instrument.Is(Stock.Descriptor))
    {
        FormatStock(change.Instrument.Unpack<Stock>());
    }
    else if (change.Instrument.Is(Currency.Descriptor))
    {
        FormatCurrency(change.Instrument.Unpack<Currency>());
    }
    else
    {
        throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="a5028-112">Protobuf 的内部反射代码使用每个生成的类型上的 `Descriptor` 静态字段来解析 `Any` 字段类型。</span><span class="sxs-lookup"><span data-stu-id="a5028-112">The `Descriptor` static field on each generated type is used by Protobuf's internal reflection code to resolve `Any` field types.</span></span> <span data-ttu-id="a5028-113">还有一个 `TryUnpack<T>` 方法，但即使在该方法失败时，也会创建 `T` 的未初始化的实例，因此，最好使用如下所示的 `Is` 方法。</span><span class="sxs-lookup"><span data-stu-id="a5028-113">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails, so it's better to use the `Is` method as shown above.</span></span>

## <a name="oneof"></a><span data-ttu-id="a5028-114">一个</span><span class="sxs-lookup"><span data-stu-id="a5028-114">Oneof</span></span>

<span data-ttu-id="a5028-115">一个字段是一项语言功能：在生成 message 类时，编译器将处理 `oneof` 关键字。</span><span class="sxs-lookup"><span data-stu-id="a5028-115">Oneof fields are a language feature: the `oneof` keyword is handled by the compiler when it generates the message class.</span></span> <span data-ttu-id="a5028-116">使用 `oneof` 指定 `ChangeNotification` 消息可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5028-116">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

```protobuf
message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
  int32 id = 1;
  oneof instrument {
    Stock stock = 2;
    Currency currency = 3;
  }
}
```

<span data-ttu-id="a5028-117">在整个消息声明中，`oneof` 集内的字段必须具有唯一的字段编号。</span><span class="sxs-lookup"><span data-stu-id="a5028-117">Fields within the `oneof` set must have unique field numbers within the overall message declaration.</span></span>

<span data-ttu-id="a5028-118">使用 `oneof`时，生成C#的代码包括一个枚举，用于指定已设置了哪些字段。</span><span class="sxs-lookup"><span data-stu-id="a5028-118">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="a5028-119">可以测试枚举，查找设置的字段。</span><span class="sxs-lookup"><span data-stu-id="a5028-119">You can test the enum to find which field is set.</span></span> <span data-ttu-id="a5028-120">未设置的字段将返回 `null` 或默认值，而不是引发异常。</span><span class="sxs-lookup"><span data-stu-id="a5028-120">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    switch (change.InstrumentCase)
    {
        case ChangeNotification.InstrumentOneofCase.None:
            return;
        case ChangeNotification.InstrumentOneofCase.Stock:
            FormatStock(change.Stock);
            break;
        case ChangeNotification.InstrumentOneofCase.Currency:
            FormatCurrency(change.Currency);
            break;
        default:
            throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="a5028-121">设置作为 `oneof` 集的一部分的任何字段都将自动清除该集中的任何其他字段。</span><span class="sxs-lookup"><span data-stu-id="a5028-121">Setting any field that is part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="a5028-122">不能将 `repeated` 与 `oneof`一起使用。</span><span class="sxs-lookup"><span data-stu-id="a5028-122">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="a5028-123">相反，您可以创建包含重复字段或 `oneof` 集的嵌套消息，以解决此限制。</span><span class="sxs-lookup"><span data-stu-id="a5028-123">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a5028-124">[上一页](protobuf-reserved.md)
>[下一页](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="a5028-124">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
