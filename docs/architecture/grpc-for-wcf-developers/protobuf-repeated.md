---
title: 列表和数组的重复字段-gRPC for WCF 开发人员
description: 了解 Protobuf 如何处理集合及其与 .NET 集合之间的关系。
ms.date: 09/09/2019
ms.openlocfilehash: 16f2b5a54b032f32c8fcb9d572d5284fe589cb01
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542954"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>列表和数组的重复字段

使用 `repeated` prefix 关键字在协议缓冲区（Protobuf）中指定列表。 下面的示例演示如何创建列表：

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

在生成的代码中，`repeated` 字段由 `Google.Protobuf.Collections.RepeatedField<T>` 泛型类型（而不是任何内置 .NET 集合类型）表示。 

`RepeatedField<T>` 类型包括将列表序列化和反序列化为二进制线路格式所需的代码。 它实现所有标准 .NET 集合接口，如 <xref:System.Collections.Generic.IList%601> 和 <xref:System.Collections.Generic.IEnumerable%601>。 因此，您可以使用 LINQ 查询或轻松地将其转换为数组或列表。

>[!div class="step-by-step"]
>[上一页](protobuf-nested-types.md)
>[下一页](protobuf-reserved.md)
