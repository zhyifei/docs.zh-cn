---
title: 选择容器基于应用程序的 Azure 计算平台
description: 更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |选择容器基于应用程序的 Azure 计算平台
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: ebf022a52aaaf95ae335976f5e097921b0ac8006
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958007"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="a6275-103">选择容器基于应用程序的 Azure 计算平台</span><span class="sxs-lookup"><span data-stu-id="a6275-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="a6275-104">在阅读了前面的部分后，您已经注意到，Azure 将是提供多项选择打开云。</span><span class="sxs-lookup"><span data-stu-id="a6275-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="a6275-105">您可以使用最适合你的需求，但是，它还显示有关你容器化应用程序应使用何种产品/技术问题。</span><span class="sxs-lookup"><span data-stu-id="a6275-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="a6275-106">作为 *： 默认情况下*建议，以下是本指南中建议的主要条件：</span><span class="sxs-lookup"><span data-stu-id="a6275-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

  - <span data-ttu-id="a6275-107">**单个整体应用：** 选择 Azure App Service</span><span class="sxs-lookup"><span data-stu-id="a6275-107">**Single monolithic app:** Choose Azure App Service</span></span>
  - <span data-ttu-id="a6275-108">**N 层应用程序：** 选择 orchestrators 如 Azure Kubernetes 服务 (AKS)、 Service Fabric (SF) 或应用程序服务，如果你有一个或几个后端服务</span><span class="sxs-lookup"><span data-stu-id="a6275-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
  - <span data-ttu-id="a6275-109">**Linux 微服务：** 选择 AKS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="a6275-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
  - <span data-ttu-id="a6275-110">**Windows 微服务：** 选择 Service Fabric</span><span class="sxs-lookup"><span data-stu-id="a6275-110">**Windows microservices:** Choose Service Fabric</span></span>
  - <span data-ttu-id="a6275-111">**无服务器函数和事件处理程序：** 选择 Azure 函数</span><span class="sxs-lookup"><span data-stu-id="a6275-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
  - <span data-ttu-id="a6275-112">**大规模批处理：** 选择 Azure 批处理</span><span class="sxs-lookup"><span data-stu-id="a6275-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="a6275-113">但是，此建议应采取的 salt，捏合与该产品的选择将依赖于特定应用程序的需求和特征。</span><span class="sxs-lookup"><span data-stu-id="a6275-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="a6275-114">即使最初它们可能看起来类似的类型，并非所有应用程序都是相同的。</span><span class="sxs-lookup"><span data-stu-id="a6275-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="a6275-115">在应用程序的需求的更深入地分析之后, 选择产品可能不同。</span><span class="sxs-lookup"><span data-stu-id="a6275-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="a6275-116">但是，作为起点，最好能够从你可以评估的初步指导，而且测试根据某些优先级。</span><span class="sxs-lookup"><span data-stu-id="a6275-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="a6275-117">在下一步的图中，你可以分析更具有全局性时详细的决策表。</span><span class="sxs-lookup"><span data-stu-id="a6275-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="a6275-118">请注意如何基础操作系统 (Windows vs。Linux) 以及某些 orchestrators 更加成熟上 Linux 容器和其他 Windows 容器，也可以是决定因素。</span><span class="sxs-lookup"><span data-stu-id="a6275-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="a6275-119">例如，Linux 容器是在 Kubernetes (在 Azure 中的 AKS) 但不太成熟于 Service Fabric 非常成熟的。</span><span class="sxs-lookup"><span data-stu-id="a6275-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="a6275-120">另一方面，Windows 容器是在 Service Fabric 中 （在 2017 年 5 月发布） 更加成熟完善一些和较低成熟 AKS 中。</span><span class="sxs-lookup"><span data-stu-id="a6275-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="a6275-121">但是，在 OS 成熟度这些差异将淡入淡出将来和多个平台将具有可比较 OS 成熟度和决策的布局有关基于你的应用程序可能需要或基于每个平台的生态系统的特定功能的首选项的详细信息原因。</span><span class="sxs-lookup"><span data-stu-id="a6275-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="a6275-122">[上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[下一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="a6275-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
