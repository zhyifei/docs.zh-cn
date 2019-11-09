---
title: 将 eShopOnContainers 部署到 Azure
description: 使用 Azure Kubernetes 服务、Helm 和 DevSpaces 部署 eShopOnContainers 应用程序。
ms.date: 06/30/2019
ms.openlocfilehash: 21033cc904dc595193c69f3452ce2522740f8ff6
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840489"
---
# <a name="deploying-eshoponcontainers-to-azure"></a>将 eShopOnContainers 部署到 Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Azure 使用各种服务支持 eShopOnContainers 应用程序的逻辑。 推荐的方法是使用 Azure Kubernetes 服务（AKS）的 Kubernetes。 这可以与 Helm 部署结合，以确保轻松地重复基础结构配置。 或者，开发人员可以在开发过程中利用 Kubernetes Azure Dev Spaces。 另一种做法是使用 Azure 无服务器功能（如 Azure Functions 和 Azure 逻辑应用）承载应用程序的功能。

## <a name="azure-kubernetes-service"></a>Azure Kubernetes 服务

如果要在自己的 AKS 群集中托管 eShopOnContainers 应用程序，第一步是创建群集。 你可以使用 Azure 门户执行此操作，该操作将引导你完成所需的步骤，或者可以使用 Azure CLI，请务必确保启用基于角色的访问控制（RBAC）和应用程序路由。 EShopOnContainers 文档介绍了创建你自己的 AKS 群集时所涉及的步骤。 创建群集后，必须启用对 Kubernetes 仪表板的访问权限，此时你应该能够浏览到 Kubernetes 仪表板来管理群集。

创建并配置群集后，可以使用 Helm 和 Tiller 将应用程序部署到该群集。

## <a name="deploying-to-azure-kubernetes-service-using-helm"></a>使用 Helm 部署到 Azure Kubernetes 服务

AKS 的基本部署可能使用自定义 CLI 脚本或简单的部署文件，但更复杂的应用程序应使用 Helm 等依赖项管理工具。 Helm 由云本机计算基础维护，可帮助你定义、安装和升级 Kubernetes 应用程序。 Helm 由命令行客户端 Helm 使用，后者使用 Helm 图表和群集内组件 Tiller。 Helm 图表使用标准 YAML 格式的文件来描述一组相关的 Kubernetes 资源，这些资源通常与它们所描述的应用程序进行版本控制。 Helm 图的范围从简单到复杂，具体取决于它们所描述的安装的要求。

你将在/k8s/helm 文件夹中找到 eShopOnContainers helm 图。 图2-6 显示了如何将应用程序的不同组件组织到 helm 用于定义和管理部署的文件夹结构中。

![eShopOnContainers 体系结构](./media/eshoponcontainers-helm-folder.png)
**图 2-6**。 EShopOnContainers helm 文件夹。

使用 `helm install` 命令安装每个单独的组件。 这些命令易于编写脚本，eShopOnContainers 提供了一个 "部署全部" 脚本，该脚本可循环浏览不同的组件并使用各自的 helm 图表安装这些组件。 结果就是一个可重复执行的过程，该过程与源代码管理中的应用程序进行了版本控制，团队中的任何人都可以使用单行脚本命令将其部署到 AKS 群集。 尤其是在与 Azure Dev Spaces 结合时，这使开发人员可以轻松地诊断和测试其对基于微服务的云本机应用程序所做的更改。

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Azure Dev Spaces 有助于各个开发人员在开发期间在 Azure 中托管自己的唯一 AKS 群集版本。 这将最大程度地降低本地计算机要求，并允许团队成员快速查看其更改在实际 AKS 环境中的行为。 Azure Dev Spaces 提供了一种 CLI，使开发人员可以使用它来管理其开发空间，并根据需要部署到特定的子开发人员空间。 每个子开发人员空间都使用唯一的 URL 子域进行引用，允许并行部署已修改的群集，以便各个开发人员可以避免相互冲突的正在进行中的工作。 在图2-7 中，可以看到开发人员 Susie 如何将她自己的自行车微服务版本部署到其开发人员空间。 然后，她可以使用以她的空间名称（susie.s.dev.myapp.eus.azds.io）开头的自定义 URL 来测试她的更改。

![eShopOnContainers 体系结构](./media/azure-devspaces-one.png)
**图 2-7**。 开发人员 Susie 将部署自己的自行车微服务版本并对其进行测试。

同时，开发人员 John 正在自定义预订微服务，并需要对其更改进行测试。 他能够将自己的更改部署到自己的开发空间，而不会与 Susie 的更改发生冲突，如图2-8 所示。 他可以使用自己的 URL 测试其更改，该 URL 以其空间的名称作为前缀（john.s.dev.myapp.eus.azds.io）。

![eShopOnContainers 体系结构](./media/azure-devspaces-two.png)
**图 2-8**。 开发人员 John 部署自己的保留版本微服务，并对其进行测试，而不会与其他开发人员发生冲突。

使用 Azure Dev Spaces，团队可以直接使用 AKS，同时对其更改进行单独的更改、部署和测试。 此方法减少了单独专用托管环境的需要，因为每个开发人员都有效地拥有自己的 AKS 环境。 开发人员可以使用其 CLI 来处理 Azure Dev Spaces 或启动其应用程序，以便直接从 Visual Studio Azure Dev Spaces。 [了解有关 Azure Dev Spaces 工作和配置的详细信息。](https://docs.microsoft.com/azure/dev-spaces/how-dev-spaces-works)

## <a name="azure-functions-and-logic-apps-serverless"></a>Azure Functions 和逻辑应用（无服务器）

EShopOnContainers 示例包括对跟踪联机市场营销活动的支持。 Azure Function 用于请求给定市场活动 ID 的市场营销活动详细信息。 单个 Azure 函数终结点更简单、更充分，而不是出于此目的创建一个完整的 ASP.NET Core 应用程序。 Azure Functions 具有比完全 ASP.NET Core 应用程序更简单的生成和部署模型，尤其是在配置为在 Kubernetes 中运行时。 部署函数的脚本使用 Azure 资源管理器（ARM）模板和 Azure CLI。 此市场活动详细信息微服务不是面向客户的，与在线商店没有相同的要求，因此它非常适合 Azure Functions。 函数需要某些配置才能正常工作，如数据库连接字符串数据和图像基 URI 设置。 在 Azure 门户中配置 Azure Functions。

## <a name="references"></a>reference

- [eShopOnContainers：在 AKS 中创建 Kubernetes 群集](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)#create-kubernetes-cluster-in-aks)
- [eShopOnContainers： Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces)
- [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/about)

>[!div class="step-by-step"]
>[上一页](map-eshoponcontainers-azure-services.md)
>[下一页](centralized-configuration.md)
