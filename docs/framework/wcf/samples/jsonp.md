---
title: JSONP
ms.date: 03/30/2017
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
ms.openlocfilehash: bd5d9afcfa35e598191db1d125418686f5dd0af1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510353"
---
# <a name="jsonp"></a><span data-ttu-id="0d22d-102">JSONP</span><span class="sxs-lookup"><span data-stu-id="0d22d-102">JSONP</span></span>
<span data-ttu-id="0d22d-103">本示例演示在 WCF REST 服务中如何支持 JSON with Padding (JSONP)。</span><span class="sxs-lookup"><span data-stu-id="0d22d-103">This sample demonstrates how to support JSON with Padding (JSONP) in WCF REST services.</span></span> <span data-ttu-id="0d22d-104">JSONP 是通过在当前文档中生成脚本标记来调用跨域脚本时使用的约定。</span><span class="sxs-lookup"><span data-stu-id="0d22d-104">JSONP is a convention used to invoke cross-domain scripts by generating script tags in the current document.</span></span> <span data-ttu-id="0d22d-105">结果在指定的回调函数中返回。</span><span class="sxs-lookup"><span data-stu-id="0d22d-105">The result is returned in a specified callback function.</span></span> <span data-ttu-id="0d22d-106">JSONP 基于如思想`<script src="http://..." >`可以从任何域评估脚本，而这些标记检索的脚本评估在其中可能已定义其他函数的范围。</span><span class="sxs-lookup"><span data-stu-id="0d22d-106">JSONP is based on the idea that tags such as `<script src="http://..." >` can evaluate scripts from any domain and the script retrieved by those tags is evaluated within a scope in which other functions may already be defined.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="0d22d-107">演示</span><span class="sxs-lookup"><span data-stu-id="0d22d-107">Demonstrates</span></span>  
 <span data-ttu-id="0d22d-108">使用 JSONP 进行跨域脚本编写。</span><span class="sxs-lookup"><span data-stu-id="0d22d-108">Cross-domain scripting with JSONP.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="0d22d-109">讨论</span><span class="sxs-lookup"><span data-stu-id="0d22d-109">Discussion</span></span>  
 <span data-ttu-id="0d22d-110">本示例包含一个网页，该网页在页面呈现在浏览器中后动态添加脚本块。</span><span class="sxs-lookup"><span data-stu-id="0d22d-110">The sample includes a Web page that dynamically adds a script block after the page has been rendered in the browser.</span></span> <span data-ttu-id="0d22d-111">此脚本块调用一个 WCF REST 服务，该服务有一个 `GetCustomer` 操作。</span><span class="sxs-lookup"><span data-stu-id="0d22d-111">This script block calls a WCF REST service that has a single operation, `GetCustomer`.</span></span> <span data-ttu-id="0d22d-112">WCF REST 服务返回包装在回调函数名内的客户名称和地址。</span><span class="sxs-lookup"><span data-stu-id="0d22d-112">The WCF REST service returns a customer’s name and address wrapped in a callback function name.</span></span> <span data-ttu-id="0d22d-113">当 WCF REST 服务响应时，会使用客户数据调用网页上的回调函数，该回调函数会在网页上显示数据。</span><span class="sxs-lookup"><span data-stu-id="0d22d-113">When the WCF REST service responds, the callback function on the Web page is invoked with the customer data and the callback function displays the data on the Web page.</span></span> <span data-ttu-id="0d22d-114">脚本标记的注入和回调函数的执行由 ASP.NET AJAX ScriptManager 控件自动处理。</span><span class="sxs-lookup"><span data-stu-id="0d22d-114">The injection of the script tag and the execution of the callback function is automatically handled by the ASP.NET AJAX ScriptManager control.</span></span> <span data-ttu-id="0d22d-115">使用模式与所有 ASP.NET AJAX 代理相同，只是多了一行用于启用 JSONP 的代码，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="0d22d-115">The usage pattern is the same as with all ASP.NET AJAX proxies, with the addition of one line to enable JSONP, as shown in the following code:</span></span>  
  
```csharp  
var proxy = new JsonpAjaxService.CustomerService();  
proxy.set_enableJsonp(true);  
proxy.GetCustomer(onSuccess, onFail, null);  
```  
  
 <span data-ttu-id="0d22d-116">网页可以调用 WCF REST 服务，因为该服务使用 <xref:System.ServiceModel.Description.WebScriptEndpoint> 且 `crossDomainScriptAccessEnabled` 设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0d22d-116">The Web page can call the WCF REST service because the service is using the <xref:System.ServiceModel.Description.WebScriptEndpoint> with `crossDomainScriptAccessEnabled` set to `true`.</span></span> <span data-ttu-id="0d22d-117">这两个配置都在下的 Web.config 文件中完成\<system.serviceModel > 元素。</span><span class="sxs-lookup"><span data-stu-id="0d22d-117">Both of these configurations are done in the Web.config file under the \<system.serviceModel> element.</span></span>  
  
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
  
 <span data-ttu-id="0d22d-118">ScriptManager 管理与服务的交互并隐藏手动实现 JSONP 访问的复杂性。</span><span class="sxs-lookup"><span data-stu-id="0d22d-118">ScriptManager manages the interaction with the service and hides away the complexity of manually implementing JSONP access.</span></span> <span data-ttu-id="0d22d-119">当`crossDomainScriptAccessEnabled`设置为`true`和操作的响应格式是 JSON，WCF 基础结构会检查回调查询字符串参数的请求的 URI 和包装 JSON 响应的回调查询字符串值参数。</span><span class="sxs-lookup"><span data-stu-id="0d22d-119">When `crossDomainScriptAccessEnabled` is set to `true` and the response format for an operation is JSON, the WCF infrastructure inspects the URI of the request for a callback query string parameter and wraps the JSON response with the value of the callback query string parameter.</span></span> <span data-ttu-id="0d22d-120">在本示例中，网页使用以下 URI 调用 WCF REST 服务。</span><span class="sxs-lookup"><span data-stu-id="0d22d-120">In the sample, the Web page calls the WCF REST service with the following URI.</span></span>  
  
```  
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0  
```  
  
 <span data-ttu-id="0d22d-121">因为回调查询字符串参数的值为 `JsonPCallback`，所以 WCF 服务返回如下面的示例所示的 JSONP 响应。</span><span class="sxs-lookup"><span data-stu-id="0d22d-121">Because the callback query string parameter has a value of `JsonPCallback`, the WCF service returns a JSONP response shown in the following example.</span></span>  
  
```  
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});  
```  
  
 <span data-ttu-id="0d22d-122">此 JSONP 响应包含 JSON 格式的客户数据（使用网页请求的回调函数名进行包装）。</span><span class="sxs-lookup"><span data-stu-id="0d22d-122">This JSONP response includes the customer data formatted as JSON, wrapped with the callback function name that the Web page requested.</span></span> <span data-ttu-id="0d22d-123">ScriptManager 将使用脚本标记执行此回调以完成跨域请求，然后将结果传递给 onSuccess 处理程序，该处理程序会传递给 ASP.NET AJAX 代理的 GetCustomer 操作。</span><span class="sxs-lookup"><span data-stu-id="0d22d-123">ScriptManager will execute this callback using a script tag to accomplish the cross-domain request, and then pass the result to the onSuccess handler that was passed to the GetCustomer operation of the ASP.NET AJAX proxy.</span></span>  
  
 <span data-ttu-id="0d22d-124">本示例由两个 ASP.NET web 应用程序组成： 一个包含仅的 WCF 服务，另一个包含调用该服务的.aspx 网页。</span><span class="sxs-lookup"><span data-stu-id="0d22d-124">The sample consists of two ASP.NET web applications: one contains just a WCF service, and another one contains the .aspx webpage, which calls the service.</span></span> <span data-ttu-id="0d22d-125">运行解决方案时，[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 将在不同的端口承载这两个网站，从而创建服务和客户端存在于不同域中的环境。</span><span class="sxs-lookup"><span data-stu-id="0d22d-125">When running the solution, [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] will host the two websites on different ports, which creates an environment where the service and client live on different domains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0d22d-126">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="0d22d-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0d22d-127">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="0d22d-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0d22d-128">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="0d22d-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0d22d-129">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="0d22d-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="0d22d-130">运行示例</span><span class="sxs-lookup"><span data-stu-id="0d22d-130">To run the sample</span></span>  
  
1.  <span data-ttu-id="0d22d-131">打开 JSONP 示例的解决方案。</span><span class="sxs-lookup"><span data-stu-id="0d22d-131">Open the solution for the JSONP Sample.</span></span>  
  
2.  <span data-ttu-id="0d22d-132">按 F5 启动`http://localhost:26648/JSONPClientPage.aspx`在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="0d22d-132">Press F5 to launch `http://localhost:26648/JSONPClientPage.aspx` in the browser.</span></span>  
  
3.  <span data-ttu-id="0d22d-133">请注意，在页面加载后，"Name"和"Address"的文本输入填充的值。</span><span class="sxs-lookup"><span data-stu-id="0d22d-133">Notice that after the page loads, the text inputs for "Name" and "Address" are populated by values.</span></span>  <span data-ttu-id="0d22d-134">在浏览器完成呈现页面后，从对 WCF 服务的调用并提供这些值。</span><span class="sxs-lookup"><span data-stu-id="0d22d-134">These values were supplied from a call to the WCF service after the browser finished rendering the page.</span></span>
