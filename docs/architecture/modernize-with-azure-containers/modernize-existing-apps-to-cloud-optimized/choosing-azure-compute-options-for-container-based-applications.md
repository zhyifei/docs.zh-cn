---
title: 为基于容器的应用程序选择 Azure 计算平台
description: 通过 Azure 云和 Windows 容器现代化现有 .NET 应用程序 | 为基于容器的应用程序选择 Azure 计算平台
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2019
ms.locfileid: "73737017"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="f3529-103">为基于容器的应用程序选择 Azure 计算平台</span><span class="sxs-lookup"><span data-stu-id="f3529-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="f3529-104">正如你在阅读前面章节时所注意到的，Azure 是一个提供多项选择的开放云。</span><span class="sxs-lookup"><span data-stu-id="f3529-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="f3529-105">你可以充分利用它来满足你的需求，但是它也提出了一些关于你应该为容器化应用程序采用哪些产品/技术的问题。</span><span class="sxs-lookup"><span data-stu-id="f3529-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="f3529-106">作为“默认”  建议，以下是本指南中建议的主要标准：</span><span class="sxs-lookup"><span data-stu-id="f3529-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="f3529-107">**单一整体式应用：** 选择 Azure 应用服务</span><span class="sxs-lookup"><span data-stu-id="f3529-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="f3529-108">**N 层应用：** 如果拥有单个或几个后端服务，请选择“业务流程协调程序”，如 Azure Kubernetes 服务 (AKS) 或应用服务</span><span class="sxs-lookup"><span data-stu-id="f3529-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS) or App Service if you have a single or a few back-end services</span></span>
- <span data-ttu-id="f3529-109">**微服务：** 为容器选择 AKS 或 Azure Web 应用</span><span class="sxs-lookup"><span data-stu-id="f3529-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="f3529-110">**无服务器函数和事件处理程序：** 选择“Azure Functions”</span><span class="sxs-lookup"><span data-stu-id="f3529-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="f3529-111">**大规模 Batch：** 选择“Azure Batch”</span><span class="sxs-lookup"><span data-stu-id="f3529-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="f3529-112">但是，这一建议并不完全可信，因为产品的选择取决于具体的应用程序需求和特性。</span><span class="sxs-lookup"><span data-stu-id="f3529-112">However, this recommendation should be taken with a pinch of salt, as the product's selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="f3529-113">并非所有的应用程序都是相同的，即使它们最初可能看起来是类似的。</span><span class="sxs-lookup"><span data-stu-id="f3529-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="f3529-114">在对应用程序的需求进行更深入的分析之后，所选择的产品可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="f3529-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="f3529-115">但最好一开始就获得初步指导，你可以基于特定的优先级从其中开始评估和测试。</span><span class="sxs-lookup"><span data-stu-id="f3529-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="f3529-116">在图 1 中，你可以看到不同种类应用及其理想的 Azure 托管方案的明细。</span><span class="sxs-lookup"><span data-stu-id="f3529-116">In Figure 1, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![哪些 Azure 托管方案最适合不同应用的表。](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> <span data-ttu-id="f3529-118">[上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [下一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="f3529-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
