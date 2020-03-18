---
title: 原托布夫保留字段 - gRPC 面向 WCF 开发人员
description: 了解跨版本兼容性的保留字段。
ms.date: 09/09/2019
ms.openlocfilehash: bde658c671e970b7ec841d71d5b4284eb91195f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147940"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="19a26-103">Protobuf 保留字段</span><span class="sxs-lookup"><span data-stu-id="19a26-103">Protobuf reserved fields</span></span>

<span data-ttu-id="19a26-104">协议缓冲区 （Protobuf） 中的向后兼容性保证依赖于始终表示相同数据项的字段编号。</span><span class="sxs-lookup"><span data-stu-id="19a26-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="19a26-105">如果从服务新版本中的消息中删除了字段，则不应重复使用该字段编号。</span><span class="sxs-lookup"><span data-stu-id="19a26-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="19a26-106">您可以使用`reserved`关键字来强化此值。</span><span class="sxs-lookup"><span data-stu-id="19a26-106">You can enfore this by using the `reserved` keyword.</span></span>

<span data-ttu-id="19a26-107">如果`displayName`从`marketId`前面定义`Stock`的消息中删除 和 字段，则应保留其字段编号，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="19a26-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="19a26-108">您还可以将`reserved`关键字用作将来可能添加的字段的占位符。</span><span class="sxs-lookup"><span data-stu-id="19a26-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="19a26-109">您可以使用`to`关键字将连续字段数表示为范围。</span><span class="sxs-lookup"><span data-stu-id="19a26-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="19a26-110">[上一个](protobuf-repeated.md)
>[下一个](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="19a26-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
