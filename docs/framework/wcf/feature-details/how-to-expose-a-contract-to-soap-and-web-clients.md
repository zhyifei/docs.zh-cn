---
title: 如何：向 SOAP 和 Web 客户端公开协定
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
ms.openlocfilehash: d82c5e3fc33528eadc3c404cca59a3dcf905e0e2
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47396950"
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a><span data-ttu-id="81585-102">如何：向 SOAP 和 Web 客户端公开协定</span><span class="sxs-lookup"><span data-stu-id="81585-102">How to: Expose a Contract to SOAP and Web Clients</span></span>

<span data-ttu-id="81585-103">默认情况下，Windows Communication Foundation (WCF) 使终结点仅供 SOAP 客户端。</span><span class="sxs-lookup"><span data-stu-id="81585-103">By default, Windows Communication Foundation (WCF) makes endpoints available only to SOAP clients.</span></span> <span data-ttu-id="81585-104">在中[如何： 创建基本 WCF Web HTTP 服务](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)，终结点可向非 SOAP 客户端。</span><span class="sxs-lookup"><span data-stu-id="81585-104">In [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), an endpoint is made available to non-SOAP clients.</span></span> <span data-ttu-id="81585-105">有时可能需要使相同的协定可以同时作为 Web 终结点和 SOAP 终结点使用。</span><span class="sxs-lookup"><span data-stu-id="81585-105">There may be times when you want to make the same contract available both ways, as a Web endpoint and as a SOAP endpoint.</span></span> <span data-ttu-id="81585-106">本主题演示了如何实现此目的的示例。</span><span class="sxs-lookup"><span data-stu-id="81585-106">This topic shows an example of how to do this.</span></span>

## <a name="to-define-the-service-contract"></a><span data-ttu-id="81585-107">定义服务协定</span><span class="sxs-lookup"><span data-stu-id="81585-107">To define the service contract</span></span>

1. <span data-ttu-id="81585-108">定义服务协定使用标记的接口<xref:System.ServiceModel.ServiceContractAttribute>，<xref:System.ServiceModel.Web.WebInvokeAttribute>和<xref:System.ServiceModel.Web.WebGetAttribute>属性，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="81585-108">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes, as shown in the following code:</span></span>

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="81585-109">默认情况下，<xref:System.ServiceModel.Web.WebInvokeAttribute> 将 POST 调用映射到操作。</span><span class="sxs-lookup"><span data-stu-id="81585-109">By default <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="81585-110">但是，可以通过指定“method=”参数指定要映射到操作的方法。</span><span class="sxs-lookup"><span data-stu-id="81585-110">You can, however, specify the method to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="81585-111"><xref:System.ServiceModel.Web.WebGetAttribute> 不具有“method=”参数，仅将 GET 调用映射到服务操作。</span><span class="sxs-lookup"><span data-stu-id="81585-111"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="81585-112">实现服务协定，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="81585-112">Implement the service contract, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="81585-113">承载服务</span><span class="sxs-lookup"><span data-stu-id="81585-113">To host the service</span></span>

1. <span data-ttu-id="81585-114">创建<xref:System.ServiceModel.ServiceHost>对象，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="81585-114">Create a <xref:System.ServiceModel.ServiceHost> object, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. <span data-ttu-id="81585-115">添加<xref:System.ServiceModel.Description.ServiceEndpoint>与<xref:System.ServiceModel.BasicHttpBinding>对于 SOAP 终结点，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="81585-115">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.BasicHttpBinding> for the SOAP endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. <span data-ttu-id="81585-116">添加<xref:System.ServiceModel.Description.ServiceEndpoint>与<xref:System.ServiceModel.WebHttpBinding>为非 SOAP 终结点，并添加<xref:System.ServiceModel.Description.WebHttpBehavior>到终结点，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="81585-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.WebHttpBinding> for the non-SOAP endpoint and add the <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. <span data-ttu-id="81585-117">调用`Open()`上<xref:System.ServiceModel.ServiceHost>实例，以打开服务主机，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="81585-117">Call `Open()` on a <xref:System.ServiceModel.ServiceHost> instance to open the service host, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="81585-118">在 Internet Explorer 中调用映射到 GET 的服务操作</span><span class="sxs-lookup"><span data-stu-id="81585-118">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="81585-119">打开 Internet Explorer 并键入"`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`"然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="81585-119">Open Internet Explorer and type "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="81585-120">URL 包含服务的基址 (`http://localhost:8000/`)，该终结点的相对地址 ("")，服务操作调用 ("EchoWithGet") 和问号后跟一系列由与号分隔的命名参数 (&)。</span><span class="sxs-lookup"><span data-stu-id="81585-120">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a><span data-ttu-id="81585-121">使用代码在 Web 终结点上调用服务操作</span><span class="sxs-lookup"><span data-stu-id="81585-121">To call service operations on the Web endpoint in code</span></span>

1. <span data-ttu-id="81585-122">在 <xref:System.ServiceModel.Web.WebChannelFactory%601> 块中创建 `using` 的实例，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="81585-122">Create an instance of <xref:System.ServiceModel.Web.WebChannelFactory%601> within a `using` block, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> <span data-ttu-id="81585-123">将自动在 `Close()` 块末尾处的通道上调用 `using`。</span><span class="sxs-lookup"><span data-stu-id="81585-123">`Close()` is automatically called on the channel at the end of the `using` block.</span></span>

1. <span data-ttu-id="81585-124">创建通道并调用服务，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="81585-124">Create the channel and call the service, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a><span data-ttu-id="81585-125">在 SOAP 终结点上调用服务操作</span><span class="sxs-lookup"><span data-stu-id="81585-125">To call service operations on the SOAP endpoint</span></span>

1. <span data-ttu-id="81585-126">在 <xref:System.ServiceModel.ChannelFactory> 块中创建 `using` 的实例，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="81585-126">Create an instance of <xref:System.ServiceModel.ChannelFactory> within a `using` block, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. <span data-ttu-id="81585-127">创建通道并调用服务，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="81585-127">Create the channel and call the service, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a><span data-ttu-id="81585-128">关闭服务主机</span><span class="sxs-lookup"><span data-stu-id="81585-128">To close the service host</span></span>

1. <span data-ttu-id="81585-129">关闭服务主机，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="81585-129">Close the service host, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a><span data-ttu-id="81585-130">示例</span><span class="sxs-lookup"><span data-stu-id="81585-130">Example</span></span>

<span data-ttu-id="81585-131">下面是本主题中列出的完整代码：</span><span class="sxs-lookup"><span data-stu-id="81585-131">The following is the full code listing for this topic:</span></span>

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a><span data-ttu-id="81585-132">编译代码</span><span class="sxs-lookup"><span data-stu-id="81585-132">Compiling the code</span></span>

 <span data-ttu-id="81585-133">编译 Service.cs 时，请参考 System.ServiceModel.dll 和 System.ServiceModel.Web.dll。</span><span class="sxs-lookup"><span data-stu-id="81585-133">When compiling Service.cs, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="81585-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="81585-134">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="81585-135">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="81585-135">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)