---
title: 在 DockerFile 中使用 Windows PowerShell 命令来设置 Windows 容器 (基于 Docker 标准)
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 5e85beea0efbee6a2b6594e3a49d705505a36e1c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149388"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>在 DockerFile 中使用 Windows PowerShell 命令来设置 Windows 容器 (基于 Docker 标准)

与[Windows 容器](/virtualization/windowscontainers/about/index)，可以将转换现有的 Windows 应用程序到 Docker 映像并使用与 Docker 生态系统的其余部分相同的工具进行部署。

若要使用 Windows 容器，您只需在 DockerFile 中编写 Windows PowerShell 命令如以下示例所示：

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

在这种情况下，我们使用 Windows PowerShell 来安装 Windows Server Core 基本映像，以及 IIS。

在类似的方式，还可以使用 Windows PowerShell 命令来设置其他组件，如传统的 ASP.NET 4.x 和.NET 4.6 或任何其他 Windows 软件，如下所示：

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[上一页](visual-studio-tools-for-docker.md)
>[下一页](../docker-devops-workflow/index.md)
