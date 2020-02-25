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
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="bc8bb-103">列表和数组的重复字段</span><span class="sxs-lookup"><span data-stu-id="bc8bb-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="bc8bb-104">使用 `repeated` prefix 关键字在协议缓冲区（Protobuf）中指定列表。</span><span class="sxs-lookup"><span data-stu-id="bc8bb-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="bc8bb-105">下面的示例演示如何创建列表：</span><span class="sxs-lookup"><span data-stu-id="bc8bb-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="bc8bb-106">在生成的代码中，`repeated` 字段由 `Google.Protobuf.Collections.RepeatedField<T>` 泛型类型（而不是任何内置 .NET 集合类型）表示。</span><span class="sxs-lookup"><span data-stu-id="bc8bb-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> 

<span data-ttu-id="bc8bb-107">`RepeatedField<T>` 类型包括将列表序列化和反序列化为二进制线路格式所需的代码。</span><span class="sxs-lookup"><span data-stu-id="bc8bb-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="bc8bb-108">它实现所有标准 .NET 集合接口，如 <xref:System.Collections.Generic.IList%601> 和 <xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="bc8bb-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="bc8bb-109">因此，您可以使用 LINQ 查询或轻松地将其转换为数组或列表。</span><span class="sxs-lookup"><span data-stu-id="bc8bb-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bc8bb-110">[上一页](protobuf-nested-types.md)
>[下一页](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="bc8bb-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
