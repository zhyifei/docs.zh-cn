---
title: "何时不将部署到 Windows 容器"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |何时不将部署到 Windows 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 538cb518cd169f42b3e8b7324ca108a1d366137a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="3ec0f-103">何时不将部署到 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="3ec0f-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="3ec0f-104">Windows 容器不支持某些 Windows 技术。</span><span class="sxs-lookup"><span data-stu-id="3ec0f-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="3ec0f-105">在这些情况下，仍需要将迁移到标准 Vm，通常使用只是 Windows 和 IIS。</span><span class="sxs-lookup"><span data-stu-id="3ec0f-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="3ec0f-106">不支持在 Windows 容器中截至中旬 2017年的情况下：</span><span class="sxs-lookup"><span data-stu-id="3ec0f-106">Cases not supported in Windows Containers, as of mid-2017:</span></span>

-   <span data-ttu-id="3ec0f-107">在 Windows 容器中当前不支持 Microsoft 消息队列 (MSMQ)。</span><span class="sxs-lookup"><span data-stu-id="3ec0f-107">Microsoft Message Queuing (MSMQ) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="3ec0f-108">UserVoice 请求论坛</span><span class="sxs-lookup"><span data-stu-id="3ec0f-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="3ec0f-109">论坛</span><span class="sxs-lookup"><span data-stu-id="3ec0f-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="3ec0f-110">Microsoft 分布式事务处理协调器 (MSDTC) 当前不支持在 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="3ec0f-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers</span></span>

    -   [<span data-ttu-id="3ec0f-111">GitHub 问题</span><span class="sxs-lookup"><span data-stu-id="3ec0f-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="3ec0f-112">Microsoft Office 目前不支持容器</span><span class="sxs-lookup"><span data-stu-id="3ec0f-112">Microsoft Office currently does not support containers</span></span>

    -   [<span data-ttu-id="3ec0f-113">UserVoice 请求论坛</span><span class="sxs-lookup"><span data-stu-id="3ec0f-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

<span data-ttu-id="3ec0f-114">其他不受支持的方案和来自社区的请求，请参阅 UserVoice 论坛为 Windows 容器： <https://windowsserver.uservoice.com/forums/304624-containers>。</span><span class="sxs-lookup"><span data-stu-id="3ec0f-114">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3ec0f-115">其他资源</span><span class="sxs-lookup"><span data-stu-id="3ec0f-115">Additional resources</span></span>

-   <span data-ttu-id="3ec0f-116">**虚拟机和 Azure 中的容器**</span><span class="sxs-lookup"><span data-stu-id="3ec0f-116">**Virtual machines and containers in Azure**</span></span>

    [<span data-ttu-id="3ec0f-117">https://docs.microsoft.com/azure/virtual-machines/windows/containers</span><span class="sxs-lookup"><span data-stu-id="3ec0f-117">https://docs.microsoft.com/azure/virtual-machines/windows/containers</span></span>](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
<span data-ttu-id="3ec0f-118">[上一页](deploy-existing-net-apps-as-windows-containers.md)
[下一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="3ec0f-118">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
