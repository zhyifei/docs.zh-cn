---
title: 如何：承载和运行基本的 Windows Communication Foundation 服务
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: b79c3246b7c12a3a99a5c68586387fc30573dcb6
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562289"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="9dde5-102">如何：承载和运行基本的 Windows Communication Foundation 服务</span><span class="sxs-lookup"><span data-stu-id="9dde5-102">How to: Host and Run a Basic Windows Communication Foundation Service</span></span>

<span data-ttu-id="9dde5-103">这是创建 Windows Communication Foundation (WCF) 应用程序所需六项任务中的第三项。</span><span class="sxs-lookup"><span data-stu-id="9dde5-103">This is the third of six tasks required to create a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="9dde5-104">有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。</span><span class="sxs-lookup"><span data-stu-id="9dde5-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="9dde5-105">本主题说明如何在控制台应用程序中承载 Windows Communication Foundation (WCF) 服务。</span><span class="sxs-lookup"><span data-stu-id="9dde5-105">This topic describes how to host a Windows Communication Foundation (WCF) service in a console application.</span></span> <span data-ttu-id="9dde5-106">此过程包含以下步骤：</span><span class="sxs-lookup"><span data-stu-id="9dde5-106">This procedure consists of the following steps:</span></span>

- <span data-ttu-id="9dde5-107">创建用于承载服务的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="9dde5-107">Create a console application project to host the service.</span></span>

- <span data-ttu-id="9dde5-108">为服务创建服务主机。</span><span class="sxs-lookup"><span data-stu-id="9dde5-108">Create a service host for the service.</span></span>

- <span data-ttu-id="9dde5-109">启用元数据交换。</span><span class="sxs-lookup"><span data-stu-id="9dde5-109">Enable metadata exchange.</span></span>

- <span data-ttu-id="9dde5-110">打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="9dde5-110">Open the service host.</span></span>

<span data-ttu-id="9dde5-111">在过程后面的以下示例中提供了在此任务中编写的代码的完整清单。</span><span class="sxs-lookup"><span data-stu-id="9dde5-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>

## <a name="create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="9dde5-112">创建新的控制台应用程序以承载服务</span><span class="sxs-lookup"><span data-stu-id="9dde5-112">Create a new console application to host the service</span></span>

1. <span data-ttu-id="9dde5-113">通过右键单击入门解决方案并选择 Visual Studio 中创建新的控制台应用程序项目**外** > **新项目**。</span><span class="sxs-lookup"><span data-stu-id="9dde5-113">Create a new Console Application project in Visual Studio by right-clicking on the Getting Started solution and selecting **Add** > **New Project**.</span></span> <span data-ttu-id="9dde5-114">在**添加新项目**对话框中的，在左侧，选择**Windows Desktop**类别中的下**Visual C#** 或者**Visual Basic**。</span><span class="sxs-lookup"><span data-stu-id="9dde5-114">In the **Add New Project** dialog, on the left-hand side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> <span data-ttu-id="9dde5-115">选择**控制台应用 (.NET Framework)** 模板，然后命名项目**GettingStartedHost**。</span><span class="sxs-lookup"><span data-stu-id="9dde5-115">Select the **Console App (.NET Framework)** template, and then name the project **GettingStartedHost**.</span></span>

2. <span data-ttu-id="9dde5-116">将对 GettingStartedLib 项目的引用添加到 GettingStartedHost 项目。</span><span class="sxs-lookup"><span data-stu-id="9dde5-116">Add a reference to the GettingStartedLib project to the GettingStartedHost project.</span></span> <span data-ttu-id="9dde5-117">右键单击**引用**文件夹中的 GettingStartedHost 项目下**解决方案资源管理器**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="9dde5-117">Right-click on the **References** folder under the GettingStartedHost project in **Solution Explorer**, and then select **Add Reference**.</span></span> <span data-ttu-id="9dde5-118">在中**添加引用**对话框中，选择**解决方案**在对话框的左侧，在对话框的中心部分选择 GettingStartedLib，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="9dde5-118">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog, select GettingStartedLib in the center section of the dialog, and then choose **Add**.</span></span> <span data-ttu-id="9dde5-119">这使 GettingStartedLib 项目中定义的类型可用于 GettingStartedHost 项目。</span><span class="sxs-lookup"><span data-stu-id="9dde5-119">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>

3. <span data-ttu-id="9dde5-120">将对 System.ServiceModel 的引用添加到 GettingStartedHost 项目。</span><span class="sxs-lookup"><span data-stu-id="9dde5-120">Add a reference to System.ServiceModel to the GettingStartedHost project.</span></span> <span data-ttu-id="9dde5-121">右键单击**引用**文件夹中的 GettingStartedHost 项目下**解决方案资源管理器**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="9dde5-121">Right-click the **References** folder under the GettingStartedHost project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="9dde5-122">在中**添加引用**对话框中，选择**Framework**下的对话框左侧**程序集**。</span><span class="sxs-lookup"><span data-stu-id="9dde5-122">In the **Add Reference** dialog, select **Framework** on the left-hand side of the dialog under **Assemblies**.</span></span> <span data-ttu-id="9dde5-123">找到并选择**System.ServiceModel**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="9dde5-123">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> <span data-ttu-id="9dde5-124">通过选择保存解决方案**文件** > **全部保存**。</span><span class="sxs-lookup"><span data-stu-id="9dde5-124">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="host-the-service"></a><span data-ttu-id="9dde5-125">托管服务</span><span class="sxs-lookup"><span data-stu-id="9dde5-125">Host the service</span></span>

<span data-ttu-id="9dde5-126">打开 Program.cs 或 Module.vb 文件，并输入以下代码：</span><span class="sxs-lookup"><span data-stu-id="9dde5-126">Open the Program.cs or Module.vb file and enter the following code:</span></span>

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
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")

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

<span data-ttu-id="9dde5-127">**步骤 1** -创建要保存服务的基址的 Uri 类的实例。</span><span class="sxs-lookup"><span data-stu-id="9dde5-127">**Step 1** - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="9dde5-128">服务由包含一个基址和一个可选 URI 的 URL 来标识。</span><span class="sxs-lookup"><span data-stu-id="9dde5-128">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="9dde5-129">基址的格式如下：[传输协议]://[计算机名或域][:可选端口号]/[可选 URI 段]。计算器服务的基址使用 HTTP 传输协议、本地主机、端口 8000 和 URI 段“GettingStarted”</span><span class="sxs-lookup"><span data-stu-id="9dde5-129">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>

<span data-ttu-id="9dde5-130">**步骤 2** – 创建的实例<xref:System.ServiceModel.ServiceHost>类以承载服务。</span><span class="sxs-lookup"><span data-stu-id="9dde5-130">**Step 2** – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="9dde5-131">构造函数采用两个参数：实现服务协定的类的类型，以及服务的基址。</span><span class="sxs-lookup"><span data-stu-id="9dde5-131">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>

<span data-ttu-id="9dde5-132">**步骤 3** – 创建<xref:System.ServiceModel.Description.ServiceEndpoint>实例。</span><span class="sxs-lookup"><span data-stu-id="9dde5-132">**Step 3** – Creates a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="9dde5-133">服务终结点由地址、绑定和服务协定组成。</span><span class="sxs-lookup"><span data-stu-id="9dde5-133">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="9dde5-134">因此<xref:System.ServiceModel.Description.ServiceEndpoint> 构造函数采用服务协定接口类型、绑定和地址。</span><span class="sxs-lookup"><span data-stu-id="9dde5-134">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="9dde5-135">服务协定是在服务类型中定义和实现的 `ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="9dde5-135">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="9dde5-136">在此示例中使用的绑定是 <xref:System.ServiceModel.WSHttpBinding>，这是用于连接到符合 WS-＊ 规范的终结点的内置绑定。</span><span class="sxs-lookup"><span data-stu-id="9dde5-136">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="9dde5-137">有关 WCF 绑定的详细信息，请参阅 [WCF 绑定概述](../../../docs/framework/wcf/bindings-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9dde5-137">For more information about WCF bindings, see [WCF Bindings Overview](../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="9dde5-138">该地址追加到基址以标识终结点。</span><span class="sxs-lookup"><span data-stu-id="9dde5-138">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="9dde5-139">在此代码中指定的地址为"CalculatorService"，因此终结点的完全限定的地址是`"http://localhost:8000/GettingStarted/CalculatorService"`。</span><span class="sxs-lookup"><span data-stu-id="9dde5-139">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"`.</span></span>

    > [!IMPORTANT]
    > Adding a service endpoint is optional when using .NET Framework 4 or later. In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service. For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md). For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).

<span data-ttu-id="9dde5-140">**步骤 4** -启用元数据交换。</span><span class="sxs-lookup"><span data-stu-id="9dde5-140">**Step 4** – Enable metadata exchange.</span></span> <span data-ttu-id="9dde5-141">客户端将使用元数据交换来生成将用于调用服务操作的代理。</span><span class="sxs-lookup"><span data-stu-id="9dde5-141">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="9dde5-142">要启用元数据交换，请创建 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 实例，将其 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> 属性设置为 `true`，并将行为添加到 <xref:System.ServiceModel.ServiceHost> 实例的 <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` 集合。</span><span class="sxs-lookup"><span data-stu-id="9dde5-142">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

<span data-ttu-id="9dde5-143">**步骤 5** – 打开<xref:System.ServiceModel.ServiceHost>侦听传入消息。</span><span class="sxs-lookup"><span data-stu-id="9dde5-143">**Step 5** – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="9dde5-144">注意，代码会等待用户按 Enter。</span><span class="sxs-lookup"><span data-stu-id="9dde5-144">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="9dde5-145">如果不这样做，应用程序将立即关闭，并且服务将关闭。另请注意，使用了 try/catch 块。</span><span class="sxs-lookup"><span data-stu-id="9dde5-145">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="9dde5-146">在实例化 <xref:System.ServiceModel.ServiceHost> 后，所有其他代码放置在 try/catch 块中。</span><span class="sxs-lookup"><span data-stu-id="9dde5-146">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="9dde5-147">有关 <xref:System.ServiceModel.ServiceHost> 引发的安全捕获异常的详细信息，请参阅[避免出现与 Using 语句有关的问题](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span><span class="sxs-lookup"><span data-stu-id="9dde5-147">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dde5-148">编辑 App.config 中 GettingStartedLib 以反映在代码中所做的更改：</span><span class="sxs-lookup"><span data-stu-id="9dde5-148">Edit App.config in GettingStartedLib to reflect the changes made in code:</span></span>
> 1. <span data-ttu-id="9dde5-149">更改第 14 行 `<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="9dde5-149">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
> 2. <span data-ttu-id="9dde5-150">更改到的第 17 行 `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="9dde5-150">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
> 3. <span data-ttu-id="9dde5-151">更改到第 22 行 `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="9dde5-151">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="9dde5-152">验证服务正常工作</span><span class="sxs-lookup"><span data-stu-id="9dde5-152">Verify the service is working</span></span>

1. <span data-ttu-id="9dde5-153">运行 GettingStartedHost 控制台应用程序从 Visual Studio 内部。</span><span class="sxs-lookup"><span data-stu-id="9dde5-153">Run the GettingStartedHost console application from inside Visual Studio.</span></span>

   <span data-ttu-id="9dde5-154">必须使用管理员特权运行服务。</span><span class="sxs-lookup"><span data-stu-id="9dde5-154">The service must be run with administrator privileges.</span></span> <span data-ttu-id="9dde5-155">使用管理员特权打开 Visual Studio，因为 GettingStartedHost 也是使用管理员特权运行。</span><span class="sxs-lookup"><span data-stu-id="9dde5-155">Because Visual Studio was opened with administrator privileges, GettingStartedHost is also run with administrator privileges.</span></span> <span data-ttu-id="9dde5-156">此外可以打开新命令提示符处使用**以管理员身份运行**并运行 service.exe。</span><span class="sxs-lookup"><span data-stu-id="9dde5-156">You can also open a new command prompt using **Run as administrator** and run service.exe within it.</span></span>

2. <span data-ttu-id="9dde5-157">打开 web 浏览器并浏览到服务的调试页在`http://localhost:8000/GettingStarted/CalculatorService`。</span><span class="sxs-lookup"><span data-stu-id="9dde5-157">Open a web browser and browse to the service's debug page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

## <a name="example"></a><span data-ttu-id="9dde5-158">示例</span><span class="sxs-lookup"><span data-stu-id="9dde5-158">Example</span></span>

<span data-ttu-id="9dde5-159">下面的示例包括本教程中前面步骤的服务协定和实现，并将服务承载于控制台应用程序中。</span><span class="sxs-lookup"><span data-stu-id="9dde5-159">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>

<span data-ttu-id="9dde5-160">若要此命令行编译器进行编译，编译 IService1.cs 和 Service1.cs 到引用的类库`System.ServiceModel.dll`。</span><span class="sxs-lookup"><span data-stu-id="9dde5-160">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library that references `System.ServiceModel.dll`.</span></span> <span data-ttu-id="9dde5-161">将 Program.cs 编译为一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="9dde5-161">Compile Program.cs as a console application.</span></span>

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
            Uri baseAddress = new Uri("http://localhost:8000/ServiceModelSamples/Service");

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
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")

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
> <span data-ttu-id="9dde5-162">此类服务需要在计算机上注册 HTTP 地址以进行侦听的权限。</span><span class="sxs-lookup"><span data-stu-id="9dde5-162">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="9dde5-163">管理员帐户具有此权限，但对于非管理员帐户来说，必须授予对 HTTP 命名空间的权限。</span><span class="sxs-lookup"><span data-stu-id="9dde5-163">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="9dde5-164">有关如何配置命名空间预留的详细信息，请参阅[配置 HTTP 和 HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)。</span><span class="sxs-lookup"><span data-stu-id="9dde5-164">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="9dde5-165">在 Visual Studio 下运行时，必须使用管理员特权运行 service.exe。</span><span class="sxs-lookup"><span data-stu-id="9dde5-165">When running under Visual Studio, the service.exe must be run with administrator privileges.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9dde5-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9dde5-166">Next steps</span></span>

<span data-ttu-id="9dde5-167">此时服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="9dde5-167">Now the service is running.</span></span> <span data-ttu-id="9dde5-168">在下一个任务中，将创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="9dde5-168">In the next task, you create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9dde5-169">如何： 创建 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="9dde5-169">How to: Create a WCF client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)

<span data-ttu-id="9dde5-170">有关疑难解答的信息，请参阅[疑难解答入门教程](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="9dde5-170">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9dde5-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="9dde5-171">See also</span></span>

- [<span data-ttu-id="9dde5-172">入门</span><span class="sxs-lookup"><span data-stu-id="9dde5-172">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="9dde5-173">自承载</span><span class="sxs-lookup"><span data-stu-id="9dde5-173">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)