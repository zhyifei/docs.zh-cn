---
title: 部署承载于 Internet 信息服务中的 WCF 服务
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: 67f6877546951bd92b235218f10f6ccc7011ef5c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463853"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>部署承载于 Internet 信息服务中的 WCF 服务

开发和部署在 Internet 信息服务 （IIS） 中托管的 Windows 通信基础 （WCF） 服务包括以下任务：

- 确保正确安装和注册 IIS、ASP.NET、WCF 和 WCF 激活组件。

- 创建新的 IIS 应用程序，或重用现有的ASP.NET应用程序。

- 为 WCF 服务创建 .svc 文件。

- 将服务实现部署到 IIS 应用程序。

- 配置 WCF 服务。

有关创建 IIS 托管的 WCF 服务的详细演练，请参阅[如何：在 IIS 中托管 WCF 服务](how-to-host-a-wcf-service-in-iis.md)。

## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>确保已正确安装和注册 IIS、ASP.NET 和 WCF

必须安装 WCF、IIS 和ASP.NET才能使 IIS 托管的 WCF 服务正常运行。 安装 WCF（作为 .NET 框架的一部分）、ASP.NET和 IIS 的过程因操作系统而异。 有关安装 WCF 和 .NET 框架的详细信息，请参阅[为开发人员安装 .NET 框架](../../install/guide-for-developers.md)。 要在 Windows 10 上安装 IIS，请在 **"控制面板**"中打开**程序和功能**，然后选择 **"打开或关闭 Windows 功能**"。 在**Windows 功能**中，选择**互联网信息服务**，然后选择 **"确定**"。

![突出显示了 IIS 的 Windows 功能](./media/windows-features-iis.png)

有关在其他操作系统上安装 IIS 的说明，请参阅[在 Windows Vista 和 Windows 7 上安装 IIS，](/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7)并在 Windows 服务器[2012 R2 上安装 IIS 8.5](/iis/install/installing-iis-85/installing-iis-85-on-windows-server-2012-r2)。

如果计算机上已存在 IIS，则 .NET 框架的安装过程会自动将 WCF 注册到 IIS。 如果在 .NET 框架之后安装了 IIS，则需要执行其他步骤才能将 WCF 注册到 IIS 并ASP.NET。 根据您的操作系统，可以按如下所述执行此操作：

- Windows 7 和 Windows 服务器 2003：使用[服务模型注册工具 （ServiceModelReg.exe）](../../../../docs/framework/wcf/servicemodelreg-exe.md)工具向 IIS 注册 WCF。 要使用此工具，在[可视化工作室的开发人员命令提示符](../../tools/developer-command-prompt-for-vs.md)中键入**ServiceModelReg.exe/i /x** 。

- Windows 7：最后，您必须验证ASP.NET是否配置为使用 .NET 框架版本 4 或更高版本。 通过运行带有该`–i`选项ASPNET_Regiis工具来执行此操作。 有关详细信息，请参阅[ASP.NET IIS 注册工具](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90))。

## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>创建新的 IIS 应用程序或重新使用现有的 ASP.NET 应用程序

IIS 托管的 WCF 服务必须驻留在 IIS 应用程序内。 您可以创建新的 IIS 应用程序来独占 WCF 服务。 或者，您可以将 WCF 服务部署到已托管ASP.NET 2.0 内容（如 .aspx 页和ASP.NET Web 服务 [ASMX]）的现有应用程序。 有关这些选项的详细信息，请参阅[WCF 服务和 ASP.NET](wcf-services-and-aspnet.md)中的"与 ASP.NET并排托管 WCF"和"以ASP.NET兼容性模式托管 WCF 服务"部分。

请注意，IIS 6.0 和更高版本会定期重新启动隔离的面向对象的编程应用程序。 默认值为 1740 分钟。 支持的最大值为 71,582 分钟。 可以禁用此重新启动。 有关此属性的详细信息，请参阅[定期重新启动时间](https://docs.microsoft.com/previous-versions/iis/6.0-sdk/ms525914(v=vs.90))。

## <a name="create-an-svc-file-for-the-wcf-service"></a>为 WCF 服务创建 .svc 文件

IIS 中托管的 WCF 服务表示为 IIS 应用程序中的特殊内容文件 （.svc 文件）。 此模型与在 IIS 应用程序内将 ASMX 页表示为 .asmx 文件的方式类似。 .svc 文件包含特定于 WCF 的处理指令[\@（ServiceHost），](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)允许 WCF 托管基础结构激活托管服务以响应传入的消息。 .svc 文件的最常见语法如以下语句所示。

`<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>`

它由[\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)指令和单个属性`Service`组成。 `Service` 属性的值是服务实现的公共语言运行库 (CLR) 类型名称。 使用此指令与使用以下代码创建服务主机基本等效。

```csharp
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );
```

也可以执行其他承载配置，如创建服务的基址列表。 也可以使用自定义 <xref:System.ServiceModel.Activation.ServiceHostFactory> 扩展指令以用于自定义承载解决方案。 托管 WCF 服务的 IIS 应用程序不负责管理实例的<xref:System.ServiceModel.ServiceHost>创建和生存期。 当收到 .svc 文件的第<xref:System.ServiceModel.ServiceHost>一个请求时，托管的 WCF 托管基础结构会动态创建必要的实例。 在代码显式关闭该实例之前或回收应用程序时，不释放该实例。

有关 .svc 文件的语法的详细信息，请参阅[\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)。

## <a name="deploy-the-service-implementation-to-the-iis-application"></a>将服务实现部署到 IIS 应用程序

IIS 中托管的 WCF 服务使用与 ASP.NET 2.0 相同的动态编译模型。 与ASP.NET一样，您可以通过多种方式在不同位置部署 IIS 托管的 WCF 服务的实现代码，如下所示：

- 作为全局程序集缓存 (GAC) 或应用程序的 \bin 目录中的预编译 .dll 文件。 在部署类库的新版本后，才更新预编译的二进制文件。

- 作为位于应用程序的 _App_Code 目录中的未编译源文件。 处理应用程序的第一个请求时，动态需要位于此目录中的源文件。 对 \App_Code 目录中文件进行的任何更改都导致在收到下一个请求时回收和重新编译整个应用程序。

- 作为直接放置在 .svc 文件中的未编译代码。 实现代码也可以位于\@服务的 .svc 文件中，在 ServiceHost 指令之后。 对内联代码进行的任何更改导致在收到下一个请求时回收和重新编译应用程序。

有关ASP.NET 2.0 编译模型的详细信息，请参阅[ASP.NET编译概述](https://docs.microsoft.com/previous-versions/aspnet/ms178466(v=vs.100))。

## <a name="configure-the-wcf-service"></a>配置 WCF 服务

IIS 托管的 WCF 服务将其配置存储在应用程序 Web.config 文件中。 IIS 托管的服务使用与 IIS 外部托管的 WCF 服务相同的配置元素和语法。 但是，下面的约束对 IIS 承载环境是唯一的：

- 承载于 IIS 中的服务的基址。

- 在 IIS 之外托管 WCF 服务的应用程序可以通过将一组基本地址 URI 传递给<xref:System.ServiceModel.ServiceHost>构造函数或在服务配置中提供[\<主机>](../../../../docs/framework/configure-apps/file-schema/wcf/host.md)元素来控制其托管服务的基本地址。 承载于 IIS 中的服务无法控制其基址；承载于 IIS 中的服务的基址是其 .svc 文件的地址。

### <a name="endpoint-addresses-for-iis-hosted-services"></a>承载于 IIS 中的服务的终结点地址

承载于 IIS 中时，任何终结点地址始终被认为相对于表示服务的 .svc 文件的地址。 例如，如果 WCF 服务的基本地址具有`http://localhost/Application1/MyService.svc`以下终结点配置：

```xml
<endpoint address="anotherEndpoint" />
```

这提供了可在 处 到达的`http://localhost/Application1/MyService.svc/anotherEndpoint`终结点。

同样，使用空字符串作为相对地址的终结点配置元素提供可在 处`http://localhost/Application1/MyService.svc`访问的终结点，该终结点是基本地址。

```xml
<endpoint address="" />
```

对于承载于 IIS 中的服务的终结点，必须始终使用相对终结点地址。 如果终结点地址未指向承载公开终结点的服务的`http://localhost/MyService.svc`IIS 应用程序，则提供完全限定的终结点地址（例如），可能会导致服务部署中的错误。 对所承载的服务使用相对终结点地址避免了这些潜在冲突。

### <a name="available-transports"></a>可用传输

IIS 5.1 和 IIS 6.0 中托管的 WCF 服务仅限于使用基于 HTTP 的通信。 在这些 IIS 平台上，将所承载的服务配置为使用非 HTTP 绑定会导致服务激活期间出错。 对于 IIS 7.0，支持的传输包括 HTTP、Net.TCP、Net.Pipe、Net.MSMQ 和 msmq.formatname，用于向后与现有 MSMQ 应用程序兼容。

### <a name="http-transport-security"></a>HTTP 传输安全

IIS 托管的 WCF 服务可以使用 HTTP 传输安全性（例如，HTTPS 和 HTTP 身份验证方案（如基本、摘要和 Windows 集成身份验证），只要包含该服务的 IIS 虚拟目录支持这些设置。 所承载终结点的绑定上的 HTTP 传输安全设置必须与包含它的 IIS 虚拟目录上的传输安全设置匹配。

例如，配置为使用 HTTP 摘要身份验证的 WCF 终结点必须驻留在 IIS 虚拟目录中，该虚拟目录也配置为允许 HTTP 摘要身份验证。 IIS 设置和 WCF 终结点设置的不匹配组合会导致服务激活期间出错。

## <a name="see-also"></a>请参阅

- [在 Internet 信息服务中承载](hosting-in-internet-information-services.md)
- [Internet 信息服务承载最佳实践](internet-information-services-hosting-best-practices.md)
- [Windows Server App Fabric 承载功能](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
