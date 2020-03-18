---
title: 原托布夫保留字段 - gRPC 面向 WCF 开发人员
description: 了解跨版本兼容性的保留字段。
ms.date: 09/09/2019
ms.openlocfilehash: bde658c671e970b7ec841d71d5b4284eb91195f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147940"
---
# <a name="protobuf-reserved-fields"></a>Protobuf 保留字段

协议缓冲区 （Protobuf） 中的向后兼容性保证依赖于始终表示相同数据项的字段编号。 如果从服务新版本中的消息中删除了字段，则不应重复使用该字段编号。 您可以使用`reserved`关键字来强化此值。

如果`displayName`从`marketId`前面定义`Stock`的消息中删除 和 字段，则应保留其字段编号，如以下示例所示。

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

您还可以将`reserved`关键字用作将来可能添加的字段的占位符。 您可以使用`to`关键字将连续字段数表示为范围。

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[上一个](protobuf-repeated.md)
>[下一个](protobuf-any-oneof.md)
