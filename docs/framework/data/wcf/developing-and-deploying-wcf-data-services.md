---
title: 开发和部署 WCF 数据服务
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: 4591175da5078a194bfe69884701e5432a0c38a3
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389732"
---
# <a name="develop-and-deploy-wcf-data-services"></a>开发和部署 WCF 数据服务

本文提供有关开发和部署 WCF 数据服务的信息。 有关 WCF 数据服务的详细信息，请参阅[入门](getting-started-with-wcf-data-services.md)和[概述](wcf-data-services-overview.md)。

## <a name="develop-wcf-data-services"></a>开发 WCF 数据服务

当您使用 WCF 数据服务创建支持开放数据协议 （OData） 的数据服务时，必须在开发期间执行以下基本任务：

1. **定义数据模型**

     WCF 数据服务支持各种数据服务提供商，使您能够根据来自各种数据源（从关系数据库到后期绑定数据类型）的数据定义数据模型。 有关详细信息，请参阅[数据服务提供商](data-services-providers-wcf-data-services.md)。

2. **创建数据服务**

     大多数基本数据服务公开一个从 <xref:System.Data.Services.DataService%601> 类继承的类和一个作为实体容器的命名空间限定名称的 `T` 类型。 有关详细信息，请参阅 [Defining WCF Data Services](defining-wcf-data-services.md)的信息。

3. **配置数据服务**

     默认情况下，WCF 数据服务会禁止访问实体容器公开的资源。 该<xref:System.Data.Services.DataServiceConfiguration>接口使您能够配置对资源和服务操作的访问，指定支持版本的 OData，并定义其他服务范围的行为，例如批处理行为或可在单个响应源中返回的最大实体数。 有关详细信息，请参阅[配置数据服务](configuring-the-data-service-wcf-data-services.md)。

本文主要介绍使用 Visual Studio 开发和部署数据服务。 有关 WCF 数据服务为将数据公开为 O 数据馈送而提供的灵活性的信息，请参阅[定义 WCF 数据服务](defining-wcf-data-services.md)。

### <a name="choose-a-development-web-server"></a>选择开发 Web 服务器

当您使用 Visual Studio 2015 将 WCF 数据服务开发为ASP.NET应用程序或ASP.NET网站时，您可以选择在开发期间运行数据服务的 Web 服务器。 以下 Web 服务器与 Visual Studio 集成，以便更轻松地在本地计算机上测试和调试数据服务。

1. **本地 IIS 服务器**

     当您创建在 Internet 信息服务 （IIS） 上运行ASP.NET应用程序或ASP.NET网站的数据服务时，我们建议您使用本地计算机上的 IIS 开发和测试数据服务。 在 IIS 上运行数据服务更便于在调试过程中跟踪 HTTP 请求。 这还允许预先确定 IIS 访问数据服务所需的文件、数据库和其他资源所必须具备的权限。 要在 IIS 上运行数据服务，请确保正确安装和配置 IIS 和 Windows 通信基础 （WCF），并授予对文件系统和数据库中的 IIS 帐户的访问权限。 有关详细信息，请参阅 [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md)。

    > [!NOTE]
    > 您必须运行具有管理员权限的 Visual Studio，才能启用开发环境来配置本地 IIS 服务器。

2. **Visual Studio 开发服务器**

     Visual Studio 包括一个内置的 Web 服务器，即可视化工作室开发服务器，它是ASP.NET项目的默认 Web 服务器。 此 Web 服务器旨在ASP.NET开发期间在本地计算机上运行项目。 [WCF 数据服务快速入门](quickstart-wcf-data-services.md)演示如何创建在可视化工作室开发服务器中运行的数据服务。

     当您使用 Visual Studio 开发服务器开发数据服务时，应注意以下限制：

    - 该服务器只能在本地计算机上访问。

    - 该服务器侦听 `localhost` 和特定端口，而非端口 80，后者是 HTTP 消息的默认端口。 有关详细信息，请参阅 [Visual Studio 中用于 ASP.NET Web 项目的 Web 服务器](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120))。

    - 该服务器在当前用户帐户的上下文中运行数据服务。 例如，如果您以管理员级用户身份运行，则在可视化工作室开发服务器中运行的数据服务将具有管理员级权限。 这会导致数据服务能够访问在部署到 IIS 服务器时无权访问的资源。

    - 该服务器不包含 IIS 的额外功能，如身份验证。

    - 此服务器无法处理分块 HTTP 流，默认情况下，WCF 数据服务客户端在从数据服务访问大型二进制数据时发送这些数据。 有关详细信息，请参阅[流式处理提供程序](streaming-provider-wcf-data-services.md)。

    - 此服务器在处理 URL 中的句点`.`（ ） 字符时出现问题，即使 WCF 数据服务在键值中支持此字符。

    > [!TIP]
    > 即使可以使用 Visual Studio 开发服务器在开发期间测试数据服务，但在部署到运行 IIS 的 Web 服务器后，也应再次测试它们。

3. **Microsoft Azure 开发环境**

     适用于可视化工作室的 Windows Azure 工具包括一组用于在可视化工作室中开发 Windows Azure 服务的集成工具。 使用这些工具，可以开发可部署到 Microsoft Azure 的数据服务，并且可以在部署之前在本地计算机上测试数据服务。 使用 Visual Studio 开发在 Windows Azure 平台上运行的数据服务时，请使用这些工具。 有关安装这些工具的信息，请参阅[Visual Studio 2015 的 Azure 工具](../../../azure/sdk/vs2015-install.md)。 有关开发在 Windows Azure 上运行的数据服务的详细信息，请参阅在[Windows Azure 中部署 OData 服务](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure)的帖子。

### <a name="development-tips"></a>开发提示

开发数据服务时请考虑以下事项：

- 如果计划对用户进行身份验证或限制特定用户的访问，请确定数据服务的安全要求。 有关更多信息，请参见 [Securing WCF Data Services](securing-wcf-data-services.md)。

- 通过允许您检查请求和响应消息的内容，HTTP 检查程序在调试数据服务时非常有用。 可以使用任何可显示原始数据包的网络数据包分析器检查发向数据服务的 HTTP 请求和来自数据服务的响应。

- 调试数据服务时，您可能希望从数据服务获得与常规操作期间有关错误的详细信息。 通过将 <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> 中的 <xref:System.Data.Services.DataServiceConfiguration> 属性设置为 `true` 并将数据服务类的 <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> 特性的 <xref:System.ServiceModel.Description.ServiceDebugBehavior> 属性设置为 `true`，可以从数据服务获取其他错误信息。 有关详细信息，请参阅[调试 WCF 数据服务](https://docs.microsoft.com/archive/blogs/phaniraj/debugging-wcf-data-services)后。 您还可以在 WCF 中启用跟踪，以查看 HTTP 消息层中引发的异常。 有关更多信息，请参见 [Configuring Tracing](../../wcf/diagnostics/tracing/configuring-tracing.md)。

- 数据服务通常作为应用程序项目ASP.NET开发，但您也可以在 Visual Studio 中创建数据服务作为ASP.NET网站项目。 有关这两种项目之间的差异的信息，请参阅[Visual Studio 中的 Web 应用程序项目与网站项目](https://docs.microsoft.com/previous-versions/aspnet/dd547590(v=vs.110))。

- 当您使用 Visual Studio 中的"**添加新项目"** 对话框创建数据服务时，数据服务由 iIS 中的ASP.NET托管。 虽然ASP.NET和 IIS 是数据服务的默认主机，但支持其他托管选项。 有关详细信息，请参阅[托管数据服务](hosting-the-data-service-wcf-data-services.md)。

## <a name="deploy-wcf-data-services"></a>部署 WCF 数据服务

WCF 数据服务在选择承载数据服务的过程方面很灵活。 您可以使用 Visual Studio 将数据服务部署到以下平台：

- **承载有 IIS 的 Web 服务器**

    当数据服务作为ASP.NET项目开发时，可以使用标准ASP.NET部署过程将其部署到 IIS Web 服务器。  Visual Studio 为ASP.NET提供以下部署技术，具体取决于承载要部署的数据服务的ASP.NET项目类型。

  - **ASP.NET Web 应用程序的部署技术**

    - [如何：在 Visual Studio 中创建 Web 部署包](https://docs.microsoft.com/previous-versions/aspnet/dd465323(v=vs.110))

    - [如何：在可视化工作室中使用一键发布部署 Web 项目](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110))

  - **ASP.NET 网站的部署技术**

    - [如何：使用复制网站工具复制网站文件](https://docs.microsoft.com/previous-versions/aspnet/c95809c0(v=vs.100))

    - [如何：发布网站](https://docs.microsoft.com/previous-versions/aspnet/20yh9f1b(v=vs.100))

    - [演练：使用 XCOPY 部署ASP.NET Web 应用程序](https://docs.microsoft.com/previous-versions/aspnet/f735abw9(v=vs.100))

     有关ASP.NET应用程序的部署选项的详细信息，请参阅 Visual Studio[和 ASP.NET 的 Web 部署概述](https://docs.microsoft.com/previous-versions/aspnet/dd394698(v=vs.110))。

    > [!TIP]
    > 在尝试将数据服务部署到 IIS 之前，请确保已测试了向运行 IIS 的 Web 服务器的部署。 有关详细信息，请参阅 [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md)。

- **Microsoft Azure**

     可以使用 Visual Studio 的 Windows Azure 工具将数据服务部署到 Windows Azure。 可以从[微软下载中心](https://go.microsoft.com/fwlink/?LinkID=201848)下载 Visual Studio 的 Windows Azure 工具。 有关将数据服务部署到 Windows Azure 的详细信息，请参阅在 Windows [Azure 中部署 OData 服务](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure)的帖子。

### <a name="deployment-considerations"></a>部署注意事项

部署数据服务时请考虑以下事项：

- 部署使用实体框架提供程序访问 SQL Server 数据库的数据服务时，可能还必须通过数据服务部署来传播数据结构、数据或两者。 Visual Studio 可以自动创建脚本 （.sql 文件）以在目标数据库中执行此操作，这些脚本可以包含在ASP.NET应用程序的 Web 部署包中。 有关详细信息，请参阅[如何：使用 Web 应用程序项目部署数据库](https://docs.microsoft.com/previous-versions/dd465343(v=vs.100))。 对于ASP.NET网站，您可以通过在可视化工作室中使用**数据库发布向导**来执行此操作。 有关详细信息，请参阅发布[SQL 数据库](https://docs.microsoft.com/previous-versions/aspnet/bb907585(v=vs.100))。

- 由于 WCF 数据服务包含基本的 WCF 实现，因此可以使用 Windows 服务器 AppFabric 监视部署到在 Windows 服务器上运行的 IIS 的数据服务。 有关使用 Windows 服务器 AppFabric 监视数据服务的详细信息，请参阅使用[Windows 服务器 AppFabric 跟踪 WCF 数据服务](https://docs.microsoft.com/archive/blogs/rjacobs/tracking-wcf-data-services-with-windows-server-appfabric)的帖子。

## <a name="see-also"></a>另请参阅

- [承载数据服务](hosting-the-data-service-wcf-data-services.md)
- [WCF 数据服务的安全](securing-wcf-data-services.md)
- [定义 WCF 数据服务](defining-wcf-data-services.md)
