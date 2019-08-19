---
title: 为基于容器的应用程序选择 Azure 计算平台
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |为基于容器的应用程序选择 Azure 计算平台
ms.date: 05/04/2018
ms.openlocfilehash: 64ae542e006bf7a5d7a0be08fe1cff9770552a77
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578340"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="bf3b4-103">为基于容器的应用程序选择 Azure 计算平台</span><span class="sxs-lookup"><span data-stu-id="bf3b4-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="bf3b4-104">正如你在阅读前面几节中所注意到的, Azure 是一个开放的云, 它提供多个选择。</span><span class="sxs-lookup"><span data-stu-id="bf3b4-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="bf3b4-105">您可以最大程度地满足您的需求, 但它还会对您应该为容器化应用程序使用的产品/技术提出问题。</span><span class="sxs-lookup"><span data-stu-id="bf3b4-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="bf3b4-106">作为*默认*建议, 以下是本指南中建议的主要标准:</span><span class="sxs-lookup"><span data-stu-id="bf3b4-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="bf3b4-107">**单一单一应用程序:** 选择 Azure App Service</span><span class="sxs-lookup"><span data-stu-id="bf3b4-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="bf3b4-108">**N 层应用程序:** 如果有一个或多个后端服务, 请选择 "协调器", 例如 "Azure Kubernetes Service (AKS)" 或 "应用服务"</span><span class="sxs-lookup"><span data-stu-id="bf3b4-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="bf3b4-109">**微服务**选择 AKS 或适用于容器的 Azure Web 应用</span><span class="sxs-lookup"><span data-stu-id="bf3b4-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="bf3b4-110">**& 事件处理程序的无服务器函数:** 选择 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="bf3b4-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="bf3b4-111">**大规模批:** 选择 Azure Batch</span><span class="sxs-lookup"><span data-stu-id="bf3b4-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="bf3b4-112">但是, 这一建议应该用到了一把盐, 因为产品的选择取决于具体的应用程序的需求和特性。</span><span class="sxs-lookup"><span data-stu-id="bf3b4-112">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="bf3b4-113">并非所有应用程序都是相同的, 即使最初它们可能看起来类似。</span><span class="sxs-lookup"><span data-stu-id="bf3b4-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="bf3b4-114">在对应用程序的需求进行更深入的分析之后, 所选产品可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="bf3b4-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="bf3b4-115">但作为起点, 最好具有初始指导, 可以根据特定优先级开始评估和测试。</span><span class="sxs-lookup"><span data-stu-id="bf3b4-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="bf3b4-116">在下图中, 你可以看到不同种类的应用的细目及其理想的 Azure 托管方案。</span><span class="sxs-lookup"><span data-stu-id="bf3b4-116">In the next figure, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="bf3b4-117">[上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [下一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="bf3b4-117">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
