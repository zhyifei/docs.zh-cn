---
title: Protobuf 嵌套类型-WCF 开发人员 gRPC
description: 了解 Protobuf 和 gRPC 中的嵌套消息类型及其生成方式C#。
ms.date: 09/09/2019
ms.openlocfilehash: bbc7ed41516d29f867bbc9da5b258f6a3c9ff261
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967387"
---
# <a name="protobuf-nested-types"></a>Protobuf 嵌套类型

正如C#允许在其他类中声明类，Protobuf 允许在其他消息中嵌套消息定义。 下面的示例演示如何创建嵌套消息类型：

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

在生成C#的代码中，将在 `HelloRequest` 类中的嵌套静态 `Types` 类中声明 `Inner` 类型：

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
>[上一页](protobuf-data-types.md)
>[下一页](protobuf-repeated.md)
