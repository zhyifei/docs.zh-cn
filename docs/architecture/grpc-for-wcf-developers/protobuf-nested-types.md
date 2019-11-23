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
# <a name="protobuf-nested-types"></a><span data-ttu-id="9fd4b-103">Protobuf 嵌套类型</span><span class="sxs-lookup"><span data-stu-id="9fd4b-103">Protobuf nested types</span></span>

<span data-ttu-id="9fd4b-104">正如C#允许在其他类中声明类，Protobuf 允许在其他消息中嵌套消息定义。</span><span class="sxs-lookup"><span data-stu-id="9fd4b-104">Just like C# allows you to declare classes inside other classes, Protobuf allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="9fd4b-105">下面的示例演示如何创建嵌套消息类型：</span><span class="sxs-lookup"><span data-stu-id="9fd4b-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="9fd4b-106">在生成C#的代码中，将在 `HelloRequest` 类中的嵌套静态 `Types` 类中声明 `Inner` 类型：</span><span class="sxs-lookup"><span data-stu-id="9fd4b-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="9fd4b-107">[上一页](protobuf-data-types.md)
>[下一页](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="9fd4b-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>
