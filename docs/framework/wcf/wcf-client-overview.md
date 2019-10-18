---
title: WCF 客户端概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: 9aba83bd3e05e3f390b3d1553bd7974c64c41037
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321337"
---
# <a name="wcf-client-overview"></a><span data-ttu-id="0732a-102">WCF 客户端概述</span><span class="sxs-lookup"><span data-stu-id="0732a-102">WCF Client Overview</span></span>
<span data-ttu-id="0732a-103">本部分介绍什么是客户端应用程序、如何配置、创建和使用 Windows Communication Foundation （WCF）客户端，以及如何保护客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="0732a-103">This section describes what client applications do, how to configure, create, and use a Windows Communication Foundation (WCF) client, and how to secure client applications.</span></span>  
  
## <a name="using-wcf-client-objects"></a><span data-ttu-id="0732a-104">使用 WCF 客户端对象</span><span class="sxs-lookup"><span data-stu-id="0732a-104">Using WCF Client Objects</span></span>  
 <span data-ttu-id="0732a-105">客户端应用程序是一种托管应用程序，它使用 WCF 客户端与其他应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="0732a-105">A client application is a managed application that uses a WCF client to communicate with another application.</span></span> <span data-ttu-id="0732a-106">若要为 WCF 服务创建客户端应用程序，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0732a-106">To create a client application for a WCF service requires the following steps:</span></span>  
  
1. <span data-ttu-id="0732a-107">获取服务终结点的服务协定、绑定以及地址信息。</span><span class="sxs-lookup"><span data-stu-id="0732a-107">Obtain the service contract, bindings, and address information for a service endpoint.</span></span>  
  
2. <span data-ttu-id="0732a-108">使用此信息创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="0732a-108">Create a WCF client using that information.</span></span>  
  
3. <span data-ttu-id="0732a-109">调用操作。</span><span class="sxs-lookup"><span data-stu-id="0732a-109">Call operations.</span></span>  
  
4. <span data-ttu-id="0732a-110">关闭 WCF 客户端对象。</span><span class="sxs-lookup"><span data-stu-id="0732a-110">Close the WCF client object.</span></span>  
  
 <span data-ttu-id="0732a-111">以下部分将讨论上述这些步骤，并简单介绍以下问题：</span><span class="sxs-lookup"><span data-stu-id="0732a-111">The following sections discuss these steps and provide brief introductions to the following issues:</span></span>  
  
- <span data-ttu-id="0732a-112">处理错误。</span><span class="sxs-lookup"><span data-stu-id="0732a-112">Handling errors.</span></span>  
  
- <span data-ttu-id="0732a-113">配置和保护客户端。</span><span class="sxs-lookup"><span data-stu-id="0732a-113">Configuring and securing clients.</span></span>  
  
- <span data-ttu-id="0732a-114">为双工服务创建回调对象。</span><span class="sxs-lookup"><span data-stu-id="0732a-114">Creating callback objects for duplex services.</span></span>  
  
- <span data-ttu-id="0732a-115">异步调用服务。</span><span class="sxs-lookup"><span data-stu-id="0732a-115">Calling services asynchronously.</span></span>  
  
- <span data-ttu-id="0732a-116">使用客户端通道调用服务。</span><span class="sxs-lookup"><span data-stu-id="0732a-116">Calling services using client channels.</span></span>  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a><span data-ttu-id="0732a-117">获取服务协定、绑定和地址</span><span class="sxs-lookup"><span data-stu-id="0732a-117">Obtain the Service Contract, Bindings, and Addresses</span></span>  
 <span data-ttu-id="0732a-118">在 WCF 中，服务和客户端使用托管属性、接口和方法为协定建模。</span><span class="sxs-lookup"><span data-stu-id="0732a-118">In WCF, services and clients model contracts using managed attributes, interfaces, and methods.</span></span> <span data-ttu-id="0732a-119">若要连接客户端应用程序中的服务，则需要获取该服务协定的类型信息。</span><span class="sxs-lookup"><span data-stu-id="0732a-119">To connect to a service in a client application, you need to obtain the type information for the service contract.</span></span> <span data-ttu-id="0732a-120">通常，你可以使用配置的[元数据实用工具（svcutil.exe）](servicemodel-metadata-utility-tool-svcutil-exe.md)来执行此操作，该工具从服务下载元数据，使用所选的语言将其转换为托管的源代码文件，并创建客户端应用程序配置文件您可以使用来配置您的 WCF 客户端对象。</span><span class="sxs-lookup"><span data-stu-id="0732a-120">Typically, you do this by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), which downloads metadata from the service, converts it to a managed source code file in the language of your choice, and creates a client application configuration file that you can use to configure your WCF client object.</span></span> <span data-ttu-id="0732a-121">例如，如果要创建一个 WCF 客户端对象来调用 `MyCalculatorService`，并且知道该服务的元数据是在 `http://computerName/MyCalculatorService/Service.svc?wsdl` 发布的，则下面的代码示例演示如何使用 Svcutil.exe 来获取包含服务 co 的 `ClientCode.vb` 文件托管代码中的 ntract。</span><span class="sxs-lookup"><span data-stu-id="0732a-121">For example, if you are going to create an WCF client object to invoke a `MyCalculatorService`, and you know that the metadata for that service is published at `http://computerName/MyCalculatorService/Service.svc?wsdl`, then the following code example shows how to use Svcutil.exe to obtain a `ClientCode.vb` file that contains the service contract in managed code.</span></span>  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 <span data-ttu-id="0732a-122">可以将此协定代码编译为客户端应用程序或另一个程序集，客户端应用程序随后可以使用该程序集创建 WCF 客户端对象。</span><span class="sxs-lookup"><span data-stu-id="0732a-122">You can either compile this contract code into the client application or into another assembly that the client application can then use to create an WCF client object.</span></span> <span data-ttu-id="0732a-123">可以使用配置文件配置客户端对象以与服务正确连接。</span><span class="sxs-lookup"><span data-stu-id="0732a-123">You can use the configuration file to configure the client object to properly connect to the service .</span></span>  
  
 <span data-ttu-id="0732a-124">有关此过程的示例，请参阅[如何：创建客户端](how-to-create-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-124">For an example of this process, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="0732a-125">有关协定的更完整信息，请参阅[约定](./feature-details/contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-125">For more complete information about contracts, see [Contracts](./feature-details/contracts.md).</span></span>  
  
## <a name="create-a-wcf-client-object"></a><span data-ttu-id="0732a-126">创建一个 WCF 客户端对象</span><span class="sxs-lookup"><span data-stu-id="0732a-126">Create a WCF Client Object</span></span>  
 <span data-ttu-id="0732a-127">WCF 客户端是一个本地对象，该对象表示一个窗体中的 WCF 服务，客户端可以使用该对象与远程服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="0732a-127">A WCF client is a local object that represents a WCF service in a form that the client can use to communicate with the remote service.</span></span> <span data-ttu-id="0732a-128">WCF 客户端类型实现目标服务协定，因此，当你创建一个协定并配置它时，你可以直接使用该客户端对象来调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="0732a-128">WCF client types implement the target service contract, so when you create one and configure it, you can then use the client object directly to invoke service operations.</span></span> <span data-ttu-id="0732a-129">WCF 运行时将方法调用转换为消息，将其发送到服务，侦听答复，并将这些值作为返回值返回到 WCF 客户端对象，或 `out` 或 `ref` 参数返回。</span><span class="sxs-lookup"><span data-stu-id="0732a-129">The WCF run time converts the method calls into messages, sends them to the service, listens for the reply, and returns those values to the WCF client object as return values or `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="0732a-130">你还可以使用 WCF 客户端信道对象连接和使用服务。</span><span class="sxs-lookup"><span data-stu-id="0732a-130">You can also use WCF client channel objects to connect with and use services.</span></span> <span data-ttu-id="0732a-131">有关详细信息，请参阅[WCF 客户端体系结构](./feature-details/client-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-131">For details, see [WCF Client Architecture](./feature-details/client-architecture.md).</span></span>  
  
#### <a name="creating-a-new-wcf-object"></a><span data-ttu-id="0732a-132">创建一个新的 WCF 对象</span><span class="sxs-lookup"><span data-stu-id="0732a-132">Creating a New WCF Object</span></span>  
 <span data-ttu-id="0732a-133">为了演示如何使用 <xref:System.ServiceModel.ClientBase%601> 类，现假设已从服务应用程序生成了下面的简单服务协定。</span><span class="sxs-lookup"><span data-stu-id="0732a-133">To illustrate the use of a <xref:System.ServiceModel.ClientBase%601> class, assume the following simple service contract has been generated from a service application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0732a-134">如果使用 Visual Studio 创建 WCF 客户端，则在你向项目添加服务引用时，会自动将对象加载到对象浏览器中。</span><span class="sxs-lookup"><span data-stu-id="0732a-134">If you are using Visual Studio to create your WCF client, objects are loaded automatically into the object browser when you add a service reference to your project.</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 <span data-ttu-id="0732a-135">如果使用的不是 Visual Studio，请检查生成的协定代码，查找 `ISampleService` 扩展 <xref:System.ServiceModel.ClientBase%601> 和服务协定接口的类型。</span><span class="sxs-lookup"><span data-stu-id="0732a-135">If you are not using Visual Studio, examine the generated contract code to find the type that extends <xref:System.ServiceModel.ClientBase%601> and the service contract interface `ISampleService`.</span></span> <span data-ttu-id="0732a-136">在这种情况下，该类型看上去类似下列代码：</span><span class="sxs-lookup"><span data-stu-id="0732a-136">In this case, that type looks like the following code:</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 <span data-ttu-id="0732a-137">可以通过使用其中一个构造函数将此类创建为一个本地对象，并对该本地对象进行配置，然后使用它连接到 `ISampleService` 类型的服务。</span><span class="sxs-lookup"><span data-stu-id="0732a-137">This class can be created as a local object using one of the constructors, configured, and then used to connect to a service of the type `ISampleService`.</span></span>  
  
 <span data-ttu-id="0732a-138">建议先创建 WCF 客户端对象，然后使用该对象，并在单个 try/catch 块内将其关闭。</span><span class="sxs-lookup"><span data-stu-id="0732a-138">It is recommended that you create your WCF client object first, and then use it and close it inside a single try/catch block.</span></span> <span data-ttu-id="0732a-139">不应使用 `using` 语句（`Using` 在 Visual Basic 中），因为它可能会在某些失败模式下屏蔽异常。</span><span class="sxs-lookup"><span data-stu-id="0732a-139">You should not use the `using` statement (`Using` in Visual Basic) because it may mask exceptions in certain failure modes.</span></span> <span data-ttu-id="0732a-140">有关详细信息，请参阅以下各节，并[使用 Close 和 Abort 释放 WCF 客户端资源](./samples/use-close-abort-release-wcf-client-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-140">For more information, see the following sections as well as [Use Close and Abort to release WCF client resources](./samples/use-close-abort-release-wcf-client-resources.md).</span></span>  
  
### <a name="contracts-bindings-and-addresses"></a><span data-ttu-id="0732a-141">协定、绑定和地址</span><span class="sxs-lookup"><span data-stu-id="0732a-141">Contracts, Bindings, and Addresses</span></span>  
 <span data-ttu-id="0732a-142">必须先配置客户端对象，然后才能创建 WCF 客户端对象。</span><span class="sxs-lookup"><span data-stu-id="0732a-142">Before you can create a WCF client object, you must configure the client object.</span></span> <span data-ttu-id="0732a-143">具体来说，它必须具有要使用的服务*终结点*。</span><span class="sxs-lookup"><span data-stu-id="0732a-143">Specifically, it must have a service *endpoint* to use.</span></span> <span data-ttu-id="0732a-144">终结点由服务协定、绑定和地址组成。</span><span class="sxs-lookup"><span data-stu-id="0732a-144">An endpoint is the combination of a service contract, a binding, and an address.</span></span> <span data-ttu-id="0732a-145">（有关终结点的详细信息，请参阅[终结点：地址、绑定和协定](./feature-details/endpoints-addresses-bindings-and-contracts.md)。）通常，此信息位于客户端应用程序配置文件（例如 Svcutil.exe 工具生成的文件）的[\<endpoint >](../configure-apps/file-schema/wcf/endpoint-of-client.md)元素中，并在创建客户端对象时自动加载。</span><span class="sxs-lookup"><span data-stu-id="0732a-145">(For more information about endpoints, see [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md).) Typically, this information is located in the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-of-client.md) element in a client application configuration file, such as the one the Svcutil.exe tool generates, and is loaded automatically when you create your client object.</span></span> <span data-ttu-id="0732a-146">这两个 WCF 客户端类型还具有重载，使你能够以编程方式指定此信息。</span><span class="sxs-lookup"><span data-stu-id="0732a-146">Both WCF client types also have overloads that enable you to programmatically specify this information.</span></span>  
  
 <span data-ttu-id="0732a-147">例如，上述示例中所使用的 `ISampleService` 的生成的配置文件包含以下终结点信息。</span><span class="sxs-lookup"><span data-stu-id="0732a-147">For example, a generated configuration file for an `ISampleService` used in the preceding examples contains the following endpoint information.</span></span>  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 <span data-ttu-id="0732a-148">此配置文件在 `<client>` 元素中指定目标终结点。</span><span class="sxs-lookup"><span data-stu-id="0732a-148">This configuration file specifies a target endpoint in the `<client>` element.</span></span> <span data-ttu-id="0732a-149">有关使用多个目标终结点的详细信息，请参阅 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> 或 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> 构造函数。</span><span class="sxs-lookup"><span data-stu-id="0732a-149">For more information about using multiple target endpoints, see the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> constructors.</span></span>  
  
## <a name="calling-operations"></a><span data-ttu-id="0732a-150">调用操作</span><span class="sxs-lookup"><span data-stu-id="0732a-150">Calling Operations</span></span>  
 <span data-ttu-id="0732a-151">创建并配置客户端对象后，创建一个 try/catch 块，调用操作的方式与在本地对象时相同，并关闭 WCF 客户端对象。</span><span class="sxs-lookup"><span data-stu-id="0732a-151">Once you have a client object created and configured, create a try/catch block, call operations in the same way that you would if the object were local, and close the WCF client object.</span></span> <span data-ttu-id="0732a-152">当客户端应用程序调用第一个操作时，WCF 将自动打开基础通道，并在回收对象时关闭基础通道。</span><span class="sxs-lookup"><span data-stu-id="0732a-152">When the client application calls the first operation, WCF automatically opens the underlying channel, and the underlying channel is closed when the object is recycled.</span></span> <span data-ttu-id="0732a-153">（或者，还可以在调用其他操作之前或之后显式打开和关闭该通道。）</span><span class="sxs-lookup"><span data-stu-id="0732a-153">(Alternatively, you can also explicitly open and close the channel prior to or subsequent to calling other operations.)</span></span>  
  
 <span data-ttu-id="0732a-154">例如，如果您具有以下服务协定：</span><span class="sxs-lookup"><span data-stu-id="0732a-154">For example, if you have the following service contract:</span></span>  
  
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
  
 <span data-ttu-id="0732a-155">可以通过创建 WCF 客户端对象并调用其方法来调用操作，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="0732a-155">You can call operations by creating a WCF client object and calling its methods, as the following code example demonstrates.</span></span> <span data-ttu-id="0732a-156">请注意，WCF 客户端对象的打开、调用和关闭发生在单个 try/catch 块中。</span><span class="sxs-lookup"><span data-stu-id="0732a-156">Note that the opening, calling, and closing of the WCF client object occurs within a single try/catch block.</span></span> <span data-ttu-id="0732a-157">有关详细信息，请参阅[使用 Wcf 客户端访问服务](./feature-details/accessing-services-using-a-client.md)和[使用关闭和中止来释放 WCF 客户端资源](./samples/use-close-abort-release-wcf-client-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-157">For more information, see [Accessing Services Using a WCF Client](./feature-details/accessing-services-using-a-client.md) and [Use Close and Abort to release WCF client resources](./samples/use-close-abort-release-wcf-client-resources.md).</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a><span data-ttu-id="0732a-158">处理错误</span><span class="sxs-lookup"><span data-stu-id="0732a-158">Handling Errors</span></span>  
 <span data-ttu-id="0732a-159">当打开基础客户端通道（无论是通过显式打开还是通过调用操作自动打开）、使用客户端或通道对象调用操作，或关闭基础客户端通道时，都会在客户端应用程序中出现异常。</span><span class="sxs-lookup"><span data-stu-id="0732a-159">Exceptions can occur in a client application when opening the underlying client channel (whether explicitly or automatically by calling an operation), using the client or channel object to call operations, or when closing the underlying client channel.</span></span> <span data-ttu-id="0732a-160">除了由操作返回的 SOAP 错误导致引发的任何 <xref:System.TimeoutException?displayProperty=nameWithType> 对象外，建议您至少将应用程序设置为能够处理可能的 <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> 和 <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> 异常。</span><span class="sxs-lookup"><span data-stu-id="0732a-160">It is recommended at a minimum that applications expect to handle possible <xref:System.TimeoutException?displayProperty=nameWithType> and <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> exceptions in addition to any <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> objects thrown as a result of SOAP faults returned by operations.</span></span> <span data-ttu-id="0732a-161">操作协定中指定的 SOAP 错误将作为 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> 在客户端应用程序中引发，此异常中的类型参数为 SOAP 错误的详细信息类型。</span><span class="sxs-lookup"><span data-stu-id="0732a-161">SOAP faults specified in the operation contract are raised to client applications as a <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the type parameter is the detail type of the SOAP fault.</span></span> <span data-ttu-id="0732a-162">有关在客户端应用程序中处理错误条件的详细信息，请参阅[发送和接收](sending-and-receiving-faults.md)错误。</span><span class="sxs-lookup"><span data-stu-id="0732a-162">For more information about handling error conditions in a client application, see [Sending and Receiving Faults](sending-and-receiving-faults.md).</span></span> <span data-ttu-id="0732a-163">有关演示如何在客户端中处理错误的完整示例，请参阅[预期异常](./samples/expected-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-163">For a complete sample the shows how to handle errors in a client, see [Expected Exceptions](./samples/expected-exceptions.md).</span></span>  
  
## <a name="configuring-and-securing-clients"></a><span data-ttu-id="0732a-164">配置和保护客户端</span><span class="sxs-lookup"><span data-stu-id="0732a-164">Configuring and Securing Clients</span></span>  
 <span data-ttu-id="0732a-165">若要配置客户端，请首先为客户端或通道对象加载目标终结点信息，通常是从配置文件中加载该信息，但是也可以使用客户端构造函数和属性以编程方式加载。</span><span class="sxs-lookup"><span data-stu-id="0732a-165">Configuring a client starts with the required loading of target endpoint information for the client or channel object, usually from a configuration file, although you can also load this information programmatically using the client constructors and properties.</span></span> <span data-ttu-id="0732a-166">但是，若要启用特定的客户端行为或实施一些安全方案还需要执行其他配置步骤。</span><span class="sxs-lookup"><span data-stu-id="0732a-166">However, additional configuration steps are required to enable certain client behavior and for many security scenarios.</span></span>  
  
 <span data-ttu-id="0732a-167">例如，服务协定的安全需求已在服务协定接口中声明，并且如果 Svcutil.exe 已创建了一个配置文件，则该文件通常会包含一个能够支持服务安全需求的绑定。</span><span class="sxs-lookup"><span data-stu-id="0732a-167">For example, security requirements for service contracts are declared in the service contract interface, and if Svcutil.exe created a configuration file, that file usually contains a binding that is capable of supporting the security requirements of the service.</span></span> <span data-ttu-id="0732a-168">但是在某些情况中，可能需要更多的安全配置，例如配置客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="0732a-168">In some cases, however, more security configuration may be required, such as configuring client credentials.</span></span> <span data-ttu-id="0732a-169">有关 WCF 客户端安全配置的完整信息，请参阅[保护客户端](securing-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-169">For complete information about the configuration of security for WCF clients, see [Securing Clients](securing-clients.md).</span></span>  
  
 <span data-ttu-id="0732a-170">此外，在客户端应用程序中还可以启用一些自定义修改，例如自定义运行时行为。</span><span class="sxs-lookup"><span data-stu-id="0732a-170">In addition, some custom modifications can be enabled in client applications, such as custom run-time behaviors.</span></span> <span data-ttu-id="0732a-171">有关如何配置自定义客户端行为的详细信息，请参阅[配置客户端行为](configuring-client-behaviors.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-171">For more information about how to configure a custom client behavior, see [Configuring Client Behaviors](configuring-client-behaviors.md).</span></span>  
  
## <a name="creating-callback-objects-for-duplex-services"></a><span data-ttu-id="0732a-172">为双工服务创建回调对象</span><span class="sxs-lookup"><span data-stu-id="0732a-172">Creating Callback Objects for Duplex Services</span></span>  
 <span data-ttu-id="0732a-173">双工服务指定一个回调协定，客户端应用程序必须实现该协定以便提供一个该服务能够根据协定要求调用的回调对象。</span><span class="sxs-lookup"><span data-stu-id="0732a-173">Duplex services specify a callback contract that the client application must implement in order to provide a callback object for the service to call according to the requirements of the contract.</span></span> <span data-ttu-id="0732a-174">虽然回调对象不是完整的服务（例如，您无法使用回调对象启动一个通道），但是为了实现和配置，这些回调对象可以被视为一种服务。</span><span class="sxs-lookup"><span data-stu-id="0732a-174">Although callback objects are not full services (for example, you cannot initiate a channel with a callback object), for the purposes of implementation and configuration they can be thought of as a kind of service.</span></span>  
  
 <span data-ttu-id="0732a-175">双工服务的客户端必须：</span><span class="sxs-lookup"><span data-stu-id="0732a-175">Clients of duplex services must:</span></span>  
  
- <span data-ttu-id="0732a-176">实现一个回调协定类。</span><span class="sxs-lookup"><span data-stu-id="0732a-176">Implement a callback contract class.</span></span>  
  
- <span data-ttu-id="0732a-177">创建回调协定实现类的实例，并使用它来创建传递给 WCF 客户端构造函数的 <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> 对象。</span><span class="sxs-lookup"><span data-stu-id="0732a-177">Create an instance of the callback contract implementation class and use it to create the <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> object that you pass to the WCF client constructor.</span></span>  
  
- <span data-ttu-id="0732a-178">调用操作并处理操作回调。</span><span class="sxs-lookup"><span data-stu-id="0732a-178">Invoke operations and handle operation callbacks.</span></span>  
  
 <span data-ttu-id="0732a-179">双工 WCF 客户端对象的功能类似于它们的非双工，但它们公开支持回调所需的功能，包括回调服务的配置。</span><span class="sxs-lookup"><span data-stu-id="0732a-179">Duplex WCF client objects function like their nonduplex counterparts, with the exception that they expose the functionality necessary to support callbacks, including the configuration of the callback service.</span></span>  
  
 <span data-ttu-id="0732a-180">例如，可以通过使用回调类的 <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> 属性 (Attribute) 的属性 (Property)，控制回调对象运行时行为的各个方面。</span><span class="sxs-lookup"><span data-stu-id="0732a-180">For example, you can control various aspects of callback object runtime behavior by using properties of the <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> attribute on the callback class.</span></span> <span data-ttu-id="0732a-181">另一个示例是使用 <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> 类将异常信息返回给调用回调对象的服务。</span><span class="sxs-lookup"><span data-stu-id="0732a-181">Another example is the use of the <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> class to enable the return of exception information to services that call the callback object.</span></span> <span data-ttu-id="0732a-182">有关详细信息，请参阅[双工服务](./feature-details/duplex-services.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-182">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span> <span data-ttu-id="0732a-183">有关完整示例，请参阅[双工](./samples/duplex.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-183">For a complete sample, see [Duplex](./samples/duplex.md).</span></span>  
  
 <span data-ttu-id="0732a-184">在运行 Internet 信息服务 (IIS) 5.1 的 Windows XP 计算机上，双工客户端必须使用 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> 类指定一个客户端基址，否则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="0732a-184">On Windows XP computers running Internet Information Services (IIS) 5.1, duplex clients must specify a client base address using the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> class or an exception is thrown.</span></span> <span data-ttu-id="0732a-185">下面的代码示例演示如何在代码中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0732a-185">The following code example shows how to do this in code.</span></span>  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 <span data-ttu-id="0732a-186">下面的代码演示如何在配置文件中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0732a-186">The following code shows how to do this in a configuration file</span></span>  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a><span data-ttu-id="0732a-187">异步调用服务</span><span class="sxs-lookup"><span data-stu-id="0732a-187">Calling Services Asynchronously</span></span>  
 <span data-ttu-id="0732a-188">如何调用操作完全取决于客户端开发人员。</span><span class="sxs-lookup"><span data-stu-id="0732a-188">How operations are called is entirely up to the client developer.</span></span> <span data-ttu-id="0732a-189">这是因为当在托管代码中表示组成操作的消息时，这些消息可以映射到同步或异步方法中。</span><span class="sxs-lookup"><span data-stu-id="0732a-189">This is because the messages that make up an operation can be mapped to either synchronous or asynchronous methods when expressed in managed code.</span></span> <span data-ttu-id="0732a-190">因此，如果想要生成异步调用操作的客户端，则可以使用 Svcutil.exe 通过 `/async` 选项生成异步客户端代码。</span><span class="sxs-lookup"><span data-stu-id="0732a-190">Therefore, if you want to build a client that calls operations asynchronously, you can use Svcutil.exe to generate asynchronous client code using the `/async` option.</span></span> <span data-ttu-id="0732a-191">有关详细信息，请参阅[如何：异步调用服务操作](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-191">For more information, see [How to: Call Service Operations Asynchronously](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span>  
  
## <a name="calling-services-using-wcf-client-channels"></a><span data-ttu-id="0732a-192">使用 WCF 客户端通道调用服务</span><span class="sxs-lookup"><span data-stu-id="0732a-192">Calling Services Using WCF Client Channels</span></span>  
 <span data-ttu-id="0732a-193">WCF 客户端类型扩展 <xref:System.ServiceModel.ClientBase%601>，该类型本身派生自 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> 接口以公开基础通道系统。</span><span class="sxs-lookup"><span data-stu-id="0732a-193">WCF client types extend <xref:System.ServiceModel.ClientBase%601>, which itself derives from <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> interface to expose the underlying channel system.</span></span> <span data-ttu-id="0732a-194">可以同时使用目标服务协定和 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 类来调用服务。</span><span class="sxs-lookup"><span data-stu-id="0732a-194">You can invoke services by using the target service contract with the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="0732a-195">有关详细信息，请参阅[WCF 客户端体系结构](./feature-details/client-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="0732a-195">For details, see [WCF Client Architecture](./feature-details/client-architecture.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0732a-196">请参阅</span><span class="sxs-lookup"><span data-stu-id="0732a-196">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
