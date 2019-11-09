---
title: 列表和数组的重复字段-gRPC for WCF 开发人员
description: 了解如何通过 Protobuf 处理集合，以及如何将其与 .NET 集合相关。
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 740af8af39af9bf31be17ad831f481176e30d81f
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841395"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>列表和数组的重复字段

使用 `repeated` prefix 关键字在 Protobuf 中指定列表。 下面的示例演示如何创建列表：

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

在生成的代码中，`repeated` 字段由 `Google.Protobuf.Collections.RepeatedField<T>` 泛型类型（而不是任何内置 .NET 集合类型）表示。 `RepeatedField<T>` 类型包括将列表序列化和反序列化为二进制线路格式所需的代码。 它实现所有标准 .NET 集合接口（如 <xref:System.Collections.Generic.IList%601> 和 <xref:System.Collections.Generic.IEnumerable%601>），因此可以使用 LINQ 查询或轻松地将其转换为数组或列表。

>[!div class="step-by-step"]
>[上一页](protobuf-nested-types.md)
>[下一页](protobuf-reserved.md)
