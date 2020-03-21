---
title: 教程：开始使用 Windows 通信基础应用程序
description: 这些教程提供了创建 WCF 应用程序的介绍。
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: df73f953372202796cebce9d3e3f28bd617c67ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184113"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>教程：开始使用 Windows 通信基础应用程序
以下一系列教程将向您介绍 Windows 通信基础 （WCF） 编程体验。 按顺序完成这些教程将为您提供对创建 WCF 应用程序所需的步骤的介绍性理解。 完成后，您将有一个正在运行的 WCF 服务和一个 WCF 客户端调用该服务。

本教程假定您正在使用 Visual Studio 作为开发环境。 如果您正在使用其他开发环境，请忽略特定于 Visual Studio 的说明。

有关可以下载和运行的示例 WCF 应用程序，请参阅[Windows 通信基础示例](samples/index.md)。 有关示例的介绍，请参阅[入门示例](samples/getting-started-sample.md)。

有关创建服务和客户端的深入信息，请参阅[基本 WCF 编程](basic-wcf-programming.md)。

## <a name="wcf-tutorials"></a>WCF 教程

前三个教程介绍如何定义 WCF 服务协定、如何实现它以及如何托管它。 您创建的服务在控制台应用程序中自托管。 您还可以在 Microsoft 互联网信息服务 （IIS） 下托管服务。 有关详细信息，请参阅[如何：在 IIS 中托管 WCF 服务](feature-details/how-to-host-a-wcf-service-in-iis.md)。 尽管在本教程中使用代码配置服务，但您也可以[在配置文件中配置服务](configuring-services-using-configuration-files.md)。

- [教程：定义服务协定](how-to-define-a-wcf-service-contract.md)

    使用用户定义的界面创建 WCF 协定。 此协定定义服务公开的功能。

- [教程：实现服务合同](how-to-implement-a-wcf-contract.md)

    定义协定后，必须使用服务类实现它。

- [教程：托管并运行基本服务](how-to-host-and-run-a-basic-wcf-service.md)

    配置服务的终结点，并在控制台应用程序中托管服务。 要使服务处于活动状态，必须配置该服务并在运行时环境中托管它。 此运行时环境创建服务并控制其上下文和生存期。

接下来的两个教程介绍如何创建、配置和使用客户端应用程序来调用服务公开的操作。 服务发布定义客户端应用程序与服务进行通信所需信息的元数据。 Visual Studio 自动访问此元数据的过程，并用它来构造服务的客户端应用程序。 如果您决定不使用 Visual Studio，则可以使用[服务模型元数据实用程序工具 （*Svcutil.exe*）。](servicemodel-metadata-utility-tool-svcutil-exe.md)

- [教程：创建客户端](how-to-create-a-wcf-client.md)

    检索元数据以从 WCF 服务创建 WCF 客户端代理。 通过使用 Visual Studio 添加服务引用来检索元数据，或者可以使用服务模型元数据实用程序工具。 指定客户端用于访问服务的终结点。

- [教程：使用客户端](how-to-use-a-wcf-client.md)

    使用 WCF 客户端代理调用服务操作。

## <a name="reference"></a>参考

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>另请参阅

- [概念概述](conceptual-overview.md)
- [文档指南](guide-to-the-documentation.md)
- [什么是 Windows 通信基础](whats-wcf.md)
- [WCF 功能详细信息](feature-details/index.md)
- [基本编程生命周期](basic-programming-lifecycle.md)
- [构建客户端](building-clients.md)
- [基本 WCF 编程](basic-wcf-programming.md)
- [如何：创建双工协定](feature-details/how-to-create-a-duplex-contract.md)
- [如何：使用双工协定访问服务](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [服务模型元数据实用程序工具 （Svcutil.exe）](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [如何：使用 Svcutil.exe 下载元数据文档](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [如何：使用配置文件发布服务的元数据](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [使用绑定配置服务和客户端](using-bindings-to-configure-services-and-clients.md)
- [入门示例](samples/getting-started-sample.md)
- [Windows 通信基础示例](samples/index.md)
- [自承载](samples/self-host.md)
