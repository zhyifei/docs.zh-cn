---
title: Docker 容器、映像和注册表
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 43b76f738fa4b7c89423a5b9fac7ef91f40880c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568727"
---
# <a name="docker-containers-images-and-registries"></a>Docker 容器、映像和注册表

当使用 Docker，你创建的应用程序或服务和包它和到容器映像及其依赖项。 映像是应用或服务及其配置和依赖项的静态表示形式。

若要运行的应用程序或服务，应用程序的映像是实例化以创建一个容器，将在 Docker 主机运行。 最初，会在开发环境或 PC 中测试容器。

将图像存储在注册表中，它将充当的图像库中。 部署到生产 orchestrators 时，你需要注册表。 Docker 通过[Docker 中心](https://hub.docker.com/)维护公共注册表；其他供应商为不同映像集合提供注册表。 或者，企业可以拥有一个本地专用注册表，用于其 Docker 映像。

图 1-4 显示图像和注册表在 Docker 中的如何与其他组件关联。 还显示了供应商的多个注册表产品/服务。

![](./media/image4.png)

图 1-4： 的 Docker 术语和概念的分类

通过将图像放在注册表中，你可以存储静态且不会改变应用程序，包括所有依赖关系，在 framework 级别。 您然后可以进行版本化和部署在多个环境中的映像并因此提供了一致部署单元。

私有映像注册表，可以在本地托管，或者在云中，建议在以下情况下：

-   由于保密性，不能公开分享映像。

-   在映像和所选部署环境之间，希望网络延迟保持最低。 例如，如果你的生产环境是 Azure，你可能想要在 Azure 容器注册表中存储映像，以便将降至最低网络延迟。 同样，如果生产环境是在本地，便需要使本地 Docker 信任的注册表在相同的本地网络中可用。

>[!div class="step-by-step"]
[以前] (docker-terminology.md) [下一步] (Docker-application-lifecycle/index.md)
