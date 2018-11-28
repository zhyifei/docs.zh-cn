---
title: Docker 容器、映像和注册表
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: ff5a1f3e4b09ac9f7ea600d3f127523b96fcce55
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106358"
---
# <a name="docker-containers-images-and-registries"></a>Docker 容器、映像和注册表

当使用Docker时，您可以创建应用程序或服务，并将其及其依赖项打包到容器映像中。 映像是应用程序或服务及其配置和依赖项的静态表示形式。

要运行应用程序或服务，应用程序的映像将被实例化以创建一个容器，该容器将在 Docker 主机上运行。 容器最初在开发环境或 PC 中进行测试。

您将映像存储在注册表中，该注册表充当映像库。 当部署到生产 orchestrators 时需要注册表。 Docker 通过[Docker Hub](https://hub.docker.com/)维护一个公共注册表； 其他供应商为不同的映像集合提供注册表。 或者，企业可以在本地使用私有注册表来获取自己的 Docker 映像。

图 1-4 显示映像和注册表在 Docker 中的如何与其他组件关联。 还显示了供应商的多个注册表产品/服务。

![](./media/image4.png)

图 1-4： Docker 术语和概念的分类

通过将映像放在注册表中，您可以在框架级别存储静态和不可变的应用程序，包括它们的所有依赖项。 然后，您可以在多个环境中对映像进行版本管理和部署，从而提供一致的部署单元。

建议在以下情况下使用驻留在本地或云中的私有映像注册表：

-   由于保密性，不能公开分享映像。

-   您希望映像与所选部署环境之间的网络延迟最小。 例如，如果您的生产环境是 Azure ，则可能希望将映像存储在 Azure 容器注册表中，以便最小化网络延迟。 类似的，如果您的生产环境在本地，您可能希望在同一本地网络中提供本地 Docker 信任的注册表。



>[!div class="step-by-step"]
[上一页](docker-terminology.md)
[下一页](Docker-application-lifecycle/index.md)
