---
title: SystemWebRouting 集成示例
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 2f12d80085e3ac27dac8ce80b6bb09f69337bfd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143949"
---
# <a name="systemwebrouting-integration-sample"></a>SystemWebRouting 集成示例
此示例演示 <xref:System.Web.Routing> 命名空间中承载层与类的集成。 通过 <xref:System.Web.Routing> 命名空间中的类，应用程序可以使用不直接与物理资源对应的 URL。 使用 Web 路由允许开发人员为 HTTP 创建虚拟地址，然后映射回实际的 WCF 服务。 如果必须以不使用物理文件或资源的方式承载 WCF 服务，或者必须使用不包含 .html 或 .aspx 这类文件的 URL 访问服务时，这会十分有用。 此示例演示如何利用 <xref:System.Web.Routing.RouteTable> 类创建映射到 global.asax 中定义的运行服务的虚拟 URI。

> [!NOTE]
> <xref:System.Web.Routing> 命名空间中的类仅适用于 HTTP 上承载的服务。  
  
此示例使用 WCF 创建两个 RSS`movies`源：一`channels`个源和一个源。 要激活服务的 URL 不包含扩展，并且在从`Application_Start``Global`<xref:System.Web.HttpApplication>类派生的类的方法中注册。  
  
> [!NOTE]
> 此示例仅适用于 Internet 信息服务 （IIS） 7.0 及更高版本，因为 IIS 6.0 使用不同的方法来支持无扩展 URL。  

#### <a name="to-download-this-sample"></a>下载此示例
  
此示例可能已安装在您的计算机上。 在继续操作之前，请先检查以下（默认）目录：  

`<InstallDrive>:\WF_WCF_Samples`  

 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  

`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1. 使用可视化工作室，打开 Web 路由集成.sln 文件。  
  
2. 若要运行解决方案并启动 Web 开发服务器，请按 F5。  
  
     出现该示例的目录列表。 请注意，不存在具有 .svc 文件扩展名的文件。  
  
3. 在地址栏中，添加到`movies`URL 中，以便读取`http://localhost:[port]/movies`并按 ENTER。  
  
     电影源显示在浏览器中。  
  
4. 在地址栏中，添加到`channels`URL 中，以便读取`http://localhost:[port]/channels`并按 ENTER。  
  
     通道源显示在浏览器中。  
  
5. 按 Alt+F4 关闭 Web 浏览器。  
  
     如果开发服务器尚未退出，请右键单击通知区域图标并选择 **"停止**"。  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>在 IIS 中承载时使用此示例  
  
1. 使用可视化工作室，打开 Web 路由集成.sln 文件。  
  
2. 按 Ctrl+Shift+B 生成项目。  
  
3. 在 Internet 信息服务 (IIS) 管理器中创建 Web 应用程序。  
  
    1. 在 IIS 管理器中，右键单击**默认网站**并选择"**添加应用程序**"。  
  
    2. 对于**别名**，键入`WebRoutingIntegration`。  
  
    3. 对于**物理路径**，选择项目中的服务文件夹。  
  
    4. 按 **“确定”**。  
  
4. 通过右键单击 Web 应用程序并选择 **"管理应用程序**"然后 **"浏览"** 来启动应用程序。  
  
5. 在地址栏中，添加到`movies`URL 中，以便读取`http://localhost:[port]/movies`并按 ENTER。  
  
     电影源显示在浏览器中。  
  
6. 在地址栏中，添加到`channels`URL 中，以便读取`http://localhost:[port]/channels`并按 ENTER。  
  
     通道源显示在浏览器中。  
  
7. 按 Alt+F4 关闭 Web 浏览器。  
  
 此示例演示可以在承载层中使用 <xref:System.Web.Routing> 命名空间中的类进行编写，以便对 HTTP 上承载的服务的请求进行路由。  
  
> [!NOTE]
> 如果默认应用程序池版本设置为版本 2，则必须将其更新为 .NET 框架 4。  
  
## <a name="see-also"></a>另请参阅

- [AppFabric 承载和持久性示例](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
