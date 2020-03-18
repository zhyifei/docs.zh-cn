---
title: 原数枚 - gRPC 面向 WCF 开发人员
description: 了解如何在 Protobuf 中声明和使用枚举。
ms.date: 09/09/2019
ms.openlocfilehash: 2177f568a671fa0e651625c6e025ac70c243feb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148070"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="33c6a-103">Protobuf 枚举</span><span class="sxs-lookup"><span data-stu-id="33c6a-103">Protobuf enumerations</span></span>

<span data-ttu-id="33c6a-104">Protobuf 支持枚举类型。</span><span class="sxs-lookup"><span data-stu-id="33c6a-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="33c6a-105">您在上一节中看到了此支持，其中使用枚举来确定`Oneof`字段的类型。</span><span class="sxs-lookup"><span data-stu-id="33c6a-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="33c6a-106">您可以定义自己的枚举类型，Protobuf 将将它们编译为 C# 枚举类型。</span><span class="sxs-lookup"><span data-stu-id="33c6a-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span>

<span data-ttu-id="33c6a-107">由于您可以将 Protobuf 用于各种语言，因此枚举的命名约定与 C# 约定不同。</span><span class="sxs-lookup"><span data-stu-id="33c6a-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="33c6a-108">但是，代码生成器将名称转换为传统的 C# 大小写。</span><span class="sxs-lookup"><span data-stu-id="33c6a-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="33c6a-109">如果字段名称的 Pascal 大小写以枚举名称开头，则将其删除。</span><span class="sxs-lookup"><span data-stu-id="33c6a-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="33c6a-110">例如，在下面的 Protobuf 枚举中，字段用 预缀为`ACCOUNT_STATUS`。</span><span class="sxs-lookup"><span data-stu-id="33c6a-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="33c6a-111">此前缀等效于 Pascal 大小写枚举名称`AccountStatus`。</span><span class="sxs-lookup"><span data-stu-id="33c6a-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="33c6a-112">生成器创建等效于以下代码的 C# 枚举：</span><span class="sxs-lookup"><span data-stu-id="33c6a-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="33c6a-113">Protobuf 枚举定义*必须*具有零常量作为第一个字段。</span><span class="sxs-lookup"><span data-stu-id="33c6a-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="33c6a-114">与 C# 中一样，您可以声明具有相同值的多个字段。</span><span class="sxs-lookup"><span data-stu-id="33c6a-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="33c6a-115">但是，您必须使用枚举中`allow_alias`的选项显式启用此选项：</span><span class="sxs-lookup"><span data-stu-id="33c6a-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="33c6a-116">您可以在`.proto`文件中的顶层声明枚举，也可以嵌套在消息定义中。</span><span class="sxs-lookup"><span data-stu-id="33c6a-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="33c6a-117">嵌套枚举（类似于嵌套消息）将在生成的消息类中的`.Types`静态类中声明。</span><span class="sxs-lookup"><span data-stu-id="33c6a-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="33c6a-118">无法将[[Flags]](xref:System.FlagsAttribute)属性应用于 Protobuf 生成的枚举，并且 Protobuf 不理解位级枚举组合。</span><span class="sxs-lookup"><span data-stu-id="33c6a-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="33c6a-119">查看以下示例：</span><span class="sxs-lookup"><span data-stu-id="33c6a-119">Look at the following example:</span></span>

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

<span data-ttu-id="33c6a-120">如果设置为`product.AvailableIn``Region.NorthAmerica | Region.SouthAmerica`，则序列化为整数值`3`。</span><span class="sxs-lookup"><span data-stu-id="33c6a-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="33c6a-121">当客户端或服务器尝试取消序列化该值时，它不会在 的`3`枚举定义中找到匹配项。</span><span class="sxs-lookup"><span data-stu-id="33c6a-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="33c6a-122">结果将为`Region.None`。</span><span class="sxs-lookup"><span data-stu-id="33c6a-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="33c6a-123">在 Protobuf 中使用多个枚举值的最佳方法是使用枚举类型的`repeated`字段。</span><span class="sxs-lookup"><span data-stu-id="33c6a-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="33c6a-124">[上一个](protobuf-any-oneof.md)
>[下一个](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="33c6a-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
