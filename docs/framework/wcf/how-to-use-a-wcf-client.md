---
title: 如何：使用 Windows Communication Foundation 客户端
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 12e911fb899cb85121c129b762828cdda01e64f1
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532579"
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="38e38-102">如何：使用 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="38e38-102">How to: Use a Windows Communication Foundation Client</span></span>

<span data-ttu-id="38e38-103">这是创建基本 Windows Communication Foundation (WCF) 应用程序所需的六项任务的最后一个。</span><span class="sxs-lookup"><span data-stu-id="38e38-103">This is the last of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="38e38-104">有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。</span><span class="sxs-lookup"><span data-stu-id="38e38-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="38e38-105">一旦创建并配置 Windows Communication Foundation (WCF) 代理，可以创建一个客户端实例和可以编译客户端应用程序，并将其用于与 WCF 服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="38e38-105">Once a Windows Communication Foundation (WCF) proxy has been created and configured, a client instance can be created and the client application can be compiled and used to communicate with the WCF service.</span></span> <span data-ttu-id="38e38-106">本主题介绍用于实例化和使用 WCF 客户端的过程。</span><span class="sxs-lookup"><span data-stu-id="38e38-106">This topic describes procedures for instantiating and using a WCF client.</span></span> <span data-ttu-id="38e38-107">此过程执行三项操作：</span><span class="sxs-lookup"><span data-stu-id="38e38-107">This procedure does three things:</span></span>

1.  <span data-ttu-id="38e38-108">实例化 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="38e38-108">Instantiates a WCF client.</span></span>

2.  <span data-ttu-id="38e38-109">从生成的代理调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="38e38-109">Calls the service operations from the generated proxy.</span></span>

3.  <span data-ttu-id="38e38-110">在完成操作调用后关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="38e38-110">Closes the client once the operation call is completed.</span></span>

## <a name="use-a-windows-communication-foundation-client"></a><span data-ttu-id="38e38-111">使用 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="38e38-111">Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="38e38-112">打开 GettingStartedClient 项目中的 Program.cs 或 program.vb 文件，然后将现有代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="38e38-112">Open the Program.cs or Program.vb file from the GettingStartedClient project and replace the existing code with the following code:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using GettingStartedClient.ServiceReference1;

namespace GettingStartedClient
{
    class Program
    {
        static void Main(string[] args)
        {
            //Step 1: Create an instance of the WCF proxy.
            CalculatorClient client = new CalculatorClient();

            // Step 2: Call the service operations.
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

            //Step 3: Closing the client gracefully closes the connection and cleans up resources.
            client.Close();
        }
    }
}
```

```vb
Imports System
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClientVB2.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy
        Dim Client As New CalculatorClient()

        'Step 2: Call the service operations.
        'Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        'Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        'Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        'Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Closing the client gracefully closes the connection and cleans up resources.
        Client.Close()

        Console.WriteLine()
        Console.WriteLine("Press <ENTER> to terminate client.")
        Console.ReadLine()

    End Sub

End Module
```

<span data-ttu-id="38e38-113">请注意`using`或`Imports`导入语句`GettingStartedClient.ServiceReference1`。</span><span class="sxs-lookup"><span data-stu-id="38e38-113">Notice the `using` or `Imports` statement that imports the `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="38e38-114">这将生成的代码导入**添加服务引用**Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="38e38-114">This imports the code generated by **Add Service Reference** in Visual Studio.</span></span> <span data-ttu-id="38e38-115">该代码实例化 WCF 代理然后调用由计算器服务公开的服务操作的每个，关闭代理，并终止。</span><span class="sxs-lookup"><span data-stu-id="38e38-115">The code instantiates the WCF proxy and then calls each of the service operations exposed by the calculator service, closes the proxy, and terminates.</span></span>

<span data-ttu-id="38e38-116">现在，您已经完成了教程。</span><span class="sxs-lookup"><span data-stu-id="38e38-116">You have now completed the tutorial.</span></span> <span data-ttu-id="38e38-117">您定义了服务协定、实现了服务协定、生成了 WCF 代理、配置了 WCF 客户端应用程序，然后使用代理调用了服务操作。</span><span class="sxs-lookup"><span data-stu-id="38e38-117">You defined a service contract, implemented the service contract, generated a WCF proxy, configured a WCF client application, and then used the proxy to call service operations.</span></span> <span data-ttu-id="38e38-118">若要测试应用程序，首先运行 GettingStartedHost 以启动服务，然后运行 GettingStartedClient。</span><span class="sxs-lookup"><span data-stu-id="38e38-118">To test out the application, first run GettingStartedHost to start the service and then run GettingStartedClient.</span></span>

<span data-ttu-id="38e38-119">GettingStartedHost 的输出应类似于：</span><span class="sxs-lookup"><span data-stu-id="38e38-119">The output from GettingStartedHost should look like this:</span></span>

```text
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714
```

<span data-ttu-id="38e38-120">GettingStartedClient 的输出应类似于：</span><span class="sxs-lookup"><span data-stu-id="38e38-120">The output from GettingStartedClient should look like this:</span></span>

```text
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.
```

## <a name="see-also"></a><span data-ttu-id="38e38-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="38e38-121">See also</span></span>

- [<span data-ttu-id="38e38-122">生成客户端</span><span class="sxs-lookup"><span data-stu-id="38e38-122">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)
- [<span data-ttu-id="38e38-123">如何：创建客户端</span><span class="sxs-lookup"><span data-stu-id="38e38-123">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="38e38-124">入门教程</span><span class="sxs-lookup"><span data-stu-id="38e38-124">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="38e38-125">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="38e38-125">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="38e38-126">如何：创建双工协定</span><span class="sxs-lookup"><span data-stu-id="38e38-126">How to: Create a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="38e38-127">如何：使用双工协定访问服务</span><span class="sxs-lookup"><span data-stu-id="38e38-127">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="38e38-128">入门</span><span class="sxs-lookup"><span data-stu-id="38e38-128">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="38e38-129">自承载</span><span class="sxs-lookup"><span data-stu-id="38e38-129">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)