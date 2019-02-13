---
title: 在 DockerFile 中使用 Windows PowerShell 命令来设置 Windows 容器 (基于 Docker 标准)
description: 了解如何使用 Docker 在 Windows 容器中时使用 PowerShell
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: df9e98e3f963b6492e1008455251b61a8cb6e771
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219966"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="74a18-103">在 DockerFile 中使用 Windows PowerShell 命令来设置 Windows 容器 (基于 Docker 标准)</span><span class="sxs-lookup"><span data-stu-id="74a18-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="74a18-104">与[Windows 容器](/virtualization/windowscontainers/about/index)，可以将转换现有的 Windows 应用程序到 Docker 映像并使用与 Docker 生态系统的其余部分相同的工具进行部署。</span><span class="sxs-lookup"><span data-stu-id="74a18-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="74a18-105">若要使用 Windows 容器，您只需在 DockerFile 中编写 Windows PowerShell 命令如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="74a18-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="74a18-106">在这种情况下，我们使用 Windows PowerShell 来安装 Windows Server Core 基本映像，以及 IIS。</span><span class="sxs-lookup"><span data-stu-id="74a18-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="74a18-107">在类似的方式，还可以使用 Windows PowerShell 命令来设置其他组件，如传统的 ASP.NET 4.x 和.NET 4.6 或任何其他 Windows 软件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="74a18-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="74a18-108">[上一页](visual-studio-tools-for-docker.md)
>[下一页](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="74a18-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>
