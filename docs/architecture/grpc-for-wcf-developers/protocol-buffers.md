---
title: 协议缓冲区-适用于 WCF 开发人员的 gRPC
description: 用于 gRPC 网络的协议缓冲区网络格式简介。
ms.date: 09/09/2019
ms.openlocfilehash: dbe8cb43475cfeec19051daf68452ef86269372f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967293"
---
# <a name="protocol-buffers"></a>协议缓冲区

gRPC services 以*协议缓冲区（Protobuf）消息*的形式发送和接收数据，类似于 WCF 的数据协定。 Protobuf 是一种将结构化数据序列化到计算机以进行读取和写入的有效方法，不会产生诸如 XML 或 JSON 之类的用户可读格式产生的开销。

本章介绍了 Protobuf 的工作原理，以及如何定义你自己的 Protobuf 消息。

## <a name="how-protobuf-works"></a>Protobuf 的工作原理

大多数 .NET 对象序列化技术（包括 WCF 的数据协定）通过使用反射在运行时分析对象结构。 与此相反，大多数 Protobuf 库要求在 `.proto` 文件中使用专用语言（*协议缓冲区语言*）预先定义结构。 编译器将使用此文件为任何支持的平台（包括 .NET、Java、C/C++、JavaScript 等）生成代码。 Protobuf 编译器（`protoc`）由 Google 维护，但其他实现可用。 生成的代码是高效的并且经过优化，可快速序列化和反序列化数据。

Protobuf 连网格式本身是二进制编码，使用一些巧妙的技巧来最大程度地减少用于表示消息的字节数。 不需要对二进制编码格式的了解使用 Protobuf，但如果您感兴趣，可以在[协议缓冲区网站](https://developers.google.com/protocol-buffers/docs/encoding)上了解有关该格式的详细信息。

>[!div class="step-by-step"]
>[上一页](why-grpc.md)
>[下一页](protobuf-messages.md)
