---
title: Protobuf 和一个字段的变量类型-gRPC for WCF 开发人员
description: 了解如何使用 Any 类型和一个关键字在消息中表示变体对象类型。
ms.date: 09/09/2019
ms.openlocfilehash: 6fe7acbd1ec35289f7ad6f3acee8509ab934619d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543191"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="d6898-103">Protobuf 和一个字段的变量类型</span><span class="sxs-lookup"><span data-stu-id="d6898-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="d6898-104">在 Windows Communication Foundation （WCF）中处理动态属性类型（即，类型 `object`的属性）非常复杂。</span><span class="sxs-lookup"><span data-stu-id="d6898-104">Handling dynamic property types (that is, properties of type `object`) in Windows Communication Foundation (WCF) is complicated.</span></span> <span data-ttu-id="d6898-105">例如，必须指定序列化程序并提供[KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="d6898-105">For example, you must specify serializers and provide [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes.</span></span>

<span data-ttu-id="d6898-106">协议缓冲区（Protobuf）提供了两个用于处理可能属于多个类型的值的更简单选项。</span><span class="sxs-lookup"><span data-stu-id="d6898-106">Protocol Buffer (Protobuf) provides two simpler options for dealing with values that might be of more than one type.</span></span> <span data-ttu-id="d6898-107">`Any` 类型可以表示任何已知的 Protobuf 消息类型。</span><span class="sxs-lookup"><span data-stu-id="d6898-107">The `Any` type can represent any known Protobuf message type.</span></span> <span data-ttu-id="d6898-108">您可以使用 `oneof` 关键字来指定在任何消息中只能设置一个字段范围中的一个字段。</span><span class="sxs-lookup"><span data-stu-id="d6898-108">And you can use the `oneof` keyword to specify that only one of a range of fields can be set in any message.</span></span>

## <a name="any"></a><span data-ttu-id="d6898-109">Any</span><span class="sxs-lookup"><span data-stu-id="d6898-109">Any</span></span>

<span data-ttu-id="d6898-110">`Any` 是 Protobuf 的 "已知类型"：一系列有用的可重复使用的消息类型，具有所有支持语言的实现。</span><span class="sxs-lookup"><span data-stu-id="d6898-110">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="d6898-111">若要使用 `Any` 类型，必须导入 `google/protobuf/any.proto` 定义。</span><span class="sxs-lookup"><span data-stu-id="d6898-111">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

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

<span data-ttu-id="d6898-112">在C#代码中，`Any` 类提供用于设置字段、提取消息和检查类型的方法。</span><span class="sxs-lookup"><span data-stu-id="d6898-112">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

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

<span data-ttu-id="d6898-113">Protobuf 的内部反射代码使用每个生成的类型上的 `Descriptor` 静态字段来解析 `Any` 字段类型。</span><span class="sxs-lookup"><span data-stu-id="d6898-113">Protobuf's internal reflection code uses the `Descriptor` static field on each generated type to resolve `Any` field types.</span></span> <span data-ttu-id="d6898-114">还有一个 `TryUnpack<T>` 方法，但即使在失败时也会创建 `T` 的未初始化实例。</span><span class="sxs-lookup"><span data-stu-id="d6898-114">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails.</span></span> <span data-ttu-id="d6898-115">如前文所述，最好使用 `Is` 方法。</span><span class="sxs-lookup"><span data-stu-id="d6898-115">It's better to use the `Is` method as shown earlier.</span></span>

## <a name="oneof"></a><span data-ttu-id="d6898-116">一个</span><span class="sxs-lookup"><span data-stu-id="d6898-116">Oneof</span></span>

<span data-ttu-id="d6898-117">一个字段是一项语言功能：编译器在生成 message 类时处理 `oneof` 关键字。</span><span class="sxs-lookup"><span data-stu-id="d6898-117">Oneof fields are a language feature: the compiler handles the `oneof` keyword when it generates the message class.</span></span> <span data-ttu-id="d6898-118">使用 `oneof` 指定 `ChangeNotification` 消息可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6898-118">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

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

<span data-ttu-id="d6898-119">在整个消息声明中，`oneof` 集内的字段必须具有唯一的字段编号。</span><span class="sxs-lookup"><span data-stu-id="d6898-119">Fields within the `oneof` set must have unique field numbers in the overall message declaration.</span></span>

<span data-ttu-id="d6898-120">使用 `oneof`时，生成C#的代码包括一个枚举，用于指定已设置了哪些字段。</span><span class="sxs-lookup"><span data-stu-id="d6898-120">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="d6898-121">可以测试枚举，查找设置的字段。</span><span class="sxs-lookup"><span data-stu-id="d6898-121">You can test the enum to find which field is set.</span></span> <span data-ttu-id="d6898-122">未设置的字段将返回 `null` 或默认值，而不是引发异常。</span><span class="sxs-lookup"><span data-stu-id="d6898-122">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

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

<span data-ttu-id="d6898-123">设置属于 `oneof` 集一部分的任何字段都将自动清除该集中的任何其他字段。</span><span class="sxs-lookup"><span data-stu-id="d6898-123">Setting any field that's part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="d6898-124">不能将 `repeated` 与 `oneof`一起使用。</span><span class="sxs-lookup"><span data-stu-id="d6898-124">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="d6898-125">相反，您可以创建包含重复字段或 `oneof` 集的嵌套消息，以解决此限制。</span><span class="sxs-lookup"><span data-stu-id="d6898-125">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d6898-126">[上一页](protobuf-reserved.md)
>[下一页](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="d6898-126">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
