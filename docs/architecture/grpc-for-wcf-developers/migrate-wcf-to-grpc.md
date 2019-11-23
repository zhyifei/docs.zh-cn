---
title: 将 WCF 解决方案迁移到 WCF 开发人员的 gRPC-gRPC
description: 如何将不同类型的 WCF 服务迁移到 gRPC 中的等效类型。
ms.date: 09/02/2019
ms.openlocfilehash: 33823d20e1593323a03da12981c5a4534c4d491a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971776"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="1a2c1-103">将 WCF 解决方案迁移到 gRPC</span><span class="sxs-lookup"><span data-stu-id="1a2c1-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="1a2c1-104">本章将介绍如何使用 ASP.NET Core 3.0 gRPC 项目，并演示如何将不同类型的 WCF 服务迁移到 gRPC 等效项：</span><span class="sxs-lookup"><span data-stu-id="1a2c1-104">This chapter will look at how to work with ASP.NET Core 3.0 gRPC projects and demonstrate migrating different types of WCF service to the gRPC equivalent:</span></span>

- <span data-ttu-id="1a2c1-105">创建 ASP.NET Core 3.0 gRPC 项目。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-105">Create an ASP.NET Core 3.0 gRPC project.</span></span>
- <span data-ttu-id="1a2c1-106">简单的请求-答复操作到 gRPC 一元 RPC。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-106">Simple Request-Reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="1a2c1-107">用于 gRPC 客户端流式处理 RPC 的单向操作。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="1a2c1-108">用于 gRPC 双向流式处理 RPC 的全双工服务。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-108">Full Duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="1a2c1-109">在本章末尾，还可以使用流式处理服务与重复字段的比较来返回数据集，并使用客户端库。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-109">There's also a comparison of using streaming services versus repeated fields for returning data sets, and the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="1a2c1-110">示例 WCF 应用程序是一组股票交易服务的最小存根，使用称为*Autofac*的开源反转（IoC）容器库来注入依赖关系。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-110">The sample WCF application is a minimal stub of a set of stock trading services, using the open-source Inversion of Control (IoC) container library called *Autofac* for dependency injection.</span></span> <span data-ttu-id="1a2c1-111">它包括三个服务，每个服务类型一个。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-111">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="1a2c1-112">以下部分将更详细地讨论服务。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-112">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="1a2c1-113">可从 GitHub 上的[dotnet/grpc 开发人员](https://github.com/dotnet-architecture/grpc-for-wcf-developers)下载解决方案。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-113">The solutions can be downloaded from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="1a2c1-114">服务使用虚设数据来最大程度地减少外部依赖项。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-114">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="1a2c1-115">这些示例包括每个服务的 WCF 和 gRPC 实现。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-115">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1a2c1-116">[上一页](ws-protocols.md)
>[下一页](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="1a2c1-116">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
