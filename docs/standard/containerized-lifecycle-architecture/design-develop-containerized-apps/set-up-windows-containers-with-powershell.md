---
title: "使用在 DockerFile 中的 Windows PowerShell 命令来设置 Windows 容器 (Docker 标准基于)"
description: "使用 Microsoft 平台和工具的 Docker 容器化应用程序生命周期"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: f7e92b0f1c749e2c00e3afc4ffcfc2fc88d7628f
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2017
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="bf952-104">使用在 DockerFile 中的 Windows PowerShell 命令来设置 Windows 容器 (Docker 标准基于)</span><span class="sxs-lookup"><span data-stu-id="bf952-104">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="bf952-105">与[Windows 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)，你可以将转换现有的 Windows 应用程序为 Docker 映像并将其部署与 Docker 生态系统的其余部分所在的相同工具。</span><span class="sxs-lookup"><span data-stu-id="bf952-105">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="bf952-106">若要使用 Windows 容器，你只需编写 Windows PowerShell 命令在 DockerFile，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="bf952-106">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="bf952-107">在这种情况下，我们将使用 Windows PowerShell 安装 Windows Server Core 基础映像以及 IIS。</span><span class="sxs-lookup"><span data-stu-id="bf952-107">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="bf952-108">在类似的方式，你还可以使用 Windows PowerShell 命令设置其他组件，如传统 ASP.NET 4.x 和.NET 4.6 或任何其他 Windows 软件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bf952-108">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="bf952-109">[以前](visual-studio 的工具的对于-docker.md) [下一步] (.../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="bf952-109">[Previous] (visual-studio-tools-for-docker.md) [Next] (../docker-devops-workflow/index.md)</span></span>
