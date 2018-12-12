---
title: Docker 容器、映像和注册表
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: af235280c985d20f9e6a2ee6096edbe6c3aad63a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53142744"
---
# <a name="docker-containers-images-and-registries"></a>Docker 容器、映像和注册表

使用 Docker 时，可以创建应用和服务并将它们及其依赖项打包到容器映像中。 映像是应用或服务及其配置和依赖项的静态表示形式。

若要运行应用或服务，应用的映像会被实例化，从而创建一个在 Docker 主机上运行的容器。 容器最初在开发环境或 PC 中进行测试。

将映像存储在充当映像库的注册表中。 需要注册表才可部署到生产协调程序。 Docker 通过 [Docker 中心](https://hub.docker.com/)维护公用注册表；其他供应商为不同的映像集合提供注册表。 或者，企业可以在本地为自己的 Docker 映像建立一个专用注册表。

图 1-4 显示了 Docker 中的映像和注册表如何与其他组件相关联。 图中还显示了供应商提供的多个注册表产品/服务。

![](./media/image4.png)

图 1-4:Docker 术语和概念的分类

通过将图像放在注册表中，您可以存储静态和不可变的应用程序，包括所有依赖项，在框架级别。 然后，可在多个环境中对映像进行版本管理和部署，从而提供一致的部署单元。

建议在以下情况下使用托管在本地或云中的专用映像注册表：

-   由于保密性，不能公开分享映像。

-   希望映像与所选部署环境之间的网络延迟最小。 例如，如果生产环境为 Azure，则你可能希望将映像存储在 Azure 容器注册表中，使网络延迟最小。 同样，如果生产环境为本地，则你可能希望在同一本地网络中提供一个本地 Doker 可信注册表。

>[!div class="step-by-step"]
>[上一页](docker-terminology.md)
>[下一页](Docker-application-lifecycle/index.md)