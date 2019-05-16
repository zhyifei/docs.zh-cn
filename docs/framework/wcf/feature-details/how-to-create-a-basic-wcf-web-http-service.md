---
title: 如何：创建基本 WCF Web HTTP 服务
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 877662d3-d372-4e08-b417-51f66a0095cd
ms.openlocfilehash: d2d05e0c3bb24c44bf78dc41074b8759270cf49b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636516"
---
# <a name="how-to-create-a-basic-wcf-web-http-service"></a><span data-ttu-id="24424-102">如何：创建基本 WCF Web HTTP 服务</span><span class="sxs-lookup"><span data-stu-id="24424-102">How to: Create a Basic WCF Web HTTP Service</span></span>

<span data-ttu-id="24424-103">Windows Communication Foundation (WCF) 可以创建公开 Web 终结点的服务。</span><span class="sxs-lookup"><span data-stu-id="24424-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a Web endpoint.</span></span> <span data-ttu-id="24424-104">Web 终结点通过 XML 或 JSON 发送数据，没有 SOAP 信封。</span><span class="sxs-lookup"><span data-stu-id="24424-104">Web endpoints send data by XML or JSON, there is no SOAP envelope.</span></span> <span data-ttu-id="24424-105">本主题演示如何公开这类终结点。</span><span class="sxs-lookup"><span data-stu-id="24424-105">This topic demonstrates how to expose such an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="24424-106">确保 Web 终结点安全的唯一方式是使用传输安全通过 HTTPS 将其公开。</span><span class="sxs-lookup"><span data-stu-id="24424-106">The only way to secure a Web endpoint is to expose it through HTTPS, using transport security.</span></span> <span data-ttu-id="24424-107">使用基于消息的安全性时，通常将安全信息放置在 SOAP 标头中，原因是发送到非 SOAP 终结点的信息不包含 SOAP 信封，没有地方放置安全信息，因而必须依赖于传输安全性。</span><span class="sxs-lookup"><span data-stu-id="24424-107">When using message-based security, security information is usually placed in SOAP headers and because the messages sent to non-SOAP endpoints contain no SOAP envelope, there is nowhere to place the security information and you must rely on transport security.</span></span>

## <a name="to-create-a-web-endpoint"></a><span data-ttu-id="24424-108">创建 Web 终结点</span><span class="sxs-lookup"><span data-stu-id="24424-108">To create a Web endpoint</span></span>

1. <span data-ttu-id="24424-109">使用以 <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> 和 <xref:System.ServiceModel.Web.WebGetAttribute> 属性标记的接口来定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="24424-109">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes.</span></span>

     [!code-csharp[htBasicService#0](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#0)]
     [!code-vb[htBasicService#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="24424-110">默认情况下，<xref:System.ServiceModel.Web.WebInvokeAttribute> 将 POST 调用映射到操作。</span><span class="sxs-lookup"><span data-stu-id="24424-110">By default, <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="24424-111">但是，可以通过指定“method=”参数指定要映射到操作的 HTTP 方法（例如，HEAD、PUT 或 DELETE）。</span><span class="sxs-lookup"><span data-stu-id="24424-111">You can, however, specify the HTTP method (for example, HEAD, PUT, or DELETE) to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="24424-112"><xref:System.ServiceModel.Web.WebGetAttribute> 不具有“method=”参数，仅将 GET 调用映射到服务操作。</span><span class="sxs-lookup"><span data-stu-id="24424-112"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="24424-113">实现服务协定。</span><span class="sxs-lookup"><span data-stu-id="24424-113">Implement the service contract.</span></span>

     [!code-csharp[htBasicService#1](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#1)]
     [!code-vb[htBasicService#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="24424-114">承载服务</span><span class="sxs-lookup"><span data-stu-id="24424-114">To host the service</span></span>

1. <span data-ttu-id="24424-115">创建 <xref:System.ServiceModel.Web.WebServiceHost> 对象。</span><span class="sxs-lookup"><span data-stu-id="24424-115">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>

     [!code-csharp[htBasicService#2](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#2)]
     [!code-vb[htBasicService#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#2)]

2. <span data-ttu-id="24424-116">添加一个带有 <xref:System.ServiceModel.Description.ServiceEndpoint> 的 <xref:System.ServiceModel.Description.WebHttpBehavior>。</span><span class="sxs-lookup"><span data-stu-id="24424-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>

     [!code-csharp[htBasicService#3](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#3)]
     [!code-vb[htBasicService#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#3)]

    > [!NOTE]
    > <span data-ttu-id="24424-117">如果不添加终结点，则 <xref:System.ServiceModel.Web.WebServiceHost> 自动创建默认终结点。</span><span class="sxs-lookup"><span data-stu-id="24424-117">If you do not add an endpoint, <xref:System.ServiceModel.Web.WebServiceHost> automatically creates a default endpoint.</span></span> <span data-ttu-id="24424-118"><xref:System.ServiceModel.Web.WebServiceHost> 还添加 <xref:System.ServiceModel.Description.WebHttpBehavior> 并禁用 HTTP 帮助页和 Web 服务描述语言 (WSDL) GET 功能，因此元数据终结点不会妨碍默认的 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="24424-118"><xref:System.ServiceModel.Web.WebServiceHost> also adds <xref:System.ServiceModel.Description.WebHttpBehavior> and disables the HTTP Help page and the Web Services Description Language (WSDL) GET functionality so the metadata endpoint does not interfere with the default HTTP endpoint.</span></span>
    >
    >  <span data-ttu-id="24424-119">当尝试调用终结点上的操作时，添加 URL 为 "" 的非 SOAP 终结点会导致意外行为。</span><span class="sxs-lookup"><span data-stu-id="24424-119">Adding a non-SOAP endpoint with a URL of "" causes unexpected behavior when an attempt is made to call an operation on the endpoint.</span></span> <span data-ttu-id="24424-120">这样做的原因是终结点的 URI 是用于帮助页面 （当浏览到 WCF 服务的基址时显示的页面） 的 URI 相同的侦听。</span><span class="sxs-lookup"><span data-stu-id="24424-120">The reason for this is the listen URI of the endpoint is the same as the URI for the help page (the page that is displayed when you browse to the base address of a WCF service).</span></span>

     <span data-ttu-id="24424-121">要防止此类情况发生，可以执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="24424-121">You can do one of the following actions to prevent this from happening:</span></span>

    - <span data-ttu-id="24424-122">总是为非 SOAP 终结点指定非空白 URI。</span><span class="sxs-lookup"><span data-stu-id="24424-122">Always specify a non-blank URI for a non-SOAP endpoint.</span></span>

    - <span data-ttu-id="24424-123">关闭帮助页。</span><span class="sxs-lookup"><span data-stu-id="24424-123">Turn off the help page.</span></span> <span data-ttu-id="24424-124">这可以通过以下代码：</span><span class="sxs-lookup"><span data-stu-id="24424-124">This can be done with the following code:</span></span>

     [!code-csharp[htBasicService#4](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#4)]
     [!code-vb[htBasicService#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#4)]

3. <span data-ttu-id="24424-125">打开服务主机并等待用户按 Enter。</span><span class="sxs-lookup"><span data-stu-id="24424-125">Open the service host and wait until the user presses ENTER.</span></span>

     [!code-csharp[htBasicService#5](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#5)]
     [!code-vb[htBasicService#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#5)]

     <span data-ttu-id="24424-126">此示例演示如何使用控制台应用程序来承载 Web 样式服务。</span><span class="sxs-lookup"><span data-stu-id="24424-126">This sample demonstrates how to host a Web-Style service with a console application.</span></span> <span data-ttu-id="24424-127">还可以在 IIS 内承载这类服务。</span><span class="sxs-lookup"><span data-stu-id="24424-127">You can also host such a service within IIS.</span></span> <span data-ttu-id="24424-128">为此，在 .svc 文件中指定 <xref:System.ServiceModel.Activation.WebServiceHostFactory> 类，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="24424-128">To do this, specify the <xref:System.ServiceModel.Activation.WebServiceHostFactory> class in a .svc file as the following code demonstrates.</span></span>

    ```
    <%ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Samples.Service"
        Factory=System.ServiceModel.Activation.WebServiceHostFactory%>
    ```

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="24424-129">在 Internet Explorer 中调用映射到 GET 的服务操作</span><span class="sxs-lookup"><span data-stu-id="24424-129">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="24424-130">打开 Internet Explorer 并键入"`http://localhost:8000/EchoWithGet?s=Hello, world!`"然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="24424-130">Open Internet Explorer and type "`http://localhost:8000/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="24424-131">URL 包含服务的基址 (`http://localhost:8000/`)，该终结点的相对地址 ("")，服务操作调用 ("EchoWithGet") 和问号后跟一系列由与号分隔的命名参数 (&)。</span><span class="sxs-lookup"><span data-stu-id="24424-131">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-in-code"></a><span data-ttu-id="24424-132">在代码中调用服务操作</span><span class="sxs-lookup"><span data-stu-id="24424-132">To call service operations in code</span></span>

1. <span data-ttu-id="24424-133">创建 <xref:System.ServiceModel.ChannelFactory%601> 块内的 `using` 的实例。</span><span class="sxs-lookup"><span data-stu-id="24424-133">Create an instance of <xref:System.ServiceModel.ChannelFactory%601> within a `using` block.</span></span>

     [!code-csharp[htBasicService#6](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#6)]
     [!code-vb[htBasicService#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#6)]

2. <span data-ttu-id="24424-134">将 <xref:System.ServiceModel.Description.WebHttpBehavior> 添加到 <xref:System.ServiceModel.ChannelFactory%601> 调用的终结点。</span><span class="sxs-lookup"><span data-stu-id="24424-134">Add <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint the <xref:System.ServiceModel.ChannelFactory%601> calls.</span></span>

     [!code-csharp[htBasicService#7](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#7)]
     [!code-vb[htBasicService#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#7)]

3. <span data-ttu-id="24424-135">创建通道并调用服务。</span><span class="sxs-lookup"><span data-stu-id="24424-135">Create the channel and call the service.</span></span>

     [!code-csharp[htBasicService#8](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#8)]
     [!code-vb[htBasicService#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#8)]

4. <span data-ttu-id="24424-136">关闭 <xref:System.ServiceModel.Web.WebServiceHost>。</span><span class="sxs-lookup"><span data-stu-id="24424-136">Close the <xref:System.ServiceModel.Web.WebServiceHost>.</span></span>

     [!code-csharp[htBasicService#9](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#9)]
     [!code-vb[htBasicService#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#9)]

## <a name="example"></a><span data-ttu-id="24424-137">示例</span><span class="sxs-lookup"><span data-stu-id="24424-137">Example</span></span>

<span data-ttu-id="24424-138">下面列出了此示例的完整代码。</span><span class="sxs-lookup"><span data-stu-id="24424-138">The following is the full code listing for this example.</span></span>

[!code-csharp[htBasicService#10](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#10)]
[!code-vb[htBasicService#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#10)]

## <a name="compiling-the-code"></a><span data-ttu-id="24424-139">编译代码</span><span class="sxs-lookup"><span data-stu-id="24424-139">Compiling the code</span></span>

<span data-ttu-id="24424-140">编译 Service.cs 时，请引用 System.ServiceModel.dll 和 System.ServiceModel.Web.dll。</span><span class="sxs-lookup"><span data-stu-id="24424-140">When compiling Service.cs reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="24424-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="24424-141">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="24424-142">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="24424-142">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
