---
title: JSONP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f9a9355c223d3d37811383d52d64f0ac6ddeeaea
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="jsonp"></a>JSONP
本示例演示在 WCF REST 服务中如何支持 JSON with Padding (JSONP)。 JSONP 是通过在当前文档中生成脚本标记来调用跨域脚本时使用的约定。 结果在指定的回调函数中返回。 JSONP 基于这样的标记如\<脚本 src ="http:/ /..."> 可以从任何域评估脚本，并在其中可能已定义其他函数范围内计算这些标记检索的脚本。  
  
## <a name="demonstrates"></a>演示  
 使用 JSONP 进行跨域脚本编写。  
  
## <a name="discussion"></a>讨论  
 本示例包含一个网页，该网页在页面呈现在浏览器中后动态添加脚本块。 此脚本块调用一个 WCF REST 服务，该服务有一个 `GetCustomer` 操作。 WCF REST 服务返回包装在回调函数名内的客户名称和地址。 当 WCF REST 服务响应时，会使用客户数据调用网页上的回调函数，该回调函数会在网页上显示数据。 脚本标记的注入和回调函数的执行由 ASP.NET AJAX ScriptManager 控件自动处理。 使用模式与所有 ASP.NET AJAX 代理相同，只是多了一行用于启用 JSONP 的代码，如下面的代码所示：  
  
```csharp  
var proxy = new JsonpAjaxService.CustomerService();  
proxy.set_enableJsonp(true);  
proxy.GetCustomer(onSuccess, onFail, null);  
```  
  
 网页可以调用 WCF REST 服务，因为该服务使用 <xref:System.ServiceModel.Description.WebScriptEndpoint> 且 `crossDomainScriptAccessEnabled` 设置为 `true`。 这两项配置都在 Web.config 文件在下完成\<system.serviceModel > 元素。  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 ScriptManager 管理与服务的交互并隐藏手动实现 JSONP 访问的复杂性。 当 `crossDomainScriptAccessEnabled` 设置为 `true` 并且操作的响应格式为 JSON 时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 基础结构会检查请求的 URI 以查找回调查询字符串参数，然后使用回调查询字符串参数的值包装 JSON 响应。 在本示例中，网页使用以下 URI 调用 WCF REST 服务。  
  
```  
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0  
```  
  
 因为回调查询字符串参数的值为 `JsonPCallback`，所以 WCF 服务返回如下面的示例所示的 JSONP 响应。  
  
```  
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});  
```  
  
 此 JSONP 响应包含 JSON 格式的客户数据（使用网页请求的回调函数名进行包装）。 ScriptManager 将使用脚本标记执行此回调以完成跨域请求，然后将结果传递给 onSuccess 处理程序，该处理程序会传递给 ASP.NET AJAX 代理的 GetCustomer 操作。  
  
 本示例由两个 ASP.NET Web 应用程序组成：一个应用程序只包含一个 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务，另一个应用程序包含调用该服务的 .aspx 网页。 运行解决方案时，[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 将在不同的端口承载这两个网站，从而创建服务和客户端存在于不同域中的环境。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  打开 JSONP 示例的解决方案。  
  
2.  按 F5 以启动超链接"http://localhost:26648/JSONPClientPage.aspx"在浏览器的 http://localhost:26648/JSONPClientPage.aspx。  
  
3.  请注意，在页面加载后，"名称"和"Address"的文本输入会使用值填充。  这些值是在浏览器完成呈现页面后调用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务所提供的。
