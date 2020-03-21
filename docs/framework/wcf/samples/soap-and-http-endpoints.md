---
title: SOAP 和 HTTP 终结点
ms.date: 03/30/2017
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
ms.openlocfilehash: f10b1aa4514aee50c0c0d17cabdb9516a3ca7584
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144014"
---
# <a name="soap-and-http-endpoints"></a>SOAP 和 HTTP 终结点
此示例演示如何实现基于 RPC 的服务，并使用 WCF Web 编程模型以 SOAP 格式和"纯旧 XML"（POX） 格式公开该服务。 有关服务 HTTP 绑定的更多详细信息，请参阅[基本 HTTP 服务](../../../../docs/framework/wcf/samples/basic-http-service.md)示例。 本示例重点介绍有关使用不同绑定通过 SOAP 和 HTTP 公开相同服务的详细信息。  
  
## <a name="demonstrates"></a>演示  
 使用 WCF 通过 SOAP 和 HTTP 公开 RPC 服务。  
  
## <a name="discussion"></a>讨论区  
 此示例由两个组件组成：包含 WCF 服务的 Web 应用程序项目（服务）和使用 SOAP 和 HTTP 绑定调用服务操作的控制台应用程序（客户端）。  
  
 WCF 服务公开了 2`GetData`个`PutData`操作 ，并且与作为输入传递的字符串相呼应。 这些服务操作使用 <xref:System.ServiceModel.Web.WebGetAttribute> 和 <xref:System.ServiceModel.Web.WebInvokeAttribute> 进行批注。 这些特性控制这些操作的 HTTP 投影。 此外，这些操作使用 <xref:System.ServiceModel.OperationContractAttribute> 进行批注，从而使其可以通过 SOAP 绑定进行公开。 服务的 `PutData` 方法引发 <xref:System.ServiceModel.Web.WebFaultException>，该异常使用 HTTP 状态代码通过 HTTP 发回，通过 SOAP 作为 SOAP 错误发回。  
  
 Web.config 文件配置具有 3 个终结点的 WCF 服务：  
  
- ~/service.svc/mex 终结点，公开服务元数据供基于 SOAP 的客户端访问。  
  
- ~/service.svc/http 终结点，使客户端可以使用 HTTP 绑定访问服务。  
  
- ~/service.svc/soap 终结点，使客户端可以使用 SOAP over HTTP 绑定访问服务。  
  
 HTTP 终结点配置了已`webHttp``helpEnabled`设置为`true`> 标准终结点<。 因此，服务在 ~/service.svc/http/help 上公开基于 XHTML 的页面，基于 HTTP 的客户端可以使用该页面访问服务。  
  
 客户端项目演示使用 SOAP 代理（通过**添加服务引用**生成）访问服务，并使用 访问服务<xref:System.Net.WebClient>。  
  
 该示例包含一个 Web 承载的服务和一个控制台应用程序。 在控制台应用程序运行时，客户端会对服务进行请求，并将响应中的相关信息写入控制台窗口。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1. 打开 SOAP 和 HTTP 终结点示例的解决方案。  
  
2. 按 CTRL+SHIFT+B 生成解决方案。  
  
3. 如果尚未打开，请按 CTRL+W，S 打开**解决方案资源管理器**窗口。  
  
4. 在 **"解决方案资源管理器"** 窗口中，右键单击 **"服务**"项目并将光标放在 **"调试**上下文"菜单选项上，以便显示 **"开始新实例"** 上下文菜单。 单击 **"启动新实例**"。 这将启动承载服务的 ASP.NET 开发服务器。  
  
5. 在"解决方案资源管理器"窗口中，右键单击"客户端"项目并将光标放在 **"调试上下文"** 菜单选项上，以便显示 **"开始新实例"** 上下文菜单。 单击 **"启动新实例**"。  
  
6. 出现客户端控制台窗口，该窗口提供了正在运行的服务的 URI，以及该服务的 HTML 帮助页的 URI。 可随时通过在浏览器中键入 HTML 帮助页的 URI 来查看该帮助页。  
  
7. 在示例运行时，客户端将写入当前活动的状态。  
  
8. 按任意键可终止客户端控制台应用程序。  
  
9. 按 Shift+F5 可停止调试服务。  
  
10. 在 Windows 通知区域中，右键单击ASP.NET开发服务器图标，然后从上下文菜单中选择 **"停止**"。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
