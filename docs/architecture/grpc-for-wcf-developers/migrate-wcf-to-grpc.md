---
title: 将 WCF 解决方案迁移到 WCF 开发人员的 gRPC-gRPC
description: 如何将不同类型的 WCF 服务迁移到 gRPC 中的等效类型。
ms.date: 09/02/2019
ms.openlocfilehash: 12e724ab46a33547d352da7a604a5a994e617bc2
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628509"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a>将 WCF 解决方案迁移到 gRPC

本章介绍如何使用 ASP.NET Core 3.0 gRPC 项目，并演示如何将不同类型的 Windows Communication Foundation （WCF）服务迁移到 gRPC 等效项：

- 创建 ASP.NET Core 3.0 gRPC 项目。
- 简单的请求-答复操作到 gRPC 一元 RPC。
- 用于 gRPC 客户端流式处理 RPC 的单向操作。
- 全双工服务，gRPC 双向流式处理 RPC。

还比较了如何使用流式处理服务与重复字段来返回数据集，并在本章末尾讨论了如何使用客户端库。

示例 WCF 应用程序是一组股票交易服务的最小存根。 它使用名为 Autofac 的开源反转控制（IoC）容器库来注入依赖关系。 它包括三个服务，每个服务类型一个。 以下部分将更详细地讨论服务。 可以从 GitHub 上的[dotnet/grpc-for wcf 开发人员](https://github.com/dotnet-architecture/grpc-for-wcf-developers)下载解决方案。 服务使用虚设数据来最大程度地减少外部依赖项。

这些示例包括每个服务的 WCF 和 gRPC 实现。

>[!div class="step-by-step"]
>[上一页](ws-protocols.md)
>[下一页](create-project.md)
