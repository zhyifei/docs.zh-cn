---
title: Docker 容器、映像和注册表
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9de37f9ee3a8fe7ce4a337fc548030b2aeadba55
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="7331c-103">Docker 容器、映像和注册表</span><span class="sxs-lookup"><span data-stu-id="7331c-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="7331c-104">当使用 Docker，你创建的应用程序或服务和包它和到容器映像及其依赖项。</span><span class="sxs-lookup"><span data-stu-id="7331c-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="7331c-105">映像是应用或服务及其配置和依赖项的静态表示形式。</span><span class="sxs-lookup"><span data-stu-id="7331c-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="7331c-106">若要运行的应用程序或服务，应用程序的映像是实例化以创建一个容器，将在 Docker 主机运行。</span><span class="sxs-lookup"><span data-stu-id="7331c-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="7331c-107">最初，会在开发环境或 PC 中测试容器。</span><span class="sxs-lookup"><span data-stu-id="7331c-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="7331c-108">将图像存储在注册表中，它将充当的图像库中。</span><span class="sxs-lookup"><span data-stu-id="7331c-108">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="7331c-109">部署到生产 orchestrators 时，你需要注册表。</span><span class="sxs-lookup"><span data-stu-id="7331c-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="7331c-110">Docker 通过[Docker 中心](https://hub.docker.com/)维护公共注册表；其他供应商为不同映像集合提供注册表。</span><span class="sxs-lookup"><span data-stu-id="7331c-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="7331c-111">或者，企业可以拥有一个本地专用注册表，用于其 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="7331c-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="7331c-112">图 1-4 显示图像和注册表在 Docker 中的如何与其他组件关联。</span><span class="sxs-lookup"><span data-stu-id="7331c-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="7331c-113">还显示了供应商的多个注册表产品/服务。</span><span class="sxs-lookup"><span data-stu-id="7331c-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="7331c-114">图 1-4： 的 Docker 术语和概念的分类</span><span class="sxs-lookup"><span data-stu-id="7331c-114">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="7331c-115">通过将图像放在注册表中，你可以存储静态且不会改变应用程序，包括所有依赖关系，在 framework 级别。</span><span class="sxs-lookup"><span data-stu-id="7331c-115">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="7331c-116">您然后可以进行版本化和部署在多个环境中的映像并因此提供了一致部署单元。</span><span class="sxs-lookup"><span data-stu-id="7331c-116">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="7331c-117">私有映像注册表，可以在本地托管，或者在云中，建议在以下情况下：</span><span class="sxs-lookup"><span data-stu-id="7331c-117">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="7331c-118">由于保密性，不能公开分享映像。</span><span class="sxs-lookup"><span data-stu-id="7331c-118">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="7331c-119">在映像和所选部署环境之间，希望网络延迟保持最低。</span><span class="sxs-lookup"><span data-stu-id="7331c-119">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="7331c-120">例如，如果你的生产环境是 Azure，你可能想要在 Azure 容器注册表中存储映像，以便将降至最低网络延迟。</span><span class="sxs-lookup"><span data-stu-id="7331c-120">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="7331c-121">同样，如果生产环境是在本地，便需要使本地 Docker 信任的注册表在相同的本地网络中可用。</span><span class="sxs-lookup"><span data-stu-id="7331c-121">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="7331c-122">[以前](docker-terminology.md) [下一步] (Docker-应用程序的生命周期/index.md)</span><span class="sxs-lookup"><span data-stu-id="7331c-122">[Previous] (docker-terminology.md) [Next] (Docker-application-lifecycle/index.md)</span></span>
