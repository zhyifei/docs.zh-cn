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
# <a name="protobuf-enumerations"></a>Protobuf 枚举

Protobuf 支持枚举类型。 您在上一节中看到了此支持，枚举用于确定 `Oneof` 字段的类型。 您可以定义自己的枚举类型，Protobuf 会将其编译为C#枚举类型。 

由于可以将 Protobuf 用于各种语言，因此枚举的命名约定不同于C#约定。 但是，代码生成器会将名称转换为传统C#大小写。 如果字段名称的 Pascal 等效项以枚举名称开头，则将其删除。

例如，在以下 Protobuf 枚举中，字段带有 `ACCOUNT_STATUS`的前缀。 此前缀等效于 Pascal 大小写枚举名称 `AccountStatus`。

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

生成器创建一个C#等效于以下代码的枚举：

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

Protobuf 枚举定义的第一个字段*必须*为零常量。 与在C#中一样，可以声明多个具有相同值的字段。 但必须使用枚举中的 "`allow_alias`" 选项显式启用此选项：

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

可以在 `.proto` 文件中的顶层声明枚举，也可以在消息定义中进行嵌套。 嵌套的枚举（如嵌套消息）将在生成的 message 类中的 `.Types` 静态类内声明。

无法将[[Flags]](xref:System.FlagsAttribute)特性应用于 Protobuf 生成的枚举，Protobuf 不了解按位枚举组合。 请查看以下示例：

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

如果将 `product.AvailableIn` 设置为 `Region.NorthAmerica | Region.SouthAmerica`，则会将其序列化为 `3`整数值。 当客户端或服务器尝试对值进行反序列化时，它在 `3`的枚举定义中找不到匹配项。 将 `Region.None`结果。

在 Protobuf 中处理多个枚举值的最佳方式是使用枚举类型的 `repeated` 字段。

>[!div class="step-by-step"]
>[上一页](protobuf-any-oneof.md)
>[下一页](protobuf-maps.md)
