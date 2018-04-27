---
title: 何时不将部署到 Windows 容器
description: 为容器化的.NET 应用程序的.NET 微服务体系结构 |何时不将部署到 Windows 容器
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b8fb31a17d1f9d91fe053596685b7560a7fa1ee1
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="when-not-to-deploy-to-windows-containers"></a>何时不将部署到 Windows 容器

Windows 容器不支持某些 Windows 技术。 在这些情况下，仍需要将迁移到标准 Vm，通常使用只是 Windows 和 IIS。

不支持在 Windows 容器中截至中旬 2017年的情况下：

-   在 Windows 容器中当前不支持 Microsoft 消息队列 (MSMQ)。

    -   [UserVoice 请求论坛](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [论坛](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Microsoft 分布式事务处理协调器 (MSDTC) 当前不支持在 Windows 容器

    -   [GitHub 问题](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   Microsoft Office 目前不支持容器

    -   [UserVoice 请求论坛](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

其他不受支持的方案和来自社区的请求，请参阅 UserVoice 论坛为 Windows 容器： <https://windowsserver.uservoice.com/forums/304624-containers>。

### <a name="additional-resources"></a>其他资源

-   **虚拟机和 Azure 中的容器**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[上一页](deploy-existing-net-apps-as-windows-containers.md)
[下一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
