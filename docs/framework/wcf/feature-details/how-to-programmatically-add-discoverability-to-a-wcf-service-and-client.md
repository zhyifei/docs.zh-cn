---
title: "如何：以编程方式向 WCF 服务和客户端添加可检测性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a0a59788544a32b78e75ac25e787dcbae478451e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a><span data-ttu-id="dbd60-102">如何：以编程方式向 WCF 服务和客户端添加可检测性</span><span class="sxs-lookup"><span data-stu-id="dbd60-102">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>
<span data-ttu-id="dbd60-103">本主题说明如何检测到 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="dbd60-103">This topic explains how to make a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service discoverable.</span></span> <span data-ttu-id="dbd60-104">它基于[自承载](http://go.microsoft.com/fwlink/?LinkId=145523)示例。</span><span class="sxs-lookup"><span data-stu-id="dbd60-104">It is based on the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span>  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a><span data-ttu-id="dbd60-105">针对 Discovery 配置现有自承载服务示例</span><span class="sxs-lookup"><span data-stu-id="dbd60-105">To configure the existing Self-Host service sample for Discovery</span></span>  
  
1.  <span data-ttu-id="dbd60-106">在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中打开自承载解决方案。</span><span class="sxs-lookup"><span data-stu-id="dbd60-106">Open the Self-Host solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="dbd60-107">示例位于 TechnologySamples\Basic\Service\Hosting\SelfHost 目录中。</span><span class="sxs-lookup"><span data-stu-id="dbd60-107">The sample is located in the TechnologySamples\Basic\Service\Hosting\SelfHost directory.</span></span>  
  
2.  <span data-ttu-id="dbd60-108">将对 `System.ServiceModel.Discovery.dll` 的引用添加到服务项目中。</span><span class="sxs-lookup"><span data-stu-id="dbd60-108">Add a reference to `System.ServiceModel.Discovery.dll` to the service project.</span></span> <span data-ttu-id="dbd60-109">你可能会看到一个表明"系统错误消息。</span><span class="sxs-lookup"><span data-stu-id="dbd60-109">You may see an error message saying "System.</span></span> <span data-ttu-id="dbd60-110">ServiceModel.Discovery.dll 或其依赖项之一要求更高版本的[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]比指定项目中..."</span><span class="sxs-lookup"><span data-stu-id="dbd60-110">ServiceModel.Discovery.dll or one of its dependencies requires a later version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] than the one specified in the project …"</span></span> <span data-ttu-id="dbd60-111">如果你看到此消息，右键单击解决方案资源管理器中的项目，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="dbd60-111">If you see this message, right-click the project in the Solution Explorer and choose **Properties**.</span></span> <span data-ttu-id="dbd60-112">在**项目属性**窗口中，请确保**目标框架**是[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dbd60-112">In the **Project Properties** window, make sure that the **Target Framework** is [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
3.  <span data-ttu-id="dbd60-113">打开 Service.cs 文件并添加下面的 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="dbd60-113">Open the Service.cs file and add the following `using` statement.</span></span>  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4.  <span data-ttu-id="dbd60-114">在 `Main()` 方法的 `using` 语句内部，将一个 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> 实例添加到服务主机中。</span><span class="sxs-lookup"><span data-stu-id="dbd60-114">In the `Main()` method, inside the `using` statement, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance to the service host.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
        {  
            // Add a ServiceDiscoveryBehavior  
            serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());                  
  
            // ...  
        }  
    }  
    ```  
  
     <span data-ttu-id="dbd60-115"><xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> 指定自身应用到的服务可供检测。</span><span class="sxs-lookup"><span data-stu-id="dbd60-115">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> specifies that the service it is applied to is discoverable.</span></span>  
  
5.  <span data-ttu-id="dbd60-116">将 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 添加到服务主机中，位置紧随添加 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> 的代码之后。</span><span class="sxs-lookup"><span data-stu-id="dbd60-116">Add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the service host right after the code that adds the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span>  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     <span data-ttu-id="dbd60-117">此代码指定应将发现消息发送到标准 UDP 发现终结点。</span><span class="sxs-lookup"><span data-stu-id="dbd60-117">This code specifies that discovery messages should be sent to the standard UDP discovery endpoint.</span></span>  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a><span data-ttu-id="dbd60-118">创建使用发现功能调用服务的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="dbd60-118">To create a client application that uses discovery to call the service</span></span>  
  
1.  <span data-ttu-id="dbd60-119">向名为 `DiscoveryClientApp` 的解决方案添加一个新控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="dbd60-119">Add a new console application to the solution called `DiscoveryClientApp`.</span></span>  
  
2.  <span data-ttu-id="dbd60-120">添加对 `System.ServiceModel.dll` 和 `System.ServiceModel.Discovery.dll` 的引用</span><span class="sxs-lookup"><span data-stu-id="dbd60-120">Add a reference to `System.ServiceModel.dll` and `System.ServiceModel.Discovery.dll`</span></span>  
  
3.  <span data-ttu-id="dbd60-121">将 GeneratedClient.cs 和 App.config 文件从现有客户端项目复制到新的 DiscoveryClientApp 项目。</span><span class="sxs-lookup"><span data-stu-id="dbd60-121">Copy the GeneratedClient.cs and App.config files from the existing client project to the new DiscoveryClientApp project.</span></span> <span data-ttu-id="dbd60-122">要执行此操作，请右键单击中的文件**解决方案资源管理器**，选择**复制**，然后选择**DiscoveryClientApp**项目中，右键单击，选择**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="dbd60-122">To do this, right-click the files in the **Solution Explorer**, select **Copy**, and then select the **DiscoveryClientApp** project, right-click and select **Paste**.</span></span>  
  
4.  <span data-ttu-id="dbd60-123">打开 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="dbd60-123">Open Program.cs.</span></span>  
  
5.  <span data-ttu-id="dbd60-124">添加下面的 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="dbd60-124">Add the following `using` statements.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6.  <span data-ttu-id="dbd60-125">将一个名为 `FindCalculatorServiceAddress()` 的静态方法添加到 `Program` 类。</span><span class="sxs-lookup"><span data-stu-id="dbd60-125">Add a static method called `FindCalculatorServiceAddress()` to the `Program` class.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     <span data-ttu-id="dbd60-126">此方法使用发现功能搜索 `CalculatorService` 服务。</span><span class="sxs-lookup"><span data-stu-id="dbd60-126">This method uses discovery to search for the `CalculatorService` service.</span></span>  
  
7.  <span data-ttu-id="dbd60-127">在 `FindCalculatorServiceAddress` 方法内部，创建新 <xref:System.ServiceModel.Discovery.DiscoveryClient> 实例，以将 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 传递给构造函数。</span><span class="sxs-lookup"><span data-stu-id="dbd60-127">Inside the `FindCalculatorServiceAddress` method, create a new <xref:System.ServiceModel.Discovery.DiscoveryClient> instance, passing in a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the constructor.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     <span data-ttu-id="dbd60-128">此代码指示 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.Discovery.DiscoveryClient> 类应使用标准 UDP 发现终结点来发送和接收发现消息。</span><span class="sxs-lookup"><span data-stu-id="dbd60-128">This tells [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] that the <xref:System.ServiceModel.Discovery.DiscoveryClient> class should use the standard UDP discovery endpoint to send and receive discovery messages.</span></span>  
  
8.  <span data-ttu-id="dbd60-129">在下一行，调用 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 方法并指定包含要搜索的服务协定的 <xref:System.ServiceModel.Discovery.FindCriteria> 实例。</span><span class="sxs-lookup"><span data-stu-id="dbd60-129">On the next line, call the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method and specify a <xref:System.ServiceModel.Discovery.FindCriteria> instance that contains the service contract you want to search for.</span></span> <span data-ttu-id="dbd60-130">在本示例中，指定的是 `ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="dbd60-130">In this case, specify `ICalculator`.</span></span>  
  
    ```csharp  
    // Find ICalculatorService endpoints              
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. <span data-ttu-id="dbd60-131">调用 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 之后，查看是否至少有一个匹配服务，然后返回第一个匹配服务的 <xref:System.ServiceModel.EndpointAddress>。</span><span class="sxs-lookup"><span data-stu-id="dbd60-131">After the call to <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, check to see if there is at least one matching service and return the <xref:System.ServiceModel.EndpointAddress> of the first matching service.</span></span> <span data-ttu-id="dbd60-132">如果找不到匹配服务，则返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="dbd60-132">Otherwise return `null`.</span></span>  
  
    ```csharp  
    if (findResponse.Endpoints.Count > 0)  
    {  
        return findResponse.Endpoints[0].Address;  
    }  
    else  
    {  
        return null;  
    }  
    ```  
  
10. <span data-ttu-id="dbd60-133">将名为 `InvokeCalculatorService` 的静态方法添加到 `Program` 类。</span><span class="sxs-lookup"><span data-stu-id="dbd60-133">Add a static method named `InvokeCalculatorService` to the `Program` class.</span></span>  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     <span data-ttu-id="dbd60-134">此方法使用从 `FindCalculatorServiceAddress` 返回的终结点地址调用计算器服务。</span><span class="sxs-lookup"><span data-stu-id="dbd60-134">This method uses the endpoint address returned from `FindCalculatorServiceAddress` to call the calculator service.</span></span>  
  
11. <span data-ttu-id="dbd60-135">在 `InvokeCalculatorService` 方法的内部，创建 `CalculatorServiceClient` 类的实例。</span><span class="sxs-lookup"><span data-stu-id="dbd60-135">Inside the `InvokeCalculatorService` method, create an instance of the `CalculatorServiceClient` class.</span></span> <span data-ttu-id="dbd60-136">此类由[自承载](http://go.microsoft.com/fwlink/?LinkId=145523)示例。</span><span class="sxs-lookup"><span data-stu-id="dbd60-136">This class is defined by the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span> <span data-ttu-id="dbd60-137">并且是使用 Svcutil.exe 生成的。</span><span class="sxs-lookup"><span data-stu-id="dbd60-137">It was generated using Svcutil.exe.</span></span>  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. <span data-ttu-id="dbd60-138">在下一行，将客户端的终结点地址设置为从 `FindCalculatorServiceAddress()` 返回的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="dbd60-138">On the next line, set the endpoint address of the client to the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. <span data-ttu-id="dbd60-139">紧随上一步骤的代码之后，调用由计算器服务公开的方法。</span><span class="sxs-lookup"><span data-stu-id="dbd60-139">Immediately after the code for the previous step, call the methods exposed by the calculator service.</span></span>  
  
    ```csharp  
    Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
  
    // Call the Add service operation.  
    double result = client.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation.  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Multiply service operation.  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
    Console.WriteLine();  
  
    //Closing the client gracefully closes the connection and cleans up resources  
    client.Close();  
    ```  
  
14. <span data-ttu-id="dbd60-140">将以下代码添加到 `Main()` 类中的 `Program` 方法以调用 `FindCalculatorServiceAddress`。</span><span class="sxs-lookup"><span data-stu-id="dbd60-140">Add code to the `Main()` method in the `Program` class to call `FindCalculatorServiceAddress`.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. <span data-ttu-id="dbd60-141">在下一行，调用 `InvokeCalculatorService()`，并传递由 `FindCalculatorServiceAddress()` 返回的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="dbd60-141">On the next line, call the `InvokeCalculatorService()` and pass in the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="dbd60-142">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="dbd60-142">To test the application</span></span>  
  
1.  <span data-ttu-id="dbd60-143">打开具有特权的命令提示符并运行 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="dbd60-143">Open an elevated command prompt and run Service.exe.</span></span>  
  
2.  <span data-ttu-id="dbd60-144">打开命令提示符并运行 Discoveryclientapp.exe。</span><span class="sxs-lookup"><span data-stu-id="dbd60-144">Open a command prompt and run Discoveryclientapp.exe.</span></span>  
  
3.  <span data-ttu-id="dbd60-145">service.exe 的输出应类似于以下输出。</span><span class="sxs-lookup"><span data-stu-id="dbd60-145">The output from service.exe should look like the following output.</span></span>  
  
    ```Output  
    Received Add(100,15.99)  
    Return: 115.99  
    Received Subtract(100,15.99)  
    Return: 84.01  
    Received Multiply(100,15.99)  
    Return: 1599  
    Received Divide(100,15.99)  
    Return: 6.25390869293308  
    ```  
  
4.  <span data-ttu-id="dbd60-146">Discoveryclientapp.exe 的输出应类似于以下输出。</span><span class="sxs-lookup"><span data-stu-id="dbd60-146">The output from Discoveryclientapp.exe should look like the following output.</span></span>  
  
    ```Output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a><span data-ttu-id="dbd60-147">示例</span><span class="sxs-lookup"><span data-stu-id="dbd60-147">Example</span></span>  
 <span data-ttu-id="dbd60-148">下面是此示例的代码清单。</span><span class="sxs-lookup"><span data-stu-id="dbd60-148">The following is a listing of the code for this sample.</span></span> <span data-ttu-id="dbd60-149">因为此代码基于[自承载](http://go.microsoft.com/fwlink/?LinkId=145523)示例列出那些更改的文件。</span><span class="sxs-lookup"><span data-stu-id="dbd60-149">Because this code is based on the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample, only those files that are changed are listed.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="dbd60-150">自承载示例中，请参阅[设置说明](http://go.microsoft.com/fwlink/?LinkId=145522)。</span><span class="sxs-lookup"><span data-stu-id="dbd60-150"> the Self-Host sample, see [Setup Instructions](http://go.microsoft.com/fwlink/?LinkId=145522).</span></span>  
  
```csharp  
// Service.cs  
using System;  
using System.Configuration;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
  
namespace Microsoft.ServiceModel.Samples  
{  
    // See SelfHost sample for service contract and implementation  
    // ...  
  
        // Host the service within this EXE console application.  
        public static void Main()  
        {  
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
            {  
                // Add the ServiceDiscoveryBehavior to make the service discoverable  
                serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
                serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
  
                // Open the ServiceHost to create listeners and start listening for messages.  
                serviceHost.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
            }  
        }  
    }  
}  
```  
  
```csharp  
// Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
using Microsoft.ServiceModel.Samples;  
using System.Text;  
  
namespace DiscoveryClientApp  
{  
    class Program  
    {  
        static EndpointAddress FindCalculatorServiceAddress()  
        {  
            // Create DiscoveryClient  
            DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
            // Find ICalculatorService endpoints              
            FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
  
            if (findResponse.Endpoints.Count > 0)  
            {  
                return findResponse.Endpoints[0].Address;  
            }  
            else  
            {  
                return null;  
            }  
        }  
  
        static void InvokeCalculatorService(EndpointAddress endpointAddress)  
        {  
            // Create a client  
            CalculatorClient client = new CalculatorClient();  
  
            // Connect to the discovered service endpoint  
            client.Endpoint.Address = endpointAddress;  
  
            Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
            double value1 = 100.00D;  
            double value2 = 15.99D;  
  
            // Call the Add service operation.  
            double result = client.Add(value1, value2);  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Subtract service operation.  
            result = client.Subtract(value1, value2);  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Multiply service operation.  
            result = client.Multiply(value1, value2);  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Divide service operation.  
            result = client.Divide(value1, value2);  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
            Console.WriteLine();  
  
            //Closing the client gracefully closes the connection and cleans up resources  
            client.Close();  
        }  
        static void Main(string[] args)  
        {  
            EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
  
            if (endpointAddress != null)  
            {  
                InvokeCalculatorService(endpointAddress);  
            }  
  
            Console.WriteLine("Press <ENTER> to exit.");  
            Console.ReadLine();  
  
        }  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="dbd60-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbd60-151">See Also</span></span>  
 [<span data-ttu-id="dbd60-152">WCF 发现概述</span><span class="sxs-lookup"><span data-stu-id="dbd60-152">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="dbd60-153">WCF 发现对象模型</span><span class="sxs-lookup"><span data-stu-id="dbd60-153">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)
