---
title: 入门示例
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- basic samples [WCF], getting started
ms.assetid: 967a3d94-0261-49ff-b85a-20bb07f1af20
ms.openlocfilehash: a69dad31e750143af8fee94de9ccdbfd609737fe
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204478"
---
# <a name="getting-started-sample"></a><span data-ttu-id="effe7-102">入门示例</span><span class="sxs-lookup"><span data-stu-id="effe7-102">Getting Started Sample</span></span>
<span data-ttu-id="effe7-103">此入门示例演示如何实现典型的服务和典型的客户端使用 Windows Communication Foundation (WCF)。</span><span class="sxs-lookup"><span data-stu-id="effe7-103">The Getting Started sample demonstrates how to implement a typical service and a typical client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="effe7-104">此示例是所有其他基本技术示例的基础。</span><span class="sxs-lookup"><span data-stu-id="effe7-104">This sample is the basis for all other basic technology samples.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="effe7-105">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="effe7-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="effe7-106">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="effe7-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="effe7-107">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="effe7-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="effe7-108">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="effe7-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="effe7-109">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="effe7-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\GettingStarted\GettingStarted`  
  
 <span data-ttu-id="effe7-110">服务描述它在服务协定中执行的操作，服务协定由服务作为元数据公开。</span><span class="sxs-lookup"><span data-stu-id="effe7-110">The service describes the operations it performs in a service contract that it exposes publicly as metadata.</span></span> <span data-ttu-id="effe7-111">服务中还包含用来实现操作的代码。</span><span class="sxs-lookup"><span data-stu-id="effe7-111">The service also contains the code to implement the operations.</span></span>  
  
 <span data-ttu-id="effe7-112">客户端中包含服务协定的定义，以及一个用来访问服务的代理类。</span><span class="sxs-lookup"><span data-stu-id="effe7-112">The client contains a definition of the service contract and a proxy class for accessing the service.</span></span> <span data-ttu-id="effe7-113">从服务元数据中使用生成代理代码[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="effe7-113">The proxy code is generated from the service metadata using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
 <span data-ttu-id="effe7-114">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 上，服务承载于 Windows 激活服务 (WAS) 中。</span><span class="sxs-lookup"><span data-stu-id="effe7-114">On [!INCLUDE[wv](../../../../includes/wv-md.md)], the service is hosted in the Windows Activation Service (WAS).</span></span> <span data-ttu-id="effe7-115">在 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 和 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 上，服务由 Internet 信息服务 (IIS) 和 ASP.NET 承载。</span><span class="sxs-lookup"><span data-stu-id="effe7-115">On [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], it is hosted by Internet Information Services (IIS) and ASP.NET.</span></span> <span data-ttu-id="effe7-116">如果将服务承载于 IIS 或 WAS 中，那么，在首次访问服务时，系统将自动激活服务。</span><span class="sxs-lookup"><span data-stu-id="effe7-116">Hosting a service in IIS or WAS allows the service to be activated automatically when it is accessed for the first time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="effe7-117">如果你想要开始使用示例承载控制台应用程序而不是 IIS 中的服务，请参阅[自托管](../../../../docs/framework/wcf/samples/self-host.md)示例。</span><span class="sxs-lookup"><span data-stu-id="effe7-117">If you would prefer to get started with a sample that hosts the service in a console application instead of IIS, see the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span>  
  
 <span data-ttu-id="effe7-118">服务和客户端的配置文件设置中均指定了访问详细信息，这些设置在部署时提供了灵活性。</span><span class="sxs-lookup"><span data-stu-id="effe7-118">The service and client specify access details in configuration file settings, which provide flexibility at the time of deployment.</span></span> <span data-ttu-id="effe7-119">其中包括指定地址、绑定和协定的终结点定义。</span><span class="sxs-lookup"><span data-stu-id="effe7-119">This includes an endpoint definition that specifies an address, binding, and contract.</span></span> <span data-ttu-id="effe7-120">绑定为如何访问服务指定了传输和安全详细信息。</span><span class="sxs-lookup"><span data-stu-id="effe7-120">The binding specifies transport and security details for how the service is to be accessed.</span></span>  
  
 <span data-ttu-id="effe7-121">服务配置了一个运行时行为来发布其元数据。</span><span class="sxs-lookup"><span data-stu-id="effe7-121">The service configures a run-time behavior to publish its metadata.</span></span>  
  
 <span data-ttu-id="effe7-122">该服务实现定义“请求-答复”通信模式的协定。</span><span class="sxs-lookup"><span data-stu-id="effe7-122">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="effe7-123">该协定由 `ICalculator` 接口定义，此接口公开数学运算（加、减、乘和除）。</span><span class="sxs-lookup"><span data-stu-id="effe7-123">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="effe7-124">客户端向给定的数学运算发出请求，服务使用结果进行回复。</span><span class="sxs-lookup"><span data-stu-id="effe7-124">The client makes requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="effe7-125">服务实现一个 `ICalculator` 协定，下面的代码对该协定进行了定义。</span><span class="sxs-lookup"><span data-stu-id="effe7-125">The service implements an `ICalculator` contract that is defined in the following code.</span></span>  
  
```vb  
' Define a service contract.  
    <ServiceContract(Namespace:="http://Microsoft.Samples.GettingStarted")>  
     Public Interface ICalculator  
        <OperationContract()>  
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()>  
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()>  
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()>  
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
    End Interface  
```  
  
```csharp  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
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
```  
  
 <span data-ttu-id="effe7-126">服务实现计算并返回相应的结果，如下面的示例代码中所示。</span><span class="sxs-lookup"><span data-stu-id="effe7-126">The service implementation calculates and returns the appropriate result, as shown in the following example code.</span></span>  
  
```vb  
' Service class which implements the service contract.  
Public Class CalculatorService  
Implements ICalculator  
Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add  
Return n1 + n2  
End Function  
  
Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract  
Return n1 - n2  
End Function  
  
Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply  
Return n1 * n2  
End Function  
  
Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide  
Return n1 / n2  
End Function  
End Class  
```  
  
```csharp  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
```  
  
 <span data-ttu-id="effe7-127">服务会公开一个终结点，以便与使用配置文件 (Web.config) 定义的服务进行通信，如下面的示例配置中所示。</span><span class="sxs-lookup"><span data-stu-id="effe7-127">The service exposes an endpoint for communicating with the service, defined using a configuration file (Web.config), as shown in the following sample configuration.</span></span>  
  
```xaml  
<services>  
    <service   
        name="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- ICalculator is exposed at the base address provided by  
         host: http://localhost/servicemodelsamples/service.svc.  -->  
       <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
       ...  
    </service>  
</services>  
```  
  
 <span data-ttu-id="effe7-128">服务在 IIS 或 WAS 主机所提供的基址处公开该终结点。</span><span class="sxs-lookup"><span data-stu-id="effe7-128">The service exposes the endpoint at the base address provided by the IIS or WAS host.</span></span> <span data-ttu-id="effe7-129">绑定是用标准 <xref:System.ServiceModel.WSHttpBinding> 进行配置的，该标准配置提供 HTTP 通信以及用来进行寻址和实现安全性的标准 Web 服务协议。</span><span class="sxs-lookup"><span data-stu-id="effe7-129">The binding is configured with a standard <xref:System.ServiceModel.WSHttpBinding>, which provides HTTP communication and standard Web service protocols for addressing and security.</span></span> <span data-ttu-id="effe7-130">协定是由服务实现的 `ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="effe7-130">The contract is the `ICalculator` implemented by the service.</span></span>  
  
 <span data-ttu-id="effe7-131">经过配置之后，可以在访问服务`http://localhost/servicemodelsamples/service.svc`在同一台计算机上的客户端。</span><span class="sxs-lookup"><span data-stu-id="effe7-131">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="effe7-132">若要使远程计算机上的客户端能够访问该服务，必须指定完全限定域名，而不是本地主机。</span><span class="sxs-lookup"><span data-stu-id="effe7-132">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span>  
  
 <span data-ttu-id="effe7-133">默认情况下，框架不公开任何元数据。</span><span class="sxs-lookup"><span data-stu-id="effe7-133">The framework does not expose metadata by default.</span></span> <span data-ttu-id="effe7-134">在这种情况下，该服务将打开<xref:System.ServiceModel.Description.ServiceMetadataBehavior>，并公开一个元数据交换 (MEX) 终结点位于`http://localhost/servicemodelsamples/service.svc/mex`。</span><span class="sxs-lookup"><span data-stu-id="effe7-134">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> and exposes a metadata exchange (MEX) endpoint at `http://localhost/servicemodelsamples/service.svc/mex`.</span></span> <span data-ttu-id="effe7-135">下面的配置对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="effe7-135">The following configuration demonstrates this.</span></span>  
  
```xaml  
<system.serviceModel>  
  <services>  
    <service   
        name="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
      ...  
      <!-- the mex endpoint is explosed at  
       http://localhost/servicemodelsamples/service.svc/mex -->  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange" />  
    </service>  
  </services>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults  
   attribute to true-->  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
        <serviceMetadata httpGetEnabled="True"/>  
        <serviceDebug includeExceptionDetailInFaults="False" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="effe7-136">客户端通信使用给定的协定类型，通过生成的客户端类[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="effe7-136">The client communicates using a given contract type by using a client class that is generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="effe7-137">所生成的这个客户端类包含在 generatedClient.cs 文件或 generatedClient.vb 文件中。</span><span class="sxs-lookup"><span data-stu-id="effe7-137">This generated client is contained in the file generatedClient.cs or generatedClient.vb.</span></span> <span data-ttu-id="effe7-138">此实用工具检索给定服务的元数据，并生成要由客户端应用程序使用给定的协定类型进行通信的客户端。</span><span class="sxs-lookup"><span data-stu-id="effe7-138">This utility retrieves metadata for a given service and generates a client for use by the client application to communicate using a given contract type.</span></span> <span data-ttu-id="effe7-139">承载服务必须可用于生成客户端代码，因为将使用该服务来检索更新的元数据。</span><span class="sxs-lookup"><span data-stu-id="effe7-139">The hosted service must be available to generate the client code, because the service is used to retrieve the updated metadata.</span></span>  
  
 <span data-ttu-id="effe7-140">在客户端目录中通过从 SDK 命令提示运行以下命令来生成类型化代理：</span><span class="sxs-lookup"><span data-stu-id="effe7-140">Run the following command from the SDK command prompt in the client directory to generate the typed proxy:</span></span>  
  
```  
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
```  
  
 <span data-ttu-id="effe7-141">若要在 Visual Basic 中生成客户端，请从 SDK 命令提示中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="effe7-141">To generate client in Visual Basic type the following from the SDK command prompt:</span></span>  
  
 `Svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb`  
  
 <span data-ttu-id="effe7-142">通过使用所生成的客户端类，客户端可以通过配置相应的地址和绑定来访问给定的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="effe7-142">By using the generated client, the client can access a given service endpoint by configuring the appropriate address and binding.</span></span> <span data-ttu-id="effe7-143">像服务一样，客户端使用配置文件 (App.config) 来指定要与其通信的终结点。</span><span class="sxs-lookup"><span data-stu-id="effe7-143">Like the service, the client uses a configuration file (App.config) to specify the endpoint with which it wants to communicate.</span></span> <span data-ttu-id="effe7-144">客户端终结点配置由服务终结点的绝对地址、绑定和协定组成，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="effe7-144">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract, as shown in the following example.</span></span>  
  
```xaml  
<client>  
     <endpoint  
         address="http://localhost/servicemodelsamples/service.svc"   
         binding="wsHttpBinding"   
         contract=" Microsoft.ServiceModel.Samples.ICalculator" />  
</client>  
```  
  
 <span data-ttu-id="effe7-145">该客户端实现将实例化客户端，并使用类型化接口开始与服务通信，如下面的示例代码中所示。</span><span class="sxs-lookup"><span data-stu-id="effe7-145">The client implementation instantiates the client and uses the typed interface to begin communicating with the service, as shown in the following example code.</span></span>  
  
```vb  
' Create a client  
Dim client As New CalculatorClient()  
  
' Call the Add service operation.  
            Dim value1 = 100.0R  
            Dim value2 = 15.99R  
            Dim result = client.Add(value1, value2)  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)  
  
' Call the Subtract service operation.  
value1 = 145.00R  
value2 = 76.54R  
result = client.Subtract(value1, value2)  
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)  
  
' Call the Multiply service operation.  
value1 = 9.00R  
value2 = 81.25R  
result = client.Multiply(value1, value2)  
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)  
  
' Call the Divide service operation.  
value1 = 22.00R  
value2 = 7.00R  
result = client.Divide(value1, value2)  
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)  
  
'Closing the client gracefully closes the connection and cleans up resources  
```  
  
```csharp  
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
// Call the Subtract service operation.  
value1 = 145.00D;  
value2 = 76.54D;  
result = client.Subtract(value1, value2);  
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
// Call the Multiply service operation.  
value1 = 9.00D;  
value2 = 81.25D;  
result = client.Multiply(value1, value2);  
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
// Call the Divide service operation.  
value1 = 22.00D;  
value2 = 7.00D;  
result = client.Divide(value1, value2);  
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
//Closing the client releases all communication resources.  
client.Close();  
```  
  
 <span data-ttu-id="effe7-146">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="effe7-146">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="effe7-147">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="effe7-147">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="effe7-148">此入门示例演示了一种创建服务和客户端的标准方法。</span><span class="sxs-lookup"><span data-stu-id="effe7-148">The Getting Started sample shows the standard way to create a service and client.</span></span> <span data-ttu-id="effe7-149">另[基本](../../../../docs/framework/wcf/samples/basic-sample.md)在此示例，用于演示特定产品功能上构建。</span><span class="sxs-lookup"><span data-stu-id="effe7-149">The other [Basic](../../../../docs/framework/wcf/samples/basic-sample.md) build on this sample to demonstrate specific product features.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="effe7-150">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="effe7-150">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="effe7-151">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="effe7-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="effe7-152">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="effe7-152">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="effe7-153">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="effe7-153">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="effe7-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="effe7-154">See also</span></span>
- [<span data-ttu-id="effe7-155">如何：承载于托管应用程序的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="effe7-155">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="effe7-156">如何：承载在 IIS 中的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="effe7-156">How to: Host a WCF Service in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
