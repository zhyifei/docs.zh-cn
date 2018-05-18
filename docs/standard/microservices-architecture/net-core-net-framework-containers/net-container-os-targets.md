---
title: 使用 .NET 容器时定位的操作系统
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用 .NET 容器时定位的操作系统
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 0b06f64027a736ead148ea5511cf20e900b8b39a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="what-os-to-target-with-net-containers"></a>使用 .NET 容器时定位的操作系统

由于 Docker 支持多种操作系统，且鉴于 .NET Framework 和 .NET Core 之间的差异，应根据所使用的框架，面向特定操作系统和特定版本。 

对于 Windows，可使用 Windows Server Core 或 Windows Nano Server。 这两种 Windows 版本分别提供 .NET Framework 和 .NET Core 各自所需的特征（Windows Server Core 中的 IIS 与 Nano Server 中自承载的 web 服务器，如 Kestrel）。 

对于 Linux，正式的 .NET Docker 映像（如 Debian）中提供并支持多个发行版本。

图 3-1 显示基于所使用的 .NET framework，可使用的操作系统版本。

![](./media/image1.png)

**图 3-1。** 根据 .NET framework 确定要面向的操作系统

如果想使用不同的 Linux 发行版本或要使用 Microsoft 不支持的映像版本，还可以创建自己的 Docker 映像。 例如，可以使用 ASP.NET Core 创建一个在传统 .NET Framework 和 Windows Server Core 上运行的映像，但这不是常见的 Docker 方案。

将映像名称添加到 Dockerfile 文件后，可根据所使用的标记选择操作系统和版本，如下例所示：

-   microsoft/**dotnet:2.0.0-runtime-jessie**

        .NET Core 2.0 runtime-only on Linux

-   microsoft/**dotnet:2.0.0-runtime-nanoserver-1709** 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   microsoft/**aspnetcore:2.0**
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
[上一项] (container-framework-choice-factors.md) [下一项] (official-net-docker-images.md)
