---
title: 如何：使用 HTTPS 创建自定义可靠会话绑定
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: f39325829cf4b548482a6a570a5aa1fd65e61a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039528"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="22432-102">如何：使用 HTTPS 创建自定义可靠会话绑定</span><span class="sxs-lookup"><span data-stu-id="22432-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="22432-103">本主题演示如何对可靠会话使用安全套接字层 (SSL) 传输安全。</span><span class="sxs-lookup"><span data-stu-id="22432-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="22432-104">若要通过 HTTPS 使用可靠会话，必须创建使用可靠会话和 HTTPS 传输协议的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="22432-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="22432-105">使用代码以强制方式或配置文件中以声明方式启用可靠会话。</span><span class="sxs-lookup"><span data-stu-id="22432-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="22432-106">此过程使用客户端和服务配置文件来启用可靠会话和[  **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md)元素。</span><span class="sxs-lookup"><span data-stu-id="22432-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="22432-107">此过程的关键部分是 **\<终结点 >** 配置元素包含`bindingConfiguration`引用一个名为的自定义绑定配置的属性`reliableSessionOverHttps`。</span><span class="sxs-lookup"><span data-stu-id="22432-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="22432-108">[ **\<绑定 >** ](../../../../docs/framework/misc/binding.md)配置元素将引用此名称来指定通过包括使用可靠会话和 HTTPS 传输 **\<reliableSession >** 并 **\<httpsTransport >** 元素。</span><span class="sxs-lookup"><span data-stu-id="22432-108">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="22432-109">此示例中的源副本，请参阅[自定义绑定可靠会话通过 HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md)。</span><span class="sxs-lookup"><span data-stu-id="22432-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="22432-110">该服务使用 CustomBinding 配置为使用可靠会话与 HTTPS 一起使用</span><span class="sxs-lookup"><span data-stu-id="22432-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="22432-111">为该类型的服务定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="22432-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="22432-112">在服务类中实现该服务协定。</span><span class="sxs-lookup"><span data-stu-id="22432-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="22432-113">请注意，该服务的实现内部未指定地址或绑定信息。</span><span class="sxs-lookup"><span data-stu-id="22432-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="22432-114">您无需编写代码，以便从配置文件中检索的地址或绑定信息。</span><span class="sxs-lookup"><span data-stu-id="22432-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="22432-115">创建*Web.config*文件以配置一个终结点`CalculatorService`与名为的自定义绑定`reliableSessionOverHttps`使用可靠会话和 HTTPS 传输。</span><span class="sxs-lookup"><span data-stu-id="22432-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="22432-116">创建*Service.svc*包含行的文件：</span><span class="sxs-lookup"><span data-stu-id="22432-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. <span data-ttu-id="22432-117">位置*Service.svc* Internet 信息服务 (IIS) 虚拟目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="22432-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="22432-118">客户端使用 CustomBinding 配置为使用可靠会话与 HTTPS 一起使用</span><span class="sxs-lookup"><span data-stu-id="22432-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="22432-119">使用[ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)从命令行以从服务元数据生成代码。</span><span class="sxs-lookup"><span data-stu-id="22432-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="22432-120">生成的客户端包含`ICalculator`定义客户端实现必须满足的服务协定的接口。</span><span class="sxs-lookup"><span data-stu-id="22432-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="22432-121">生成的客户端应用程序还包含 `ClientCalculator` 的实现。</span><span class="sxs-lookup"><span data-stu-id="22432-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="22432-122">请注意，该服务的实现内部未指定地址和绑定信息。</span><span class="sxs-lookup"><span data-stu-id="22432-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="22432-123">您无需编写代码，以便从配置文件中检索的地址和绑定信息。</span><span class="sxs-lookup"><span data-stu-id="22432-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="22432-124">配置名为的自定义绑定`reliableSessionOverHttps`以使用 HTTPS 传输和可靠会话。</span><span class="sxs-lookup"><span data-stu-id="22432-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="22432-125">在应用程序中创建 `ClientCalculator` 的实例，然后调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="22432-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="22432-126">编译并运行客户端。</span><span class="sxs-lookup"><span data-stu-id="22432-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="22432-127">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="22432-127">.NET Framework security</span></span>

<span data-ttu-id="22432-128">因为此示例中使用的证书是使用创建的测试证书*Makecert.exe*，当您尝试访问 HTTPS 地址，例如，将出现安全警报`https://localhost/servicemodelsamples/service.svc`，从你的浏览器。</span><span class="sxs-lookup"><span data-stu-id="22432-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="22432-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="22432-129">See also</span></span>

- [<span data-ttu-id="22432-130">可靠会话</span><span class="sxs-lookup"><span data-stu-id="22432-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
