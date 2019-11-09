---
title: Protobuf 嵌套类型-WCF 开发人员 gRPC
description: 了解 Protobuf 和 gRPC 中的嵌套消息类型及其生成方式C#。
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: ec9fc522619230c1201bfef1e8128f7356936212
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841401"
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
