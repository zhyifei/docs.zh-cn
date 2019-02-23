---
title: 如何托管并运行基本的 Windows Communication Foundation 服务
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 73633c2c6119204f2fb608b32ae794a2e07b27d0
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747069"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="4f346-102">如何托管并运行基本的 Windows Communication Foundation 服务</span><span class="sxs-lookup"><span data-stu-id="4f346-102">How to host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="4f346-103">这是创建 Windows Communication Foundation (WCF) 应用程序所需六项任务中的第三项。</span><span class="sxs-lookup"><span data-stu-id="4f346-103">This is the third of six tasks required to create a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="4f346-104">有关全部六项任务的概述，请参阅[入门教程](getting-started-tutorial.md)主题。</span><span class="sxs-lookup"><span data-stu-id="4f346-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="4f346-105">本主题说明如何在控制台应用程序中承载 Windows Communication Foundation (WCF) 服务。</span><span class="sxs-lookup"><span data-stu-id="4f346-105">This topic describes how to host a Windows Communication Foundation (WCF) service in a console application.</span></span> <span data-ttu-id="4f346-106">此过程包含以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4f346-106">This procedure consists of the following steps:</span></span>

- <span data-ttu-id="4f346-107">创建用于承载服务的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="4f346-107">Create a console application project to host the service.</span></span>

- <span data-ttu-id="4f346-108">为服务创建服务主机。</span><span class="sxs-lookup"><span data-stu-id="4f346-108">Create a service host for the service.</span></span>

- <span data-ttu-id="4f346-109">启用元数据交换。</span><span class="sxs-lookup"><span data-stu-id="4f346-109">Enable metadata exchange.</span></span>

- <span data-ttu-id="4f346-110">打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="4f346-110">Open the service host.</span></span>

<span data-ttu-id="4f346-111">在过程后面的以下示例中提供了在此任务中编写的代码的完整清单。</span><span class="sxs-lookup"><span data-stu-id="4f346-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>

## <a name="create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="4f346-112">创建新的控制台应用程序以承载服务</span><span class="sxs-lookup"><span data-stu-id="4f346-112">Create a new console application to host the service</span></span>

1. <span data-ttu-id="4f346-113">通过右键单击入门解决方案并选择 Visual Studio 中创建新的控制台应用程序项目**外** > **新项目**。</span><span class="sxs-lookup"><span data-stu-id="4f346-113">Create a new Console Application project in Visual Studio by right-clicking on the Getting Started solution and selecting **Add** > **New Project**.</span></span> <span data-ttu-id="4f346-114">在**添加新项目**对话框中的，在左侧，选择**Windows Desktop**类别中的下**Visual C#** 或者**Visual Basic**。</span><span class="sxs-lookup"><span data-stu-id="4f346-114">In the **Add New Project** dialog, on the left-hand side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> <span data-ttu-id="4f346-115">选择**控制台应用 (.NET Framework)** 模板，然后命名项目**GettingStartedHost**。</span><span class="sxs-lookup"><span data-stu-id="4f346-115">Select the **Console App (.NET Framework)** template, and then name the project **GettingStartedHost**.</span></span>

2. <span data-ttu-id="4f346-116">将对 GettingStartedLib 项目的引用添加到 GettingStartedHost 项目。</span><span class="sxs-lookup"><span data-stu-id="4f346-116">Add a reference to the GettingStartedLib project to the GettingStartedHost project.</span></span> <span data-ttu-id="4f346-117">右键单击**引用**文件夹中的 GettingStartedHost 项目下**解决方案资源管理器**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="4f346-117">Right-click on the **References** folder under the GettingStartedHost project in **Solution Explorer**, and then select **Add Reference**.</span></span> <span data-ttu-id="4f346-118">在中**添加引用**对话框中，选择**解决方案**在对话框的左侧，在对话框的中心部分选择 GettingStartedLib，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="4f346-118">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog, select GettingStartedLib in the center section of the dialog, and then choose **Add**.</span></span> <span data-ttu-id="4f346-119">这使 GettingStartedLib 项目中定义的类型可用于 GettingStartedHost 项目。</span><span class="sxs-lookup"><span data-stu-id="4f346-119">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>

3. <span data-ttu-id="4f346-120">将对 System.ServiceModel 的引用添加到 GettingStartedHost 项目。</span><span class="sxs-lookup"><span data-stu-id="4f346-120">Add a reference to System.ServiceModel to the GettingStartedHost project.</span></span> <span data-ttu-id="4f346-121">右键单击**引用**文件夹中的 GettingStartedHost 项目下**解决方案资源管理器**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="4f346-121">Right-click the **References** folder under the GettingStartedHost project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="4f346-122">在中**添加引用**对话框中，选择**Framework**下的对话框左侧**程序集**。</span><span class="sxs-lookup"><span data-stu-id="4f346-122">In the **Add Reference** dialog, select **Framework** on the left-hand side of the dialog under **Assemblies**.</span></span> <span data-ttu-id="4f346-123">找到并选择**System.ServiceModel**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="4f346-123">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> <span data-ttu-id="4f346-124">通过选择保存解决方案**文件** > **全部保存**。</span><span class="sxs-lookup"><span data-stu-id="4f346-124">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="host-the-service"></a><span data-ttu-id="4f346-125">托管服务</span><span class="sxs-lookup"><span data-stu-id="4f346-125">Host the service</span></span>

<span data-ttu-id="4f346-126">打开 Program.cs 或 Module.vb 文件，并输入以下代码：</span><span class="sxs-lookup"><span data-stu-id="4f346-126">Open the Program.cs or Module.vb file and enter the following code:</span></span>

```csharp
using System;
using System.ServiceModel;
using System.ServiceModel.Description;
using GettingStartedLib;

namespace GettingStartedHost
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 1 Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 Create a ServiceHost instance
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 Start the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
                selfHost.Close();
            }
            catch (CommunicationException ce)
            {
                Console.WriteLine("An exception occurred: {0}", ce.Message);
                selfHost.Abort();
            }
        }
    }
}
```

```vb
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 Create a URI to serve as the base address
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted")

            ' Step 2 Create a ServiceHost instance
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
           Try

                ' Step 3 Add a service endpoint
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 Enable metadata exchange.
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 Start the service
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

<span data-ttu-id="4f346-127">**步骤 1** -创建要保存服务的基址的 Uri 类的实例。</span><span class="sxs-lookup"><span data-stu-id="4f346-127">**Step 1** - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="4f346-128">服务由包含一个基址和一个可选 URI 的 URL 来标识。</span><span class="sxs-lookup"><span data-stu-id="4f346-128">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="4f346-129">基址的格式如下：[传输协议]://[计算机名或域][:可选端口号]/[可选 URI 段]。计算器服务的基址使用 HTTP 传输协议、本地主机、端口 8000 和 URI 段“GettingStarted”</span><span class="sxs-lookup"><span data-stu-id="4f346-129">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>

<span data-ttu-id="4f346-130">**步骤 2** – 创建的实例<xref:System.ServiceModel.ServiceHost>类以承载服务。</span><span class="sxs-lookup"><span data-stu-id="4f346-130">**Step 2** – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="4f346-131">构造函数采用两个参数：实现服务协定的类的类型，以及服务的基址。</span><span class="sxs-lookup"><span data-stu-id="4f346-131">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>

<span data-ttu-id="4f346-132">**步骤 3** – 创建<xref:System.ServiceModel.Description.ServiceEndpoint>实例。</span><span class="sxs-lookup"><span data-stu-id="4f346-132">**Step 3** – Creates a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="4f346-133">服务终结点由地址、绑定和服务协定组成。</span><span class="sxs-lookup"><span data-stu-id="4f346-133">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="4f346-134">因此<xref:System.ServiceModel.Description.ServiceEndpoint> 构造函数采用服务协定接口类型、绑定和地址。</span><span class="sxs-lookup"><span data-stu-id="4f346-134">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="4f346-135">服务协定是在服务类型中定义和实现的 `ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="4f346-135">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="4f346-136">在此示例中使用的绑定是 <xref:System.ServiceModel.WSHttpBinding>，这是用于连接到符合 WS-＊ 规范的终结点的内置绑定。</span><span class="sxs-lookup"><span data-stu-id="4f346-136">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="4f346-137">有关 WCF 绑定的详细信息，请参阅 [WCF 绑定概述](bindings-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4f346-137">For more information about WCF bindings, see [WCF Bindings Overview](bindings-overview.md).</span></span> <span data-ttu-id="4f346-138">该地址追加到基址以标识终结点。</span><span class="sxs-lookup"><span data-stu-id="4f346-138">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="4f346-139">在此代码中指定的地址为"CalculatorService"，因此终结点的完全限定的地址是`"http://localhost:8000/GettingStarted/CalculatorService"`。</span><span class="sxs-lookup"><span data-stu-id="4f346-139">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f346-140">使用 .NET Framework 4 或更高版本时，添加服务终结点是可选的。</span><span class="sxs-lookup"><span data-stu-id="4f346-140">Adding a service endpoint is optional when using .NET Framework 4 or later.</span></span> <span data-ttu-id="4f346-141">在这些版本中，如果在代码或配置中未添加任何终结点，则 WCF 为该服务实现的基址和协定的每个组合添加一个默认终结点。</span><span class="sxs-lookup"><span data-stu-id="4f346-141">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="4f346-142">有关默认终结点的详细信息，请参阅[指定终结点地址](specifying-an-endpoint-address.md)。</span><span class="sxs-lookup"><span data-stu-id="4f346-142">For more information about default endpoints see [Specifying an Endpoint Address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="4f346-143">有关默认终结点、绑定和行为的详细信息，请参阅[简化配置](simplified-configuration.md)和 [WCF 服务的简化配置](./samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="4f346-143">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

<span data-ttu-id="4f346-144">**步骤 4** -启用元数据交换。</span><span class="sxs-lookup"><span data-stu-id="4f346-144">**Step 4** – Enable metadata exchange.</span></span> <span data-ttu-id="4f346-145">客户端将使用元数据交换来生成将用于调用服务操作的代理。</span><span class="sxs-lookup"><span data-stu-id="4f346-145">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="4f346-146">要启用元数据交换，请创建 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 实例，将其 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> 属性设置为 `true`，并将行为添加到 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 实例的 <xref:System.ServiceModel.ServiceHost> 集合。</span><span class="sxs-lookup"><span data-stu-id="4f346-146">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

<span data-ttu-id="4f346-147">**步骤 5** – 打开<xref:System.ServiceModel.ServiceHost>侦听传入消息。</span><span class="sxs-lookup"><span data-stu-id="4f346-147">**Step 5** – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="4f346-148">注意，代码会等待用户按 Enter。</span><span class="sxs-lookup"><span data-stu-id="4f346-148">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="4f346-149">如果不这样做，应用程序将立即关闭，并且服务将关闭。另请注意，使用了 try/catch 块。</span><span class="sxs-lookup"><span data-stu-id="4f346-149">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="4f346-150">在实例化 <xref:System.ServiceModel.ServiceHost> 后，所有其他代码放置在 try/catch 块中。</span><span class="sxs-lookup"><span data-stu-id="4f346-150">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="4f346-151">有关安全捕获引发的异常详细信息<xref:System.ServiceModel.ServiceHost>，请参阅[使用关闭和中止发布 WCF 客户端资源](samples/use-close-abort-release-wcf-client-resources.md)</span><span class="sxs-lookup"><span data-stu-id="4f346-151">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f346-152">当添加 WCF 服务库时，Visual Studio 可以承载它为您调试通过启动服务主机时。</span><span class="sxs-lookup"><span data-stu-id="4f346-152">When you add a WCF Service Library, Visual Studio can host it for you when you debug by starting a service host.</span></span> <span data-ttu-id="4f346-153">若要避免冲突可以禁用此。</span><span class="sxs-lookup"><span data-stu-id="4f346-153">To avoid conflicts you can disable this.</span></span> 
> 1. <span data-ttu-id="4f346-154">打开 GettingStartedLib 项目属性。</span><span class="sxs-lookup"><span data-stu-id="4f346-154">Open Project Properties for GettingStartedLib.</span></span>
> 2. <span data-ttu-id="4f346-155">转到**WCF 选项**并取消选中**启动 WCF 服务主机时调试**。</span><span class="sxs-lookup"><span data-stu-id="4f346-155">Go to **WCF Options** and uncheck **Start WCF Service Host when debugging**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="4f346-156">验证服务正常工作</span><span class="sxs-lookup"><span data-stu-id="4f346-156">Verify the service is working</span></span>

1. <span data-ttu-id="4f346-157">运行 GettingStartedHost 控制台应用程序从 Visual Studio 内部。</span><span class="sxs-lookup"><span data-stu-id="4f346-157">Run the GettingStartedHost console application from inside Visual Studio.</span></span>

   <span data-ttu-id="4f346-158">必须使用管理员特权运行服务。</span><span class="sxs-lookup"><span data-stu-id="4f346-158">The service must be run with administrator privileges.</span></span> <span data-ttu-id="4f346-159">使用管理员特权打开 Visual Studio，因为 GettingStartedHost 也是使用管理员特权运行。</span><span class="sxs-lookup"><span data-stu-id="4f346-159">Because Visual Studio was opened with administrator privileges, GettingStartedHost is also run with administrator privileges.</span></span> <span data-ttu-id="4f346-160">此外可以打开新命令提示符处使用**以管理员身份运行**并运行 service.exe。</span><span class="sxs-lookup"><span data-stu-id="4f346-160">You can also open a new command prompt using **Run as administrator** and run service.exe within it.</span></span>

2. <span data-ttu-id="4f346-161">打开 web 浏览器并浏览到服务的调试页在`http://localhost:8000/GettingStarted/`。</span><span class="sxs-lookup"><span data-stu-id="4f346-161">Open a web browser and browse to the service's debug page at `http://localhost:8000/GettingStarted/`.</span></span> <span data-ttu-id="4f346-162">**请注意 ！结束斜杠很重要。**</span><span class="sxs-lookup"><span data-stu-id="4f346-162">**Note! Ending slash is significant.**</span></span>

## <a name="example"></a><span data-ttu-id="4f346-163">示例</span><span class="sxs-lookup"><span data-stu-id="4f346-163">Example</span></span>

<span data-ttu-id="4f346-164">下面的示例包括本教程中前面步骤的服务协定和实现，并将服务承载于控制台应用程序中。</span><span class="sxs-lookup"><span data-stu-id="4f346-164">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>

<span data-ttu-id="4f346-165">若要此命令行编译器进行编译，编译 IService1.cs 和 Service1.cs 到引用的类库`System.ServiceModel.dll`。</span><span class="sxs-lookup"><span data-stu-id="4f346-165">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library that references `System.ServiceModel.dll`.</span></span> <span data-ttu-id="4f346-166">将 Program.cs 编译为一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="4f346-166">Compile Program.cs as a console application.</span></span>

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
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

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```csharp
using System;
using System.ServiceModel;
using System.ServiceModel.Description;
using GettingStartedLib;

namespace GettingStartedHost
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 of the hosting procedure: Create ServiceHost
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 of the hosting procedure: Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 of the hosting procedure: Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
                selfHost.Close();
            }
            catch (CommunicationException ce)
            {
                Console.WriteLine("An exception occurred: {0}", ce.Message);
                selfHost.Abort();
            }
        }
    }
}
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
    Public Interface ICalculator

        <OperationContract()> _
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
End Namespace
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

```vb
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

            ' Step 2 of the hosting procedure: Create ServiceHost
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
            Try

                ' Step 3 of the hosting procedure: Add a service endpoint.
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 of the hosting procedure: Enable metadata exchange.
                ' Enable metadata exchange
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

> [!NOTE]
> <span data-ttu-id="4f346-167">此类服务需要在计算机上注册 HTTP 地址以进行侦听的权限。</span><span class="sxs-lookup"><span data-stu-id="4f346-167">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="4f346-168">管理员帐户具有此权限，但对于非管理员帐户来说，必须授予对 HTTP 命名空间的权限。</span><span class="sxs-lookup"><span data-stu-id="4f346-168">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="4f346-169">有关如何配置命名空间预留的详细信息，请参阅[配置 HTTP 和 HTTPS](feature-details/configuring-http-and-https.md)。</span><span class="sxs-lookup"><span data-stu-id="4f346-169">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="4f346-170">在 Visual Studio 下运行时，必须使用管理员特权运行 service.exe。</span><span class="sxs-lookup"><span data-stu-id="4f346-170">When running under Visual Studio, the service.exe must be run with administrator privileges.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4f346-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4f346-171">Next steps</span></span>

<span data-ttu-id="4f346-172">此时服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="4f346-172">Now the service is running.</span></span> <span data-ttu-id="4f346-173">在下一个任务中，将创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="4f346-173">In the next task, you create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4f346-174">如何：创建 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="4f346-174">How to: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)

<span data-ttu-id="4f346-175">有关疑难解答的信息，请参阅[疑难解答入门教程](troubleshooting-the-getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="4f346-175">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](troubleshooting-the-getting-started-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4f346-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f346-176">See also</span></span>

- [<span data-ttu-id="4f346-177">入门</span><span class="sxs-lookup"><span data-stu-id="4f346-177">Getting Started</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="4f346-178">自承载</span><span class="sxs-lookup"><span data-stu-id="4f346-178">Self-Host</span></span>](samples/self-host.md)
- [<span data-ttu-id="4f346-179">托管服务</span><span class="sxs-lookup"><span data-stu-id="4f346-179">Hosting Services</span></span>](hosting-services.md)
