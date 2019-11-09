---
title: 用于字典的 Protobuf 映射-适用于 WCF 开发人员的 gRPC
description: 了解如何使用 Protobuf 映射来表示。NET 的字典类型。
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: aef6b0f378e7a63f362ec42642cae15b32d49a08
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841449"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="501a6-103">词典的 Protobuf 映射</span><span class="sxs-lookup"><span data-stu-id="501a6-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="501a6-104">可以在消息中表示命名值的任意集合，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="501a6-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="501a6-105">在 .NET 中，这通常是使用字典类型处理的。</span><span class="sxs-lookup"><span data-stu-id="501a6-105">In .NET this is commonly handled using dictionary types.</span></span> <span data-ttu-id="501a6-106">Protobuf 等效于 .NET <xref:System.Collections.Generic.IDictionary%602> 类型为 `map<key_type, value_type>` 类型。</span><span class="sxs-lookup"><span data-stu-id="501a6-106">Protobuf's equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="501a6-107">本部分演示如何在 Protobuf 中声明 `map`，以及如何使用生成的代码。</span><span class="sxs-lookup"><span data-stu-id="501a6-107">This section shows how to declare a `map` in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="501a6-108">在生成的代码中，`map` 字段使用 `Google.Protobuf.Collections.MapField<TKey, TValue>` 类，该类实现标准 .NET 集合接口，包括 <xref:System.Collections.Generic.IDictionary%602>。</span><span class="sxs-lookup"><span data-stu-id="501a6-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class, which implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="501a6-109">映射字段不能直接在消息定义中重复，但您可以创建包含映射的嵌套消息，并对消息类型使用 `repeated`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="501a6-109">Map fields can't be directly repeated in a message definition, but you can create a nested message containing a map and use `repeated` on the message type, like in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="501a6-110">在代码中使用 MapField 属性</span><span class="sxs-lookup"><span data-stu-id="501a6-110">Using MapField properties in code</span></span>

<span data-ttu-id="501a6-111">`map` 字段生成的 `MapField` 属性是只读的，将永远不会 `null`。</span><span class="sxs-lookup"><span data-stu-id="501a6-111">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="501a6-112">若要设置地图属性，请对空 `MapField` 属性使用 `Add(IDictionary<TKey,TValue> values)` 方法，以便从任何 .NET 字典复制值。</span><span class="sxs-lookup"><span data-stu-id="501a6-112">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="501a6-113">其他阅读材料</span><span class="sxs-lookup"><span data-stu-id="501a6-113">Further reading</span></span>

<span data-ttu-id="501a6-114">有关 Protobuf 的详细信息，请参阅官方[Protobuf 文档](https://developers.google.com/protocol-buffers/docs/overview)。</span><span class="sxs-lookup"><span data-stu-id="501a6-114">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="501a6-115">[上一页](protobuf-enums.md)
>[下一页](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="501a6-115">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
