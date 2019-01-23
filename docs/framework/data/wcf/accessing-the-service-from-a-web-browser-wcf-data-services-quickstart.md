---
title: 从 Web 浏览器访问服务（WCF 数据服务快速入门）
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: 15a74e47774c532e75eca8a60a1af3a3e4f03f58
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591638"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="46c6c-102">从 Web 浏览器访问服务（WCF 数据服务快速入门）</span><span class="sxs-lookup"><span data-stu-id="46c6c-102">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="46c6c-103">这是 WCF 数据服务快速入门的第二个任务。</span><span class="sxs-lookup"><span data-stu-id="46c6c-103">This is the second task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="46c6c-104">在本任务中，可以从 Visual Studio 中启动 WCF 数据服务和 （可选） 禁用 Web 浏览器中的源的阅读。</span><span class="sxs-lookup"><span data-stu-id="46c6c-104">In this task, you start the WCF Data Services from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="46c6c-105">你然后检索服务定义文档，以及通过 Web 浏览器向公开的资源提交 HTTP GET 请求访问数据服务资源。</span><span class="sxs-lookup"><span data-stu-id="46c6c-105">You then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>

> [!NOTE]
> <span data-ttu-id="46c6c-106">默认情况下，Visual Studio 自动为计算机上的 `localhost` URI 分配一个端口号。</span><span class="sxs-lookup"><span data-stu-id="46c6c-106">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="46c6c-107">本任务在 URI 示例中使用端口号 `12345`。</span><span class="sxs-lookup"><span data-stu-id="46c6c-107">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="46c6c-108">有关如何在 Visual Studio 项目中设置特定的端口号的详细信息请参阅[创建数据服务](../../../../docs/framework/data/wcf/creating-the-data-service.md)。</span><span class="sxs-lookup"><span data-stu-id="46c6c-108">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="46c6c-109">使用 Internet Explorer 请求默认服务文档</span><span class="sxs-lookup"><span data-stu-id="46c6c-109">To request the default service document by using Internet Explorer</span></span>

1.  <span data-ttu-id="46c6c-110">在 Internet Explorer 中，从**工具**菜单中，选择**Internet 选项**，单击**内容**选项卡上，单击**设置**，并清除**打开源阅读视图**。</span><span class="sxs-lookup"><span data-stu-id="46c6c-110">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>

     <span data-ttu-id="46c6c-111">这可确保禁用源阅读。</span><span class="sxs-lookup"><span data-stu-id="46c6c-111">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="46c6c-112">如果未禁用此功能，则 Web 浏览器会将返回的 AtomPub 编码文档视为 XML 源，而不是显示原始 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="46c6c-112">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="46c6c-113">当浏览器无法将该源作为原始 XML 数据显示时，你应该仍能够以页面源代码的形式查看该源。</span><span class="sxs-lookup"><span data-stu-id="46c6c-113">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>

2.  <span data-ttu-id="46c6c-114">在 Visual Studio 中，按**F5**键启动调试应用程序。</span><span class="sxs-lookup"><span data-stu-id="46c6c-114">In Visual Studio, press the **F5** key to start debugging the application.</span></span>

3.  <span data-ttu-id="46c6c-115">在本地计算机上打开 Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="46c6c-115">Open a Web browser on the local computer.</span></span> <span data-ttu-id="46c6c-116">在地址栏中，输入以下 URI：</span><span class="sxs-lookup"><span data-stu-id="46c6c-116">In the address bar, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc
    ```

     <span data-ttu-id="46c6c-117">这会返回默认服务文档，其中包含由此数据服务公开的实体集的列表。</span><span class="sxs-lookup"><span data-stu-id="46c6c-117">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>

## <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="46c6c-118">从 Web 浏览器访问实体集资源</span><span class="sxs-lookup"><span data-stu-id="46c6c-118">To access entity set resources from a Web browser</span></span>

1.  <span data-ttu-id="46c6c-119">在 Web 浏览器的地址栏中，输入以下 URI：</span><span class="sxs-lookup"><span data-stu-id="46c6c-119">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers
    ```

     <span data-ttu-id="46c6c-120">这会返回 Northwind 示例数据库中所有客户的集。</span><span class="sxs-lookup"><span data-stu-id="46c6c-120">This returns a set of all customers in the Northwind sample database.</span></span>

2.  <span data-ttu-id="46c6c-121">在 Web 浏览器的地址栏中，输入以下 URI：</span><span class="sxs-lookup"><span data-stu-id="46c6c-121">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     <span data-ttu-id="46c6c-122">这会返回特定客户 `ALFKI` 的实体实例。</span><span class="sxs-lookup"><span data-stu-id="46c6c-122">This returns an entity instance for the specific customer, `ALFKI`.</span></span>

3.  <span data-ttu-id="46c6c-123">在 Web 浏览器的地址栏中，输入以下 URI：</span><span class="sxs-lookup"><span data-stu-id="46c6c-123">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     <span data-ttu-id="46c6c-124">这会遍历客户与订单之间的关系，以返回特定客户 `ALFKI` 的所有订单的集。</span><span class="sxs-lookup"><span data-stu-id="46c6c-124">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>

4.  <span data-ttu-id="46c6c-125">在 Web 浏览器的地址栏中，输入以下 URI：</span><span class="sxs-lookup"><span data-stu-id="46c6c-125">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     <span data-ttu-id="46c6c-126">这会筛选属于特定客户 `ALFKI` 的订单，以便只根据提供的 `OrderID` 值返回特定订单。</span><span class="sxs-lookup"><span data-stu-id="46c6c-126">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>

## <a name="next-steps"></a><span data-ttu-id="46c6c-127">后续步骤</span><span class="sxs-lookup"><span data-stu-id="46c6c-127">Next Steps</span></span>

<span data-ttu-id="46c6c-128">您已成功从 Web 浏览器中，浏览器发出 HTTP GET 请求到指定的资源访问 WCF 数据服务。</span><span class="sxs-lookup"><span data-stu-id="46c6c-128">You have successfully accessed the WCF Data Services from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="46c6c-129">使用 Web 浏览器，可以轻松试验请求的寻址语法并查看结果。</span><span class="sxs-lookup"><span data-stu-id="46c6c-129">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="46c6c-130">不过，通常情况下并不会通过此方式访问生产数据服务。</span><span class="sxs-lookup"><span data-stu-id="46c6c-130">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="46c6c-131">通常，应用程序会通过应用程序代码或脚本语言与数据服务进行交互。</span><span class="sxs-lookup"><span data-stu-id="46c6c-131">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="46c6c-132">接下来，您将创建一个客户端应用程序，该应用程序使用客户端库访问数据服务资源，就像它们是公共语言运行时 (CLR) 对象一样：</span><span class="sxs-lookup"><span data-stu-id="46c6c-132">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="46c6c-133">创建 .NET Framework 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="46c6c-133">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="46c6c-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="46c6c-134">See also</span></span>

- [<span data-ttu-id="46c6c-135">访问数据服务资源</span><span class="sxs-lookup"><span data-stu-id="46c6c-135">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
