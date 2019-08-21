---
title: 何时不部署到 Windows 容器
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |何时不部署到 Windows 容器
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577950"
---
# <a name="when-not-to-deploy-to-windows-containers"></a>何时不部署到 Windows 容器

Windows 容器不支持某些 Windows 技术。 在这些情况下, 你仍需要迁移到标准 Vm, 通常只需要 Windows 和 IIS。

Windows 容器不支持的情况, 2018:

- Microsoft 消息队列 (MSMQ) 当前只能在基于 Windows Server v1803 版本的 Windows 容器中使用, 而不能在任何其他以前版本中使用。

  - [UserVoice 请求论坛](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [讨论论坛](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- Windows 容器当前不支持 Microsoft 分布式事务处理协调器 (MSDTC)。

  - [GitHub 问题](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- Microsoft Office 当前不支持容器。

  - [UserVoice 请求论坛](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- UI 应用 (具有可视用户界面的客户端应用) 不受支持。

- Windows 基础结构角色 (DNS、DHCP、DC、NTP、打印、文件服务器、IAM 等) 不受支持。

有关其他不受支持的方案和社区中的请求, 请参阅适用于 Windows 容器的<https://windowsserver.uservoice.com/forums/304624-containers>UserVoice 论坛:。

### <a name="additional-resources"></a>其他资源

- **Azure 中的虚拟机和容器**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [上一页](deploy-existing-net-apps-as-windows-containers.md)
> [下一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
