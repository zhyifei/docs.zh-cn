---
title: 将 WCF 解决方案迁移到 WCF 开发人员的 gRPC-gRPC
description: 如何将不同类型的 WCF 服务迁移到 gRPC 中的等效类型。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 65c30b777d9981cb3291b846f698f2a69b4498fc
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841497"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a>将 WCF 解决方案迁移到 gRPC

本章将介绍如何使用 ASP.NET Core 3.0 gRPC 项目，并演示如何将不同类型的 WCF 服务迁移到 gRPC 等效项：

- 创建 ASP.NET Core 3.0 gRPC 项目。
- 简单的请求-答复操作到 gRPC 一元 RPC。
- 用于 gRPC 客户端流式处理 RPC 的单向操作。
- 用于 gRPC 双向流式处理 RPC 的全双工服务。

在本章末尾，还可以使用流式处理服务与重复字段的比较来返回数据集，并使用客户端库。

示例 WCF 应用程序是一组股票交易服务的最小存根，使用称为*Autofac*的开源反转（IoC）容器库来注入依赖关系。 它包括三个服务，每个服务类型一个。 以下部分将更详细地讨论服务。 可从 GitHub 上的[dotnet/grpc 开发人员](https://github.com/dotnet-architecture/grpc-for-wcf-developers)下载解决方案。 服务使用虚设数据来最大程度地减少外部依赖项。

这些示例包括每个服务的 WCF 和 gRPC 实现。

>[!div class="step-by-step"]
>[上一页](ws-protocols.md)
>[下一页](create-project.md)
