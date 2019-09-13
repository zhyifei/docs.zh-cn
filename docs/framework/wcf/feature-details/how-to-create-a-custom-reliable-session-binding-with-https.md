---
title: 如何：使用 HTTPS 创建自定义可靠会话绑定
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 7f22eeaae39b4d9a83c77c7f3e9db1d7d3f04e8e
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895197"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="0f85e-102">如何：使用 HTTPS 创建自定义可靠会话绑定</span><span class="sxs-lookup"><span data-stu-id="0f85e-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="0f85e-103">本主题演示如何对可靠会话使用安全套接字层 (SSL) 传输安全。</span><span class="sxs-lookup"><span data-stu-id="0f85e-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="0f85e-104">若要通过 HTTPS 使用可靠会话，必须创建使用可靠会话和 HTTPS 传输协议的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="0f85e-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="0f85e-105">可以通过使用代码以强制方式或在配置文件中以声明方式启用可靠会话。</span><span class="sxs-lookup"><span data-stu-id="0f85e-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="0f85e-106">此过程使用客户端和服务配置文件来启用可靠会话和[ **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md)元素。</span><span class="sxs-lookup"><span data-stu-id="0f85e-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="0f85e-107">此过程的关键部分是 **\<端点 >** 配置元素包含一个`bindingConfiguration`属性，该属性引用名为`reliableSessionOverHttps`的自定义绑定配置。</span><span class="sxs-lookup"><span data-stu-id="0f85e-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="0f85e-108">绑定 > 配置元素通过包括 **\<reliableSession >** 和 httpsTransport， [ **\<** ](../../../../docs/framework/misc/binding.md)  **\<来指定是否使用可靠会话和 HTTPS 传输 >** 元素。</span><span class="sxs-lookup"><span data-stu-id="0f85e-108">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="0f85e-109">有关此示例的源副本，请参阅[通过 HTTPS 自定义绑定可靠会话](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md)。</span><span class="sxs-lookup"><span data-stu-id="0f85e-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="0f85e-110">使用 CustomBinding 配置服务，以便将可靠会话与 HTTPS 一起使用</span><span class="sxs-lookup"><span data-stu-id="0f85e-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="0f85e-111">为该类型的服务定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="0f85e-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="0f85e-112">在服务类中实现该服务协定。</span><span class="sxs-lookup"><span data-stu-id="0f85e-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="0f85e-113">请注意，在服务的实现内未指定地址或绑定信息。</span><span class="sxs-lookup"><span data-stu-id="0f85e-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="0f85e-114">无需编写代码即可从配置文件中检索地址或绑定信息。</span><span class="sxs-lookup"><span data-stu-id="0f85e-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="0f85e-115">创建一个*web.config*文件，以便`CalculatorService`使用一个名`reliableSessionOverHttps`为的自定义绑定（使用可靠会话和 HTTPS 传输）为设置终结点。</span><span class="sxs-lookup"><span data-stu-id="0f85e-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="0f85e-116">创建包含以下行的*服务 .svc*文件：</span><span class="sxs-lookup"><span data-stu-id="0f85e-116">Create a *Service.svc* file that contains the line:</span></span>

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. <span data-ttu-id="0f85e-117">将*服务 .svc*文件放在 INTERNET INFORMATION SERVICES （IIS）虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="0f85e-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="0f85e-118">使用 CustomBinding 配置客户端以使用与 HTTPS 的可靠会话</span><span class="sxs-lookup"><span data-stu-id="0f85e-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="0f85e-119">使用[*Svcutil.exe*元数据实用工具（）](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)从命令行生成服务元数据中的代码。</span><span class="sxs-lookup"><span data-stu-id="0f85e-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="0f85e-120">生成的客户端包含`ICalculator`定义客户端实现必须满足的服务协定的接口。</span><span class="sxs-lookup"><span data-stu-id="0f85e-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="0f85e-121">生成的客户端应用程序还包含 `ClientCalculator` 的实现。</span><span class="sxs-lookup"><span data-stu-id="0f85e-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="0f85e-122">请注意，在服务的实现内未指定地址和绑定信息。</span><span class="sxs-lookup"><span data-stu-id="0f85e-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="0f85e-123">不需要编写代码来检索配置文件中的地址和绑定信息。</span><span class="sxs-lookup"><span data-stu-id="0f85e-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="0f85e-124">将名`reliableSessionOverHttps`为的自定义绑定配置为使用 HTTPS 传输和可靠会话。</span><span class="sxs-lookup"><span data-stu-id="0f85e-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="0f85e-125">在应用程序中创建 `ClientCalculator` 的实例，然后调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="0f85e-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="0f85e-126">编译并运行客户端。</span><span class="sxs-lookup"><span data-stu-id="0f85e-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="0f85e-127">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="0f85e-127">.NET Framework security</span></span>

<span data-ttu-id="0f85e-128">由于本示例中使用的证书是用*Makecert*创建的测试证书，因此当你尝试从浏览器访问 HTTPS 地址（例如`https://localhost/servicemodelsamples/service.svc`）时，会出现安全警报。</span><span class="sxs-lookup"><span data-stu-id="0f85e-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f85e-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f85e-129">See also</span></span>

- [<span data-ttu-id="0f85e-130">可靠会话</span><span class="sxs-lookup"><span data-stu-id="0f85e-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
