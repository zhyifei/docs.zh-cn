---
title: Protobuf 保留字段-WCF 开发人员 gRPC
description: 了解有关跨版本兼容性的保留字段。
ms.date: 09/09/2019
ms.openlocfilehash: 50082a1aab2e7707a1839b9d56455124a9e4a6a1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542971"
---
# <a name="protobuf-reserved-fields"></a>Protobuf 保留字段

协议缓冲区（Protobuf）中的向后兼容性保证依赖于字段编号始终表示相同的数据项。 如果从服务的新版本的消息中删除字段，则永远不应重复使用该字段号。 可以使用 `reserved` 关键字强制此。 

如果从前面定义的 `Stock` 消息中删除了 "`displayName`" 和 "`marketId`" 字段，则应该保留其字段编号，如以下示例中所示。

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

你还可以使用 `reserved` 关键字作为以后可能添加的字段的占位符。 可以通过使用 `to` 关键字将连续的字段编号表示为范围。

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[上一页](protobuf-repeated.md)
>[下一页](protobuf-any-oneof.md)
