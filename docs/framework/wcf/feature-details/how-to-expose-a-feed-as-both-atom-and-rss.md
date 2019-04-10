---
title: 如何：作为 Atom 和 RSS 公开源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fe374932-67f5-487d-9325-f868812b92e4
ms.openlocfilehash: 17494b00259839be3beb580a516ff017ec3de50e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228401"
---
# <a name="how-to-expose-a-feed-as-both-atom-and-rss"></a><span data-ttu-id="bbbc5-102">如何：作为 Atom 和 RSS 公开源</span><span class="sxs-lookup"><span data-stu-id="bbbc5-102">How to: Expose a Feed as Both Atom and RSS</span></span>
<span data-ttu-id="bbbc5-103">Windows Communication Foundation (WCF) 可以创建公开联合源的服务。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="bbbc5-104">本主题讨论如何使用 Atom 1.0 和 RSS 2.0 创建公开联合源的联合服务。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-104">This topic discusses how to create a syndication service that exposes a syndication feed using both Atom 1.0 and RSS 2.0.</span></span> <span data-ttu-id="bbbc5-105">此服务公开一个可以返回任一联合格式的终结点。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-105">This service exposes one endpoint that can return either syndication format.</span></span> <span data-ttu-id="bbbc5-106">为了简单起见，本示例中使用的服务为自承载服务。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-106">For simplicity the service used in this sample is self hosted.</span></span> <span data-ttu-id="bbbc5-107">在生产环境中，此类型的服务将承载在 IIS 或 WAS 下。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-107">In a production environment a service of this type would be hosted under IIS or WAS.</span></span> <span data-ttu-id="bbbc5-108">有关不同 WCF 托管选项的详细信息，请参阅[Hosting](../../../../docs/framework/wcf/feature-details/hosting.md)。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-108">For more information about the different WCF hosting options, see [Hosting](../../../../docs/framework/wcf/feature-details/hosting.md).</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="bbbc5-109">创建基本联合服务</span><span class="sxs-lookup"><span data-stu-id="bbbc5-109">To create a basic syndication service</span></span>  
  
1.  <span data-ttu-id="bbbc5-110">使用通过 <xref:System.ServiceModel.Web.WebGetAttribute> 属性标记的接口定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-110">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="bbbc5-111">作为联合源公开的每个操作都会返回一个 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> 对象。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-111">Each operation that is exposed as a syndication feed returns a <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> object.</span></span> <span data-ttu-id="bbbc5-112">请注意 <xref:System.ServiceModel.Web.WebGetAttribute> 的参数。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-112">Note the parameters for the <xref:System.ServiceModel.Web.WebGetAttribute>.</span></span> `UriTemplate` <span data-ttu-id="bbbc5-113">指定用来调用此服务操作的 URL。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-113">specifies the URL used to invoke this service operation.</span></span> <span data-ttu-id="bbbc5-114">为此参数字符串包含文本和大括号中的变量 ({*格式*})。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-114">The string for this parameter contains literals and a variable in braces ({*format*}).</span></span> <span data-ttu-id="bbbc5-115">此变量与服务操作的 `format` 参数相对应。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-115">This variable corresponds to the service operation's `format` parameter.</span></span> <span data-ttu-id="bbbc5-116">有关详细信息，请参阅 <xref:System.UriTemplate>。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-116">For more information, see <xref:System.UriTemplate>.</span></span> `BodyStyle` <span data-ttu-id="bbbc5-117">会影响写入此服务操作发送和接收的消息的方式。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-117">affects how the messages that this service operation sends and receives are written.</span></span> <xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> <span data-ttu-id="bbbc5-118">指定发往和来自此服务操作的数据但不包装基础结构定义的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-118">specifies that the data sent to and from this service operation are not wrapped by infrastructure-defined XML elements.</span></span> <span data-ttu-id="bbbc5-119">有关详细信息，请参阅 <xref:System.ServiceModel.Web.WebMessageBodyStyle>。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-119">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle>.</span></span>  
  
     [!code-csharp[htAtomRss#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#0)]
     [!code-vb[htAtomRss#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#0)]  
  
    > [!NOTE]
    >  <span data-ttu-id="bbbc5-120">在此接口中使用 <xref:System.ServiceModel.ServiceKnownTypeAttribute> 以指定服务操作返回的类型。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-120">Use the <xref:System.ServiceModel.ServiceKnownTypeAttribute> to specify the types that are returned by the service operations in this interface.</span></span>  
  
2.  <span data-ttu-id="bbbc5-121">实现服务协定。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-121">Implement the service contract.</span></span>  
  
     [!code-csharp[htAtomRss#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#1)]
     [!code-vb[htAtomRss#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#1)]  
  
3.  <span data-ttu-id="bbbc5-122">创建 <xref:System.ServiceModel.Syndication.SyndicationFeed> 对象，并添加作者、类别和说明。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-122">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htAtomRss#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#2)]
     [!code-vb[htAtomRss#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#2)]  
  
4.  <span data-ttu-id="bbbc5-123">创建若干 <xref:System.ServiceModel.Syndication.SyndicationItem> 对象。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-123">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htAtomRss#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#3)]
     [!code-vb[htAtomRss#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#3)]  
  
5.  <span data-ttu-id="bbbc5-124">向源中添加 <xref:System.ServiceModel.Syndication.SyndicationItem> 对象。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-124">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> objects to the feed.</span></span>  
  
     [!code-csharp[htAtomRss#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#4)]
     [!code-vb[htAtomRss#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#4)]  
  
6.  <span data-ttu-id="bbbc5-125">使用格式参数返回请求的格式。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-125">Use the format parameter to return the requested format.</span></span>  
  
     [!code-csharp[htAtomRss#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#5)]
     [!code-vb[htAtomRss#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="bbbc5-126">承载服务</span><span class="sxs-lookup"><span data-stu-id="bbbc5-126">To host the service</span></span>  
  
1.  <span data-ttu-id="bbbc5-127">创建 <xref:System.ServiceModel.Web.WebServiceHost> 对象。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-127">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span> <span data-ttu-id="bbbc5-128">除非在代码或配置中指定了一个终结点，<xref:System.ServiceModel.Web.WebServiceHost> 类会自动在服务的基地址添加终结点。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-128">The <xref:System.ServiceModel.Web.WebServiceHost> class automatically adds an endpoint at the service's base address unless one is specified in code or configuration.</span></span> <span data-ttu-id="bbbc5-129">在此示例中，不指定任何终结点，因此公开默认终结点。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-129">In this sample, no endpoints are specified so the default endpoint is exposed.</span></span>  
  
     [!code-csharp[htAtomRss#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#6)]
     [!code-vb[htAtomRss#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#6)]  
  
2.  <span data-ttu-id="bbbc5-130">打开服务主机，从服务加载源，显示源，然后等待用户按 Enter。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-130">Open the service host, load the feed from the service, display the feed, and wait for the user to press ENTER.</span></span>  
  
     [!code-csharp[htAtomRss#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#8)]
     [!code-vb[htAtomRss#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="bbbc5-131">使用 HTTP GET 调用 GetBlog</span><span class="sxs-lookup"><span data-stu-id="bbbc5-131">To call GetBlog with an HTTP GET</span></span>  
  
1.  <span data-ttu-id="bbbc5-132">打开 Internet Explorer，键入以下 URL，并按 ENTER: `http://localhost:8000/BlogService/GetBlog`。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-132">Open Internet Explorer, type the following URL, and press ENTER: `http://localhost:8000/BlogService/GetBlog`.</span></span>
  
     <span data-ttu-id="bbbc5-133">URL 包含服务的基址 (`http://localhost:8000/BlogService`)，终结点和要调用的服务操作的相对地址。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-133">The URL contains the base address of the service (`http://localhost:8000/BlogService`), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="bbbc5-134">从代码中调用 GetBlog()</span><span class="sxs-lookup"><span data-stu-id="bbbc5-134">To call GetBlog() from code</span></span>  
  
1.  <span data-ttu-id="bbbc5-135">使用基址和调用的方法创建 <xref:System.Xml.XmlReader>。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-135">Create an <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htAtomRss#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#9)]
     [!code-vb[htAtomRss#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#9)]  
  
2.  <span data-ttu-id="bbbc5-136">调用静态 <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> 方法，同时传入刚刚创建的 <xref:System.Xml.XmlReader>。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-136">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htAtomRss#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#10)]
     [!code-vb[htAtomRss#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#10)]  
  
     <span data-ttu-id="bbbc5-137">这将调用服务操作，并用从服务操作返回的格式化程序填充新的 <xref:System.ServiceModel.Syndication.SyndicationFeed>。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-137">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3.  <span data-ttu-id="bbbc5-138">访问源对象。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-138">Access the feed object.</span></span>  
  
     [!code-csharp[htAtomRss#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#11)]
     [!code-vb[htAtomRss#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="bbbc5-139">示例</span><span class="sxs-lookup"><span data-stu-id="bbbc5-139">Example</span></span>  
 <span data-ttu-id="bbbc5-140">下面列出了此示例的完整代码。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-140">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htAtomRss#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bbbc5-141">编译代码</span><span class="sxs-lookup"><span data-stu-id="bbbc5-141">Compiling the Code</span></span>  
 <span data-ttu-id="bbbc5-142">编译前面的代码时，请引用 System.ServiceModel.dll 和 System.ServiceModel.Web.dll。</span><span class="sxs-lookup"><span data-stu-id="bbbc5-142">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbbc5-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbbc5-143">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
