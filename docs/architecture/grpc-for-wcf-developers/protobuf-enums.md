---
title: Protobuf 枚举-WCF 开发人员 gRPC
description: 了解如何在 Protobuf 中声明和使用枚举。
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: f18196f54caba824d7101782a88cf3bf699560d5
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841413"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="85bf6-103">Protobuf 枚举</span><span class="sxs-lookup"><span data-stu-id="85bf6-103">Protobuf enumerations</span></span>

<span data-ttu-id="85bf6-104">Protobuf 支持枚举类型，如下一节中所示，枚举用于确定 `oneof` 字段的类型。</span><span class="sxs-lookup"><span data-stu-id="85bf6-104">Protobuf supports enumeration types, as seen in the previous section where an enum was used to determine the type of a `oneof` field.</span></span> <span data-ttu-id="85bf6-105">您可以定义自己的枚举类型，Protobuf 会将其编译C#为枚举类型。</span><span class="sxs-lookup"><span data-stu-id="85bf6-105">You can define your own enumeration types and Protobuf will compile them to C# enum types.</span></span> <span data-ttu-id="85bf6-106">由于 Protobuf 可以与不同的C#语言一起使用，因此枚举的命名约定不同于约定。</span><span class="sxs-lookup"><span data-stu-id="85bf6-106">Since Protobuf can be used with different languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="85bf6-107">但是，代码生成器非常聪明，并将名称转换为传统C#大小写形式。</span><span class="sxs-lookup"><span data-stu-id="85bf6-107">However, the code generator is clever and converts the names to the traditional C# case.</span></span> <span data-ttu-id="85bf6-108">如果字段名称的 Pascal 等效项以枚举名称开头，则将其删除。</span><span class="sxs-lookup"><span data-stu-id="85bf6-108">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="85bf6-109">例如，在此 Protobuf 枚举中，字段带有 `ACCOUNT_STATUS`的前缀，这等同于 Pascal 事例枚举名称： `AccountStatus`。</span><span class="sxs-lookup"><span data-stu-id="85bf6-109">For example, in this Protobuf enumeration the fields are prefixed with `ACCOUNT_STATUS`, which is equivalent to the Pascal case enum name: `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="85bf6-110">因此，生成器创建了C#等效于以下代码的枚举：</span><span class="sxs-lookup"><span data-stu-id="85bf6-110">So, the generator creates a C# enum equivalent to the following code:</span></span>

```csharp
public enum AccountStatus
{
    Unknown = 0,
    Pending = 1,
    Active = 2,
    Suspended = 3,
    Closed = 4
}
```

<span data-ttu-id="85bf6-111">Protobuf 枚举定义的第一个字段**必须**为零常量。</span><span class="sxs-lookup"><span data-stu-id="85bf6-111">Protobuf enumeration definitions **must** have a zero constant as their first field.</span></span> <span data-ttu-id="85bf6-112">与在C#中一样，你可以声明多个具有相同值的字段，但必须使用枚举中的 `allow_alias` 选项显式启用此选项：</span><span class="sxs-lookup"><span data-stu-id="85bf6-112">As in C#, you can declare multiple fields with the same value, but you must explicitly enable this option using the `allow_alias` option in the enum:</span></span>

```protobuf
enum AccountStatus {
  option allow_alias = true;
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
  ACCOUNT_STATUS_CANCELLED = 4;
}
```

<span data-ttu-id="85bf6-113">可以在 `.proto` 文件中的顶层声明枚举，也可以在消息定义中进行嵌套。</span><span class="sxs-lookup"><span data-stu-id="85bf6-113">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="85bf6-114">嵌套的枚举（如嵌套消息）将在生成的 message 类中的 `.Types` 静态类内声明。</span><span class="sxs-lookup"><span data-stu-id="85bf6-114">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="85bf6-115">无法将[[Flags]](xref:System.FlagsAttribute)特性应用于 Protobuf 生成的枚举，Protobuf 不了解按位枚举组合。</span><span class="sxs-lookup"><span data-stu-id="85bf6-115">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="85bf6-116">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="85bf6-116">Take a look at the following example:</span></span>

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region available_in = 1;
}
```

<span data-ttu-id="85bf6-117">如果将 `product.AvailableIn` 设置为 `Region.NorthAmerica | Region.SouthAmerica`，则会将其序列化为 `3`整数值。</span><span class="sxs-lookup"><span data-stu-id="85bf6-117">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="85bf6-118">当客户端或服务器尝试对值进行反序列化时，它在 `3` 的枚举定义中找不到匹配项，结果将 `Region.None`。</span><span class="sxs-lookup"><span data-stu-id="85bf6-118">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3` and the result will be `Region.None`.</span></span>

<span data-ttu-id="85bf6-119">在 Protobuf 中处理多个枚举值的最佳方式是使用枚举类型的 `repeated` 字段。</span><span class="sxs-lookup"><span data-stu-id="85bf6-119">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="85bf6-120">[上一页](protobuf-any-oneof.md)
>[下一页](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="85bf6-120">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
