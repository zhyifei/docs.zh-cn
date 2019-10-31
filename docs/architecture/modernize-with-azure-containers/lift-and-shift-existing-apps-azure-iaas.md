---
title: 将现有 .NET 应用程序直接迁移到 Azure IaaS （云基础结构就绪）
description: 利用 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化。
ms.date: 04/28/2018
ms.openlocfilehash: c7638a034dbb27baea1b097bdb66175bfb5a71f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089635"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a><span data-ttu-id="1109c-103">将现有 .NET 应用程序直接迁移到 Azure IaaS （云基础结构就绪）</span><span class="sxs-lookup"><span data-stu-id="1109c-103">Lift and shift existing .NET apps to Azure IaaS (Cloud Infrastructure-Ready)</span></span>

> <span data-ttu-id="1109c-104">远景：作为第一步，若要减少本地投资和硬件和网络维护的总成本，只需将现有应用程序 rehost 到云中。</span><span class="sxs-lookup"><span data-stu-id="1109c-104">Vision: As a first step, to reduce your on-premises investment and total cost of hardware and networking maintenance, simply rehost your existing applications in the cloud.</span></span>

<span data-ttu-id="1109c-105">在*介绍如何*将现有应用程序迁移到 azure 基础结构即服务（IaaS）平台之前，请务必分析要直接迁移到 azure 中的 IaaS*的原因。*</span><span class="sxs-lookup"><span data-stu-id="1109c-105">Before getting into *how* to migrate your existing applications to the Azure infrastructure as a service (IaaS) platform, it's important to analyze the reasons *why* you'd want to migrate directly to IaaS in Azure.</span></span> <span data-ttu-id="1109c-106">此现代化成熟度级别的方案实质上是开始在云中使用 Vm，而不是继续使用当前的本地基础结构。</span><span class="sxs-lookup"><span data-stu-id="1109c-106">The scenario at this modernization maturity level essentially is to start using VMs in the cloud, instead of continuing to use your current, on-premises infrastructure.</span></span>

<span data-ttu-id="1109c-107">要*分析的另一点是，* 可能需要迁移到纯 IaaS 云，而不是只是在 Azure 中添加更高级的托管服务。</span><span class="sxs-lookup"><span data-stu-id="1109c-107">Another point to analyze is *why* you might want to migrate to pure IaaS cloud instead of just adding more advanced managed services in Azure.</span></span> <span data-ttu-id="1109c-108">首先确定哪些情况下可能需要 IaaS。</span><span class="sxs-lookup"><span data-stu-id="1109c-108">Determine what cases might require IaaS in the first place.</span></span>

<span data-ttu-id="1109c-109">图2-1 定位现代化成熟度中的云基础结构就绪应用程序：</span><span class="sxs-lookup"><span data-stu-id="1109c-109">Figure 2-1 positions Cloud Infrastructure-Ready applications in the modernization maturity levels:</span></span>

![定位云基础结构就绪应用程序](./media/image2-1.png)

<span data-ttu-id="1109c-111">**图 2-1.**</span><span class="sxs-lookup"><span data-stu-id="1109c-111">**Figure 2-1.**</span></span> <span data-ttu-id="1109c-112">定位云基础结构就绪应用程序</span><span class="sxs-lookup"><span data-stu-id="1109c-112">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a><span data-ttu-id="1109c-113">为什么要将现有 .NET web 应用程序迁移到 Azure IaaS</span><span class="sxs-lookup"><span data-stu-id="1109c-113">Why migrate existing .NET web applications to Azure IaaS</span></span>

<span data-ttu-id="1109c-114">即使在初始 IaaS 级别迁移到云的主要原因是要实现成本降低。</span><span class="sxs-lookup"><span data-stu-id="1109c-114">The main reason to migrate to the cloud, even at an initial IaaS level, is to achieve cost reductions.</span></span> <span data-ttu-id="1109c-115">通过使用更多的托管基础结构服务，你的组织可以降低其对硬件维护、服务器或 VM 预配和部署以及基础结构管理的投资。</span><span class="sxs-lookup"><span data-stu-id="1109c-115">By using more managed infrastructure services, your organization can lower its investment in hardware maintenance, server or VM provisioning and deployment, and infrastructure management.</span></span>

<span data-ttu-id="1109c-116">决定将应用移到云后，选择 IaaS 而不是更高级选项（如 PaaS）的主要原因就是，IaaS 环境会更熟悉。</span><span class="sxs-lookup"><span data-stu-id="1109c-116">After you make the decision to move your apps to the cloud, the main reason why you might choose IaaS instead of more advanced options like PaaS is simply that the IaaS environment will be more familiar.</span></span> <span data-ttu-id="1109c-117">迁移到类似于你当前的本地环境的环境提供较低的学习曲线，使其成为云的最快途径。</span><span class="sxs-lookup"><span data-stu-id="1109c-117">Moving to an environment that's similar to your current, on-premises environment offers a lower learning curve, which makes it the quickest path to the cloud.</span></span>

<span data-ttu-id="1109c-118">但是，将最快的途径带入云并不意味着你可以从在云中运行应用程序获得最大的好处。</span><span class="sxs-lookup"><span data-stu-id="1109c-118">However, taking the quickest path to the cloud doesn't mean that you will gain the most benefit from having your applications running in the cloud.</span></span> <span data-ttu-id="1109c-119">任何组织都将从已推出的云优化和云本机成熟度级别的云迁移中获得最大的好处。</span><span class="sxs-lookup"><span data-stu-id="1109c-119">Any organization will gain the most significant benefits from a cloud migration at the already introduced Cloud-Optimized and Cloud-Native maturity levels.</span></span>

<span data-ttu-id="1109c-120">它还明显表明，如果应用程序已在云中运行，甚至在 IaaS 上运行，就更容易实现现代化和重塑。</span><span class="sxs-lookup"><span data-stu-id="1109c-120">It also has become evident that applications are easier to modernize and rearchitect in the future when they are already running in the cloud, even on IaaS.</span></span> <span data-ttu-id="1109c-121">已实现应用程序数据迁移。</span><span class="sxs-lookup"><span data-stu-id="1109c-121">Application data migration has already been achieved.</span></span> <span data-ttu-id="1109c-122">此外，你的组织将获得在云中工作所需的技能，并使班次成为 "云文化"。</span><span class="sxs-lookup"><span data-stu-id="1109c-122">Also, your organization will have gained skills required for working in the cloud and made the shift to operating in a "cloud culture."</span></span>

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a><span data-ttu-id="1109c-123">何时迁移到 IaaS 而不是迁移到 PaaS</span><span class="sxs-lookup"><span data-stu-id="1109c-123">When to migrate to IaaS instead of to PaaS</span></span>

<span data-ttu-id="1109c-124">接下来的部分讨论基于 PaaS 平台和服务的云优化应用程序。</span><span class="sxs-lookup"><span data-stu-id="1109c-124">The next sections discuss Cloud-Optimized applications that are mostly based on PaaS platforms and services.</span></span> <span data-ttu-id="1109c-125">这些应用为你带来了迁移到云的最大好处。</span><span class="sxs-lookup"><span data-stu-id="1109c-125">These apps give you the most benefits from migrating to the cloud.</span></span>

<span data-ttu-id="1109c-126">如果你的目标只是将现有应用程序迁移到云，请先确定现有应用程序，这些应用程序不需要进行大量修改即可在 Azure App Service 中运行。</span><span class="sxs-lookup"><span data-stu-id="1109c-126">If your goal is simply to move existing applications to the cloud, first, identify existing applications that would not require substantial modification to run in Azure App Service.</span></span> <span data-ttu-id="1109c-127">这些应用应是云优化的第一个候选项。</span><span class="sxs-lookup"><span data-stu-id="1109c-127">These apps should be the first candidates for Cloud-Optimized.</span></span>

<span data-ttu-id="1109c-128">然后，对于仍无法移至 Windows 容器和 PaaS 的应用（如 Azure Kubernetes Service），请将其迁移到简单的普通 Vm （IaaS）。</span><span class="sxs-lookup"><span data-stu-id="1109c-128">Then, for the apps that still cannot move to Windows Containers and PaaS such as App Service or orchestrators like Azure Kubernetes Service, migrate those to simple plain VMs (IaaS).</span></span>

<span data-ttu-id="1109c-129">但请记住，正确配置、保护和维护 Vm 需要比在 Azure 中使用 PaaS 服务更多的时间和 IT 专业知识。</span><span class="sxs-lookup"><span data-stu-id="1109c-129">But, keep in mind that correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to using PaaS services in Azure.</span></span> <span data-ttu-id="1109c-130">如果考虑使用 Azure 虚拟机，请确保将修补、更新和管理 VM 环境所需的日常维护工作纳入考虑。</span><span class="sxs-lookup"><span data-stu-id="1109c-130">If you are considering Azure Virtual Machines, make sure that you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="1109c-131">Azure 虚拟机为 IaaS。</span><span class="sxs-lookup"><span data-stu-id="1109c-131">Azure Virtual Machines is IaaS.</span></span>

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a><span data-ttu-id="1109c-132">使用 Azure Migrate 分析现有应用程序并将其迁移到 Azure</span><span class="sxs-lookup"><span data-stu-id="1109c-132">Use Azure Migrate to analyze and migrate your existing applications to Azure</span></span>

<span data-ttu-id="1109c-133">迁移到云不一定很困难。</span><span class="sxs-lookup"><span data-stu-id="1109c-133">Migrating to the cloud doesn't have to be difficult.</span></span> <span data-ttu-id="1109c-134">但许多组织都在努力开始-深入了解环境以及应用程序、工作负荷和数据之间的紧密相关性。</span><span class="sxs-lookup"><span data-stu-id="1109c-134">But many organizations struggle to get started - to get deep visibility into the environment and the tight interdependencies between applications, workloads, and data.</span></span> <span data-ttu-id="1109c-135">如果没有该可见性，则很难规划转发的路径。</span><span class="sxs-lookup"><span data-stu-id="1109c-135">Without that visibility, it can be difficult to plan the path forward.</span></span> <span data-ttu-id="1109c-136">如果没有关于成功迁移所需内容的详细信息，你的组织中将无法进行正确的对话。</span><span class="sxs-lookup"><span data-stu-id="1109c-136">Without detailed information on what's required for a successful migration, you can't have the right conversations within your organization.</span></span> <span data-ttu-id="1109c-137">您并不知道可能的成本优势，或者工作负荷是只需要直接迁移，还是需要大量返工才能成功迁移。</span><span class="sxs-lookup"><span data-stu-id="1109c-137">You don't know enough about the potential cost benefits, or whether workloads could just lift-and-shift or would require significant rework to migrate successfully.</span></span> <span data-ttu-id="1109c-138">不是很多人都想。</span><span class="sxs-lookup"><span data-stu-id="1109c-138">No wonder many organizations hesitate.</span></span>

<span data-ttu-id="1109c-139">[Azure Migrate](https://aka.ms/azuremigrate)是一项新服务，提供帮助你迁移到 Azure 所需的指导、见解和机制。</span><span class="sxs-lookup"><span data-stu-id="1109c-139">[Azure Migrate](https://aka.ms/azuremigrate) is a new service that provides the guidance, insights, and mechanisms needed to assist you in migrating to Azure.</span></span> <span data-ttu-id="1109c-140">Azure Migrate 提供：</span><span class="sxs-lookup"><span data-stu-id="1109c-140">Azure Migrate provides:</span></span>

- <span data-ttu-id="1109c-141">发现和评估本地虚拟机</span><span class="sxs-lookup"><span data-stu-id="1109c-141">Discovery and assessment for on-premises virtual machines</span></span>

- <span data-ttu-id="1109c-142">用于多层应用程序的高可信度发现的内置依赖项映射</span><span class="sxs-lookup"><span data-stu-id="1109c-142">Inbuilt dependency mapping for high-confidence discovery of multi-tier applications</span></span>

- <span data-ttu-id="1109c-143">向 Azure 虚拟机智能地调整大小</span><span class="sxs-lookup"><span data-stu-id="1109c-143">Intelligent right sizing to Azure virtual machines</span></span>

- <span data-ttu-id="1109c-144">兼容性报告与补救潜在问题的指南</span><span class="sxs-lookup"><span data-stu-id="1109c-144">Compatibility reporting with guidelines for remediating potential issues</span></span>

- <span data-ttu-id="1109c-145">与 Azure 数据库管理服务集成以实现数据库发现和迁移</span><span class="sxs-lookup"><span data-stu-id="1109c-145">Integration with Azure Database Management Service for database discovery and migration</span></span>

<span data-ttu-id="1109c-146">Azure Migrate 使你确信工作负荷可以在最小程度上进行迁移，并在 Azure 中按预期运行。</span><span class="sxs-lookup"><span data-stu-id="1109c-146">Azure Migrate gives you confidence that your workloads can migrate with minimal impact to the business and run as expected in Azure.</span></span> <span data-ttu-id="1109c-147">利用正确的工具和指南，你可以实现最大投资回报，同时确保满足关键的性能和可靠性需求。</span><span class="sxs-lookup"><span data-stu-id="1109c-147">With the right tools and guidance, you can achieve maximum return on investment while assuring that critical performance and reliability needs are met.</span></span>

<span data-ttu-id="1109c-148">图2-2 显示了 Azure Migrate 执行的所有服务器和应用程序连接的内置依赖项映射。</span><span class="sxs-lookup"><span data-stu-id="1109c-148">Figure 2-2 shows you the built-in dependency mapping for all server and application connections performed by Azure Migrate.</span></span>

![定位云基础结构就绪应用程序](./media/image2-2.png)

<span data-ttu-id="1109c-150">**图 2-2。**</span><span class="sxs-lookup"><span data-stu-id="1109c-150">**Figure 2-2.**</span></span> <span data-ttu-id="1109c-151">定位云基础结构就绪应用程序</span><span class="sxs-lookup"><span data-stu-id="1109c-151">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a><span data-ttu-id="1109c-152">使用 Azure Site Recovery 将现有 Vm 迁移到 Azure Vm</span><span class="sxs-lookup"><span data-stu-id="1109c-152">Use Azure Site Recovery to migrate your existing VMs to Azure VMs</span></span>

<span data-ttu-id="1109c-153">作为端到端[Azure Migrate](https://aka.ms/azuremigrate)的一部分， [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)是一个工具，可用于轻松地将 Web 应用迁移到 Azure 中的 vm。</span><span class="sxs-lookup"><span data-stu-id="1109c-153">As part of the end-to-end [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) is a tool that you can use to easily migrate your web apps to VMs in Azure.</span></span> <span data-ttu-id="1109c-154">你可以使用 Site Recovery 将本地 Vm 和物理服务器复制到 Azure，或将其复制到辅助本地位置。</span><span class="sxs-lookup"><span data-stu-id="1109c-154">You can use Site Recovery to replicate on-premises VMs and physical servers to Azure, or to replicate them to a secondary on-premises location.</span></span> <span data-ttu-id="1109c-155">甚至可以复制在受支持的 Azure VM、本地*Hyper-v* Vm、 *VMware* Vm 或 Windows 或 Linux 物理服务器上运行的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="1109c-155">You can even replicate a workload that's running on a supported Azure VM, on an on-premises *Hyper-V* VM, on a *VMware* VM, or on a Windows or Linux physical server.</span></span> <span data-ttu-id="1109c-156">复制到 Azure 消除了维护辅助数据中心的成本和复杂性。</span><span class="sxs-lookup"><span data-stu-id="1109c-156">Replication to Azure eliminates the cost and complexity of maintaining a secondary datacenter.</span></span>

<span data-ttu-id="1109c-157">对于部分本地和 Azure 上部分的混合环境，Site Recovery 也是专门提供的。</span><span class="sxs-lookup"><span data-stu-id="1109c-157">Site Recovery is also made specifically for hybrid environments that are partly on-premises and partly on Azure.</span></span> <span data-ttu-id="1109c-158">Site Recovery 通过将运行于 Vm 和本地物理服务器上的应用程序保持在站点出现故障的情况下，帮助确保业务连续性。</span><span class="sxs-lookup"><span data-stu-id="1109c-158">Site Recovery helps ensure business continuity by keeping your apps that are running on VMs and on-premises physical servers available if a site goes down.</span></span> <span data-ttu-id="1109c-159">它复制在 Vm 和物理服务器上运行的工作负荷，以便在主站点不可用时，它们仍可用于辅助位置。</span><span class="sxs-lookup"><span data-stu-id="1109c-159">It replicates workloads that are running on VMs and physical servers so that they remain available in a secondary location if the primary site isn't available.</span></span> <span data-ttu-id="1109c-160">当主站点重新启动并运行时，它会将工作负荷恢复到主站点。</span><span class="sxs-lookup"><span data-stu-id="1109c-160">It recovers workloads to the primary site when it's up and running again.</span></span>

<span data-ttu-id="1109c-161">图2-3 显示了如何使用 Azure Site Recovery 执行多个 VM 迁移。</span><span class="sxs-lookup"><span data-stu-id="1109c-161">Figure 2-3 shows the execution of multiple VM migrations by using Azure Site Recovery.</span></span>

![定位云基础结构就绪应用程序](./media/image2-3.png)

<span data-ttu-id="1109c-163">**图2-3。**</span><span class="sxs-lookup"><span data-stu-id="1109c-163">**Figure 2-3.**</span></span> <span data-ttu-id="1109c-164">定位云基础结构就绪应用程序</span><span class="sxs-lookup"><span data-stu-id="1109c-164">Positioning Cloud Infrastructure-Ready applications</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1109c-165">其他资源</span><span class="sxs-lookup"><span data-stu-id="1109c-165">Additional resources</span></span>

- <span data-ttu-id="1109c-166">**Azure Migrate 数据表**</span><span class="sxs-lookup"><span data-stu-id="1109c-166">**Azure Migrate Datasheet**</span></span>

    <https://aka.ms/azuremigration\_datasheet>

- <span data-ttu-id="1109c-167">**Azure Migrate**</span><span class="sxs-lookup"><span data-stu-id="1109c-167">**Azure Migrate**</span></span>

    <https://aka.ms/azuremigrate>

- <span data-ttu-id="1109c-168">**Azure 迁移中心**</span><span class="sxs-lookup"><span data-stu-id="1109c-168">**Azure migration center**</span></span>

    <https://azure.microsoft.com/migration/>

- <span data-ttu-id="1109c-169">**通过 Site Recovery 迁移到 Azure**</span><span class="sxs-lookup"><span data-stu-id="1109c-169">**Migrate to Azure with Site Recovery**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- <span data-ttu-id="1109c-170">**Azure Site Recovery 服务概述**</span><span class="sxs-lookup"><span data-stu-id="1109c-170">**Azure Site Recovery service overview**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- <span data-ttu-id="1109c-171">**将 AWS 中的 Vm 迁移到 Azure Vm**</span><span class="sxs-lookup"><span data-stu-id="1109c-171">**Migrating VMs in AWS to Azure VMs**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
><span data-ttu-id="1109c-172">[上一页](index.md)
>[下一页](migrate-your-relational-databases-to-azure.md)</span><span class="sxs-lookup"><span data-stu-id="1109c-172">[Previous](index.md)
[Next](migrate-your-relational-databases-to-azure.md)</span></span> <!-- Next Chapter -->
