---
title: 用于字典的 Protobuf 映射-适用于 WCF 开发人员的 gRPC
description: 了解如何使用 Protobuf 映射来表示 .NET 中的字典类型。
ms.date: 09/09/2019
ms.openlocfilehash: bf848bbc7e3618f6d78e280fcd85d5eb88d5cfae
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543126"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="c0f7b-103">词典的 Protobuf 映射</span><span class="sxs-lookup"><span data-stu-id="c0f7b-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="c0f7b-104">可以在消息中表示命名值的任意集合，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="c0f7b-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="c0f7b-105">在 .NET 中，这通常通过字典类型来处理。</span><span class="sxs-lookup"><span data-stu-id="c0f7b-105">In .NET, this is commonly handled through dictionary types.</span></span> <span data-ttu-id="c0f7b-106">协议缓冲区中的 .NET <xref:System.Collections.Generic.IDictionary%602> 类型（Protobuf）的等效项是 `map<key_type, value_type>` 类型。</span><span class="sxs-lookup"><span data-stu-id="c0f7b-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="c0f7b-107">本部分演示如何在 Protobuf 中声明 `map` 类型以及如何使用生成的代码。</span><span class="sxs-lookup"><span data-stu-id="c0f7b-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="c0f7b-108">在生成的代码中，`map` 字段使用 `Google.Protobuf.Collections.MapField<TKey, TValue>` 类。</span><span class="sxs-lookup"><span data-stu-id="c0f7b-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class.</span></span> <span data-ttu-id="c0f7b-109">此类实现标准 .NET 集合接口，包括 <xref:System.Collections.Generic.IDictionary%602>。</span><span class="sxs-lookup"><span data-stu-id="c0f7b-109">This class implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="c0f7b-110">映射字段不能直接在消息定义中重复。</span><span class="sxs-lookup"><span data-stu-id="c0f7b-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="c0f7b-111">但你可以创建一个包含映射的嵌套消息，并对消息类型使用 `repeated`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="c0f7b-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="c0f7b-112">在代码中使用 MapField 属性</span><span class="sxs-lookup"><span data-stu-id="c0f7b-112">Using MapField properties in code</span></span>

<span data-ttu-id="c0f7b-113">`map` 字段生成的 `MapField` 属性是只读的，将永远不会 `null`。</span><span class="sxs-lookup"><span data-stu-id="c0f7b-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="c0f7b-114">若要设置地图属性，请对空 `MapField` 属性使用 `Add(IDictionary<TKey,TValue> values)` 方法，以便从任何 .NET 字典复制值。</span><span class="sxs-lookup"><span data-stu-id="c0f7b-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="c0f7b-115">进一步阅读</span><span class="sxs-lookup"><span data-stu-id="c0f7b-115">Further reading</span></span>

<span data-ttu-id="c0f7b-116">有关 Protobuf 的详细信息，请参阅官方[Protobuf 文档](https://developers.google.com/protocol-buffers/docs/overview)。</span><span class="sxs-lookup"><span data-stu-id="c0f7b-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c0f7b-117">[上一页](protobuf-enums.md)
>[下一页](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="c0f7b-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
