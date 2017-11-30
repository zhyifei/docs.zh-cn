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
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="1262e-104">Docker 容器、 图像和注册表</span><span class="sxs-lookup"><span data-stu-id="1262e-104">Docker containers, images, and registries</span></span>

<span data-ttu-id="1262e-105">当使用 Docker，开发人员就会创建应用程序或服务和包它和到容器映像及其依赖项。</span><span class="sxs-lookup"><span data-stu-id="1262e-105">When using Docker, a developer creates an app or service and packages it and its dependencies into a container image.</span></span> <span data-ttu-id="1262e-106">映像是静态的表示形式的应用程序或服务及其配置和依赖关系。</span><span class="sxs-lookup"><span data-stu-id="1262e-106">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="1262e-107">若要运行的应用程序或服务，应用程序的映像是实例化以创建一个容器，将在 Docker 主机运行。</span><span class="sxs-lookup"><span data-stu-id="1262e-107">To run the app or service, the app’s image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="1262e-108">最初已在开发环境或 PC 测试容器。</span><span class="sxs-lookup"><span data-stu-id="1262e-108">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="1262e-109">开发人员应将图像存储在注册表中，也不能充当的图像库部署到生产 orchestrators 时需要。</span><span class="sxs-lookup"><span data-stu-id="1262e-109">Developers should store images in a registry, which acts as a library of images and is needed when deploying to production orchestrators.</span></span> <span data-ttu-id="1262e-110">Docker 所维护的公共注册表通过[Docker Hub](https://hub.docker.com/); 其他供应商提供的映像的不同集合的注册表。</span><span class="sxs-lookup"><span data-stu-id="1262e-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="1262e-111">或者，企业可以具有私有注册表本地自己 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="1262e-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="1262e-112">图 2-4 显示图像和注册表在 Docker 中的如何与其他组件关联。</span><span class="sxs-lookup"><span data-stu-id="1262e-112">Figure 2-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="1262e-113">它还显示从供应商的多个注册表产品。</span><span class="sxs-lookup"><span data-stu-id="1262e-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image5.PNG)

<span data-ttu-id="1262e-114">**图 2-4**。</span><span class="sxs-lookup"><span data-stu-id="1262e-114">**Figure 2-4**.</span></span> <span data-ttu-id="1262e-115">Docker 术语和概念的分类</span><span class="sxs-lookup"><span data-stu-id="1262e-115">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="1262e-116">将图像放在注册表中，您可以存储包括在 framework 级别及其依赖项的静态且不会改变应用程序。</span><span class="sxs-lookup"><span data-stu-id="1262e-116">Putting images in a registry lets you store static and immutable application bits, including all their dependencies at a framework level.</span></span> <span data-ttu-id="1262e-117">这些映像可以将版本控制和多个环境中部署并因此提供一致的部署单元。</span><span class="sxs-lookup"><span data-stu-id="1262e-117">Those images can then be versioned and deployed in multiple environments and therefore provide a consistent deployment unit.</span></span>

<span data-ttu-id="1262e-118">私有映像注册表，托管在本地，也不在云中，建议使用时：</span><span class="sxs-lookup"><span data-stu-id="1262e-118">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

-   <span data-ttu-id="1262e-119">不能由于保密性公开共享你的映像。</span><span class="sxs-lookup"><span data-stu-id="1262e-119">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="1262e-120">你想要你的映像和你选择的部署环境之间的最低网络延迟。</span><span class="sxs-lookup"><span data-stu-id="1262e-120">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="1262e-121">例如，如果你的生产环境是 Azure 云，你可能想要在 Azure 容器注册表中存储映像，以便将降至最低网络延迟。</span><span class="sxs-lookup"><span data-stu-id="1262e-121">For example, if your production environment is Azure cloud, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="1262e-122">类似地，如果你的生产环境上本地可能要在具有本地 Docker 受信任注册表相同的本地网络中可用。</span><span class="sxs-lookup"><span data-stu-id="1262e-122">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="1262e-123">[以前](docker-terminology.md) [下一步] (.../net-core-net-framework-containers/index.md)</span><span class="sxs-lookup"><span data-stu-id="1262e-123">[Previous] (docker-terminology.md) [Next] (../net-core-net-framework-containers/index.md)</span></span>
