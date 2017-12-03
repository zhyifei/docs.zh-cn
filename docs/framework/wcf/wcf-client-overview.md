---
title: "WCF 客户端概述"
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
helpviewer_keywords: clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6333db92d010eab7765cfc62a9f64601d5b82d55
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-client-overview"></a><span data-ttu-id="291d7-102">WCF 客户端概述</span><span class="sxs-lookup"><span data-stu-id="291d7-102">WCF Client Overview</span></span>
<span data-ttu-id="291d7-103">本节描述客户端应用程序可以做什么，如何配置、创建和使用 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 客户端，以及如何保护客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="291d7-103">This section describes what client applications do, how to configure, create, and use a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] client, and how to secure client applications.</span></span>  
  
## <a name="using-wcf-client-objects"></a><span data-ttu-id="291d7-104">使用 WCF 客户端对象</span><span class="sxs-lookup"><span data-stu-id="291d7-104">Using WCF Client Objects</span></span>  
 <span data-ttu-id="291d7-105">客户端应用程序是使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端与其他应用程序通信的托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="291d7-105">A client application is a managed application that uses a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client to communicate with another application.</span></span> <span data-ttu-id="291d7-106">若要为 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务创建一个客户端应用程序，则需要执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="291d7-106">To create a client application for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service requires the following steps:</span></span>  
  
1.  <span data-ttu-id="291d7-107">获取服务终结点的服务协定、绑定以及地址信息。</span><span class="sxs-lookup"><span data-stu-id="291d7-107">Obtain the service contract, bindings, and address information for a service endpoint.</span></span>  
  
2.  <span data-ttu-id="291d7-108">使用该信息创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端。</span><span class="sxs-lookup"><span data-stu-id="291d7-108">Create a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client using that information.</span></span>  
  
3.  <span data-ttu-id="291d7-109">调用操作。</span><span class="sxs-lookup"><span data-stu-id="291d7-109">Call operations.</span></span>  
  
4.  <span data-ttu-id="291d7-110">关闭该 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象。</span><span class="sxs-lookup"><span data-stu-id="291d7-110">Close the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object.</span></span>  
  
 <span data-ttu-id="291d7-111">以下部分将讨论上述这些步骤，并简单介绍以下问题：</span><span class="sxs-lookup"><span data-stu-id="291d7-111">The following sections discuss these steps and provide brief introductions to the following issues:</span></span>  
  
-   <span data-ttu-id="291d7-112">处理错误。</span><span class="sxs-lookup"><span data-stu-id="291d7-112">Handling errors.</span></span>  
  
-   <span data-ttu-id="291d7-113">配置和保护客户端。</span><span class="sxs-lookup"><span data-stu-id="291d7-113">Configuring and securing clients.</span></span>  
  
-   <span data-ttu-id="291d7-114">为双工服务创建回调对象。</span><span class="sxs-lookup"><span data-stu-id="291d7-114">Creating callback objects for duplex services.</span></span>  
  
-   <span data-ttu-id="291d7-115">异步调用服务。</span><span class="sxs-lookup"><span data-stu-id="291d7-115">Calling services asynchronously.</span></span>  
  
-   <span data-ttu-id="291d7-116">使用客户端通道调用服务。</span><span class="sxs-lookup"><span data-stu-id="291d7-116">Calling services using client channels.</span></span>  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a><span data-ttu-id="291d7-117">获取服务协定、绑定和地址</span><span class="sxs-lookup"><span data-stu-id="291d7-117">Obtain the Service Contract, Bindings, and Addresses</span></span>  
 <span data-ttu-id="291d7-118">在 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 中，服务和客户端使用托管属性、接口和方法对协定进行建模。</span><span class="sxs-lookup"><span data-stu-id="291d7-118">In [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], services and clients model contracts using managed attributes, interfaces, and methods.</span></span> <span data-ttu-id="291d7-119">若要连接客户端应用程序中的服务，则需要获取该服务协定的类型信息。</span><span class="sxs-lookup"><span data-stu-id="291d7-119">To connect to a service in a client application, you need to obtain the type information for the service contract.</span></span> <span data-ttu-id="291d7-120">通常情况下，你执行此操作通过使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)，该服务，从下载元数据将其转换为托管的源代码文件中您选择的语言，并创建一个客户端可用于配置的应用程序配置文件你[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]客户端对象。</span><span class="sxs-lookup"><span data-stu-id="291d7-120">Typically, you do this by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), which downloads metadata from the service, converts it to a managed source code file in the language of your choice, and creates a client application configuration file that you can use to configure your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object.</span></span> <span data-ttu-id="291d7-121">例如，如果您准备创建一个 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象来调用 `MyCalculatorService`，并且您知道该服务的元数据已在 `http://computerName/MyCalculatorService/Service.svc?wsdl` 中发布，则下面的代码示例演示如何使用 Svcutil.exe 获取一个包含托管代码中的服务协定的 `ClientCode.vb` 文件。</span><span class="sxs-lookup"><span data-stu-id="291d7-121">For example, if you are going to create an [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object to invoke a `MyCalculatorService`, and you know that the metadata for that service is published at `http://computerName/MyCalculatorService/Service.svc?wsdl`, then the following code example shows how to use Svcutil.exe to obtain a `ClientCode.vb` file that contains the service contract in managed code.</span></span>  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 <span data-ttu-id="291d7-122">您可以将此协定代码编译为客户端应用程序或另一个程序集，然后，客户端应用程序可以使用该程序集创建一个 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象。</span><span class="sxs-lookup"><span data-stu-id="291d7-122">You can either compile this contract code into the client application or into another assembly that the client application can then use to create an [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object.</span></span> <span data-ttu-id="291d7-123">可以使用配置文件配置客户端对象以与服务正确连接。</span><span class="sxs-lookup"><span data-stu-id="291d7-123">You can use the configuration file to configure the client object to properly connect to the service .</span></span>  
  
 <span data-ttu-id="291d7-124">有关此过程的示例，请参阅[如何： 创建客户端](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-124">For an example of this process, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="291d7-125">有关协定的更完整信息，请参阅[协定](../../../docs/framework/wcf/feature-details/contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-125">For more complete information about contracts, see [Contracts](../../../docs/framework/wcf/feature-details/contracts.md).</span></span>  
  
## <a name="create-a-wcf-client-object"></a><span data-ttu-id="291d7-126">创建一个 WCF 客户端对象</span><span class="sxs-lookup"><span data-stu-id="291d7-126">Create a WCF Client Object</span></span>  
 <span data-ttu-id="291d7-127">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端是表示某个 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务的一个本地对象，客户端可以使用这种表示形式与远程服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="291d7-127">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client is a local object that represents a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service in a form that the client can use to communicate with the remote service.</span></span> [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="291d7-128"> 客户端类型可实现目标服务协定，因此在您创建一个服务协定并配置它之后，就可以直接使用该客户端对象调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="291d7-128"> client types implement the target service contract, so when you create one and configure it, you can then use the client object directly to invoke service operations.</span></span> <span data-ttu-id="291d7-129">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]运行时将为方法调入消息、 将它们发送到服务，侦听回复，并返回到这些值[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]用作返回值的客户端对象或`out`或`ref`参数。</span><span class="sxs-lookup"><span data-stu-id="291d7-129">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] run time converts the method calls into messages, sends them to the service, listens for the reply, and returns those values to the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object as return values or `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="291d7-130">您还可以使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端通道对象连接和使用服务。</span><span class="sxs-lookup"><span data-stu-id="291d7-130">You can also use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client channel objects to connect with and use services.</span></span> <span data-ttu-id="291d7-131">有关详细信息，请参阅[WCF 客户端体系结构](../../../docs/framework/wcf/feature-details/client-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-131">For details, see [WCF Client Architecture](../../../docs/framework/wcf/feature-details/client-architecture.md).</span></span>  
  
#### <a name="creating-a-new-wcf-object"></a><span data-ttu-id="291d7-132">创建一个新的 WCF 对象</span><span class="sxs-lookup"><span data-stu-id="291d7-132">Creating a New WCF Object</span></span>  
 <span data-ttu-id="291d7-133">为了演示如何使用 <xref:System.ServiceModel.ClientBase%601> 类，现假设已从服务应用程序生成了下面的简单服务协定。</span><span class="sxs-lookup"><span data-stu-id="291d7-133">To illustrate the use of a <xref:System.ServiceModel.ClientBase%601> class, assume the following simple service contract has been generated from a service application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="291d7-134">如果您是使用 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端，则当您将一个服务引用添加到项目中时，对象将自动加载到对象浏览器中。</span><span class="sxs-lookup"><span data-stu-id="291d7-134">If you are using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to create your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client, objects are loaded automatically into the object browser when you add a service reference to your project.</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 <span data-ttu-id="291d7-135">如果您不是使用 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，则请检查已生成的协定代码以查找扩展 <xref:System.ServiceModel.ClientBase%601> 的类型以及服务协定接口 `ISampleService`。</span><span class="sxs-lookup"><span data-stu-id="291d7-135">If you are not using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], examine the generated contract code to find the type that extends <xref:System.ServiceModel.ClientBase%601> and the service contract interface `ISampleService`.</span></span> <span data-ttu-id="291d7-136">在这种情况下，该类型看上去类似下列代码：</span><span class="sxs-lookup"><span data-stu-id="291d7-136">In this case, that type looks like the following code:</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 <span data-ttu-id="291d7-137">可以通过使用其中一个构造函数将此类创建为一个本地对象，并对该本地对象进行配置，然后使用它连接到 `ISampleService` 类型的服务。</span><span class="sxs-lookup"><span data-stu-id="291d7-137">This class can be created as a local object using one of the constructors, configured, and then used to connect to a service of the type `ISampleService`.</span></span>  
  
 <span data-ttu-id="291d7-138">建议您首先创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象，然后使用该对象并在一个单独的 try/catch 块内将它关闭。</span><span class="sxs-lookup"><span data-stu-id="291d7-138">It is recommended that you create your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object first, and then use it and close it inside a single try/catch block.</span></span> <span data-ttu-id="291d7-139">不应该使用 `using` 语句（`Using` 中的 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]），因为该语句可以屏蔽处于某些失败模式的异常。</span><span class="sxs-lookup"><span data-stu-id="291d7-139">You should not use the `using` statement (`Using` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) because it may mask exceptions in certain failure modes.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="291d7-140">以下部分以及为[避免问题与 Using 语句](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-140"> the following sections as well as [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).</span></span>  
  
### <a name="contracts-bindings-and-addresses"></a><span data-ttu-id="291d7-141">协定、绑定和地址</span><span class="sxs-lookup"><span data-stu-id="291d7-141">Contracts, Bindings, and Addresses</span></span>  
 <span data-ttu-id="291d7-142">在可以创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象之前，必须配置客户端对象。</span><span class="sxs-lookup"><span data-stu-id="291d7-142">Before you can create a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object, you must configure the client object.</span></span> <span data-ttu-id="291d7-143">具体而言，它必须有一个服务*终结点*使用。</span><span class="sxs-lookup"><span data-stu-id="291d7-143">Specifically, it must have a service *endpoint* to use.</span></span> <span data-ttu-id="291d7-144">终结点由服务协定、绑定和地址组成。</span><span class="sxs-lookup"><span data-stu-id="291d7-144">An endpoint is the combination of a service contract, a binding, and an address.</span></span> <span data-ttu-id="291d7-145">([!INCLUDE[crabout](../../../includes/crabout-md.md)]终结点，请参阅[终结点： 地址、 绑定和协定](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)。)通常情况下，此信息是否位于[\<终结点 >](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)客户端应用程序配置文件，例如 Svcutil.exe 工具生成，并创建你的客户端时自动加载中的元素对象。</span><span class="sxs-lookup"><span data-stu-id="291d7-145">([!INCLUDE[crabout](../../../includes/crabout-md.md)] endpoints, see [Endpoints: Addresses, Bindings, and Contracts](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) Typically, this information is located in the [\<endpoint>](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) element in a client application configuration file, such as the one the Svcutil.exe tool generates, and is loaded automatically when you create your client object.</span></span> <span data-ttu-id="291d7-146">两种 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端类型都具有使您能够以编程方式指定此信息的重载。</span><span class="sxs-lookup"><span data-stu-id="291d7-146">Both [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client types also have overloads that enable you to programmatically specify this information.</span></span>  
  
 <span data-ttu-id="291d7-147">例如，上述示例中所使用的 `ISampleService` 的生成的配置文件包含以下终结点信息。</span><span class="sxs-lookup"><span data-stu-id="291d7-147">For example, a generated configuration file for an `ISampleService` used in the preceding examples contains the following endpoint information.</span></span>  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 <span data-ttu-id="291d7-148">此配置文件在 `<client>` 元素中指定目标终结点。</span><span class="sxs-lookup"><span data-stu-id="291d7-148">This configuration file specifies a target endpoint in the `<client>` element.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="291d7-149">使用多个目标终结点的更多信息，请参见 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> 或 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> 构造函数。</span><span class="sxs-lookup"><span data-stu-id="291d7-149"> using multiple target endpoints, see the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> constructors.</span></span>  
  
## <a name="calling-operations"></a><span data-ttu-id="291d7-150">调用操作</span><span class="sxs-lookup"><span data-stu-id="291d7-150">Calling Operations</span></span>  
 <span data-ttu-id="291d7-151">创建并配置了客户端对象后，请创建一个 try/catch 块，如果该对象是本地对象，则以相同的方式调用操作，然后关闭 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象。</span><span class="sxs-lookup"><span data-stu-id="291d7-151">Once you have a client object created and configured, create a try/catch block, call operations in the same way that you would if the object were local, and close the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object.</span></span> <span data-ttu-id="291d7-152">当客户端应用程序调用第一个操作时，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 将自动打开基础通道，并在回收对象时关闭基础通道。</span><span class="sxs-lookup"><span data-stu-id="291d7-152">When the client application calls the first operation, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] automatically opens the underlying channel, and the underlying channel is closed when the object is recycled.</span></span> <span data-ttu-id="291d7-153">（或者，还可以在调用其他操作之前或之后显式打开和关闭该通道。）</span><span class="sxs-lookup"><span data-stu-id="291d7-153">(Alternatively, you can also explicitly open and close the channel prior to or subsequent to calling other operations.)</span></span>  
  
 <span data-ttu-id="291d7-154">例如，如果您具有以下服务协定：</span><span class="sxs-lookup"><span data-stu-id="291d7-154">For example, if you have the following service contract:</span></span>  
  
```csharp  
namespace Microsoft.ServiceModel.Samples  
{  
    using System;  
    using System.ServiceModel;  
  
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
   {  
        [OperationContract]  
        double Add(double n1, double n2);  
        [OperationContract]  
        double Subtract(double n1, double n2);  
        [OperationContract]  
        double Multiply(double n1, double n2);  
        [OperationContract]  
        double Divide(double n1, double n2);  
    }  
}  
```  
  
```vb  
Namespace Microsoft.ServiceModel.Samples  
  
    Imports System  
    Imports System.ServiceModel  
  
    <ServiceContract(Namespace:= _  
    "http://Microsoft.ServiceModel.Samples")> _   
   Public Interface ICalculator  
        <OperationContract> _   
        Function Add(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Subtract(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Multiply(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
     Function Divide(n1 As Double, n2 As Double) As Double  
End Interface  
```  
  
 <span data-ttu-id="291d7-155">您可以通过创建一个 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象并调用其方法来调用操作，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="291d7-155">You can call operations by creating a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object and calling its methods, as the following code example demonstrates.</span></span> <span data-ttu-id="291d7-156">请注意，打开、调用和关闭 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象发生在一个 try/catch 块内。</span><span class="sxs-lookup"><span data-stu-id="291d7-156">Note that the opening, calling, and closing of the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object occurs within a single try/catch block.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="291d7-157">[使用 WCF 客户端访问服务](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)和[避免出现与 Using 语句问题](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-157"> [Accessing Services Using a WCF Client](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) and [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a><span data-ttu-id="291d7-158">处理错误</span><span class="sxs-lookup"><span data-stu-id="291d7-158">Handling Errors</span></span>  
 <span data-ttu-id="291d7-159">当打开基础客户端通道（无论是通过显式打开还是通过调用操作自动打开）、使用客户端或通道对象调用操作，或关闭基础客户端通道时，都会在客户端应用程序中出现异常。</span><span class="sxs-lookup"><span data-stu-id="291d7-159">Exceptions can occur in a client application when opening the underlying client channel (whether explicitly or automatically by calling an operation), using the client or channel object to call operations, or when closing the underlying client channel.</span></span> <span data-ttu-id="291d7-160">除了由操作返回的 SOAP 错误导致引发的任何 <xref:System.TimeoutException?displayProperty=nameWithType> 对象外，建议您至少将应用程序设置为能够处理可能的 <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> 和 <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> 异常。</span><span class="sxs-lookup"><span data-stu-id="291d7-160">It is recommended at a minimum that applications expect to handle possible <xref:System.TimeoutException?displayProperty=nameWithType> and <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> exceptions in addition to any <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> objects thrown as a result of SOAP faults returned by operations.</span></span> <span data-ttu-id="291d7-161">操作协定中指定的 SOAP 错误将作为 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> 在客户端应用程序中引发，此异常中的类型参数为 SOAP 错误的详细信息类型。</span><span class="sxs-lookup"><span data-stu-id="291d7-161">SOAP faults specified in the operation contract are raised to client applications as a <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the type parameter is the detail type of the SOAP fault.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="291d7-162">处理客户端应用程序中的错误状态，请参阅[发送和接收错误](../../../docs/framework/wcf/sending-and-receiving-faults.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-162"> handling error conditions in a client application, see [Sending and Receiving Faults](../../../docs/framework/wcf/sending-and-receiving-faults.md).</span></span> <span data-ttu-id="291d7-163">有关完整的示例演示如何处理客户端中的错误，请参阅[预期异常](../../../docs/framework/wcf/samples/expected-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-163">For a complete sample the shows how to handle errors in a client, see [Expected Exceptions](../../../docs/framework/wcf/samples/expected-exceptions.md).</span></span>  
  
## <a name="configuring-and-securing-clients"></a><span data-ttu-id="291d7-164">配置和保护客户端</span><span class="sxs-lookup"><span data-stu-id="291d7-164">Configuring and Securing Clients</span></span>  
 <span data-ttu-id="291d7-165">若要配置客户端，请首先为客户端或通道对象加载目标终结点信息，通常是从配置文件中加载该信息，但是也可以使用客户端构造函数和属性以编程方式加载。</span><span class="sxs-lookup"><span data-stu-id="291d7-165">Configuring a client starts with the required loading of target endpoint information for the client or channel object, usually from a configuration file, although you can also load this information programmatically using the client constructors and properties.</span></span> <span data-ttu-id="291d7-166">但是，若要启用特定的客户端行为或实施一些安全方案还需要执行其他配置步骤。</span><span class="sxs-lookup"><span data-stu-id="291d7-166">However, additional configuration steps are required to enable certain client behavior and for many security scenarios.</span></span>  
  
 <span data-ttu-id="291d7-167">例如，服务协定的安全要求已在服务协定接口中声明，并且如果 Svcutil.exe 已创建了一个配置文件，则该文件通常会包含一个能够支持服务安全要求的绑定。</span><span class="sxs-lookup"><span data-stu-id="291d7-167">For example, security requirements for service contracts are declared in the service contract interface, and if Svcutil.exe created a configuration file, that file usually contains a binding that is capable of supporting the security requirements of the service.</span></span> <span data-ttu-id="291d7-168">但是在某些情况中，可能需要更多的安全配置，例如配置客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="291d7-168">In some cases, however, more security configuration may be required, such as configuring client credentials.</span></span> <span data-ttu-id="291d7-169">有关安全配置的完整信息[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]客户端，请参阅[保护客户端](../../../docs/framework/wcf/securing-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-169">For complete information about the configuration of security for [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] clients, see [Securing Clients](../../../docs/framework/wcf/securing-clients.md).</span></span>  
  
 <span data-ttu-id="291d7-170">此外，在客户端应用程序中还可以启用一些自定义修改，例如自定义运行时行为。</span><span class="sxs-lookup"><span data-stu-id="291d7-170">In addition, some custom modifications can be enabled in client applications, such as custom run-time behaviors.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="291d7-171">如何配置自定义客户端行为，请参阅[配置客户端行为](../../../docs/framework/wcf/configuring-client-behaviors.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-171"> how to configure a custom client behavior, see [Configuring Client Behaviors](../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
## <a name="creating-callback-objects-for-duplex-services"></a><span data-ttu-id="291d7-172">为双工服务创建回调对象</span><span class="sxs-lookup"><span data-stu-id="291d7-172">Creating Callback Objects for Duplex Services</span></span>  
 <span data-ttu-id="291d7-173">双工服务指定一个回调协定，客户端应用程序必须实现该协定以便提供一个该服务能够根据协定要求调用的回调对象。</span><span class="sxs-lookup"><span data-stu-id="291d7-173">Duplex services specify a callback contract that the client application must implement in order to provide a callback object for the service to call according to the requirements of the contract.</span></span> <span data-ttu-id="291d7-174">虽然回调对象不是完整的服务（例如，您无法使用回调对象启动一个通道），但是为了实现和配置，这些回调对象可以被视为一种服务。</span><span class="sxs-lookup"><span data-stu-id="291d7-174">Although callback objects are not full services (for example, you cannot initiate a channel with a callback object), for the purposes of implementation and configuration they can be thought of as a kind of service.</span></span>  
  
 <span data-ttu-id="291d7-175">双工服务的客户端必须：</span><span class="sxs-lookup"><span data-stu-id="291d7-175">Clients of duplex services must:</span></span>  
  
-   <span data-ttu-id="291d7-176">实现一个回调协定类。</span><span class="sxs-lookup"><span data-stu-id="291d7-176">Implement a callback contract class.</span></span>  
  
-   <span data-ttu-id="291d7-177">创建回调协定实现类的一个实例，并使用该实例创建传递给 <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> 客户端构造函数的 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 对象。</span><span class="sxs-lookup"><span data-stu-id="291d7-177">Create an instance of the callback contract implementation class and use it to create the <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> object that you pass to the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client constructor.</span></span>  
  
-   <span data-ttu-id="291d7-178">调用操作并处理操作回调。</span><span class="sxs-lookup"><span data-stu-id="291d7-178">Invoke operations and handle operation callbacks.</span></span>  
  
 <span data-ttu-id="291d7-179">双工 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象除了会公开支持回调所必需的功能（包括回调服务的配置）以外，其他的功能和它们的非双工对应项相同。</span><span class="sxs-lookup"><span data-stu-id="291d7-179">Duplex [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client objects function like their nonduplex counterparts, with the exception that they expose the functionality necessary to support callbacks, including the configuration of the callback service.</span></span>  
  
 <span data-ttu-id="291d7-180">例如，可以通过使用回调类的 <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> 属性 (Attribute) 的属性 (Property)，控制回调对象运行时行为的各个方面。</span><span class="sxs-lookup"><span data-stu-id="291d7-180">For example, you can control various aspects of callback object runtime behavior by using properties of the <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> attribute on the callback class.</span></span> <span data-ttu-id="291d7-181">另一个示例是使用 <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> 类将异常信息返回给调用回调对象的服务。</span><span class="sxs-lookup"><span data-stu-id="291d7-181">Another example is the use of the <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> class to enable the return of exception information to services that call the callback object.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="291d7-182">[双工服务](../../../docs/framework/wcf/feature-details/duplex-services.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-182"> [Duplex Services](../../../docs/framework/wcf/feature-details/duplex-services.md).</span></span> <span data-ttu-id="291d7-183">有关完整示例，请参阅[双工](../../../docs/framework/wcf/samples/duplex.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-183">For a complete sample, see [Duplex](../../../docs/framework/wcf/samples/duplex.md).</span></span>  
  
 <span data-ttu-id="291d7-184">在运行 Internet 信息服务 (IIS) 5.1 的 Windows XP 计算机上，双工客户端必须使用 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> 类指定一个客户端基址，否则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="291d7-184">On Windows XP computers running Internet Information Services (IIS) 5.1, duplex clients must specify a client base address using the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> class or an exception is thrown.</span></span> <span data-ttu-id="291d7-185">下面的代码示例演示如何在代码中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="291d7-185">The following code example shows how to do this in code.</span></span>  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 <span data-ttu-id="291d7-186">下面的代码演示如何在配置文件中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="291d7-186">The following code shows how to do this in a configuration file</span></span>  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a><span data-ttu-id="291d7-187">异步调用服务</span><span class="sxs-lookup"><span data-stu-id="291d7-187">Calling Services Asynchronously</span></span>  
 <span data-ttu-id="291d7-188">如何调用操作完全取决于客户端开发人员。</span><span class="sxs-lookup"><span data-stu-id="291d7-188">How operations are called is entirely up to the client developer.</span></span> <span data-ttu-id="291d7-189">这是因为当在托管代码中表示组成操作的消息时，这些消息可以映射到同步或异步方法中。</span><span class="sxs-lookup"><span data-stu-id="291d7-189">This is because the messages that make up an operation can be mapped to either synchronous or asynchronous methods when expressed in managed code.</span></span> <span data-ttu-id="291d7-190">因此，如果想要生成异步调用操作的客户端，则可以使用 Svcutil.exe 通过 `/async` 选项生成异步客户端代码。</span><span class="sxs-lookup"><span data-stu-id="291d7-190">Therefore, if you want to build a client that calls operations asynchronously, you can use Svcutil.exe to generate asynchronous client code using the `/async` option.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="291d7-191">[如何： 以异步方式调用服务操作](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-191"> [How to: Call Service Operations Asynchronously](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span>  
  
## <a name="calling-services-using-wcf-client-channels"></a><span data-ttu-id="291d7-192">使用 WCF 客户端通道调用服务</span><span class="sxs-lookup"><span data-stu-id="291d7-192">Calling Services Using WCF Client Channels</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="291d7-193"> 客户端类型扩展 <xref:System.ServiceModel.ClientBase%601>，而其自身派生自 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> 接口，从而可以公开基础通道系统。</span><span class="sxs-lookup"><span data-stu-id="291d7-193"> client types extend <xref:System.ServiceModel.ClientBase%601>, which itself derives from <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> interface to expose the underlying channel system.</span></span> <span data-ttu-id="291d7-194">可以同时使用目标服务协定和 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 类来调用服务。</span><span class="sxs-lookup"><span data-stu-id="291d7-194">You can invoke services by using the target service contract with the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="291d7-195">有关详细信息，请参阅[WCF 客户端体系结构](../../../docs/framework/wcf/feature-details/client-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="291d7-195">For details, see [WCF Client Architecture](../../../docs/framework/wcf/feature-details/client-architecture.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="291d7-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="291d7-196">See Also</span></span>  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
