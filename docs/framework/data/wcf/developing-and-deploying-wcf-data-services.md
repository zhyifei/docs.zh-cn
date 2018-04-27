---
title: 开发和部署 WCF 数据服务
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6fbfd28931f484c5b643dad278b358e7ac2a2945
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="developing-and-deploying-wcf-data-services"></a>开发和部署 WCF 数据服务
本主题提供有关开发和部署 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]的信息。 有关更多基本信息[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]，请参阅[入门](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)和[概述](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)。  
  
## <a name="developing-wcf-data-services"></a>开发 WCF 数据服务  
 使用 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 创建支持 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]的数据服务时，必须在开发过程中执行以下基本任务：  
  
1.  **定义数据模型**  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 支持各种数据服务提供程序，可基于来自各种数据源（从关系数据库到后期绑定数据类型）的数据定义数据模型。 有关详细信息，请参阅[数据服务提供程序](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)。  
  
2.  **创建数据服务**  
  
     大多数基本数据服务公开一个从 <xref:System.Data.Services.DataService%601> 类继承的类和一个作为实体容器的命名空间限定名称的 `T` 类型。 有关详细信息，请参阅 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)的信息。  
  
3.  **配置数据服务**  
  
     默认情况下， [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 会禁用对实体容器所公开的资源的访问。 通过 <xref:System.Data.Services.DataServiceConfiguration> 接口可以配置对资源和服务操作的访问，指定支持的 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]版本并定义其他服务范围的行为，例如批处理行为或可在单个响应源中返回的最大实体数。 有关详细信息，请参阅[配置数据服务](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)。  
  
 本主题介绍如何使用 Visual Studio 主要的开发和部署数据服务。 有关 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 将数据公开为 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 源的灵活性方面的详细信息，请参阅 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)的信息。  
  
### <a name="choosing-a-development-web-server"></a>选择开发 Web 服务器  
 当你 WCF 数据服务开发为[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]应用程序或[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]通过使用 Visual Studio 的 Web 站点，您可以选择的 Web 服务器在开发期间运行数据服务。 以下 Web 服务器将与 Visual Studio 便于更轻松地测试和调试你在本地计算机上的数据服务集成。  
  
1.  **本地 IIS 服务器**  
  
     创建作为在 Internet Information Services (IIS) 上运行的 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序或 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 网站的数据服务时，建议使用 IIS 在本地计算机上开发和测试数据服务。 在 IIS 上运行数据服务更便于在调试过程中跟踪 HTTP 请求。 这还允许预先确定 IIS 访问数据服务所需的文件、数据库和其他资源所必须具备的权限。 要在 IIS 上运行数据服务，必须确保正确安装和配置了 IIS 和 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ，并且在文件系统和数据库中授予了 IIS 帐户的访问权限。 有关详细信息，请参阅 [如何：开发在 IIS 上运行的 WCF 数据服务](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)。  
  
    > [!NOTE]
    >  你必须具有管理员权限才能启用开发环境以配置本地 IIS 服务器来运行 Visual Studio。  
  
2.  **Visual Studio 开发服务器**  
  
     Visual Studio 包含一个内置 Web 服务器，Visual Studio 开发服务器，这是默认的 Web 服务器为[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]项目。 该 Web 服务器设计为在开发过程中在本地计算机上运行 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 项目。 [WCF 数据服务快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)演示如何创建在 Visual Studio 开发服务器上运行的数据服务。  
  
     当你使用 Visual Studio 开发服务器开发数据服务时，你应注意以下限制：  
  
    -   该服务器只能在本地计算机上访问。  
  
    -   该服务器侦听 `localhost` 和特定端口，而非端口 80，后者是 HTTP 消息的默认端口。 有关详细信息，请参阅 [Visual Studio 中用于 ASP.NET Web 项目的 Web 服务器](http://msdn.microsoft.com/library/31d4f588-df59-4b7e-b9ea-e1f2dd204328)。  
  
    -   该服务器在当前用户帐户的上下文中运行数据服务。 例如，如果你作为管理员级别的用户运行，在 Visual Studio 开发服务器中运行的数据服务将具有管理员级别特权。 这会导致数据服务能够访问在部署到 IIS 服务器时无权访问的资源。  
  
    -   该服务器不包含 IIS 的额外功能，如身份验证。  
  
    -   该服务器无法处理成块的 HTTP 流，在从数据服务访问大型二进制数据时， [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 客户端会默认发送这种流。 有关详细信息，请参阅[流提供程序](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md)。  
  
    -   该服务器在处理 URL 中的句点 (`.`) 字符时会遇到问题，即使 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 支持在键值中使用该字符。  
  
    > [!TIP]
    >  即使可以使用 Visual Studio 开发服务器在开发过程中测试数据服务，也应部署到运行 IIS 的 Web 服务器之后再次对其进行测试。  
  
3.  **Microsoft Azure 开发环境**  
  
     Windows Azure Tools for Visual Studio 包含一组集成的工具，用于开发 Visual Studio 中的 Windows Azure 服务。 使用这些工具，可以开发可部署到 Microsoft Azure 的数据服务，并且可以在部署之前在本地计算机上测试数据服务。 使用 Visual Studio 开发在 Windows Azure 平台运行的数据服务时，请使用这些工具。 你可以下载 Windows Azure Tools 从 Visual Studio [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=201848)。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 有关开发在 Microsoft Azure 上运行的数据服务，请参阅博文 [在 Microsoft Azure 中部署 OData 服务](http://go.microsoft.com/fwlink/?LinkId=201847)。  
  
### <a name="development-tips"></a>开发提示  
 开发数据服务时，应注意以下事项：  
  
-   如果计划对用户进行身份验证或将访问权限限定给特定用户，请确定数据服务的安全要求。 有关更多信息，请参见 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)。  
  
-   HTTP 检查程序在调试数据服务时会非常有帮助，通过它可以检查请求和响应消息的内容。 可以使用任何可显示原始数据包的网络数据包分析器检查发向数据服务的 HTTP 请求和来自数据服务的响应。  
  
-   与在常规操作过程中相比，在调试数据服务时可能希望获得更多有关来自数据服务的错误的信息。 通过将 <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> 中的 <xref:System.Data.Services.DataServiceConfiguration> 属性设置为 `true` 并将数据服务类的 <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> 特性的 <xref:System.ServiceModel.Description.ServiceDebugBehavior> 属性设置为 `true`，可以从数据服务获取其他错误信息。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] 博文 [调试 WCF 数据服务](http://go.microsoft.com/fwlink/?LinkId=201868)。 还可以在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中启用跟踪以查看 HTTP 消息层中出现的异常。 有关更多信息，请参见 [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)。  
  
-   数据服务通常开发为[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]应用程序项目，但你还可以创建你为数据服务[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Visual Studio 中的网站项目。 两种项目类型之间的差异的信息，请参阅[NIB: Web 应用程序项目与 Visual Studio 中的网站项目](http://msdn.microsoft.com/library/2861815e-f5a2-4378-a2f8-b8a86dc012f5)。  
  
-   当使用创建数据服务**添加新项**对话框中，在 Visual Studio 中，数据服务都由[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]在 IIS 中。 虽然 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 和 IIS 是数据服务的默认宿主，但也支持其他宿主选项。 有关详细信息，请参阅[承载数据服务](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)。  
  
## <a name="deploying-wcf-data-services"></a>部署 WCF 数据服务  
 WCF 数据服务在选择承载数据服务的过程方面很灵活。 可以使用 Visual Studio 将数据服务部署到以下平台：  
  
-   **承载有 IIS 的 Web 服务器**  
  
     将数据服务作为 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 项目开发时，可以使用标准 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 部署过程将其部署到 IIS Web 服务器。  Visual Studio 提供的以下部署技术[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]，具体类型取决于的[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]承载要部署的数据服务的项目。  
  
    -   **ASP.NET Web 应用程序的部署技术**  
  
        -   [Web 部署包](http://msdn.microsoft.com/library/1f9713c8-9540-494c-b80d-9893b970ad6f)  
  
        -   [一键式发布](http://msdn.microsoft.com/library/59226246-99ad-4aec-975d-7c61e8a8911c)  
  
    -   **ASP.NET 网站的部署技术**  
  
        -   [“复制网站”工具](http://msdn.microsoft.com/library/b819aed4-014b-427e-be80-02317b1bb003)  
  
        -   [“发布网站”工具](http://msdn.microsoft.com/library/d0a1a20f-15be-4940-9485-cb8e4aa8181b)  
  
        -   [XCopy](http://msdn.microsoft.com/library/4312c651-2119-49be-bbeb-ee28bdbfe71e)  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 部署选项[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]应用程序，请参阅[for Visual Studio 和 ASP.NET 的 Web 部署概述](http://msdn.microsoft.com/library/99bd1927-b59f-4e02-87b4-55c6ba2adbc3)。  
  
    > [!TIP]
    >  在尝试将数据服务部署到 IIS 之前，请确保已测试了向运行 IIS 的 Web 服务器的部署。 有关详细信息，请参阅 [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)。  
  
-   **Microsoft Azure**  
  
     通过使用 Windows Azure Tools for Visual Studio，可部署到 Windows Azure 的数据服务。 你可以下载 Windows Azure Tools 从 Visual Studio [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=201848)。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 有关将数据服务部署到 Microsoft Azure，请参阅博文 [在 Microsoft Azure 中部署 OData 服务](http://go.microsoft.com/fwlink/?LinkId=201847)。  
  
### <a name="deployment-considerations"></a>部署注意事项  
 部署数据服务时，应注意以下事项：  
  
-   当您部署使用 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 提供程序访问 SQL Server 数据库的数据服务时，还可能需要通过数据服务部署传播数据结构和/或数据。 Visual Studio 可以自动创建脚本 (.sql files) 来执行此操作在目标数据库中，并且这些脚本可以包含的 Web 部署包在[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]应用程序。 有关详细信息，请参阅[NIB： 如何： 部署数据库与 Web 应用程序项目](http://msdn.microsoft.com/library/683b33f1-8a3d-45cf-af6e-61ab50fc518b)。 有关[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]网站上，你可以使用执行此操作**数据库发布向导**Visual Studio 中。 有关详细信息，请参阅 [Deploying a Database by Using the Database Publishing Wizard](http://msdn.microsoft.com/library/1e3682e7-8b57-4da6-a393-af9640ccf8b7)。  
  
-   因为 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 包括基本 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 实现，您可以使用 Windows Server AppFabric 来监视数据服务（它部署到在 Windows Server 上运行的 IIS）。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 有关使用 Windows Server AppFabric 监视数据服务，请参阅博文 [Tracking WCF Data Services with Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=202005)（使用 Windows Server AppFabric 跟踪 WCF 数据服务）。  
  
## <a name="see-also"></a>请参阅  
 [承载数据服务](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)  
 [确保 WCF Data Services 的安全](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 [定义 WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
