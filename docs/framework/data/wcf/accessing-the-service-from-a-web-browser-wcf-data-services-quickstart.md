---
title: "从 Web 浏览器访问服务（WCF 数据服务快速入门）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49deb2e209127f92a333195e9fcd0d1e1bece7d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="af9ac-102">从 Web 浏览器访问服务（WCF 数据服务快速入门）</span><span class="sxs-lookup"><span data-stu-id="af9ac-102">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>
<span data-ttu-id="af9ac-103">在此任务中，您将从 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 启动 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]，然后可以选择在 Web 浏览器中禁用源读取。</span><span class="sxs-lookup"><span data-stu-id="af9ac-103">In this task, you will start the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="af9ac-104">你将进而检索服务定义文档以及提交给公开的资源的 Web 浏览器通过 HTTP GET 请求以访问数据服务资源。</span><span class="sxs-lookup"><span data-stu-id="af9ac-104">You will then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af9ac-105">默认情况下，[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 自动为计算机上的 `localhost` URI 分配一个端口号。</span><span class="sxs-lookup"><span data-stu-id="af9ac-105">By default, [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="af9ac-106">本任务在 URI 示例中使用端口号 `12345`。</span><span class="sxs-lookup"><span data-stu-id="af9ac-106">This task uses the port number `12345` in the URI examples.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="af9ac-107">如何在中设置特定的端口号你[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]项目，请参阅[创建数据服务](../../../../docs/framework/data/wcf/creating-the-data-service.md)。</span><span class="sxs-lookup"><span data-stu-id="af9ac-107"> how to set a specific port number in your [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] project see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
### <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="af9ac-108">使用 Internet Explorer 请求默认服务文档</span><span class="sxs-lookup"><span data-stu-id="af9ac-108">To request the default service document by using Internet Explorer</span></span>  
  
1.  <span data-ttu-id="af9ac-109">在 Internet Explorer 中，从**工具**菜单上，选择**Internet 选项**，单击**内容**选项卡上，单击**设置**，然后清除**打开源阅读视图**。</span><span class="sxs-lookup"><span data-stu-id="af9ac-109">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>  
  
     <span data-ttu-id="af9ac-110">这可确保禁用源阅读。</span><span class="sxs-lookup"><span data-stu-id="af9ac-110">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="af9ac-111">如果未禁用此功能，则 Web 浏览器会将返回的 AtomPub 编码文档视为 XML 源，而不是显示原始 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="af9ac-111">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="af9ac-112">当浏览器无法将该源作为原始 XML 数据显示时，您应该仍能够以页面源代码的形式查看该源。</span><span class="sxs-lookup"><span data-stu-id="af9ac-112">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>  
  
2.  <span data-ttu-id="af9ac-113">在 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 中，按 F5 键以开始调试应用程序。</span><span class="sxs-lookup"><span data-stu-id="af9ac-113">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], press the F5 key to start debugging the application.</span></span>  
  
3.  <span data-ttu-id="af9ac-114">在本地计算机上打开 Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="af9ac-114">Open a Web browser on the local computer.</span></span> <span data-ttu-id="af9ac-115">在地址栏中，输入以下 URI：</span><span class="sxs-lookup"><span data-stu-id="af9ac-115">In the address bar, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     <span data-ttu-id="af9ac-116">这会返回默认服务文档，其中包含由此数据服务公开的实体集的列表。</span><span class="sxs-lookup"><span data-stu-id="af9ac-116">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>  
  
### <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="af9ac-117">从 Web 浏览器访问实体集资源</span><span class="sxs-lookup"><span data-stu-id="af9ac-117">To access entity set resources from a Web browser</span></span>  
  
1.  <span data-ttu-id="af9ac-118">在 Web 浏览器的地址栏中，输入以下 URI：</span><span class="sxs-lookup"><span data-stu-id="af9ac-118">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers  
    ```  
  
     <span data-ttu-id="af9ac-119">这会返回 Northwind 示例数据库中所有客户的集。</span><span class="sxs-lookup"><span data-stu-id="af9ac-119">This returns a set of all customers in the Northwind sample database.</span></span>  
  
2.  <span data-ttu-id="af9ac-120">在 Web 浏览器的地址栏中，输入以下 URI：</span><span class="sxs-lookup"><span data-stu-id="af9ac-120">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')  
    ```  
  
     <span data-ttu-id="af9ac-121">这会返回特定客户 `ALFKI` 的实体实例。</span><span class="sxs-lookup"><span data-stu-id="af9ac-121">This returns an entity instance for the specific customer, `ALFKI`.</span></span>  
  
3.  <span data-ttu-id="af9ac-122">在 Web 浏览器的地址栏中，输入以下 URI：</span><span class="sxs-lookup"><span data-stu-id="af9ac-122">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders  
    ```  
  
     <span data-ttu-id="af9ac-123">这会遍历客户与订单之间的关系，以返回特定客户 `ALFKI` 的所有订单的集。</span><span class="sxs-lookup"><span data-stu-id="af9ac-123">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>  
  
4.  <span data-ttu-id="af9ac-124">在 Web 浏览器的地址栏中，输入以下 URI：</span><span class="sxs-lookup"><span data-stu-id="af9ac-124">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643  
    ```  
  
     <span data-ttu-id="af9ac-125">这会筛选属于特定客户 `ALFKI` 的订单，以便只根据提供的 `OrderID` 值返回特定订单。</span><span class="sxs-lookup"><span data-stu-id="af9ac-125">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="af9ac-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="af9ac-126">Next Steps</span></span>  
 <span data-ttu-id="af9ac-127">您已成功从 Web 浏览器访问 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]，浏览器会向指定资源发出 HTTP GET 请求。</span><span class="sxs-lookup"><span data-stu-id="af9ac-127">You have successfully accessed the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="af9ac-128">使用 Web 浏览器，可以轻松试验请求的寻址语法并查看结果。</span><span class="sxs-lookup"><span data-stu-id="af9ac-128">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="af9ac-129">不过，通常情况下并不会通过此方式访问生产数据服务。</span><span class="sxs-lookup"><span data-stu-id="af9ac-129">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="af9ac-130">通常，应用程序会通过应用程序代码或脚本语言与数据服务进行交互。</span><span class="sxs-lookup"><span data-stu-id="af9ac-130">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="af9ac-131">接下来，您将创建一个客户端应用程序，该应用程序使用客户端库访问数据服务资源，就像它们是公共语言运行时 (CLR) 对象一样：</span><span class="sxs-lookup"><span data-stu-id="af9ac-131">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>  
  
 [<span data-ttu-id="af9ac-132">创建.NET Framework 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="af9ac-132">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a><span data-ttu-id="af9ac-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af9ac-133">See Also</span></span>  
 [<span data-ttu-id="af9ac-134">访问数据服务资源</span><span class="sxs-lookup"><span data-stu-id="af9ac-134">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
