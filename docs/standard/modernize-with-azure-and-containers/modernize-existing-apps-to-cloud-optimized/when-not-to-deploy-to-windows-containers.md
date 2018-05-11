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
# <a name="when-not-to-deploy-to-windows-containers"></a>何时不将部署到 Windows 容器

Windows 容器不支持某些 Windows 技术。 在这些情况下，仍需要将迁移到标准 Vm，通常使用只是 Windows 和 IIS。

不支持 Windows 容器中，从 5 月 2018年开始的情况下： 

-   Microsoft 消息队列 (MSMQ) 当前才可用，在基于 Windows Server v1803 版本中，Windows 容器中而不是在任何其他先前版本中可用。 

    -   [UserVoice 请求论坛](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [论坛](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   在 Windows 容器中当前不支持 Microsoft 分布式事务处理协调器 (MSDTC)。

    -   [GitHub 问题](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   Microsoft Office 目前不支持容器。

    -   [UserVoice 请求论坛](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   UI 应用 （使用可见的用户界面的客户端应用程序） 不支持的方案。

-   Windows 基础结构角色 (DNS、 DHCP、 DC、 NTP，打印，文件服务器，IAM 等) 不支持的方案。


其他不受支持的方案和来自社区的请求，请参阅 UserVoice 论坛为 Windows 容器： <https://windowsserver.uservoice.com/forums/304624-containers>。

### <a name="additional-resources"></a>其他资源

-   **虚拟机和 Azure 中的容器**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[上一页](deploy-existing-net-apps-as-windows-containers.md)
[下一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
