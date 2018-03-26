---
title: 如何：检索元数据并实现兼容服务。
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ac7654fa041688bbd703d564f6703df9671fbaea
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2018
---
# <a name="how-to-retrieve-metadata-and-implement-a-compliant-service"></a><span data-ttu-id="41d53-102">如何：检索元数据并实现兼容服务。</span><span class="sxs-lookup"><span data-stu-id="41d53-102">How to: Retrieve Metadata and Implement a Compliant Service</span></span>
<span data-ttu-id="41d53-103">通常，设计和实现服务并不是由同一个人完成的。</span><span class="sxs-lookup"><span data-stu-id="41d53-103">Often, the same person does not design and implement services.</span></span> <span data-ttu-id="41d53-104">在交互操作应用程序很重要的环境中，可以用 Web 服务描述语言 (WSDL) 设计或描述协定，而且开发人员必须实现一个与所提供的协定相兼容的服务。</span><span class="sxs-lookup"><span data-stu-id="41d53-104">In environments where interoperating applications are important, contracts can be designed or described in Web Services Description Language (WSDL) and a developer must implement a service that complies with the provided contract.</span></span> <span data-ttu-id="41d53-105">您可能还需要将现有服务迁移到 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]，但保留连网格式。</span><span class="sxs-lookup"><span data-stu-id="41d53-105">You may also want to migrate an existing service to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] but preserve the wire format.</span></span> <span data-ttu-id="41d53-106">此外，双工协定还需要调用方实现一个回调协定。</span><span class="sxs-lookup"><span data-stu-id="41d53-106">In addition, duplex contracts require callers to implement a callback contract as well.</span></span>  
  
 <span data-ttu-id="41d53-107">在这些情况下，你必须使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) （或等效的工具） 可实现以满足的要求采用托管语言生成服务协定接口协定。</span><span class="sxs-lookup"><span data-stu-id="41d53-107">In these cases, you must use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (or an equivalent tool) to generate a service contract interface in a managed language that you can implement to fulfill the requirements of the contract.</span></span> <span data-ttu-id="41d53-108">通常[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)用于获取与通道工厂一起使用的服务协定或[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]以及与客户端配置文件，它将设置的客户端类型正确的绑定和地址。</span><span class="sxs-lookup"><span data-stu-id="41d53-108">Typically the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) is used to acquire a service contract that is used with a channel factory or a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client type as well as with a client configuration file that sets up the correct binding and address.</span></span> <span data-ttu-id="41d53-109">若要使用生成的配置文件，则必须将其更改到服务配置文件中。</span><span class="sxs-lookup"><span data-stu-id="41d53-109">To use the generated configuration file, you must change it into a service configuration file.</span></span> <span data-ttu-id="41d53-110">您可能还需要修改服务协定。</span><span class="sxs-lookup"><span data-stu-id="41d53-110">You may also need to modify the service contract.</span></span>  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a><span data-ttu-id="41d53-111">检索数据并实现兼容服务</span><span class="sxs-lookup"><span data-stu-id="41d53-111">To retrieve data and implement a compliant service</span></span>  
  
1.  <span data-ttu-id="41d53-112">使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)针对元数据文件或生成代码文件的元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="41d53-112">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) against metadata files or a metadata endpoint to generate a code file.</span></span>  
  
2.  <span data-ttu-id="41d53-113">搜索输出代码文件中包含相关接口的部分（以防存在多个接口），此接口是用 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> 属性标记的。</span><span class="sxs-lookup"><span data-stu-id="41d53-113">Search for the portion of the output code file that contains the interface of interest (in case there is more than one) that is marked with the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="41d53-114">下面的代码示例显示由生成的两个接口[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="41d53-114">The following code example shows the two interfaces generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="41d53-115">第一个 (`ISampleService`) 是服务协定接口，实现它可创建兼容服务。</span><span class="sxs-lookup"><span data-stu-id="41d53-115">The first (`ISampleService`) is the service contract interface that you implement to create a compliant service.</span></span> <span data-ttu-id="41d53-116">第二个 (`ISampleServiceChannel`) 是帮助器接口，客户端使用它可同时扩展服务协定接口和 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>，且该接口可用于客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="41d53-116">The second (`ISampleServiceChannel`) is a helper interface for client use that extends both the service contract interface and <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> and is for use in a client application.</span></span>  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3.  <span data-ttu-id="41d53-117">如果 WSDL 未指定所有操作的答复操作，则生成的操作协定可能会将 <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> 属性设置为通配符 (\*)。</span><span class="sxs-lookup"><span data-stu-id="41d53-117">If the WSDL does not specify a reply action for all of the operations, the generated operation contracts may have the <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> property set to the wildcard character (\*).</span></span> <span data-ttu-id="41d53-118">移除该属性设置。</span><span class="sxs-lookup"><span data-stu-id="41d53-118">Remove this property setting.</span></span> <span data-ttu-id="41d53-119">否则，当您实现服务协定元数据时，将不能为这些操作导出元数据。</span><span class="sxs-lookup"><span data-stu-id="41d53-119">Otherwise, when you implement the service contract metadata, the metadata cannot be exported for those operations.</span></span>  
  
4.  <span data-ttu-id="41d53-120">实现类上的接口并承载服务。</span><span class="sxs-lookup"><span data-stu-id="41d53-120">Implement the interface on a class and host the service.</span></span> <span data-ttu-id="41d53-121">有关示例，请参阅[如何： 实现服务协定](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)，或请参阅下面的示例部分中的简单实现。</span><span class="sxs-lookup"><span data-stu-id="41d53-121">For an example, see [How to: Implement a Service Contract](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md), or see a simple implementation below in the Example section.</span></span>  
  
5.  <span data-ttu-id="41d53-122">在客户端的配置文件[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)生成时，更改[\<客户端 >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md)的配置节[ \<服务 >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md)配置节。</span><span class="sxs-lookup"><span data-stu-id="41d53-122">In the client configuration file that the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generates, change the [\<client>](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) configuration section to a [\<services>](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) configuration section.</span></span> <span data-ttu-id="41d53-123">（有关生成的客户端应用程序配置文件的示例，请参见下面的“示例”部分。）</span><span class="sxs-lookup"><span data-stu-id="41d53-123">(For an example of a generated client application configuration file, see the following "Example" section.)</span></span>  
  
6.  <span data-ttu-id="41d53-124">在[\<服务 >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md)配置部分中，创建`name`属性中[\<服务 >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md)配置节，用于你的服务实现。</span><span class="sxs-lookup"><span data-stu-id="41d53-124">Within the [\<services>](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) configuration section, create a `name` attribute in the [\<services>](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) configuration section for your service implementation.</span></span>  
  
7.  <span data-ttu-id="41d53-125">将服务的 `name` 属性设置为服务实现的配置名称。</span><span class="sxs-lookup"><span data-stu-id="41d53-125">Set the service `name` attribute to the configuration name for your service implementation.</span></span>  
  
8.  <span data-ttu-id="41d53-126">将使用实现的服务协定的终结点配置元素添加到服务配置部分。</span><span class="sxs-lookup"><span data-stu-id="41d53-126">Add the endpoint configuration elements that use the implemented service contract to the service configuration section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41d53-127">示例</span><span class="sxs-lookup"><span data-stu-id="41d53-127">Example</span></span>  
 <span data-ttu-id="41d53-128">下面的代码示例演示通过运行生成的代码文件的大部分[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)针对元数据文件。</span><span class="sxs-lookup"><span data-stu-id="41d53-128">The following code example shows the majority of a code file generated by running the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) against metadata files.</span></span>  
  
 <span data-ttu-id="41d53-129">下面的代码演示：</span><span class="sxs-lookup"><span data-stu-id="41d53-129">The following code shows:</span></span>  
  
-   <span data-ttu-id="41d53-130">实现时符合协定要求的服务协定接口 (`ISampleService`)。</span><span class="sxs-lookup"><span data-stu-id="41d53-130">The service contract interface that, when implemented, complies with the contract requirements (`ISampleService`).</span></span>  
  
-   <span data-ttu-id="41d53-131">客户端所使用的帮助器接口，可用于同时扩展服务协定接口和 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>，并可用于客户端应用程序 (`ISampleServiceChannel`)。</span><span class="sxs-lookup"><span data-stu-id="41d53-131">The helper interface for client use that extends both the service contract interface and <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> and is for use in a client application (`ISampleServiceChannel`).</span></span>  
  
-   <span data-ttu-id="41d53-132">扩展 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> 的帮助器类，可用于客户端应用程序 (`SampleServiceClient`)。</span><span class="sxs-lookup"><span data-stu-id="41d53-132">The helper class that extends <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> and is for use in a client application (`SampleServiceClient`).</span></span>  
  
-   <span data-ttu-id="41d53-133">从服务生成的配置文件。</span><span class="sxs-lookup"><span data-stu-id="41d53-133">The configuration file generated from the service.</span></span>  
  
-   <span data-ttu-id="41d53-134">简单的 `ISampleService` 服务实现。</span><span class="sxs-lookup"><span data-stu-id="41d53-134">A simple `ISampleService` service implementation.</span></span>  
  
-   <span data-ttu-id="41d53-135">客户端配置文件到服务器端版本的转换。</span><span class="sxs-lookup"><span data-stu-id="41d53-135">A conversion of the client-side configuration file to a service-side version.</span></span>  
  
 [!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]    
 [!code-xml[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]     
 [!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]    
 [!code-xml[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]    
  
## <a name="see-also"></a><span data-ttu-id="41d53-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41d53-136">See Also</span></span>  
 [<span data-ttu-id="41d53-137">ServiceModel 元数据实用工具 (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="41d53-137">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
