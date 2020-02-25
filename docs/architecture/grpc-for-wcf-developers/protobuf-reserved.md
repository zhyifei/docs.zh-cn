---
title: Protobuf 保留字段-WCF 开发人员 gRPC
description: 了解有关跨版本兼容性的保留字段。
ms.date: 09/09/2019
ms.openlocfilehash: 50082a1aab2e7707a1839b9d56455124a9e4a6a1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542971"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="527c2-103">Protobuf 保留字段</span><span class="sxs-lookup"><span data-stu-id="527c2-103">Protobuf reserved fields</span></span>

<span data-ttu-id="527c2-104">协议缓冲区（Protobuf）中的向后兼容性保证依赖于字段编号始终表示相同的数据项。</span><span class="sxs-lookup"><span data-stu-id="527c2-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="527c2-105">如果从服务的新版本的消息中删除字段，则永远不应重复使用该字段号。</span><span class="sxs-lookup"><span data-stu-id="527c2-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="527c2-106">可以使用 `reserved` 关键字强制此。</span><span class="sxs-lookup"><span data-stu-id="527c2-106">You can enfore this by using the `reserved` keyword.</span></span> 

<span data-ttu-id="527c2-107">如果从前面定义的 `Stock` 消息中删除了 "`displayName`" 和 "`marketId`" 字段，则应该保留其字段编号，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="527c2-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="527c2-108">你还可以使用 `reserved` 关键字作为以后可能添加的字段的占位符。</span><span class="sxs-lookup"><span data-stu-id="527c2-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="527c2-109">可以通过使用 `to` 关键字将连续的字段编号表示为范围。</span><span class="sxs-lookup"><span data-stu-id="527c2-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="527c2-110">[上一页](protobuf-repeated.md)
>[下一页](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="527c2-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
