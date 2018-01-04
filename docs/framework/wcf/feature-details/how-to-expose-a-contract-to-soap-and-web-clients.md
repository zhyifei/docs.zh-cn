---
title: "如何：向 SOAP 和 Web 客户端公开协定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f13ba797b0c0e5c8b0d1eef271baf62f920f199
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a><span data-ttu-id="d65bf-102">如何：向 SOAP 和 Web 客户端公开协定</span><span class="sxs-lookup"><span data-stu-id="d65bf-102">How to: Expose a Contract to SOAP and Web Clients</span></span>
<span data-ttu-id="d65bf-103">默认情况下，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 使终结点只可用于 SOAP 客户端。</span><span class="sxs-lookup"><span data-stu-id="d65bf-103">By default, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] makes endpoints available only to SOAP clients.</span></span> <span data-ttu-id="d65bf-104">在[如何： 创建基本 WCF Web HTTP 服务](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)，终结点可用于非 SOAP 客户端。</span><span class="sxs-lookup"><span data-stu-id="d65bf-104">In [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), an endpoint is made available to non-SOAP clients.</span></span> <span data-ttu-id="d65bf-105">有时可能需要使相同的协定可以同时作为 Web 终结点和 SOAP 终结点使用。</span><span class="sxs-lookup"><span data-stu-id="d65bf-105">There may be times when you want to make the same contract available both ways, as a Web endpoint and as a SOAP endpoint.</span></span> <span data-ttu-id="d65bf-106">本主题演示了如何实现此目的的示例。</span><span class="sxs-lookup"><span data-stu-id="d65bf-106">This topic shows an example of how to do this.</span></span>  
  
### <a name="to-define-the-service-contract"></a><span data-ttu-id="d65bf-107">定义服务协定</span><span class="sxs-lookup"><span data-stu-id="d65bf-107">To define the service contract</span></span>  
  
1.  <span data-ttu-id="d65bf-108">使用通过 <xref:System.ServiceModel.ServiceContractAttribute>、<xref:System.ServiceModel.Web.WebInvokeAttribute> 和 <xref:System.ServiceModel.Web.WebGetAttribute> 特性进行标记的接口来定义服务协定，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="d65bf-108">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
     [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]  
  
    > [!NOTE]
    >  <span data-ttu-id="d65bf-109">默认情况下，<xref:System.ServiceModel.Web.WebInvokeAttribute> 将 POST 调用映射到操作。</span><span class="sxs-lookup"><span data-stu-id="d65bf-109">By default <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="d65bf-110">但是，可以通过指定“method=”参数指定要映射到操作的方法。</span><span class="sxs-lookup"><span data-stu-id="d65bf-110">You can, however, specify the method to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="d65bf-111"><xref:System.ServiceModel.Web.WebGetAttribute> 不具有“method=”参数，仅将 GET 调用映射到服务操作。</span><span class="sxs-lookup"><span data-stu-id="d65bf-111"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>  
  
2.  <span data-ttu-id="d65bf-112">实现服务协定，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="d65bf-112">Implement the service contract, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="d65bf-113">承载服务</span><span class="sxs-lookup"><span data-stu-id="d65bf-113">To host the service</span></span>  
  
1.  <span data-ttu-id="d65bf-114">创建 <xref:System.ServiceModel.ServiceHost> 对象，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="d65bf-114">Create a <xref:System.ServiceModel.ServiceHost> object, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]  
  
2.  <span data-ttu-id="d65bf-115">添加一个带有针对 SOAP 终结点的 <xref:System.ServiceModel.Description.ServiceEndpoint> 的 <xref:System.ServiceModel.BasicHttpBinding>，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="d65bf-115">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.BasicHttpBinding> for the SOAP endpoint, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]  
  
3.  <span data-ttu-id="d65bf-116">添加一个带有针对非 SOAP 终结点的 <xref:System.ServiceModel.Description.ServiceEndpoint> 的 <xref:System.ServiceModel.WebHttpBinding>，并将 <xref:System.ServiceModel.Description.WebHttpBehavior> 添加到该终结点，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="d65bf-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.WebHttpBinding> for the non-SOAP endpoint and add the <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]  
  
4.  <span data-ttu-id="d65bf-117">在 `Open()` 实例上调用 <xref:System.ServiceModel.ServiceHost> 以打开服务主机，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="d65bf-117">Call `Open()` on a <xref:System.ServiceModel.ServiceHost> instance to open the service host, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]  
  
### <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="d65bf-118">在 Internet Explorer 中调用映射到 GET 的服务操作</span><span class="sxs-lookup"><span data-stu-id="d65bf-118">To call service operations mapped to GET in Internet Explorer</span></span>  
  
1.  <span data-ttu-id="d65bf-119">打开 Internet Explorer 并键入"`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`"，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="d65bf-119">Open Internet Explorer and type "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="d65bf-120">该 URL 包含服务的基址 ("http://localhost:8000/")、终结点的相对地址 ("")、要调用的服务操作 ("EchoWithGet")、一个问号以及其后通过“and”符号 (&) 分隔的命名参数的列表。</span><span class="sxs-lookup"><span data-stu-id="d65bf-120">The URL contains the base address of the service ("http://localhost:8000/"), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>  
  
### <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a><span data-ttu-id="d65bf-121">使用代码在 Web 终结点上调用服务操作</span><span class="sxs-lookup"><span data-stu-id="d65bf-121">To call service operations on the Web endpoint in code</span></span>  
  
1.  <span data-ttu-id="d65bf-122">在 <xref:System.ServiceModel.Web.WebChannelFactory%601> 块中创建 `using` 的实例，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="d65bf-122">Create an instance of <xref:System.ServiceModel.Web.WebChannelFactory%601> within a `using` block, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="d65bf-123">将自动在 `Close()` 块末尾处的通道上调用 `using`。</span><span class="sxs-lookup"><span data-stu-id="d65bf-123">`Close()` is automatically called on the channel at the end of the `using` block.</span></span>  
  
1.  <span data-ttu-id="d65bf-124">创建通道并调用服务，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="d65bf-124">Create the channel and call the service, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]  
  
### <a name="to-call-service-operations-on-the-soap-endpoint"></a><span data-ttu-id="d65bf-125">在 SOAP 终结点上调用服务操作</span><span class="sxs-lookup"><span data-stu-id="d65bf-125">To call service operations on the SOAP endpoint</span></span>  
  
1.  <span data-ttu-id="d65bf-126">在 <xref:System.ServiceModel.ChannelFactory> 块中创建 `using` 的实例，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="d65bf-126">Create an instance of <xref:System.ServiceModel.ChannelFactory> within a `using` block, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
     [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]  
  
2.  <span data-ttu-id="d65bf-127">创建通道并调用服务，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="d65bf-127">Create the channel and call the service, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
     [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]  
  
### <a name="to-close-the-service-host"></a><span data-ttu-id="d65bf-128">关闭服务主机</span><span class="sxs-lookup"><span data-stu-id="d65bf-128">To close the service host</span></span>  
  
1.  <span data-ttu-id="d65bf-129">关闭服务主机，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="d65bf-129">Close the service host, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
     [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="d65bf-130">示例</span><span class="sxs-lookup"><span data-stu-id="d65bf-130">Example</span></span>  
 <span data-ttu-id="d65bf-131">下面列出了此主题的完整代码。</span><span class="sxs-lookup"><span data-stu-id="d65bf-131">The following is the full code listing for this topic.</span></span>  
  
 [!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
 [!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d65bf-132">编译代码</span><span class="sxs-lookup"><span data-stu-id="d65bf-132">Compiling the Code</span></span>  
 <span data-ttu-id="d65bf-133">编译 Service.cs 时，请参考 System.ServiceModel.dll 和 System.ServiceModel.Web.dll。</span><span class="sxs-lookup"><span data-stu-id="d65bf-133">When compiling Service.cs, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d65bf-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d65bf-134">See Also</span></span>  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>  
 <xref:System.ServiceModel.Web.WebInvokeAttribute>  
 <xref:System.ServiceModel.Web.WebServiceHost>  
 <xref:System.ServiceModel.ChannelFactory>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [<span data-ttu-id="d65bf-135">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="d65bf-135">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
