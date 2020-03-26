---
title: 原托布夫保留字段 - gRPC 面向 WCF 开发人员
description: 了解跨版本兼容性的保留字段。
ms.date: 09/09/2019
ms.openlocfilehash: f89513c4659a02cbc94e1c659baecb9e750acbdc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111031"
---
# <a name="protobuf-reserved-fields"></a>Protobuf 保留字段

协议缓冲区 （Protobuf） 中的向后兼容性保证依赖于始终表示相同数据项的字段编号。 如果从服务新版本中的消息中删除了字段，则不应重复使用该字段编号。 您可以使用`reserved`关键字强制执行此情况。

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
