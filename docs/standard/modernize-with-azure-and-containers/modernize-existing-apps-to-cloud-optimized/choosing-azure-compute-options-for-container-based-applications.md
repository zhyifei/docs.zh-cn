---
title: 为基于容器的应用程序选择 Azure 计算平台
description: 更新现有.NET 应用程序与 Azure 云和 Windows 容器 |选择基于容器的应用程序的 Azure 计算平台
ms.date: 05/04/2018
ms.openlocfilehash: 64ae542e006bf7a5d7a0be08fe1cff9770552a77
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833853"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="46f46-103">为基于容器的应用程序选择 Azure 计算平台</span><span class="sxs-lookup"><span data-stu-id="46f46-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="46f46-104">阅读前面的部分后，您已经注意到，Azure 是开放的云，提供多个选项。</span><span class="sxs-lookup"><span data-stu-id="46f46-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="46f46-105">可以根据需要使用最合适，但是，它还会呈现为容器化应用程序应使用何种产品/技术有关的问题。</span><span class="sxs-lookup"><span data-stu-id="46f46-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="46f46-106">作为*默认情况下*建议，下面是本指南中建议主要的准则：</span><span class="sxs-lookup"><span data-stu-id="46f46-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="46f46-107">**单个整体式应用程序：** 选择 Azure 应用服务</span><span class="sxs-lookup"><span data-stu-id="46f46-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="46f46-108">**N 层应用程序：** 如果你有一个或几个后端服务，请选择业务流程协调程序，如 Azure Kubernetes 服务 (AKS) 或应用服务</span><span class="sxs-lookup"><span data-stu-id="46f46-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="46f46-109">**微服务：** 为容器选择 AKS 或 Azure Web 应用</span><span class="sxs-lookup"><span data-stu-id="46f46-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="46f46-110">**无服务器函数 （&) 事件处理程序：** 选择 Azure 函数</span><span class="sxs-lookup"><span data-stu-id="46f46-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="46f46-111">**大规模批处理：** 选择 Azure Batch</span><span class="sxs-lookup"><span data-stu-id="46f46-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="46f46-112">但是，此建议应使用盐，片段执行如产品的选择将取决于特定应用程序的需求和特征。</span><span class="sxs-lookup"><span data-stu-id="46f46-112">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="46f46-113">即使最初它们可能看起来类似的类型，并非所有应用程序都是相同的。</span><span class="sxs-lookup"><span data-stu-id="46f46-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="46f46-114">在应用程序的需求的更深入地分析之后, 选择产品可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="46f46-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="46f46-115">但是，作为起点，最好能够从您可以开始评估的初步指导和测试基于针对特定的优先级。</span><span class="sxs-lookup"><span data-stu-id="46f46-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="46f46-116">在下图中，可以看到不同类型的应用程序和托管方案，其非常适合 Azure 的细分。</span><span class="sxs-lookup"><span data-stu-id="46f46-116">In the next figure, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="46f46-117">[上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [下一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="46f46-117">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
