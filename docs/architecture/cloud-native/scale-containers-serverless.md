---
title: 缩放容器和无服务器应用程序
description: 使用 Azure Kubernetes 服务缩放云本机应用程序，通过增加单个计算机资源来满足用户需求，或增加应用程序群集中的计算机数。
ms.date: 09/23/2019
ms.openlocfilehash: 2d0537fb3ed56beb4eccbf9b8c34a5d87793413b
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841011"
---
# <a name="scaling-containers-and-serverless-applications"></a>缩放容器和无服务器应用程序

缩放应用程序的方法有两种：向上缩放和向外缩放。前者是指向一个主机添加功能，而后者是指向主机的总数添加。 用于考虑这种情况的一个常见类比就是如何使自己和某些朋友遍布城镇。 如果它只是一个朋友，则可以跳转到两位赛车。 但如果它是三个或四个，则可能需要获取 SUVs 或 minivan 之一，增加容量以增加容量。 不过，如果总数量达到了数个或更多，则可能需要采用多个车辆（除非有人驱动某个总线），这就是通过添加更多实例（在本例中为更多车辆）来进行扩展的概念。 让我们看看这如何适用于我们的应用程序。

## <a name="the-simple-solution-scaling-up"></a>简单的解决方案：向上缩放

升级现有服务器以使其更多资源（CPU、内存、磁盘 i/o 速度、网络 i/o 速度）的过程称为 "*向上缩放*"。 在云本机应用程序中，纵向扩展并不是指在物理计算机上购买和安装实际硬件，这与从可用的选项列表中选择功能更强大的计划更多。 通常，通过修改用于宿主 Kubernetes 节点池中各个节点的虚拟机（VM）大小来扩展云本机应用。 [下一节](leverage-containers-orchestrators.md)中进一步介绍了 Kubernetes 的概念，如节点、群集和 pod。 Azure 支持各种虚拟机大小，同时运行[Windows](https://docs.microsoft.com/azure/virtual-machines/windows/sizes?toc=%2fazure%2fvirtual-machines%2fwindows%2ftoc.json)和[Linux](https://docs.microsoft.com/azure/virtual-machines/linux/sizes)。 若要对应用程序进行垂直缩放，请创建具有更大节点 VM 大小的新节点池，并将工作负荷迁移到新池。 这需要[AKS 群集的多个节点池](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)，这是目前处于预览阶段的一项功能。 无服务器应用通过选择[高级计划](https://docs.microsoft.com/azure/azure-functions/functions-scale)和高级实例大小，或选择其他专用应用服务计划进行扩展。

## <a name="scaling-out-cloud-native-apps"></a>向外扩展云本机应用

云本机应用支持向服务请求添加其他节点或盒向外扩展。 可以通过调整应用的配置设置（例如，[缩放节点池](https://docs.microsoft.com/azure/aks/use-multiple-node-pools#scale-a-node-pool-manually)）或通过自动*缩放*来手动完成此操作。 自动缩放会调整应用程序使用的资源，以响应需求，类似于恒温器如何通过拨打额外加热或冷却来响应温度。 使用自动缩放时，将禁用手动缩放。

AKS 群集可通过以下两种方式之一进行缩放：

- 由于资源限制，无法在节点上计划的[群集自动缩放程序](https://docs.microsoft.com/azure/aks/cluster-autoscaler)监视。 它根据需要添加其他节点。
- **横向 pod 自动缩放程序**使用 Kubernetes 群集中的指标服务器来监视 pod 的资源需求。 如果某个服务需要更多的资源，则自动缩放程序会增加盒的数目。

图3-13 显示了这两个缩放服务之间的关系。

![向外扩展应用服务计划。](./media/aks-cluster-autoscaler.png)

**图 3-13**。 向外扩展应用服务计划。

这些服务还可以根据需要减少 pod 或节点的数量。 这两个服务可以一起使用，并且通常一起部署到群集中。 组合后，横向 pod 自动缩放程序侧重于运行满足应用程序需求所需的 pod 数。 群集自动缩放程序侧重于运行支持计划箱所需的节点数。

### <a name="scaling-azure-functions"></a>缩放 Azure Functions

Azure Functions 自动支持向外扩展。默认消耗计划根据传入的触发事件数动态添加（和删除）资源。 仅根据执行次数、执行时间和所使用的内存，对正在使用的计算资源付费。 使用高级计划，你可以获得这些相同的功能，但你也可以控制所使用的实例大小、已准备好的实例（以避免冷启动延迟），并配置要在其上运行函数的专用 Vm。 尽管默认配置应为大多数应用提供经济实惠且可缩放的解决方案，但 "高级" 选项使开发人员可以灵活地满足自定义 Azure Functions 要求。

## <a name="references"></a>参考

- [AKS 多节点池](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)
- [AKS 群集自动缩放程序](https://docs.microsoft.com/azure/aks/cluster-autoscaler)
- [教程：在 AKS 中缩放应用程序](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale)
- [Azure Functions 缩放和托管](https://docs.microsoft.com/azure/azure-functions/functions-scale)

>[!div class="step-by-step"]
>[上一页](deploy-containers-azure.md)
>[下一页](other-deployment-options.md)
