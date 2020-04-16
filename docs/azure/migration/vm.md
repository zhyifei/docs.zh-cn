---
title: 将ASP.NET Web 应用迁移到 Azure VM
description: 了解如何将 ASP.NET Web 应用程序从本地迁移到 Azure 虚拟机。
ms.topic: how-to
ms.date: 11/15/2017
ms.openlocfilehash: cc9477de92e6105762636ed3a2241949e69ac8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2020
ms.locfileid: "81433360"
---
# <a name="migrate-an-aspnet-web-application-to-an-azure-virtual-machine"></a>将 ASP.NET Web 应用程序迁移到 Azure 虚拟机

本文档概述了解如何将 ASP.NET Web 应用程序从本地迁移到 Azure 虚拟机。

## <a name="quickstart"></a>快速入门

了解如何创建虚拟机并将应用发布到其中：[发布到 Azure VM](https://tutorials.visualstudio.com/aspnet-vm/intro)

## <a name="get-started"></a>入门

这些教程演示了创建（或迁移）虚拟机、将 Web 应用程序发布到该虚拟机的步骤，以及在 Azure 中支持应用程序所要执行的其他任务。

- 使用以下选项之一在 Azure 中为 Azure 中的ASP.NET应用程序创建虚拟机：
  - [为 ASP.NET 应用程序创建新的虚拟机](https://go.microsoft.com/fwlink/?linkid=863237)
  - [迁移现有的本地 VMWare 虚拟机](https://docs.microsoft.com/azure/migrate/tutorial-migrate-vmware)
  - [迁移现有的本地超 V 虚拟机](https://docs.microsoft.com/azure/migrate/tutorial-migrate-hyper-v)
- [使用 Visual Studio 发布应用](https://go.microsoft.com/fwlink/?linkid=863240)
- [为 VM 创建安全虚拟网络](https://docs.microsoft.com/azure/virtual-network/virtual-network-get-started-vnet-subnet)
- [为应用程序创建 CI/CD 管道](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-webdeploy-iis-deploygroups)
- [转移到 VM 规模集以实现高可用性和可伸缩性](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app)

## <a name="considerations"></a>注意事项

### <a name="benefits"></a>优点

虚拟机提供将应用程序从本地迁移到云的最简单路径。 这样就可以复制应用程序在本地使用的相同环境，同时无需维护自己的数据中心。 虚拟机规模集为虚拟机中运行的应用程序提供高可用性和可伸缩性。

### <a name="virtual-machine-size"></a>虚拟机大小

选择最大程度地针对工作负荷进行优化的虚拟机大小和类型。 有关详细信息，请参阅[Azure 中 Windows 虚拟机的大小](https://docs.microsoft.com/azure/virtual-machines/windows/sizes)。

### <a name="maintenance"></a>维护

就像在本地计算机上一样，你需要负责维护和更新虚拟机<sup>&#42;</sup>。 如果应用程序可以在 [Azure 应用服务](https://docs.microsoft.com/azure/app-service/)等平台即服务 (PaaS) 环境或者在[容器](https://docs.microsoft.com/azure/app-service/containers/)中运行，则不需要执行维护和更新。

*<sup>&#42;</sup>[虚拟机规模集的自动 OS 升级](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade)目前作为预览版服务提供*。

### <a name="virtual-networks"></a>虚拟网络

使用 Azure 虚拟网络可以：

- 构建可控的混合基础结构
- 自带 IP 地址和 DNS 服务器
- 为您的应用程序创建一个孤立且高度安全的环境
- 使用多个[连接选项](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways#s2smulti)之一将 VM 连接到本地网络
- 使用 [ExpressRoute](https://azure.microsoft.com/services/expressroute/) 将虚拟机集成到本地网络

若要开始，请参阅[虚拟网络文档](https://docs.microsoft.com/azure/virtual-network/)

### <a name="active-directory"></a>Active Directory
许多应用程序使用 Active Directory 进行身份验证和标识管理。

- 使用 Azure AD Connect 可将本地目录与 Azure Active Directory 集成。 若要开始集成，请参阅[将本地目录与 Azure Active Directory 集成](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。
- 或者，可以让应用程序使用 [ExpressRoute](https://azure.microsoft.com/services/expressroute/) 访问本地 Active Directory。

### <a name="sql-databases"></a>SQL 数据库

如果应用程序使用本地数据库，默认情况下，应用无法与该数据库通信。 可以：

- 配置一个混合网络来让应用程序访问本地运行的数据库。
- 将数据库迁移到 Azure 有关详细信息，请参阅将[SQL Server 数据库迁移到 Azure](sql.md)。

### <a name="high-availability-and-scalability"></a>高可用性和可伸缩性

#### <a name="virtual-machine-scale-sets"></a>虚拟机规模集
如果想要确保应用程序具有高可用性并可缩放，可将 VM 映像迁移到 Azure 虚拟机规模集，以提高应用程序的可用性和可伸缩性。 VM Scale 集提供了使用已配置的现有 VM 的能力，或设置生成管道以使用应用程序生成映像。

若要开始，请参阅[在虚拟机规模集上部署应用程序](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app)。

#### <a name="centralized-logging"></a>集中式日志记录
跨多个实例运行应用程序时，请考虑将日志存储在某个中心位置，例如 [Azure 存储](https://docs.microsoft.com/azure/storage/)。

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [将 SQL Server 数据库迁移到 Azure](sql.md)
