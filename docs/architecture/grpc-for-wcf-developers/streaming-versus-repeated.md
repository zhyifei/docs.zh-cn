---
title: gRPC 流式处理服务与重复字段-gRPC for WCF 开发人员
description: 将重复字段比较流式处理服务，作为通过 gRPC 传递数据集合的方式。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: e48fe4882139e029dbf5b52451a2e68cb4316677
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841323"
---
# <a name="grpc-streaming-services-versus-repeated-fields"></a>gRPC 流式处理服务与重复字段

gRPC services 提供两种方法来返回数据集或对象的列表。 协议缓冲区消息规范使用 `repeated` 关键字来声明另一消息内的列表或消息的数组。 GRPC service 规范使用 `stream` 关键字声明一个长时间运行的持久连接，其中发送多条消息，并可单独处理。 `stream` 功能还可用于长时间运行的临时数据（如通知或日志消息），但本章会将其用于返回单个数据集。

使用哪种方法取决于各种因素，例如数据集的总体大小、在客户端或服务器端创建数据集所用的时间，以及在第一项可用时数据集的使用者是否可以开始操作，或需要完整的数据集来执行任何有用的操作。

## <a name="when-to-use-repeated-fields"></a>何时使用 `repeated` 字段

对于任何大小都受限制并且可以在短时间内完全生成的数据集（例如，在一秒钟内），你应在常规 Protobuf 消息中使用 `repeated` 字段。 例如，在电子商务系统中，若要在订单内生成项列表，可能会很快，并且列表将不会太大。 使用 `repeated` 字段返回一条消息比使用 `stream` 更快，导致网络开销更少。

如果客户端在开始处理数据之前需要所有数据，并且数据集足够小，可以在内存中构造，则即使服务器内存中实际创建的数据集速度较慢，也应考虑使用 `repeated` 字段。

## <a name="when-to-use-stream-methods"></a>何时使用 `stream` 方法

使用流式处理请求或响应最好地传输消息对象很大的数据集。 在内存中构造大型对象、将其写入网络，然后释放资源更有效。 此方法可提高服务的可伸缩性。

同样，不约束大小的数据集应通过流发送，以避免在构造这些数据时内存不足。

对于每个单独项可由使用者单独处理的数据集，如果它表示可以向最终用户指示进度，则应考虑使用流。 这可以提高应用程序的明显响应能力，尽管这应该与应用程序的总体性能进行平衡。

流可能很有用的另一种情况是跨多个服务对消息进行处理。 如果链中的每个服务都返回一个流，则终端服务（即该链中的最后一个服务）可以开始返回消息，这些消息可通过链进行处理并传递回原始请求者，后者可以返回流或聚合生成单个响应消息。 此方法非常适合映射/减少等模式。

>[!div class="step-by-step"]
>[上一页](migrate-duplex-services.md)
>[下一页](client-libraries.md)
