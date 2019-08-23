---
title: SystemWebRouting 集成示例
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 032be700beaa38ed6c08ed1940aab558b2106591
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964485"
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="ec5b0-102">SystemWebRouting 集成示例</span><span class="sxs-lookup"><span data-stu-id="ec5b0-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="ec5b0-103">此示例演示 <xref:System.Web.Routing> 命名空间中承载层与类的集成。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="ec5b0-104">通过 <xref:System.Web.Routing> 命名空间中的类，应用程序可以使用不直接与物理资源对应的 URL。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="ec5b0-105">使用 Web 路由, 开发人员可以创建 HTTP 的虚拟地址, 然后将其映射回实际的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual WCF services.</span></span> <span data-ttu-id="ec5b0-106">如果必须以不使用物理文件或资源的方式承载 WCF 服务，或者必须使用不包含 .html 或 .aspx 这类文件的 URL 访问服务时，这会十分有用。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="ec5b0-107">此示例演示如何利用 <xref:System.Web.Routing.RouteTable> 类创建映射到 global.asax 中定义的运行服务的虚拟 URI。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> 

> [!NOTE]
> <span data-ttu-id="ec5b0-108"><xref:System.Web.Routing> 命名空间中的类仅适用于 HTTP 上承载的服务。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="ec5b0-109">此示例使用 WCF 创建两个 rss 源: 一个`movies`源和一个`channels`源。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="ec5b0-110">用于激活服务的 url 不包含扩展, 并且是从`Application_Start` <xref:System.Web.HttpApplication>类派生的`Global`类的方法中注册的。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec5b0-111">此示例仅适用于 Internet Information Services (IIS) 7.0 及更高版本, 因为 IIS 6.0 使用不同的方法来支持无扩展的 Url。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="ec5b0-112">下载此示例</span><span class="sxs-lookup"><span data-stu-id="ec5b0-112">To download this sample</span></span>
  
<span data-ttu-id="ec5b0-113">此示例可能已安装在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="ec5b0-114">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="ec5b0-114">Check for the following (default) directory before continuing.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 <span data-ttu-id="ec5b0-115">如果此目录不存在, 请参阅[.NET Framework 4 的 Windows Communication Foundation (wcf) 和 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)以下载所有 Windows Communication Foundation (wcf) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ec5b0-116">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="ec5b0-116">This sample is located in the following directory.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ec5b0-117">使用此示例</span><span class="sxs-lookup"><span data-stu-id="ec5b0-117">To use this sample</span></span>  
  
1. <span data-ttu-id="ec5b0-118">使用 Visual Studio 打开 WebRoutingIntegration 文件。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="ec5b0-119">若要运行解决方案并启动 Web 开发服务器，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="ec5b0-120">出现该示例的目录列表。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="ec5b0-121">请注意，不存在具有 .svc 文件扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-121">Note that there are no files with an .svc file extension.</span></span>  
  
3. <span data-ttu-id="ec5b0-122">在地址栏中, 将`movies`添加到 URL, 使其读取`http://localhost:[port]/movies`并按 enter。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-122">In the address bar, add `movies` to the URL, so that it reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="ec5b0-123">电影源显示在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-123">The movies feed appears in the browser.</span></span>  
  
4. <span data-ttu-id="ec5b0-124">在地址栏中, 将`channels`添加到 URL, 以便读取`http://localhost:[port]/channels`并按 enter。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-124">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="ec5b0-125">通道源显示在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-125">The channels feed appears in the browser.</span></span>  
  
5. <span data-ttu-id="ec5b0-126">按 Alt+F4 关闭 Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="ec5b0-127">如果尚未退出开发服务器, 请右键单击通知区域图标, 然后选择 "**停止**"。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="ec5b0-128">在 IIS 中承载时使用此示例</span><span class="sxs-lookup"><span data-stu-id="ec5b0-128">To use this sample when hosted in IIS</span></span>  
  
1. <span data-ttu-id="ec5b0-129">使用 Visual Studio 打开 WebRoutingIntegration 文件。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="ec5b0-130">按 Ctrl+Shift+B 生成项目。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="ec5b0-131">在 Internet 信息服务 (IIS) 管理器中创建 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1. <span data-ttu-id="ec5b0-132">在 IIS 管理器中, 右键单击 "**默认**网站", 然后选择 "**添加应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2. <span data-ttu-id="ec5b0-133">对于 "**别名**", 键入`WebRoutingIntegration`。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3. <span data-ttu-id="ec5b0-134">对于 "**物理路径**", 选择项目中的服务文件夹。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4. <span data-ttu-id="ec5b0-135">按“确定”。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-135">Press **OK**.</span></span>  
  
4. <span data-ttu-id="ec5b0-136">启动应用程序, 方法是右键单击 Web 应用程序并选择 "**管理应用程序**", 然后单击 "**浏览**"。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5. <span data-ttu-id="ec5b0-137">在地址栏中, 将`movies`添加到 URL, 以便读取`http://localhost:[port]/movies`并按 enter。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-137">In the address bar, add `movies` to the URL, so that is reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="ec5b0-138">电影源显示在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-138">The movies feed appears in the browser.</span></span>  
  
6. <span data-ttu-id="ec5b0-139">在地址栏中, 将`channels`添加到 URL, 以便读取`http://localhost:[port]/channels`并按 enter。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-139">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="ec5b0-140">通道源显示在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-140">The channels feed appears in the browser.</span></span>  
  
7. <span data-ttu-id="ec5b0-141">按 Alt+F4 关闭 Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="ec5b0-142">此示例演示可以在承载层中使用 <xref:System.Web.Routing> 命名空间中的类进行编写，以便对 HTTP 上承载的服务的请求进行路由。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec5b0-143">如果默认应用程序池版本设置为版本[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 2, 则必须将其更新为。</span><span class="sxs-lookup"><span data-stu-id="ec5b0-143">You must update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec5b0-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec5b0-144">See also</span></span>

- [<span data-ttu-id="ec5b0-145">AppFabric 宿主和持久性示例</span><span class="sxs-lookup"><span data-stu-id="ec5b0-145">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
