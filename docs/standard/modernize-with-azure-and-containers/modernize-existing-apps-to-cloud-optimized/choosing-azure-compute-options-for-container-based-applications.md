---
title: 为基于容器的应用程序选择 Azure 计算平台
description: 更新现有.NET 应用程序与 Azure 云和 Windows 容器 |选择基于容器的应用程序的 Azure 计算平台
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: f251aecfeaf2421a5cecf218577369963bc736fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61811745"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="a2415-103">为基于容器的应用程序选择 Azure 计算平台</span><span class="sxs-lookup"><span data-stu-id="a2415-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="a2415-104">阅读前面的部分后，您已经注意到，Azure 是开放的云，提供多个选项。</span><span class="sxs-lookup"><span data-stu-id="a2415-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="a2415-105">可以根据需要使用最合适，但是，它还会呈现为容器化应用程序应使用何种产品/技术有关的问题。</span><span class="sxs-lookup"><span data-stu-id="a2415-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="a2415-106">作为*默认情况下*建议，下面是本指南中建议主要的准则：</span><span class="sxs-lookup"><span data-stu-id="a2415-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="a2415-107">**单个整体式应用程序：** 选择 Azure 应用服务</span><span class="sxs-lookup"><span data-stu-id="a2415-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="a2415-108">**N 层应用程序：** 如果你有一个或几个后端服务，请选择业务流程协调程序，如 Azure Kubernetes 服务 (AKS)、 Service Fabric (SF) 或应用服务</span><span class="sxs-lookup"><span data-stu-id="a2415-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="a2415-109">**Linux 微服务：** 选择 AKS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="a2415-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
- <span data-ttu-id="a2415-110">**Windows 微服务：** 选择 Service Fabric</span><span class="sxs-lookup"><span data-stu-id="a2415-110">**Windows microservices:** Choose Service Fabric</span></span>
- <span data-ttu-id="a2415-111">**无服务器函数 （&) 事件处理程序：** 选择 Azure 函数</span><span class="sxs-lookup"><span data-stu-id="a2415-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="a2415-112">**大规模批处理：** 选择 Azure Batch</span><span class="sxs-lookup"><span data-stu-id="a2415-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="a2415-113">但是，此建议应使用盐，片段执行如产品的选择将取决于特定应用程序的需求和特征。</span><span class="sxs-lookup"><span data-stu-id="a2415-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="a2415-114">即使最初它们可能看起来类似的类型，并非所有应用程序都是相同的。</span><span class="sxs-lookup"><span data-stu-id="a2415-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="a2415-115">在应用程序的需求的更深入地分析之后, 选择产品可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="a2415-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="a2415-116">但是，作为起点，最好能够从您可以开始评估的初步指导和测试基于针对特定的优先级。</span><span class="sxs-lookup"><span data-stu-id="a2415-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="a2415-117">在下一步图中，你可以分析多全局时详细的决策表。</span><span class="sxs-lookup"><span data-stu-id="a2415-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="a2415-118">请注意如何基础 OS (Windows vs。某些业务流程协调程序以及更成熟上 Linux 容器和 Windows 容器上其他 Linux) 也可以决定因素。</span><span class="sxs-lookup"><span data-stu-id="a2415-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="a2415-119">例如，Linux 容器是在 Kubernetes (在 Azure 中的 AKS) 中非常成熟但 Service Fabric 上不够成熟。</span><span class="sxs-lookup"><span data-stu-id="a2415-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="a2415-120">另一方面，Windows 容器是在 Service Fabric （在 2017 年 5 月发布） 中更成熟和在 AKS 中不够成熟。</span><span class="sxs-lookup"><span data-stu-id="a2415-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="a2415-121">但是，在 OS 成熟度这些差异将在将来淡多个平台具有可比较 OS 成熟度和决策将布局基于您的应用程序可能需要或基于每个平台的生态系统的特定功能的首选项将详细介绍原因。</span><span class="sxs-lookup"><span data-stu-id="a2415-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="a2415-122">[上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [下一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="a2415-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
