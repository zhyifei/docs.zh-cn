---
title: ".NET 容器定向到何种操作系统"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |.NET 容器定向到何种操作系统"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 828ccb5e7a76f9419e80793b6cb3a6ba24f358cf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="what-os-to-target-with-net-containers"></a>.NET 容器定向到何种操作系统

给定的各种操作系统支持 Docker 和.NET Framework 和.NET 核心之间的差异，应针对特定操作系统和具体取决于你使用的 framework 的特定版本。 

对于 Windows，你可以使用 Windows Server Core 或 Windows Nano Server。 这些 Windows 版本提供不同的特征 (中而不是自承载的 web 服务器，例如，Kestrel Nano Server 中的 Windows Server Core IIS) 程序可能需要的.NET Framework 或.NET Core 分别。 

对于 Linux，多个发行版的可用性和支持中 （如 Debian) 的正式.NET Docker 映像。

图 3-1 中可以看到的可能的操作系统版本，具体取决于使用的.NET framework。

![](./media/image1.png)

**图 3-1。** 具体取决于版本的.NET framework 面向的操作系统

你想要使用不同的 Linux 发行版或要用使用不由 Microsoft 提供的版本映像，你还可以在情况下创建你自己的 Docker 映像。 例如，你可能会与传统的.NET Framework 和是 Docker 不常见方案的 Windows Server Core 上运行的 ASP.NET 核心创建映像。

当映像名称添加到 Dockerfile 文件时，可以选择的操作系统和版本，具体取决于你使用，如以下示例所示的标记：

-   microsoft /**dotnet:2.0.0-运行时的 jessie**

        .NET Core 2.0 runtime-only on Linux

-   microsoft /**dotnet:2.0.0-运行时的 nanoserver-1709年** 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   microsoft /**aspnetcore:2.0**
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
[以前](容器-framework-选择-factors.md) [下一步] (官方-net-docker-images.md)
