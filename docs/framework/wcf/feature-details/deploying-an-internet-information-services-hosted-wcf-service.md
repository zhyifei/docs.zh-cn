---
title: 部署承载于 Internet 信息服务中的 WCF 服务
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: 99ed9ce5304717073057f6712a2b96d910d43bea
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46525443"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>部署承载于 Internet 信息服务中的 WCF 服务

开发和部署托管在 Internet 信息服务 (IIS) 的 Windows Communication Foundation (WCF) 服务包括以下任务：

- 请确保，IIS、 ASP.NET、 WCF 和 WCF 激活组件正确安装和注册。

- 创建新的 IIS 应用程序，或重新使用现有的 ASP.NET 应用程序。

- 创建 WCF 服务的.svc 文件。

- 将服务实现部署到 IIS 应用程序。

- 配置 WCF 服务。

创建 IIS 承载的 WCF 服务的详细演练，请参阅[如何： 承载在 IIS 中的 WCF 服务](how-to-host-a-wcf-service-in-iis.md)。

## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>确保已正确安装和注册 IIS、ASP.NET 和 WCF

为 IIS 承载的 WCF 服务才能正常工作，必须安装 WCF、 IIS 和 ASP.NET。 安装 （作为.NET Framework 的一部分） 的 WCF、 ASP.NET 和 IIS 的过程有所不同，具体取决于你的操作系统。 有关安装 WCF 和.NET Framework 的详细信息，请参阅[安装面向开发人员的.NET Framework](../../install/guide-for-developers.md)。 若要在 Windows 10 上安装 IIS，请打开**程序和功能**中**控制面板**，然后选择**打开或关闭打开的 Windows 功能**。 在中**Windows 功能**，选择**Internet Information Services** ，然后选择**确定**。

![使用 IIS 突出显示的 Windows 功能](media/windows-features-iis.png)

其他操作系统上安装 IIS 的说明可从[Windows Vista 和 Windows 7 上安装 IIS](/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7)并[Windows Server 2012 R2 上安装 IIS 8.5](/iis/install/installing-iis-85/installing-iis-85-on-windows-server-2012-r2)。

.NET Framework 的安装过程会自动注册 WCF 与 IIS 如果已在计算机上安装 IIS 的情况。 如果在.NET Framework 之后安装 IIS，则需要一个额外的步骤以将注册 IIS 和 ASP.NET 的 WCF。 根据您的操作系统，可以按如下所述执行此操作：

- Windows 7 和 Windows Server 2003： 使用[ServiceModel 注册工具 (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md)工具向 IIS 注册 WCF。 若要使用此工具，请键入**ServiceModelReg.exe /i /x**中[Visual Studio 的开发人员命令提示](../../tools/developer-command-prompt-for-vs.md)。

- Windows 7： 最后，您必须验证 ASP.NET 配置为使用.NET Framework 4 或更高版本。 为此，可运行的 ASPNET_Regiis 工具`–i`选项。 有关详细信息，请参阅[ASP.NET IIS 注册工具](https://go.microsoft.com/fwlink/?LinkId=201186)。

## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>创建新的 IIS 应用程序或重新使用现有的 ASP.NET 应用程序

IIS 承载的 WCF 服务必须驻留在 IIS 应用程序内。 可以以独占方式创建新的 IIS 应用程序承载 WCF 服务。 或者，可将 WCF 服务部署到现有应用程序已经承载[!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]内容 （如.aspx 页和 ASP.NET Web 服务 [ASMX]）。 有关这些选项的详细信息，请参阅"托管 WCF 的并排方案使用 ASP.NET"和"在 ASP.NET 兼容模式下承载 WCF 服务"部分中[WCF 服务和 ASP.NET](wcf-services-and-aspnet.md)。

请注意， [!INCLUDE[iis601](../../../../includes/iis601-md.md)] 和更高版本定期重新启动独立的面向对象编程应用程序。 默认值为 1740 分钟。 支持的最大值为 71,582 分钟。 可以禁用此重新启动。 有关此属性的详细信息，请参阅[PeriodicRestartTime](https://go.microsoft.com/fwlink/?LinkId=109968)。

## <a name="create-an-svc-file-for-the-wcf-service"></a>为 WCF 服务创建 .svc 文件

在 IIS 中承载的 WCF 服务表示为 IIS 应用程序内的特殊内容文件 （.svc 文件）。 此模型与在 IIS 应用程序内将 ASMX 页表示为 .asmx 文件的方式类似。 .Svc 文件包含特定于 WCF 的处理指令 ([\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)) 允许 WCF 托管基础结构激活响应传入消息中的托管的服务。 .svc 文件的最常见语法如以下语句所示。

```
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>
```

它包含[ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)指令和单个属性`Service`。 `Service` 属性的值是服务实现的公共语言运行库 (CLR) 类型名称。 使用此指令与使用以下代码创建服务主机基本等效。

```csharp
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );
```

也可以执行其他承载配置，如创建服务的基址列表。 也可以使用自定义 <xref:System.ServiceModel.Activation.ServiceHostFactory> 扩展指令以用于自定义承载解决方案。 承载 WCF 服务的 IIS 应用程序不负责创建和生存期管理<xref:System.ServiceModel.ServiceHost>实例。 托管的 WCF 托管基础结构会创建所需<xref:System.ServiceModel.ServiceHost>第一个请求收到.svc 文件时动态实例。 在代码显式关闭该实例之前或回收应用程序时，不释放该实例。

有关.svc 文件语法的详细信息，请参阅[ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)。

## <a name="deploy-the-service-implementation-to-the-iis-application"></a>将服务实现部署到 IIS 应用程序

在 IIS 中承载的 WCF 服务使用相同的动态编译模型[!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]。 就像使用 ASP.NET 中，可以按如下所示部署在不同地区的几种方法中的 IIS 承载的 WCF 服务的实现代码：

- 作为全局程序集缓存 (GAC) 或应用程序的 \bin 目录中的预编译 .dll 文件。 在部署类库的新版本后，才更新预编译的二进制文件。

- 如未编译的源文件位于应用程序的 \App_Code 目录中。 处理应用程序的第一个请求时，动态需要位于此目录中的源文件。 对 \App_Code 目录中文件进行的任何更改都导致在收到下一个请求时回收和重新编译整个应用程序。

- 如未编译的代码直接放在.svc 文件。 实现代码也可以按内联方式位于的服务的.svc 文件之后, \@ServiceHost 指令。 对内联代码进行的任何更改导致在收到下一个请求时回收和重新编译应用程序。

有关详细信息[!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]编译模型中，请参阅[ASP.NET 编译概述](https://go.microsoft.com/fwlink/?LinkId=94773)。

## <a name="configure-the-wcf-service"></a>配置 WCF 服务

IIS 承载的 WCF 服务应用程序 Web.config 文件中存储其配置。 IIS 承载的服务作为 IIS 外部承载的 WCF 服务使用相同的配置元素和语法。 但是，下面的约束对 IIS 承载环境是唯一的：

- 承载于 IIS 中的服务的基址。

- 应用程序 IIS 外部承载的 WCF 服务可以控制通过传递一组基本的服务的基址址到 Uri<xref:System.ServiceModel.ServiceHost>构造函数或通过提供[\<主机 >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md)中的元素服务的配置。 承载于 IIS 中的服务无法控制其基址；承载于 IIS 中的服务的基址是其 .svc 文件的地址。

### <a name="endpoint-addresses-for-iis-hosted-services"></a>承载于 IIS 中的服务的终结点地址

承载于 IIS 中时，任何终结点地址始终被认为相对于表示服务的 .svc 文件的地址。 例如，如果 WCF 服务的基址是`http://localhost/Application1/MyService.svc`使用以下终结点配置：

```xml
<endpoint address="anotherEndpoint" .../>
```

这提供了可以到达的终结点`http://localhost/Application1/MyService.svc/anotherEndpoint`。

同样，使用空字符串，如提供可在终结点的相对地址的终结点配置元素`http://localhost/Application1/MyService.svc`，它是基址。

```xml
<endpoint address="" ... />
```

对于承载于 IIS 中的服务的终结点，必须始终使用相对终结点地址。 提供完全限定的终结点地址 (例如， `http://localhost/MyService.svc`) 终结点地址不指向承载公开终结点的服务的 IIS 的应用程序可能导致服务的部署中的错误。 对所承载的服务使用相对终结点地址避免了这些潜在冲突。

### <a name="available-transports"></a>可用传输

在 IIS 5.1 中承载的 WCF 服务和[!INCLUDE[iis601](../../../../includes/iis601-md.md)]被限制为使用基于 HTTP 的通信。 在这些 IIS 平台上，将所承载的服务配置为使用非 HTTP 绑定会导致服务激活期间出错。 对于 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]，支持的传输包括 HTTP、Net.TCP、Net.Pipe、Net.MSMQ 以及用于与现有 MSMQ 应用程序向后兼容的 msmq.formatname。

### <a name="http-transport-security"></a>HTTP 传输安全

IIS 承载的 WCF 服务可以使用 HTTP 传输安全 （例如，HTTPS 和 HTTP 身份验证方案如基本、 摘要式和 Windows 集成身份验证），前提是包含该服务的 IIS 虚拟目录支持的那些设置。 所承载终结点的绑定上的 HTTP 传输安全设置必须与包含它的 IIS 虚拟目录上的传输安全设置匹配。

例如，配置为使用 HTTP 摘要式身份验证的 WCF 终结点必须驻留在也配置为允许 HTTP 摘要式身份验证的 IIS 虚拟目录。 IIS 设置和 WCF 终结点设置不匹配的组合会在服务激活期间出错。

## <a name="see-also"></a>请参阅

- [在 Internet Information Services 中承载](hosting-in-internet-information-services.md)
- [Internet Information Services 承载最佳做法](internet-information-services-hosting-best-practices.md)
- [Windows Server App Fabric 承载功能](https://go.microsoft.com/fwlink/?LinkId=201276)
