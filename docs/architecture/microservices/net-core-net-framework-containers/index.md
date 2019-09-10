---
title: 为 Docker 容器选择 .NET Core 还是 .NET Framework
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 为 Docker 容器选择 .NET Core 还是 .NET Framework
ms.date: 09/11/2018
ms.openlocfilehash: b01aaf25f4071e8e4a07905a12ec9dd0d89a738d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849274"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="ef855-103">为 Docker 容器选择 .NET Core 还是 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ef855-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="ef855-104">通过 .NET 生成服务器端容器化 Docker 应用程序时，有两种支持的框架：[.NET Framework 和 .NET Core](https://dotnet.microsoft.com/download)。</span><span class="sxs-lookup"><span data-stu-id="ef855-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="ef855-105">这两者共享许多 .NET 平台组件，可在它们之间共享代码。</span><span class="sxs-lookup"><span data-stu-id="ef855-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="ef855-106">但两者之间存在根本差异，可根据需要实现的目标选择框架。</span><span class="sxs-lookup"><span data-stu-id="ef855-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="ef855-107">本节提供有关何时选择各框架的指南。</span><span class="sxs-lookup"><span data-stu-id="ef855-107">This section provides guidance on when to choose each framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ef855-108">[上一页](../container-docker-introduction/docker-containers-images-registries.md)
>[下一页](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="ef855-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
