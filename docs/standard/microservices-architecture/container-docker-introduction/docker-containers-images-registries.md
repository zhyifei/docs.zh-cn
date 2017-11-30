---
title: "Docker 容器、 图像和注册表"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |Docker 容器、 图像和注册表"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 224fed34f06d10760b14aa9ecbae6c0e912915cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="docker-containers-images-and-registries"></a>Docker 容器、 图像和注册表

当使用 Docker，开发人员就会创建应用程序或服务和包它和到容器映像及其依赖项。 映像是静态的表示形式的应用程序或服务及其配置和依赖关系。

若要运行的应用程序或服务，应用程序的映像是实例化以创建一个容器，将在 Docker 主机运行。 最初已在开发环境或 PC 测试容器。

开发人员应将图像存储在注册表中，也不能充当的图像库部署到生产 orchestrators 时需要。 Docker 所维护的公共注册表通过[Docker Hub](https://hub.docker.com/); 其他供应商提供的映像的不同集合的注册表。 或者，企业可以具有私有注册表本地自己 Docker 映像。

图 2-4 显示图像和注册表在 Docker 中的如何与其他组件关联。 它还显示从供应商的多个注册表产品。

![](./media/image5.PNG)

**图 2-4**。 Docker 术语和概念的分类

将图像放在注册表中，您可以存储包括在 framework 级别及其依赖项的静态且不会改变应用程序。 这些映像可以将版本控制和多个环境中部署并因此提供一致的部署单元。

私有映像注册表，托管在本地，也不在云中，建议使用时：

-   不能由于保密性公开共享你的映像。

-   你想要你的映像和你选择的部署环境之间的最低网络延迟。 例如，如果你的生产环境是 Azure 云，你可能想要在 Azure 容器注册表中存储映像，以便将降至最低网络延迟。 类似地，如果你的生产环境上本地可能要在具有本地 Docker 受信任注册表相同的本地网络中可用。

>[!div class="step-by-step"]
[以前](docker-terminology.md) [下一步] (.../net-core-net-framework-containers/index.md)
