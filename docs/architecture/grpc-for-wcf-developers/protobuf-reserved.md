---
title: 原托布夫保留字段 - gRPC 面向 WCF 开发人员
description: 了解跨版本兼容性的保留字段。
ms.date: 09/09/2019
ms.openlocfilehash: f89513c4659a02cbc94e1c659baecb9e750acbdc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111031"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="7a664-103">Protobuf 保留字段</span><span class="sxs-lookup"><span data-stu-id="7a664-103">Protobuf reserved fields</span></span>

<span data-ttu-id="7a664-104">协议缓冲区 （Protobuf） 中的向后兼容性保证依赖于始终表示相同数据项的字段编号。</span><span class="sxs-lookup"><span data-stu-id="7a664-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="7a664-105">如果从服务新版本中的消息中删除了字段，则不应重复使用该字段编号。</span><span class="sxs-lookup"><span data-stu-id="7a664-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="7a664-106">您可以使用`reserved`关键字强制执行此情况。</span><span class="sxs-lookup"><span data-stu-id="7a664-106">You can enforce this by using the `reserved` keyword.</span></span>

<span data-ttu-id="7a664-107">如果`displayName`从`marketId`前面定义`Stock`的消息中删除 和 字段，则应保留其字段编号，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="7a664-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="7a664-108">您还可以将`reserved`关键字用作将来可能添加的字段的占位符。</span><span class="sxs-lookup"><span data-stu-id="7a664-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="7a664-109">您可以使用`to`关键字将连续字段数表示为范围。</span><span class="sxs-lookup"><span data-stu-id="7a664-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="7a664-110">[上一个](protobuf-repeated.md)
>[下一个](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="7a664-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
