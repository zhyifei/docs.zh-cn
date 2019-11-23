---
title: 列表和数组的重复字段-gRPC for WCF 开发人员
description: 了解如何通过 Protobuf 处理集合，以及如何将其与 .NET 集合相关。
ms.date: 09/09/2019
ms.openlocfilehash: 17c579bc98ba62ea74b9452bdb28efd96fc51406
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967369"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="d22e7-103">列表和数组的重复字段</span><span class="sxs-lookup"><span data-stu-id="d22e7-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="d22e7-104">使用 `repeated` prefix 关键字在 Protobuf 中指定列表。</span><span class="sxs-lookup"><span data-stu-id="d22e7-104">Lists are specified in Protobuf using the `repeated` prefix keyword.</span></span> <span data-ttu-id="d22e7-105">下面的示例演示如何创建列表：</span><span class="sxs-lookup"><span data-stu-id="d22e7-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="d22e7-106">在生成的代码中，`repeated` 字段由 `Google.Protobuf.Collections.RepeatedField<T>` 泛型类型（而不是任何内置 .NET 集合类型）表示。</span><span class="sxs-lookup"><span data-stu-id="d22e7-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="d22e7-107">`RepeatedField<T>` 类型包括将列表序列化和反序列化为二进制线路格式所需的代码。</span><span class="sxs-lookup"><span data-stu-id="d22e7-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="d22e7-108">它实现所有标准 .NET 集合接口（如 <xref:System.Collections.Generic.IList%601> 和 <xref:System.Collections.Generic.IEnumerable%601>），因此可以使用 LINQ 查询或轻松地将其转换为数组或列表。</span><span class="sxs-lookup"><span data-stu-id="d22e7-108">It implements all the standard .NET collection interfaces such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>, so you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d22e7-109">[上一页](protobuf-nested-types.md)
>[下一页](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="d22e7-109">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
