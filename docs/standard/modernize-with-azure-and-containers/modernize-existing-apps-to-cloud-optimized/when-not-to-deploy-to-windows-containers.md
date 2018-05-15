---
title: 何时不将部署到 Windows 容器
description: 更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |何时不将部署到 Windows 容器
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 819f32955ff019414bef8820d17d272eddc11bf8
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="645b4-103">何时不将部署到 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="645b4-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="645b4-104">Windows 容器不支持某些 Windows 技术。</span><span class="sxs-lookup"><span data-stu-id="645b4-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="645b4-105">在这些情况下，仍需要将迁移到标准 Vm，通常使用只是 Windows 和 IIS。</span><span class="sxs-lookup"><span data-stu-id="645b4-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="645b4-106">不支持 Windows 容器中，从 5 月 2018年开始的情况下：</span><span class="sxs-lookup"><span data-stu-id="645b4-106">Cases not supported in Windows Containers, as of May 2018:</span></span> 

-   <span data-ttu-id="645b4-107">Microsoft 消息队列 (MSMQ) 当前才可用，在基于 Windows Server v1803 版本中，Windows 容器中而不是在任何其他先前版本中可用。</span><span class="sxs-lookup"><span data-stu-id="645b4-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span> 

    -   [<span data-ttu-id="645b4-108">UserVoice 请求论坛</span><span class="sxs-lookup"><span data-stu-id="645b4-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="645b4-109">论坛</span><span class="sxs-lookup"><span data-stu-id="645b4-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="645b4-110">在 Windows 容器中当前不支持 Microsoft 分布式事务处理协调器 (MSDTC)。</span><span class="sxs-lookup"><span data-stu-id="645b4-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="645b4-111">GitHub 问题</span><span class="sxs-lookup"><span data-stu-id="645b4-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="645b4-112">Microsoft Office 目前不支持容器。</span><span class="sxs-lookup"><span data-stu-id="645b4-112">Microsoft Office currently does not support containers.</span></span>

    -   [<span data-ttu-id="645b4-113">UserVoice 请求论坛</span><span class="sxs-lookup"><span data-stu-id="645b4-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   <span data-ttu-id="645b4-114">UI 应用 （使用可见的用户界面的客户端应用程序） 不支持的方案。</span><span class="sxs-lookup"><span data-stu-id="645b4-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

-   <span data-ttu-id="645b4-115">Windows 基础结构角色 (DNS、 DHCP、 DC、 NTP，打印，文件服务器，IAM 等) 不支持的方案。</span><span class="sxs-lookup"><span data-stu-id="645b4-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>


<span data-ttu-id="645b4-116">其他不受支持的方案和来自社区的请求，请参阅 UserVoice 论坛为 Windows 容器： <https://windowsserver.uservoice.com/forums/304624-containers>。</span><span class="sxs-lookup"><span data-stu-id="645b4-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="645b4-117">其他资源</span><span class="sxs-lookup"><span data-stu-id="645b4-117">Additional resources</span></span>

-   <span data-ttu-id="645b4-118">**虚拟机和 Azure 中的容器**</span><span class="sxs-lookup"><span data-stu-id="645b4-118">**Virtual machines and containers in Azure**</span></span>

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
<span data-ttu-id="645b4-119">[上一页](deploy-existing-net-apps-as-windows-containers.md)
[下一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="645b4-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
