---
title: 列表和数组的重复字段 - 适用于 WCF 开发人员的 gRPC
description: 了解 Protobuf 如何处理集合以及它们与 .NET 集合的关系。
ms.date: 09/09/2019
ms.openlocfilehash: 63d99532d14deea7800673dd5a6350dd9362ad54
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147966"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>列表和数组的重复字段

通过使用`repeated`前缀关键字在协议缓冲区（Protobuf）中指定列表。 下面的示例演示如何创建列表：

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

在生成的代码中，`repeated`字段由泛型类型`Google.Protobuf.Collections.RepeatedField<T>`表示，而不是任何内置 .NET 集合类型。

该`RepeatedField<T>`类型包括将列表序列化并将序列化为二进制导线格式所需的代码。 它实现所有标准 .NET 集合接口，如<xref:System.Collections.Generic.IList%601><xref:System.Collections.Generic.IEnumerable%601>和 。 因此，您可以使用 LINQ 查询或轻松将其转换为数组或列表。

>[!div class="step-by-step"]
>[上一个](protobuf-nested-types.md)
>[下一个](protobuf-reserved.md)
