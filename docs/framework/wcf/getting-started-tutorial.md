---
title: 入门 Tutorial1
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], getting started
- Windows Communication Foundation [WCF], getting started
- getting started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: b0abe7a6b127a254c2f5c72dc66fc128d35374fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491358"
---
# <a name="getting-started-tutorial"></a>入门教程
在本部分中包含的主题旨在帮助您快速了解到 Windows Communication Foundation (WCF) 编程体验。 这些主题要根据本主题底部的列表中的顺序完成。 通过本教程中，可以初步了解创建 WCF 服务和客户端应用程序所需的步骤。 服务公开一个或多个终结点，其中每个终结点都公开一项或多项服务操作。 *终结点*服务的指定的地址，其中可以找到该服务，包含描述如何在客户端必须与该服务，并定义的功能的协定通信的信息的绑定向其客户端提供服务。

 在完成本教程中的系列主题之后，您将会得到一个正在运行的服务，以及一个可以调用该服务的客户端。 前三个主题描述如何定义服务协定、如何实现服务协定以及如何承载服务。 创建的服务自承载在控制台应用程序中。 服务还可在 Internet Information Services (IIS) 下承载。 有关如何执行此操作的详细信息，请参阅[如何：承载在 IIS 中的 WCF 服务](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)。 在代码中配置服务；不过，也可以在配置文件中配置服务。 有关使用配置文件的详细信息请参阅[使用配置文件配置服务](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)。

 后三个主题描述如何创建客户端代理，如何配置客户端应用程序，以及如何使用客户端代理调用由服务公开的操作。 服务发布定义客户端应用程序与服务进行通信所需信息的元数据。 Visual Studio 2012 可访问此元数据的过程进行自动化，并使用它来构建和配置服务的客户端应用程序。 如果不使用 Visual Studio 2012，则可以使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)来构建和配置服务的客户端应用程序。

在本部分中的主题假定你使用的 Visual Studio 作为开发环境。 如果使用其他开发环境，忽略的 Visual Studio 的特定说明。

有关示例应用程序，可以下载到您的硬盘和运行，请参阅中的主题[Windows Communication Foundation 示例](https://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)。 本主题中，请参阅，特别是，对于[Getting Started](../../../docs/framework/wcf/samples/getting-started-sample.md)。

有关创建服务和客户端的更多详细信息，请参阅[基本 WCF 编程](../../../docs/framework/wcf/basic-wcf-programming.md)。

## <a name="in-this-section"></a>本节内容
 [如何：定义服务协定](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)

 介绍如何创建 WCF 协定使用用户定义的接口。 协定定义服务所公开的功能。

 [如何：实现服务协定](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

 描述如何实现服务协定。 一旦定义了某一协定后，必须使用某一服务类实现该协定。

 [如何：托管并运行基本服务](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)

 描述如何在代码中配置服务的终结点，以及如何在控制台应用程序内承载服务。 若要激活服务，必须在运行时环境中配置和承载服务。 此环境将创建服务并控制其上下文和生存期。

 [如何：创建客户端](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)

 介绍如何检索用于创建 WCF 客户端代理从 WCF 服务的元数据。 此过程使用 Visual Studio 中的添加服务引用功能。

 [如何：配置客户端](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

 描述如何配置 WCF 客户端。配置客户端需要指定客户端用于访问服务的终结点。

 [如何：使用客户端](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

 介绍如何使用 WCF 客户端代理来调用服务操作。

## <a name="reference"></a>参考

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="related-sections"></a>相关章节

- [Windows Communication Foundation 示例](https://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)
- [基本编程生命周期](../../../docs/framework/wcf/basic-programming-lifecycle.md)

## <a name="see-also"></a>请参阅

- [概念性概述](../../../docs/framework/wcf/conceptual-overview.md)
- [文档使用指南](../../../docs/framework/wcf/guide-to-the-documentation.md)
- [什么是 Windows Communication Foundation](../../../docs/framework/wcf/whats-wcf.md)
- [WCF 功能详细信息](../../../docs/framework/wcf/feature-details/index.md)