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
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="a2321-103">Docker 容器、映像和注册表</span><span class="sxs-lookup"><span data-stu-id="a2321-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="a2321-104">使用 Docker 时，可以创建应用和服务并将它们及其依赖项打包到容器映像中。</span><span class="sxs-lookup"><span data-stu-id="a2321-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="a2321-105">映像是应用或服务及其配置和依赖项的静态表示形式。</span><span class="sxs-lookup"><span data-stu-id="a2321-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="a2321-106">若要运行应用或服务，应用的映像会被实例化，从而创建一个在 Docker 主机上运行的容器。</span><span class="sxs-lookup"><span data-stu-id="a2321-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="a2321-107">容器最初在开发环境或 PC 中进行测试。</span><span class="sxs-lookup"><span data-stu-id="a2321-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="a2321-108">将映像存储在充当映像库的注册表中。</span><span class="sxs-lookup"><span data-stu-id="a2321-108">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="a2321-109">需要注册表才可部署到生产协调程序。</span><span class="sxs-lookup"><span data-stu-id="a2321-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="a2321-110">Docker 通过 [Docker 中心](https://hub.docker.com/)维护公用注册表；其他供应商为不同的映像集合提供注册表。</span><span class="sxs-lookup"><span data-stu-id="a2321-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="a2321-111">或者，企业可以在本地为自己的 Docker 映像建立一个专用注册表。</span><span class="sxs-lookup"><span data-stu-id="a2321-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="a2321-112">图 1-4 显示了 Docker 中的映像和注册表如何与其他组件相关联。</span><span class="sxs-lookup"><span data-stu-id="a2321-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="a2321-113">图中还显示了供应商提供的多个注册表产品/服务。</span><span class="sxs-lookup"><span data-stu-id="a2321-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="a2321-114">图 1-4:Docker 术语和概念的分类</span><span class="sxs-lookup"><span data-stu-id="a2321-114">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="a2321-115">通过将图像放在注册表中，您可以存储静态和不可变的应用程序，包括所有依赖项，在框架级别。</span><span class="sxs-lookup"><span data-stu-id="a2321-115">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="a2321-116">然后，可在多个环境中对映像进行版本管理和部署，从而提供一致的部署单元。</span><span class="sxs-lookup"><span data-stu-id="a2321-116">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="a2321-117">建议在以下情况下使用托管在本地或云中的专用映像注册表：</span><span class="sxs-lookup"><span data-stu-id="a2321-117">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="a2321-118">由于保密性，不能公开分享映像。</span><span class="sxs-lookup"><span data-stu-id="a2321-118">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="a2321-119">希望映像与所选部署环境之间的网络延迟最小。</span><span class="sxs-lookup"><span data-stu-id="a2321-119">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="a2321-120">例如，如果生产环境为 Azure，则你可能希望将映像存储在 Azure 容器注册表中，使网络延迟最小。</span><span class="sxs-lookup"><span data-stu-id="a2321-120">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="a2321-121">同样，如果生产环境为本地，则你可能希望在同一本地网络中提供一个本地 Doker 可信注册表。</span><span class="sxs-lookup"><span data-stu-id="a2321-121">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a2321-122">[上一页](docker-terminology.md)
>[下一页](Docker-application-lifecycle/index.md)</span><span class="sxs-lookup"><span data-stu-id="a2321-122">[Previous](docker-terminology.md)
[Next](Docker-application-lifecycle/index.md)</span></span>