---
title: 使用在 DockerFile 中的 Windows PowerShell 命令来设置 Windows 容器 (Docker 标准基于)
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: d68378a12a16dd4072b381f00241e781b40c3e16
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105545"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="d42d5-103">使用在 DockerFile 中的 Windows PowerShell 命令来设置 Windows 容器 (Docker 标准基于)</span><span class="sxs-lookup"><span data-stu-id="d42d5-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="d42d5-104">与[Windows 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)，你可以将转换现有的 Windows 应用程序为 Docker 映像并将其部署与 Docker 生态系统的其余部分所在的相同工具。</span><span class="sxs-lookup"><span data-stu-id="d42d5-104">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="d42d5-105">若要使用 Windows 容器，你只需编写 Windows PowerShell 命令在 DockerFile，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="d42d5-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="d42d5-106">在这种情况下，我们将使用 Windows PowerShell 安装 Windows Server Core 基础映像以及 IIS。</span><span class="sxs-lookup"><span data-stu-id="d42d5-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="d42d5-107">在类似的方式，你还可以使用 Windows PowerShell 命令设置其他组件，如传统 ASP.NET 4.x 和.NET 4.6 或任何其他 Windows 软件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d42d5-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="d42d5-108">[上一页](visual-studio-tools-for-docker.md)
[下一页](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="d42d5-108">[Previous](visual-studio-tools-for-docker.md)
[Next](../docker-devops-workflow/index.md)</span></span>
