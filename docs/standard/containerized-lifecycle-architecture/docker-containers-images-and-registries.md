---
title: "Docker 容器、 图像和注册表"
description: "使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0cccead8833c63f19b359f830f555e7ff31daa1a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="docker-containers-images-and-registries"></a>Docker 容器、 图像和注册表

当使用 Docker，你创建的应用程序或服务和包它和到容器映像及其依赖项。 映像是静态的表示形式的应用程序或服务及其配置和依赖关系。

若要运行的应用程序或服务，应用程序的映像是实例化以创建一个容器，将在 Docker 主机运行。 最初已在开发环境或 PC 测试容器。

将图像存储在注册表中，它将充当的图像库中。 部署到生产 orchestrators 时，你需要注册表。 Docker 所维护的公共注册表通过[Docker Hub](https://hub.docker.com/); 其他供应商提供的映像的不同集合的注册表。 或者，企业可以具有私有注册表本地自己 Docker 映像。

图 1-4 显示图像和注册表在 Docker 中的如何与其他组件关联。 它还显示从供应商的多个注册表产品。

![](./media/image4.png)

图 1-4： 的 Docker 术语和概念的分类

通过将图像放在注册表中，你可以存储静态且不会改变应用程序，包括所有依赖关系，在 framework 级别。 您然后可以进行版本化和部署在多个环境中的映像并因此提供了一致部署单元。

私有映像注册表，可以在本地托管，或者在云中，建议在以下情况下：

-   不能由于保密性公开共享你的映像。

-   你想要你的映像和你选择的部署环境之间的最低网络延迟。 例如，如果你的生产环境是 Azure，你可能想要在 Azure 容器注册表中存储映像，以便将降至最低网络延迟。 类似地，如果你的生产环境上本地可能要在具有本地 Docker 受信任注册表相同的本地网络中可用。

>[!div class="step-by-step"]
[以前](docker-terminology.md) [下一步] (Docker-应用程序的生命周期/index.md)
