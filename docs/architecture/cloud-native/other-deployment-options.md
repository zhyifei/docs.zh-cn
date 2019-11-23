---
title: 其他容器部署选项
description: 使用 Azure 的其他容器部署选项
ms.date: 06/30/2019
ms.openlocfilehash: 1fcb57eedec8c9f5574fffcf409b316332032062
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841161"
---
# <a name="other-container-deployment-options"></a>其他容器部署选项

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

除了部署到 AKS 以外，还可以为容器和 Azure 容器实例将容器部署到 Azure App Service。

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a>部署到容器的应用服务有何意义？

不需要业务流程的简单生产应用程序非常适合用于容器 Azure App Service。

## <a name="how-to-deploy-to-app-service-for-containers"></a>如何部署到容器的应用服务

若要部署到[容器 Azure App Service](https://azure.microsoft.com/services/app-service/containers/)，需要配置 Azure 容器注册表（ACR）和凭据，以便对其进行访问。 将你要承载的容器推送到注册表，以便可以将其推送到你的 Azure App Service。 创建后，可以将应用程序配置为持续部署，这会在更新其对应的映像时，自动将更新部署到该应用。

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a>部署到 Azure 容器实例时有何意义？

Azure 容器实例最适合用于测试方案。 它们提供了一种快速、简单的方式将应用程序部署到云托管的容器实例。 当你不需要 Azure Kubernetes 服务提供的缩放和业务流程功能时，可以使用它们来测试或演示应用程序。

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a>如何将应用部署到 Azure 容器实例

若要部署到[Azure 容器实例（ACI）](https://docs.microsoft.com/azure/container-instances/)，需要配置 Azure 容器注册表（ACR）和凭据，以便对其进行访问。 你还必须将容器映像推送到注册表，以便将其提取到 ACI。 可以使用 Azure CLI 或通过门户来使用 ACI。 Azure 容器注册表使你可以轻松地直接从注册表内将各个容器实例部署到 ACI，如图3-14 所示。

![Azure 容器注册表运行实例](./media/acr-runinstance-contextmenu.png)

**图 3-14**。 Azure 容器注册表运行实例

通过注册表创建容器实例只需指定常用的 Azure 设置（名称、订阅、资源组和位置）、要分配给容器的内存量以及应侦听的端口。 本[快速入门演示如何使用 Azure 门户将容器实例部署到 ACI](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal)。

部署完成后，查找新部署的容器的 IP 地址，并通过指定的端口与它进行通信。

Azure 容器实例提供了在 Azure 中运行容器的最简单、最简单的方法。 无需配置应用服务或 orchestrator 或处理虚拟机。 然而，由于其简易性，ACI 应该主要用于测试目的。 如果你的应用程序需要自动可伸缩性、配置为一起使用的多个容器或任何其他复杂的功能，则可以使用其他更适合的 Azure 服务来托管你的应用程序。

## <a name="references"></a>参考

- [Azure 容器实例文档](https://docs.microsoft.com/azure/container-instances/)
- [从 ACR 部署容器实例](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
>[上一页](scale-containers-serverless.md)
>[下一页](communication-patterns.md)
