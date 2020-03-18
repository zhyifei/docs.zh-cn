---
title: 原型消息 - gRPC，面向 WCF 开发人员
description: 了解如何在 IDL 中定义 Protobuf 消息并在 C# 中生成。
ms.date: 09/09/2019
ms.openlocfilehash: 5b3d4383de39a3785ef804fec21939a740f54669
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147979"
---
# <a name="protobuf-messages"></a>Protobuf 消息

本节介绍如何在`.proto`文件中声明协议缓冲区（Protobuf）消息。 它解释了字段数和类型的基本概念，并查看`protoc`编译器生成的 C# 代码。

本章的其余部分将更详细地介绍在 Protobuf 中如何表示不同类型的数据。

## <a name="declaring-a-message"></a>声明消息

在 Windows 通信基础 （WCF） 中，股票市场交易应用程序的`Stock`类可以定义如下示例：

```csharp
namespace TraderSys
{
    [DataContract]
    public class Stock
    {
        [DataMember]
        public int Id { get; set;}
        [DataMember]
        public string Symbol { get; set;}
        [DataMember]
        public string DisplayName { get; set;}
        [DataMember]
        public int MarketId { get; set; }
    }
}
```

要在 Protobuf 中实现等效类，必须在`.proto`文件中声明它。 然后`protoc`，编译器将生成 .NET 类作为生成过程的一部分。

```protobuf
syntax "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

第一行声明正在使用的语法版本。 该语言版本 3 于 2016 年发布。 它是我们为 gRPC 服务推荐的版本。

该`option csharp_namespace`行指定要用于生成的 C# 类型的命名空间。 在为其他语言编译文件时，`.proto`将忽略此选项。 Protobuf 文件通常包含多种语言的语言特定选项。

消息`Stock`定义指定四个字段。 每个都有一个类型、一个名称和一个字段编号。

## <a name="field-numbers"></a>字段编号

字段编号是 Protobuf 的重要组成部分。 它们用于标识二进制编码数据中的字段，这意味着它们无法从服务的版本更改为版本。 优点是向后兼容性和正向兼容性是可能的。 只要处理丢失值的可能性，客户端和服务将忽略他们不知道的字段编号。

在二进制格式中，字段编号与类型标识符组合。 字段编号从 1 到 15 可以编码其类型为单个字节。 从 16 到 2，047 的数字需要 2 个字节。 如果出于任何原因需要邮件上的 2，047 个字段，则可以走高。 字段号 1 到 15 的单个字节标识符提供了更好的性能，因此应将它们用于最基本、最常用的字段。

## <a name="types"></a>类型

类型声明使用 Protobuf 的本机标量数据类型，[下一节](protobuf-data-types.md)将更详细地讨论这些类型。 本章的其余部分将介绍 Protobuf 的内置类型，并展示它们与常见的 .NET 类型的关系。

> [!NOTE]
> Protobuf 不支持本机`decimal`类型，因此`double`使用。 对于需要全小数精度的应用程序，请参阅本章下一部分[中有关小数部分](protobuf-data-types.md#decimals)的部分。

## <a name="the-generated-code"></a>生成的代码

生成应用程序时，Protobuf 会为每个消息创建类，将其本机类型映射到 C# 类型。 生成的`Stock`类型将具有以下签名：

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

生成的实际代码要比这更复杂得多。 原因是每个类都包含序列化自身并将其反序列化为二进制线格式所需的所有代码。

### <a name="property-names"></a>属性名称

请注意，Protobuf 编译器应用于`PascalCase`属性名称，尽管它们位于`snake_case``.proto`文件中。 [Protobuf 样式指南](https://developers.google.com/protocol-buffers/docs/style)建议`snake_case`在消息定义中使用，以便其他平台的代码生成生成其约定的预期情况。

>[!div class="step-by-step"]
>[上一个](protocol-buffers.md)
>[下一个](protobuf-data-types.md)
