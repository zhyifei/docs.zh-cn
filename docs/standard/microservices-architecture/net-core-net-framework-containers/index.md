---
title: 为 Docker 容器选择 .NET Core 还是 .NET Framework
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 为 Docker 容器选择 .NET Core 还是 .NET Framework
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: b483214e7bd039a71ae642aa26e69d63222af8ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="45d8d-103">为 Docker 容器选择 .NET Core 还是 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="45d8d-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="45d8d-104">通过 .NET 生成服务器端容器化 Docker 应用程序时，有两种支持的实现方式：[.NET Framework](https://www.microsoft.com/net/download/framework) 和 [.NET Core](https://www.microsoft.com/net/download/core)。</span><span class="sxs-lookup"><span data-stu-id="45d8d-104">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="45d8d-105">这两者共享许多 .NET 标准组件，可在它们之间共享代码。</span><span class="sxs-lookup"><span data-stu-id="45d8d-105">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="45d8d-106">但两者之间存在根本差异，可根据需要实现的目标选择实现方式。</span><span class="sxs-lookup"><span data-stu-id="45d8d-106">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="45d8d-107">本节提供有关何时选择每个实现方式的指南。</span><span class="sxs-lookup"><span data-stu-id="45d8d-107">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="45d8d-108">[上一页] (../container-docker-introduction/docker-containers-images-registries.md) [下一页] (general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="45d8d-108">[Previous] (../container-docker-introduction/docker-containers-images-registries.md) [Next] (general-guidance.md)</span></span>
