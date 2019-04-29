---
title: Docker 容器、映像和注册表
description: 了解注册表播放以 Docker 方式部署应用程序的整体的关键角色。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: e69490734a03cf58bf8534bc9e31110a11d44c58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795314"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="39183-103">Docker 容器、映像和注册表</span><span class="sxs-lookup"><span data-stu-id="39183-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="39183-104">使用 Docker 时，可以创建应用和服务并将它们及其依赖项打包到容器映像中。</span><span class="sxs-lookup"><span data-stu-id="39183-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="39183-105">映像是应用或服务及其配置和依赖项的静态表示形式。</span><span class="sxs-lookup"><span data-stu-id="39183-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="39183-106">若要运行应用或服务，应用的映像会被实例化，从而创建一个在 Docker 主机上运行的容器。</span><span class="sxs-lookup"><span data-stu-id="39183-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="39183-107">容器最初在开发环境或 PC 中进行测试。</span><span class="sxs-lookup"><span data-stu-id="39183-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="39183-108">在注册表中，作为映像库中存储图像。</span><span class="sxs-lookup"><span data-stu-id="39183-108">You store images in a registry, that acts as a library of images.</span></span> <span data-ttu-id="39183-109">需要注册表才可部署到生产协调程序。</span><span class="sxs-lookup"><span data-stu-id="39183-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="39183-110">Docker 通过 [Docker Hub](https://hub.docker.com/)维护一个公共注册表；其他供应商为不同映像集合提供注册表，包括 [Azure 容器注册表](https://azure.microsoft.com/services/container-registry/)。</span><span class="sxs-lookup"><span data-stu-id="39183-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images, including [Azure Container Registry](https://azure.microsoft.com/services/container-registry/).</span></span> <span data-ttu-id="39183-111">或者，企业可以在本地为自己的 Docker 映像建立一个专用注册表。</span><span class="sxs-lookup"><span data-stu-id="39183-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="39183-112">图 1-4 显示了 Docker 中的映像和注册表如何与其他组件相关联。</span><span class="sxs-lookup"><span data-stu-id="39183-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="39183-113">图中还显示了供应商提供的多个注册表产品/服务。</span><span class="sxs-lookup"><span data-stu-id="39183-113">It also shows the multiple registry offerings from vendors.</span></span>

![在 Docker 中的基本分类：注册表就像书架映像的存储，并可用于提取用于生成要运行服务或 web 应用容器。](./media/image4.png)

<span data-ttu-id="39183-118">**图 1-4**。</span><span class="sxs-lookup"><span data-stu-id="39183-118">**Figure 1-4**.</span></span> <span data-ttu-id="39183-119">Docker 术语和概念的分类</span><span class="sxs-lookup"><span data-stu-id="39183-119">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="39183-120">通过将图像放在注册表中，您可以存储静态和不可变的应用程序，包括所有依赖项，在框架级别。</span><span class="sxs-lookup"><span data-stu-id="39183-120">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="39183-121">然后，可在多个环境中对映像进行版本管理和部署，从而提供一致的部署单元。</span><span class="sxs-lookup"><span data-stu-id="39183-121">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="39183-122">无论是托管在本地还是托管在云中，在下列情况下都建议使用私有映像注册表：</span><span class="sxs-lookup"><span data-stu-id="39183-122">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

- <span data-ttu-id="39183-123">由于保密性，映像不能被公开分享。</span><span class="sxs-lookup"><span data-stu-id="39183-123">Your images must not be shared publicly due to confidentiality.</span></span>

- <span data-ttu-id="39183-124">希望映像与所选部署环境之间的网络延迟最小。</span><span class="sxs-lookup"><span data-stu-id="39183-124">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="39183-125">例如，如果生产环境是 Azure，你可能想要存储在映像[Azure 容器注册表](https://azure.microsoft.com/services/container-registry/)，以便网络延迟很小。</span><span class="sxs-lookup"><span data-stu-id="39183-125">For example, if your production environment is Azure, you probably want to store your images in [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) so that network latency is minimal.</span></span> <span data-ttu-id="39183-126">同样，如果生产环境为本地，则你可能希望在同一本地网络中提供一个本地 Doker 可信注册表。</span><span class="sxs-lookup"><span data-stu-id="39183-126">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="39183-127">[上一页](docker-terminology.md)
>[下一页](road-to-modern-applications-based-on-containers.md)</span><span class="sxs-lookup"><span data-stu-id="39183-127">[Previous](docker-terminology.md)
[Next](road-to-modern-applications-based-on-containers.md)</span></span>
