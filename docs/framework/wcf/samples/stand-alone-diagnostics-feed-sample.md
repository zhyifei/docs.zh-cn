---
title: 独立诊断源示例
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: 730cf011208ea1b57929fff4a1953fd3a935335c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807754"
---
# <a name="stand-alone-diagnostics-feed-sample"></a><span data-ttu-id="f3a4e-102">独立诊断源示例</span><span class="sxs-lookup"><span data-stu-id="f3a4e-102">Stand-Alone Diagnostics Feed Sample</span></span>
<span data-ttu-id="f3a4e-103">此示例演示如何创建 RSS/Atom 联合使用 Windows Communication Foundation (WCF) 源。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-103">This sample demonstrates how to create an RSS/Atom feed for syndication with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="f3a4e-104">它是一个基本的"Hello World"程序显示的对象模型的基础知识以及如何在 Windows Communication Foundation (WCF) 服务上进行设置。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-104">It is a basic "Hello World" program that shows the basics of the object model and how to set it up on a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="f3a4e-105">WCF 联合源建模为特殊的数据类型返回的服务操作<xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-105">WCF models syndication feeds as service operations that return a special data type, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="f3a4e-106"><xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> 的实例可以将源序列化为 RSS 2.0 和 Atom 1.0 格式。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-106">Instances of <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> can serialize a feed into both the RSS 2.0 and Atom 1.0 formats.</span></span> <span data-ttu-id="f3a4e-107">下面的示例代码演示所使用的协定。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-107">The following sample code shows the contract used.</span></span>  
  
```  
[ServiceContract(Namespace = "")]  
    interface IDiagnosticsService  
    {  
        [OperationContract]  
        //The [WebGet] attribute controls how WCF dispatches  
        //HTTP requests to service operations based on a URI suffix  
        //(the part of the request URI after the endpoint address)  
        //using the HTTP GET method. The UriTemplate specifies a relative  
        //path of 'feed', and specifies that the format is  
        //supplied using a query string.   
        [WebGet(UriTemplate="feed?format={format}")]  
        [ServiceKnownType(typeof(Atom10FeedFormatter))]  
        [ServiceKnownType(typeof(Rss20FeedFormatter))]  
        SyndicationFeedFormatter GetProcesses(string format);  
    }  
```  
  
 <span data-ttu-id="f3a4e-108">`GetProcesses`操作进行批注<xref:System.ServiceModel.Web.WebGetAttribute>属性，它使你能够控制如何 WCF 发出 HTTP GET 请求服务操作并指定所发送的消息格式。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-108">The `GetProcesses` operation is annotated with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute that enables you to control how WCF dispatches HTTP GET requests to service operations and specify the format of the messages sent.</span></span>  
  
 <span data-ttu-id="f3a4e-109">与 WCF 服务，联合源可以是自承载于任何托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-109">Like any WCF service, syndication feeds can be self hosted in any managed application.</span></span> <span data-ttu-id="f3a4e-110">联合服务需要使用特定绑定 (<xref:System.ServiceModel.WebHttpBinding>) 和特定终结点行为 (<xref:System.ServiceModel.Description.WebHttpBehavior>) 才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-110">Syndication services require a specific binding (the <xref:System.ServiceModel.WebHttpBinding>) and a specific endpoint behavior (the <xref:System.ServiceModel.Description.WebHttpBehavior>) to function correctly.</span></span> <span data-ttu-id="f3a4e-111">新的 <xref:System.ServiceModel.Web.WebServiceHost> 类提供了一个方便的 API，用于在不使用特定配置的情况下创建此类终结点。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-111">The new <xref:System.ServiceModel.Web.WebServiceHost> class provides a convenient API for creating such endpoints without specific configuration.</span></span>  
  
```  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 <span data-ttu-id="f3a4e-112">或者，可在 IIS 承载的 .svc 文件中使用 <xref:System.ServiceModel.Activation.WebServiceHostFactory> 来提供等效的功能（此技术未在此示例代码中演示）。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-112">Alternatively, you can use <xref:System.ServiceModel.Activation.WebServiceHostFactory> from within an IIS-hosted .svc file to provide equivalent functionality (this technique is not demonstrated in this sample code).</span></span>  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 <span data-ttu-id="f3a4e-113">由于此服务使用标准 HTTP GET 接收请求，因此可以使用任何识别 RSS 或 ATOM 的客户端来访问此服务。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-113">Because this service receives requests using the standard HTTP GET, you can use any RSS or ATOM-aware client to access the service.</span></span> <span data-ttu-id="f3a4e-114">例如，你可以通过导航到查看此服务的输出的http://localhost:8000/diagnostics/feed/?format=atom或http://localhost:8000/diagnostics/feed/?format=rss如 Internet Explorer 7 识别 RSS 的浏览器中。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-114">For example, you can view the output of this service by navigating to http://localhost:8000/diagnostics/feed/?format=atom or http://localhost:8000/diagnostics/feed/?format=rss in an RSS-aware browser such as Internet Explorer 7.</span></span>  
  
 <span data-ttu-id="f3a4e-115">你还可以使用[如何 WCF 联合对象模型映射到 Atom 和 RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)读取联合的数据并处理它使用命令性代码。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-115">You can also use the [How the WCF Syndication Object Model Maps to Atom and RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) to read syndicated data and process it using imperative code.</span></span>  
  
```  
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",  
new XmlReaderSettings()  
{  
//MaxCharactersInDocument can be used to control the maximum amount of data   
//read from the reader and helps prevent OutOfMemoryException  
MaxCharactersInDocument = 1024 * 64  
} );  
  
SyndicationFeed feed = SyndicationFeed.Load( reader );  
  
foreach (SyndicationItem i in feed.Items)  
{  
        XmlSyndicationContent content = i.Content as XmlSyndicationContent;  
        ProcessData pd = content.ReadContent<ProcessData>();  
  
        Console.WriteLine(i.Title.Text);  
        Console.WriteLine(pd.ToString());  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f3a4e-116">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="f3a4e-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f3a4e-117">确保你有针对 HTTP 和 HTTPS 的计算机上的正确的地址注册权限中的说明设置中所述[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-117">Ensure that you have the right address registration permission for HTTP and HTTPS on the computer as explained in the set up instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="f3a4e-118">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-118">Build the solution.</span></span>  
  
3.  <span data-ttu-id="f3a4e-119">运行控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-119">Run the console application.</span></span>  
  
4.  <span data-ttu-id="f3a4e-120">在控制台应用程序运行时，导航到http://localhost:8000/diagnostics/feed/?format=atom或http://localhost:8000/diagnostics/feed/?format=rss使用识别 RSS 的浏览器。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-120">While the console application is running, navigate to http://localhost:8000/diagnostics/feed/?format=atom or http://localhost:8000/diagnostics/feed/?format=rss using an RSS-aware browser.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f3a4e-121">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f3a4e-122">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="f3a4e-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f3a4e-123">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="f3a4e-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f3a4e-124">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="f3a4e-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a><span data-ttu-id="f3a4e-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3a4e-125">See Also</span></span>  
 [<span data-ttu-id="f3a4e-126">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="f3a4e-126">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="f3a4e-127">WCF 联合</span><span class="sxs-lookup"><span data-stu-id="f3a4e-127">WCF Syndication</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
