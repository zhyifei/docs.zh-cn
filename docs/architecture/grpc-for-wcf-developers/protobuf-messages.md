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
# <a name="protobuf-messages"></a><span data-ttu-id="7e124-103">Protobuf 消息</span><span class="sxs-lookup"><span data-stu-id="7e124-103">Protobuf messages</span></span>

<span data-ttu-id="7e124-104">本节介绍如何在`.proto`文件中声明协议缓冲区（Protobuf）消息。</span><span class="sxs-lookup"><span data-stu-id="7e124-104">This section covers how to declare Protocol Buffer (Protobuf) messages in `.proto` files.</span></span> <span data-ttu-id="7e124-105">它解释了字段数和类型的基本概念，并查看`protoc`编译器生成的 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="7e124-105">It explains the fundamental concepts of field numbers and types, and it looks at the C# code that the `protoc` compiler generates.</span></span>

<span data-ttu-id="7e124-106">本章的其余部分将更详细地介绍在 Protobuf 中如何表示不同类型的数据。</span><span class="sxs-lookup"><span data-stu-id="7e124-106">The rest of the chapter will look in more detail at how different types of data are represented in Protobuf.</span></span>

## <a name="declaring-a-message"></a><span data-ttu-id="7e124-107">声明消息</span><span class="sxs-lookup"><span data-stu-id="7e124-107">Declaring a message</span></span>

<span data-ttu-id="7e124-108">在 Windows 通信基础 （WCF） 中，股票市场交易应用程序的`Stock`类可以定义如下示例：</span><span class="sxs-lookup"><span data-stu-id="7e124-108">In Windows Communication Foundation (WCF), a `Stock` class for a stock market trading application might be defined like the following example:</span></span>

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

<span data-ttu-id="7e124-109">要在 Protobuf 中实现等效类，必须在`.proto`文件中声明它。</span><span class="sxs-lookup"><span data-stu-id="7e124-109">To implement the equivalent class in Protobuf, you must declare it in the `.proto` file.</span></span> <span data-ttu-id="7e124-110">然后`protoc`，编译器将生成 .NET 类作为生成过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="7e124-110">The `protoc` compiler will then generate the .NET class as part of the build process.</span></span>

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

<span data-ttu-id="7e124-111">第一行声明正在使用的语法版本。</span><span class="sxs-lookup"><span data-stu-id="7e124-111">The first line declares the syntax version being used.</span></span> <span data-ttu-id="7e124-112">该语言版本 3 于 2016 年发布。</span><span class="sxs-lookup"><span data-stu-id="7e124-112">Version 3 of the language was released in 2016.</span></span> <span data-ttu-id="7e124-113">它是我们为 gRPC 服务推荐的版本。</span><span class="sxs-lookup"><span data-stu-id="7e124-113">It's the version that we recommend for gRPC services.</span></span>

<span data-ttu-id="7e124-114">该`option csharp_namespace`行指定要用于生成的 C# 类型的命名空间。</span><span class="sxs-lookup"><span data-stu-id="7e124-114">The `option csharp_namespace` line specifies the namespace to be used for the generated C# types.</span></span> <span data-ttu-id="7e124-115">在为其他语言编译文件时，`.proto`将忽略此选项。</span><span class="sxs-lookup"><span data-stu-id="7e124-115">This option will be ignored when the `.proto` file is compiled for other languages.</span></span> <span data-ttu-id="7e124-116">Protobuf 文件通常包含多种语言的语言特定选项。</span><span class="sxs-lookup"><span data-stu-id="7e124-116">Protobuf files often contain language-specific options for several languages.</span></span>

<span data-ttu-id="7e124-117">消息`Stock`定义指定四个字段。</span><span class="sxs-lookup"><span data-stu-id="7e124-117">The `Stock` message definition specifies four fields.</span></span> <span data-ttu-id="7e124-118">每个都有一个类型、一个名称和一个字段编号。</span><span class="sxs-lookup"><span data-stu-id="7e124-118">Each has a type, a name, and a field number.</span></span>

## <a name="field-numbers"></a><span data-ttu-id="7e124-119">字段编号</span><span class="sxs-lookup"><span data-stu-id="7e124-119">Field numbers</span></span>

<span data-ttu-id="7e124-120">字段编号是 Protobuf 的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="7e124-120">Field numbers are an important part of Protobuf.</span></span> <span data-ttu-id="7e124-121">它们用于标识二进制编码数据中的字段，这意味着它们无法从服务的版本更改为版本。</span><span class="sxs-lookup"><span data-stu-id="7e124-121">They're used to identify fields in the binary encoded data, which means they can't change from version to version of your service.</span></span> <span data-ttu-id="7e124-122">优点是向后兼容性和正向兼容性是可能的。</span><span class="sxs-lookup"><span data-stu-id="7e124-122">The advantage is that backward compatibility and forward compatibility are possible.</span></span> <span data-ttu-id="7e124-123">只要处理丢失值的可能性，客户端和服务将忽略他们不知道的字段编号。</span><span class="sxs-lookup"><span data-stu-id="7e124-123">Clients and services will simply ignore field numbers that they don't know about, as long as the possibility of missing values is handled.</span></span>

<span data-ttu-id="7e124-124">在二进制格式中，字段编号与类型标识符组合。</span><span class="sxs-lookup"><span data-stu-id="7e124-124">In the binary format, the field number is combined with a type identifier.</span></span> <span data-ttu-id="7e124-125">字段编号从 1 到 15 可以编码其类型为单个字节。</span><span class="sxs-lookup"><span data-stu-id="7e124-125">Field numbers from 1 to 15 can be encoded with their type as a single byte.</span></span> <span data-ttu-id="7e124-126">从 16 到 2，047 的数字需要 2 个字节。</span><span class="sxs-lookup"><span data-stu-id="7e124-126">Numbers from 16 to 2,047 take 2 bytes.</span></span> <span data-ttu-id="7e124-127">如果出于任何原因需要邮件上的 2，047 个字段，则可以走高。</span><span class="sxs-lookup"><span data-stu-id="7e124-127">You can go higher if you need more than 2,047 fields on a message for any reason.</span></span> <span data-ttu-id="7e124-128">字段号 1 到 15 的单个字节标识符提供了更好的性能，因此应将它们用于最基本、最常用的字段。</span><span class="sxs-lookup"><span data-stu-id="7e124-128">The single byte identifiers for field numbers 1 to 15 offer better performance, so you should use them for the most basic, frequently used fields.</span></span>

## <a name="types"></a><span data-ttu-id="7e124-129">类型</span><span class="sxs-lookup"><span data-stu-id="7e124-129">Types</span></span>

<span data-ttu-id="7e124-130">类型声明使用 Protobuf 的本机标量数据类型，[下一节](protobuf-data-types.md)将更详细地讨论这些类型。</span><span class="sxs-lookup"><span data-stu-id="7e124-130">The type declarations are using Protobuf's native scalar data types, which are discussed in more detail in [the next section](protobuf-data-types.md).</span></span> <span data-ttu-id="7e124-131">本章的其余部分将介绍 Protobuf 的内置类型，并展示它们与常见的 .NET 类型的关系。</span><span class="sxs-lookup"><span data-stu-id="7e124-131">The rest of this chapter will cover Protobuf's built-in types and show how they relate to common .NET types.</span></span>

> [!NOTE]
> <span data-ttu-id="7e124-132">Protobuf 不支持本机`decimal`类型，因此`double`使用。</span><span class="sxs-lookup"><span data-stu-id="7e124-132">Protobuf doesn't natively support a `decimal` type, so `double` is used instead.</span></span> <span data-ttu-id="7e124-133">对于需要全小数精度的应用程序，请参阅本章下一部分[中有关小数部分](protobuf-data-types.md#decimals)的部分。</span><span class="sxs-lookup"><span data-stu-id="7e124-133">For applications that require full decimal precision, refer to the [section on decimals](protobuf-data-types.md#decimals) in the next part of this chapter.</span></span>

## <a name="the-generated-code"></a><span data-ttu-id="7e124-134">生成的代码</span><span class="sxs-lookup"><span data-stu-id="7e124-134">The generated code</span></span>

<span data-ttu-id="7e124-135">生成应用程序时，Protobuf 会为每个消息创建类，将其本机类型映射到 C# 类型。</span><span class="sxs-lookup"><span data-stu-id="7e124-135">When you build your application, Protobuf creates classes for each of your messages, mapping its native types to C# types.</span></span> <span data-ttu-id="7e124-136">生成的`Stock`类型将具有以下签名：</span><span class="sxs-lookup"><span data-stu-id="7e124-136">The generated `Stock` type would have the following signature:</span></span>

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

<span data-ttu-id="7e124-137">生成的实际代码要比这更复杂得多。</span><span class="sxs-lookup"><span data-stu-id="7e124-137">The actual code that's generated is far more complicated than this.</span></span> <span data-ttu-id="7e124-138">原因是每个类都包含序列化自身并将其反序列化为二进制线格式所需的所有代码。</span><span class="sxs-lookup"><span data-stu-id="7e124-138">The reason is that each class contains all the code necessary to serialize and deserialize itself to the binary wire format.</span></span>

### <a name="property-names"></a><span data-ttu-id="7e124-139">属性名称</span><span class="sxs-lookup"><span data-stu-id="7e124-139">Property names</span></span>

<span data-ttu-id="7e124-140">请注意，Protobuf 编译器应用于`PascalCase`属性名称，尽管它们位于`snake_case``.proto`文件中。</span><span class="sxs-lookup"><span data-stu-id="7e124-140">Note that the Protobuf compiler applied `PascalCase` to the property names, although they were `snake_case` in the `.proto` file.</span></span> <span data-ttu-id="7e124-141">[Protobuf 样式指南](https://developers.google.com/protocol-buffers/docs/style)建议`snake_case`在消息定义中使用，以便其他平台的代码生成生成其约定的预期情况。</span><span class="sxs-lookup"><span data-stu-id="7e124-141">The [Protobuf style guide](https://developers.google.com/protocol-buffers/docs/style) recommends using `snake_case` in your message definitions so that the code generation for other platforms produces the expected case for their conventions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7e124-142">[上一个](protocol-buffers.md)
>[下一个](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="7e124-142">[Previous](protocol-buffers.md)
[Next](protobuf-data-types.md)</span></span>
