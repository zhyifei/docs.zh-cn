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
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="f0e00-103">列表和数组的重复字段</span><span class="sxs-lookup"><span data-stu-id="f0e00-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="f0e00-104">通过使用`repeated`前缀关键字在协议缓冲区（Protobuf）中指定列表。</span><span class="sxs-lookup"><span data-stu-id="f0e00-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="f0e00-105">下面的示例演示如何创建列表：</span><span class="sxs-lookup"><span data-stu-id="f0e00-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="f0e00-106">在生成的代码中，`repeated`字段由泛型类型`Google.Protobuf.Collections.RepeatedField<T>`表示，而不是任何内置 .NET 集合类型。</span><span class="sxs-lookup"><span data-stu-id="f0e00-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span>

<span data-ttu-id="f0e00-107">该`RepeatedField<T>`类型包括将列表序列化并将序列化为二进制导线格式所需的代码。</span><span class="sxs-lookup"><span data-stu-id="f0e00-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="f0e00-108">它实现所有标准 .NET 集合接口，如<xref:System.Collections.Generic.IList%601><xref:System.Collections.Generic.IEnumerable%601>和 。</span><span class="sxs-lookup"><span data-stu-id="f0e00-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="f0e00-109">因此，您可以使用 LINQ 查询或轻松将其转换为数组或列表。</span><span class="sxs-lookup"><span data-stu-id="f0e00-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f0e00-110">[上一个](protobuf-nested-types.md)
>[下一个](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="f0e00-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
