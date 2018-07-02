---
title: Docker 容器、映像和注册表
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | Docker 容器、映像和注册表
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 4716159d052fd8e229ac42e5d17c72717ac86d9f
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106455"
---
# <a name="docker-containers-images-and-registries"></a>Docker 容器、映像和注册表

使用 Docker 时，开发人员会创建一个应用或服务，并将它及其依赖项打包到一个容器映像中。 映像是应用或服务及其配置和依赖项的静态表示形式。

若要运行应用或服务，应用的映像会实例化，以创建一个在 Docker 主机上运行的容器。 最初，会在开发环境或 PC 中测试容器。

开发人员应将映像存储在注册表中，该注册表可充当映射库并在部署到生产业务流程协调程序时使用。 Docker 通过[Docker 中心](https://hub.docker.com/)维护公共注册表；其他供应商为不同映像集合提供注册表。 或者，企业可以拥有一个本地专用注册表，用于其 Docker 映像。

图 2-4 显示了 Docker 中的映像和注册表与其他组件相关联的方式。 还显示了供应商的多个注册表产品/服务。

![](./media/image5.PNG)

**图 2-4**。 Docker 术语和概念的分类

将映射存储到注册表中可存储静态和不可变的应用程序，包括其在框架级别的所有依赖项。 然后，这些映像可部署到多种环境中，并进行版本控制，从而提供一致的部署单元。

无论是托管在本地还是托管在云中，在下列情况下都建议使用专用映像注册表：

-   由于保密性，不能公开分享映像。

-   在映像和所选部署环境之间，希望网络延迟保持最低。 例如，如果生产环境是 Azure 云，为实现最低的网络延迟，可将映像存储在 Azure 容器注册表中。 同样，如果生产环境是在本地，便需要使本地 Docker 信任的注册表在相同的本地网络中可用。

>[!div class="step-by-step"]
[上一页](docker-terminology.md)
[下一页](../net-core-net-framework-containers/index.md)
