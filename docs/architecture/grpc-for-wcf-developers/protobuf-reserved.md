---
title: Protobuf 保留字段-WCF 开发人员 gRPC
description: 了解有关跨版本兼容性的保留字段。
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 34697371299bdc5d9a58c0696c1ce7d19816ca87
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841389"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="55dfa-103">Protobuf 保留字段</span><span class="sxs-lookup"><span data-stu-id="55dfa-103">Protobuf reserved fields</span></span>

<span data-ttu-id="55dfa-104">Protobuf 的后向兼容性保证依赖于字段编号始终表示相同的数据项。</span><span class="sxs-lookup"><span data-stu-id="55dfa-104">Protobuf's backward-compatibility guarantees rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="55dfa-105">如果从服务的新版本的消息中删除字段，则永远不应重复使用该字段号。</span><span class="sxs-lookup"><span data-stu-id="55dfa-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="55dfa-106">这可以使用 `reserved` 关键字来强制执行。</span><span class="sxs-lookup"><span data-stu-id="55dfa-106">This can be enforced using the `reserved` keyword.</span></span> <span data-ttu-id="55dfa-107">如果从前面定义的 `Stock` 消息中删除了 "`displayName`" 和 "`marketId`" 字段，则应该保留其字段编号，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="55dfa-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="55dfa-108">`reserved` 关键字还可用作将来可能添加的字段的占位符。</span><span class="sxs-lookup"><span data-stu-id="55dfa-108">The `reserved` keyword can also be used as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="55dfa-109">可以使用 `to` 关键字将连续的字段编号表示为范围。</span><span class="sxs-lookup"><span data-stu-id="55dfa-109">Contiguous field numbers can be expressed as a range using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="55dfa-110">[上一页](protobuf-repeated.md)
>[下一页](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="55dfa-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
