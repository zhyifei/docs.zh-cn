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
# <a name="protobuf-maps-for-dictionaries"></a>词典的 Protobuf 映射

可以在消息中表示命名值的任意集合，这一点很重要。 在 .NET 中，这通常是使用字典类型处理的。 Protobuf 等效于 .NET <xref:System.Collections.Generic.IDictionary%602> 类型为 `map<key_type, value_type>` 类型。 本部分演示如何在 Protobuf 中声明 `map`，以及如何使用生成的代码。

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

在生成的代码中，`map` 字段使用 `Google.Protobuf.Collections.MapField<TKey, TValue>` 类，该类实现标准 .NET 集合接口，包括 <xref:System.Collections.Generic.IDictionary%602>。

映射字段不能直接在消息定义中重复，但您可以创建包含映射的嵌套消息，并对消息类型使用 `repeated`，如以下示例中所示：

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

## <a name="further-reading"></a>其他阅读材料

有关 Protobuf 的详细信息，请参阅官方[Protobuf 文档](https://developers.google.com/protocol-buffers/docs/overview)。

>[!div class="step-by-step"]
>[上一页](protobuf-enums.md)
>[下一页](wcf-services-to-grpc-comparison.md)
