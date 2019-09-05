---
title: 为 Docker 容器选择 .NET Core 还是 .NET Framework
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 为 Docker 容器选择 .NET Core 还是 .NET Framework
ms.date: 09/11/2018
ms.openlocfilehash: 771d23cf4610e5778f0a144386754ce10d6ae144
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "70295215"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="a8982-103">为 Docker 容器选择 .NET Core 还是 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a8982-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="a8982-104">通过 .NET 生成服务器端容器化 Docker 应用程序时，有两种支持的框架：[.NET Framework 和 .NET Core](https://www.microsoft.com/net/download)。</span><span class="sxs-lookup"><span data-stu-id="a8982-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://www.microsoft.com/net/download).</span></span> <span data-ttu-id="a8982-105">这两者共享许多 .NET 平台组件，可在它们之间共享代码。</span><span class="sxs-lookup"><span data-stu-id="a8982-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="a8982-106">但两者之间存在根本差异，可根据需要实现的目标选择框架。</span><span class="sxs-lookup"><span data-stu-id="a8982-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="a8982-107">本节提供有关何时选择各框架的指南。</span><span class="sxs-lookup"><span data-stu-id="a8982-107">This section provides guidance on when to choose each framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a8982-108">[上一页](../container-docker-introduction/docker-containers-images-registries.md)
>[下一页](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="a8982-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
