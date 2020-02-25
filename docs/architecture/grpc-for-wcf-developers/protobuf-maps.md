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
# <a name="protobuf-maps-for-dictionaries"></a>词典的 Protobuf 映射

可以在消息中表示命名值的任意集合，这一点很重要。 在 .NET 中，这通常通过字典类型来处理。 协议缓冲区中的 .NET <xref:System.Collections.Generic.IDictionary%602> 类型（Protobuf）的等效项是 `map<key_type, value_type>` 类型。 本部分演示如何在 Protobuf 中声明 `map` 类型以及如何使用生成的代码。

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

在生成的代码中，`map` 字段使用 `Google.Protobuf.Collections.MapField<TKey, TValue>` 类。 此类实现标准 .NET 集合接口，包括 <xref:System.Collections.Generic.IDictionary%602>。

映射字段不能直接在消息定义中重复。 但你可以创建一个包含映射的嵌套消息，并对消息类型使用 `repeated`，如以下示例中所示：

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>在代码中使用 MapField 属性

`map` 字段生成的 `MapField` 属性是只读的，将永远不会 `null`。 若要设置地图属性，请对空 `MapField` 属性使用 `Add(IDictionary<TKey,TValue> values)` 方法，以便从任何 .NET 字典复制值。

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a>进一步阅读

有关 Protobuf 的详细信息，请参阅官方[Protobuf 文档](https://developers.google.com/protocol-buffers/docs/overview)。

>[!div class="step-by-step"]
>[上一页](protobuf-enums.md)
>[下一页](wcf-services-to-grpc-comparison.md)
