---
title: Protobuf 枚举-WCF 开发人员 gRPC
description: 了解如何在 Protobuf 中声明和使用枚举。
ms.date: 09/09/2019
ms.openlocfilehash: 01cf4a4e5e0eda1e7ddff2a6780119fcb3120dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543139"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="f7c3a-103">Protobuf 枚举</span><span class="sxs-lookup"><span data-stu-id="f7c3a-103">Protobuf enumerations</span></span>

<span data-ttu-id="f7c3a-104">Protobuf 支持枚举类型。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="f7c3a-105">您在上一节中看到了此支持，枚举用于确定 `Oneof` 字段的类型。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="f7c3a-106">您可以定义自己的枚举类型，Protobuf 会将其编译为C#枚举类型。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span> 

<span data-ttu-id="f7c3a-107">由于可以将 Protobuf 用于各种语言，因此枚举的命名约定不同于C#约定。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="f7c3a-108">但是，代码生成器会将名称转换为传统C#大小写。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="f7c3a-109">如果字段名称的 Pascal 等效项以枚举名称开头，则将其删除。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="f7c3a-110">例如，在以下 Protobuf 枚举中，字段带有 `ACCOUNT_STATUS`的前缀。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="f7c3a-111">此前缀等效于 Pascal 大小写枚举名称 `AccountStatus`。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="f7c3a-112">生成器创建一个C#等效于以下代码的枚举：</span><span class="sxs-lookup"><span data-stu-id="f7c3a-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="f7c3a-113">Protobuf 枚举定义的第一个字段*必须*为零常量。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="f7c3a-114">与在C#中一样，可以声明多个具有相同值的字段。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="f7c3a-115">但必须使用枚举中的 "`allow_alias`" 选项显式启用此选项：</span><span class="sxs-lookup"><span data-stu-id="f7c3a-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="f7c3a-116">可以在 `.proto` 文件中的顶层声明枚举，也可以在消息定义中进行嵌套。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="f7c3a-117">嵌套的枚举（如嵌套消息）将在生成的 message 类中的 `.Types` 静态类内声明。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="f7c3a-118">无法将[[Flags]](xref:System.FlagsAttribute)特性应用于 Protobuf 生成的枚举，Protobuf 不了解按位枚举组合。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="f7c3a-119">请查看以下示例：</span><span class="sxs-lookup"><span data-stu-id="f7c3a-119">Look at the following example:</span></span>

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

<span data-ttu-id="f7c3a-120">如果将 `product.AvailableIn` 设置为 `Region.NorthAmerica | Region.SouthAmerica`，则会将其序列化为 `3`整数值。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="f7c3a-121">当客户端或服务器尝试对值进行反序列化时，它在 `3`的枚举定义中找不到匹配项。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="f7c3a-122">将 `Region.None`结果。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="f7c3a-123">在 Protobuf 中处理多个枚举值的最佳方式是使用枚举类型的 `repeated` 字段。</span><span class="sxs-lookup"><span data-stu-id="f7c3a-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f7c3a-124">[上一页](protobuf-any-oneof.md)
>[下一页](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="f7c3a-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
