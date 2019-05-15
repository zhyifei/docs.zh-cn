---
title: 在 DockerFile 中使用 Windows PowerShell 命令来设置 Windows 容器 (基于 Docker 标准)
description: 了解如何使用 Docker 在 Windows 容器中时使用 PowerShell
ms.date: 02/15/2019
ms.openlocfilehash: e91d278aef1365a111e8d67ff04092dfc6a44185
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641589"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="5e923-103">在 DockerFile 中使用 Windows PowerShell 命令来设置 Windows 容器 (基于 Docker 标准)</span><span class="sxs-lookup"><span data-stu-id="5e923-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="5e923-104">与[Windows 容器](/virtualization/windowscontainers/about/index)，可以将转换现有的 Windows 应用程序到 Docker 映像并使用与 Docker 生态系统的其余部分相同的工具进行部署。</span><span class="sxs-lookup"><span data-stu-id="5e923-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="5e923-105">若要使用 Windows 容器，您只需在 DockerFile 中编写 Windows PowerShell 命令如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5e923-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="5e923-106">在这种情况下，我们使用 Windows PowerShell 来安装 Windows Server Core 基本映像，以及 IIS。</span><span class="sxs-lookup"><span data-stu-id="5e923-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="5e923-107">在类似的方式，还可以使用 Windows PowerShell 命令来设置其他组件，如传统的 ASP.NET 4.x 和.NET 4.6 或任何其他 Windows 软件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5e923-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="5e923-108">[上一页](visual-studio-tools-for-docker.md)
>[下一页](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="5e923-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>
