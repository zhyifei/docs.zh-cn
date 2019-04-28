---
title: 提升并转移到 Azure IaaS （云基础结构的） 现有.NET 应用程序
description: 更新现有.NET 应用程序使用 Azure 云和 Windows 容器。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 0f9ff19c8e346560960a09d3b7c52976c478f2f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651177"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a><span data-ttu-id="5383e-103">提升并转移到 Azure IaaS （云基础结构的） 现有.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="5383e-103">Lift and shift existing .NET apps to Azure IaaS (Cloud Infrastructure-Ready)</span></span>

> <span data-ttu-id="5383e-104">设想：第一步中，若要减少你的本地投资回报和硬件和网络维护的总成本，只需重新托管云中你现有的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5383e-104">Vision: As a first step, to reduce your on-premises investment and total cost of hardware and networking maintenance, simply rehost your existing applications in the cloud.</span></span>

<span data-ttu-id="5383e-105">在着手之前*如何*若要迁移到 Azure 基础结构即服务 (IaaS) 平台将现有应用程序，务必要分析的原因*为什么*你想要直接到 IaaS 迁移在 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="5383e-105">Before getting into *how* to migrate your existing applications to the Azure infrastructure as a service (IaaS) platform, it's important to analyze the reasons *why* you'd want to migrate directly to IaaS in Azure.</span></span> <span data-ttu-id="5383e-106">在此更新成熟度级别方案实质上是开始在云中，而不是继续使用当前的本地基础结构中使用的 Vm。</span><span class="sxs-lookup"><span data-stu-id="5383e-106">The scenario at this modernization maturity level essentially is to start using VMs in the cloud, instead of continuing to use your current, on-premises infrastructure.</span></span>

<span data-ttu-id="5383e-107">若要分析的另一点是*为什么*可能想要迁移到纯 IaaS 云而不是仅仅增加了更高级的 Azure 中的托管的服务。</span><span class="sxs-lookup"><span data-stu-id="5383e-107">Another point to analyze is *why* you might want to migrate to pure IaaS cloud instead of just adding more advanced managed services in Azure.</span></span> <span data-ttu-id="5383e-108">确定用例可能首先需要 IaaS。</span><span class="sxs-lookup"><span data-stu-id="5383e-108">Determine what cases might require IaaS in the first place.</span></span>

<span data-ttu-id="5383e-109">图 2-1 现代化成熟度级别中定位云基础结构准备就绪的应用程序：</span><span class="sxs-lookup"><span data-stu-id="5383e-109">Figure 2-1 positions Cloud Infrastructure-Ready applications in the modernization maturity levels:</span></span>

![定位云基础结构准备就绪的应用程序](./media/image2-1.png)

> <span data-ttu-id="5383e-111">**图 2-1.**</span><span class="sxs-lookup"><span data-stu-id="5383e-111">**Figure 2-1.**</span></span> <span data-ttu-id="5383e-112">定位云基础结构准备就绪的应用程序</span><span class="sxs-lookup"><span data-stu-id="5383e-112">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a><span data-ttu-id="5383e-113">为什么要迁移到 Azure IaaS 的现有.NET web 应用程序</span><span class="sxs-lookup"><span data-stu-id="5383e-113">Why migrate existing .NET web applications to Azure IaaS</span></span>

<span data-ttu-id="5383e-114">若要将迁移到云中、 甚至是初始 IaaS 级别的主要原因是实现降低成本。</span><span class="sxs-lookup"><span data-stu-id="5383e-114">The main reason to migrate to the cloud, even at an initial IaaS level, is to achieve cost reductions.</span></span> <span data-ttu-id="5383e-115">通过使用更多的托管基础结构服务，你的组织可以降低硬件维护、 服务器或 VM 预配和部署和基础结构管理其投资。</span><span class="sxs-lookup"><span data-stu-id="5383e-115">By using more managed infrastructure services, your organization can lower its investment in hardware maintenance, server or VM provisioning and deployment, and infrastructure management.</span></span>

<span data-ttu-id="5383e-116">请将您的应用程序移动到云的决策后，让您决定选择 IaaS 而不是更多高级选项，如 PaaS 只需进行的 IaaS 环境的主要原因将更熟悉。</span><span class="sxs-lookup"><span data-stu-id="5383e-116">After you make the decision to move your apps to the cloud, the main reason why you might choose IaaS instead of more advanced options like PaaS is simply that the IaaS environment will be more familiar.</span></span> <span data-ttu-id="5383e-117">将移动到类似于你当前的环境，在本地环境提供了较低的学习曲线，这使得它到云的最快的途径。</span><span class="sxs-lookup"><span data-stu-id="5383e-117">Moving to an environment that's similar to your current, on-premises environment offers a lower learning curve, which makes it the quickest path to the cloud.</span></span>

<span data-ttu-id="5383e-118">但是，到云采用最快的路径并不意味着你将获得在云中运行应用程序从最大效益。</span><span class="sxs-lookup"><span data-stu-id="5383e-118">However, taking the quickest path to the cloud doesn't mean that you will gain the most benefit from having your applications running in the cloud.</span></span> <span data-ttu-id="5383e-119">任何组织都将获得云迁移已引入的云优化和云本机成熟度级别从最大的好处。</span><span class="sxs-lookup"><span data-stu-id="5383e-119">Any organization will gain the most significant benefits from a cloud migration at the already introduced Cloud-Optimized and Cloud-Native maturity levels.</span></span>

<span data-ttu-id="5383e-120">也变得很明显，应用程序是更轻松地实现现代化，并在将来重构时它们已在云中、 甚至在 IaaS 中运行。</span><span class="sxs-lookup"><span data-stu-id="5383e-120">It also has become evident that applications are easier to modernize and rearchitect in the future when they are already running in the cloud, even on IaaS.</span></span> <span data-ttu-id="5383e-121">已实现应用程序数据迁移。</span><span class="sxs-lookup"><span data-stu-id="5383e-121">Application data migration has already been achieved.</span></span> <span data-ttu-id="5383e-122">已还，获得在云中的工作所需的技能并对 shift"云区域性"。 在你的组织</span><span class="sxs-lookup"><span data-stu-id="5383e-122">Also, your organization will have gained skills required for working in the cloud and made the shift to operating in a "cloud culture."</span></span>

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a><span data-ttu-id="5383e-123">何时迁移至而不是 IaaS 到 PaaS</span><span class="sxs-lookup"><span data-stu-id="5383e-123">When to migrate to IaaS instead of to PaaS</span></span>

<span data-ttu-id="5383e-124">接下来的部分讨论云优化的应用程序的主要基于 PaaS 平台和服务。</span><span class="sxs-lookup"><span data-stu-id="5383e-124">The next sections discuss Cloud-Optimized applications that are mostly based on PaaS platforms and services.</span></span> <span data-ttu-id="5383e-125">这些应用为您提供的大多数好处迁移到云。</span><span class="sxs-lookup"><span data-stu-id="5383e-125">These apps give you the most benefits from migrating to the cloud.</span></span> 

<span data-ttu-id="5383e-126">如果你的目标是只需移动到云的现有应用程序，首先要确定不需要修改大量，若要在 Azure 应用服务中运行的现有应用程序。</span><span class="sxs-lookup"><span data-stu-id="5383e-126">If your goal is simply to move existing applications to the cloud, first, identify existing applications that would not require substantial modification to run in Azure App Service.</span></span> <span data-ttu-id="5383e-127">这些应用程序应该是第一个适合云计算得到优化。</span><span class="sxs-lookup"><span data-stu-id="5383e-127">These apps should be the first candidates for Cloud-Optimized.</span></span> 

<span data-ttu-id="5383e-128">然后，应用，仍不能移动到 Windows 容器和 PaaS 如应用服务或 Azure Service Fabric 等业务流程协调程序迁移到简单的普通 Vm (IaaS)。</span><span class="sxs-lookup"><span data-stu-id="5383e-128">Then, for the apps that still cannot move to Windows Containers and PaaS such as App Service or orchestrators like Azure Service Fabric, migrate those to simple plain VMs (IaaS).</span></span> 

<span data-ttu-id="5383e-129">但请记住，正确配置、 保护和维护 Vm 需要更多时间和 IT 专业知识相比于在 Azure 中使用 PaaS 服务。</span><span class="sxs-lookup"><span data-stu-id="5383e-129">But, keep in mind that correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to using PaaS services in Azure.</span></span> <span data-ttu-id="5383e-130">如果你正在考虑 Azure 虚拟机，请确保所需修补、 更新和管理虚拟机环境的日常维护工作将其考虑到帐户。</span><span class="sxs-lookup"><span data-stu-id="5383e-130">If you are considering Azure Virtual Machines, make sure that you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="5383e-131">Azure 虚拟机是 IaaS。</span><span class="sxs-lookup"><span data-stu-id="5383e-131">Azure Virtual Machines is IaaS.</span></span>

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a><span data-ttu-id="5383e-132">使用 Azure Migrate 来分析并迁移现有应用程序到 Azure</span><span class="sxs-lookup"><span data-stu-id="5383e-132">Use Azure Migrate to analyze and migrate your existing applications to Azure</span></span>

<span data-ttu-id="5383e-133">迁移到云并不一定要困难。</span><span class="sxs-lookup"><span data-stu-id="5383e-133">Migrating to the cloud doesn't have to be difficult.</span></span> <span data-ttu-id="5383e-134">但是，许多组织不断努力，若要开始，以深入了解到的环境和应用程序、 工作负荷和数据之间的紧密相互依赖项。</span><span class="sxs-lookup"><span data-stu-id="5383e-134">But many organizations struggle to get started - to get deep visibility into the environment and the tight interdependencies between applications, workloads, and data.</span></span> <span data-ttu-id="5383e-135">了解不清，很难进行规划的未来发展途径。</span><span class="sxs-lookup"><span data-stu-id="5383e-135">Without that visibility, it can be difficult to plan the path forward.</span></span> <span data-ttu-id="5383e-136">没有什么已成功迁移所需的详细信息，不能在组织中具有适当的对话。</span><span class="sxs-lookup"><span data-stu-id="5383e-136">Without detailed information on what's required for a successful migration, you can't have the right conversations within your organization.</span></span> <span data-ttu-id="5383e-137">您不知道有足够的潜在成本效益，还是工作负荷可能只是提升和转移或需要大量的返工，若要成功迁移。</span><span class="sxs-lookup"><span data-stu-id="5383e-137">You don't know enough about the potential cost benefits, or whether workloads could just lift-and-shift or would require significant rework to migrate successfully.</span></span> <span data-ttu-id="5383e-138">许多组织欢迎不奇怪。</span><span class="sxs-lookup"><span data-stu-id="5383e-138">No wonder many organizations hesitate.</span></span>

<span data-ttu-id="5383e-139">[Azure Migrate](https://aka.ms/azuremigrate)是一种新的服务，提供指南、 见解和机制，以帮助你迁移到 Azure。</span><span class="sxs-lookup"><span data-stu-id="5383e-139">[Azure Migrate](https://aka.ms/azuremigrate) is a new service that provides the guidance, insights, and mechanisms needed to assist you in migrating to Azure.</span></span> <span data-ttu-id="5383e-140">Azure Migrate 提供：</span><span class="sxs-lookup"><span data-stu-id="5383e-140">Azure Migrate provides:</span></span>

- <span data-ttu-id="5383e-141">发现和评估本地虚拟机</span><span class="sxs-lookup"><span data-stu-id="5383e-141">Discovery and assessment for on-premises virtual machines</span></span>

- <span data-ttu-id="5383e-142">多层应用程序的高置信度发现内置依赖关系映射</span><span class="sxs-lookup"><span data-stu-id="5383e-142">Inbuilt dependency mapping for high-confidence discovery of multi-tier applications</span></span>

- <span data-ttu-id="5383e-143">到 Azure 虚拟机的智能右大小调整</span><span class="sxs-lookup"><span data-stu-id="5383e-143">Intelligent right sizing to Azure virtual machines</span></span>

- <span data-ttu-id="5383e-144">兼容性报告修正潜在的问题的指导原则</span><span class="sxs-lookup"><span data-stu-id="5383e-144">Compatibility reporting with guidelines for remediating potential issues</span></span>

- <span data-ttu-id="5383e-145">与 Azure 数据库管理服务集成以进行数据库发现和迁移</span><span class="sxs-lookup"><span data-stu-id="5383e-145">Integration with Azure Database Management Service for database discovery and migration</span></span>

<span data-ttu-id="5383e-146">Azure Migrate 提供的工作负荷可以对业务影响最小迁移并按预期方式在 Azure 中运行的置信度。</span><span class="sxs-lookup"><span data-stu-id="5383e-146">Azure Migrate gives you confidence that your workloads can migrate with minimal impact to the business and run as expected in Azure.</span></span> <span data-ttu-id="5383e-147">使用合适的工具和指南，可以实现最大同时确保性能的关键投资回报和满足可靠性需求。</span><span class="sxs-lookup"><span data-stu-id="5383e-147">With the right tools and guidance, you can achieve maximum return on investment while assuring that critical performance and reliability needs are met.</span></span>

<span data-ttu-id="5383e-148">图 2-2 显示了由 Azure Migrate 执行的所有服务器和应用程序连接的内置依赖关系映射。</span><span class="sxs-lookup"><span data-stu-id="5383e-148">Figure 2-2 shows you the built-in dependency mapping for all server and application connections performed by Azure Migrate.</span></span>

![定位云基础结构准备就绪的应用程序](./media/image2-2.png)

> <span data-ttu-id="5383e-150">**图 2-2。**</span><span class="sxs-lookup"><span data-stu-id="5383e-150">**Figure 2-2.**</span></span> <span data-ttu-id="5383e-151">定位云基础结构准备就绪的应用程序</span><span class="sxs-lookup"><span data-stu-id="5383e-151">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a><span data-ttu-id="5383e-152">使用 Azure Site Recovery 将现有 Vm 迁移到 Azure Vm</span><span class="sxs-lookup"><span data-stu-id="5383e-152">Use Azure Site Recovery to migrate your existing VMs to Azure VMs</span></span>

<span data-ttu-id="5383e-153">作为端到端的一部分[Azure Migrate](https://aka.ms/azuremigrate)， [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)是一个工具，可用于轻松地将你的 web 应用迁移到 Azure 中的 Vm。</span><span class="sxs-lookup"><span data-stu-id="5383e-153">As part of the end-to-end [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) is a tool that you can use to easily migrate your web apps to VMs in Azure.</span></span> <span data-ttu-id="5383e-154">您可以使用 Site Recovery 将本地 Vm 和物理服务器复制到 Azure，或将它们复制到辅助的本地位置。</span><span class="sxs-lookup"><span data-stu-id="5383e-154">You can use Site Recovery to replicate on-premises VMs and physical servers to Azure, or to replicate them to a secondary on-premises location.</span></span> <span data-ttu-id="5383e-155">甚至可以复制在本地上的受支持的 Azure VM 运行的工作负荷*HYPER-V* VM 上*VMware* VM，或在 Windows 或 Linux 的物理服务器上。</span><span class="sxs-lookup"><span data-stu-id="5383e-155">You can even replicate a workload that's running on a supported Azure VM, on an on-premises *Hyper-V* VM, on a *VMware* VM, or on a Windows or Linux physical server.</span></span> <span data-ttu-id="5383e-156">复制到 Azure 消除了成本和维护辅助数据中心的复杂性。</span><span class="sxs-lookup"><span data-stu-id="5383e-156">Replication to Azure eliminates the cost and complexity of maintaining a secondary datacenter.</span></span>

<span data-ttu-id="5383e-157">此外专门为混合环境的一部分进行站点恢复的本地和部分 on Azure。</span><span class="sxs-lookup"><span data-stu-id="5383e-157">Site Recovery is also made specifically for hybrid environments that are partly on-premises and partly on Azure.</span></span> <span data-ttu-id="5383e-158">Site Recovery 可帮助确保业务连续性使你在 Vm 运行的应用程序和本地物理服务器上可用如果在站点出现故障。</span><span class="sxs-lookup"><span data-stu-id="5383e-158">Site Recovery helps ensure business continuity by keeping your apps that are running on VMs and on-premises physical servers available if a site goes down.</span></span> <span data-ttu-id="5383e-159">它将复制，以便它们仍然可用在辅助位置中，如果主站点不可用的 Vm 和物理服务器运行的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="5383e-159">It replicates workloads that are running on VMs and physical servers so that they remain available in a secondary location if the primary site isn't available.</span></span> <span data-ttu-id="5383e-160">它会恢复到主站点时已启动并再次运行的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="5383e-160">It recovers workloads to the primary site when it's up and running again.</span></span>

<span data-ttu-id="5383e-161">图 2-3 显示的多个 VM 迁移执行了使用 Azure Site Recovery。</span><span class="sxs-lookup"><span data-stu-id="5383e-161">Figure 2-3 shows the execution of multiple VM migrations by using Azure Site Recovery.</span></span>

![定位云基础结构准备就绪的应用程序](./media/image2-3.png)

> <span data-ttu-id="5383e-163">**图 2-3。**</span><span class="sxs-lookup"><span data-stu-id="5383e-163">**Figure 2-3.**</span></span> <span data-ttu-id="5383e-164">定位云基础结构准备就绪的应用程序</span><span class="sxs-lookup"><span data-stu-id="5383e-164">Positioning Cloud Infrastructure-Ready applications</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5383e-165">其他资源</span><span class="sxs-lookup"><span data-stu-id="5383e-165">Additional resources</span></span>

- <span data-ttu-id="5383e-166">**Azure Migrate Datasheet**</span><span class="sxs-lookup"><span data-stu-id="5383e-166">**Azure Migrate Datasheet**</span></span>

    <https://aka.ms/azuremigration\_datasheet>

- <span data-ttu-id="5383e-167">**Azure Migrate**</span><span class="sxs-lookup"><span data-stu-id="5383e-167">**Azure Migrate**</span></span>

    <https://aka.ms/azuremigrate>

- <span data-ttu-id="5383e-168">**Azure 迁移中心**</span><span class="sxs-lookup"><span data-stu-id="5383e-168">**Azure migration center**</span></span>

    <https://azure.microsoft.com/migration/>

- <span data-ttu-id="5383e-169">**使用 Site Recovery 迁移到 Azure**</span><span class="sxs-lookup"><span data-stu-id="5383e-169">**Migrate to Azure with Site Recovery**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- <span data-ttu-id="5383e-170">**Azure Site Recovery 服务概述**</span><span class="sxs-lookup"><span data-stu-id="5383e-170">**Azure Site Recovery service overview**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- <span data-ttu-id="5383e-171">**将 Vm 迁移到 Azure Vm 的 AWS 中**</span><span class="sxs-lookup"><span data-stu-id="5383e-171">**Migrating VMs in AWS to Azure VMs**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
><span data-ttu-id="5383e-172">[上一页](index.md)
>[下一页](migrate-your-relational-databases-to-azure.md)</span><span class="sxs-lookup"><span data-stu-id="5383e-172">[Previous](index.md)
[Next](migrate-your-relational-databases-to-azure.md)</span></span>
