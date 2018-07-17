---
title: 如何：承载和运行基本的 Windows Communication Foundation 服务
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: f1c56ed83fa214cf781a833e05642635ac24b0c5
ms.sourcegitcommit: d8bf4976eafe3289275be3811e7cb721bfff7e1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753495"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="cd013-102">如何：承载和运行基本的 Windows Communication Foundation 服务</span><span class="sxs-lookup"><span data-stu-id="cd013-102">How to: Host and Run a Basic Windows Communication Foundation Service</span></span>
<span data-ttu-id="cd013-103">这是创建 Windows Communication Foundation (WCF) 应用程序所需六项任务中的第三项。</span><span class="sxs-lookup"><span data-stu-id="cd013-103">This is the third of six tasks required to create a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="cd013-104">有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。</span><span class="sxs-lookup"><span data-stu-id="cd013-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="cd013-105">本主题说明如何在控制台应用程序中承载 Windows Communication Foundation (WCF) 服务。</span><span class="sxs-lookup"><span data-stu-id="cd013-105">This topic describes how to host a Windows Communication Foundation (WCF) service in a console application.</span></span> <span data-ttu-id="cd013-106">此过程包含以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cd013-106">This procedure consists of the following steps:</span></span>  
  
-   <span data-ttu-id="cd013-107">创建用于承载服务的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="cd013-107">Create a console application project to host the service.</span></span>  
  
-   <span data-ttu-id="cd013-108">为服务创建服务主机。</span><span class="sxs-lookup"><span data-stu-id="cd013-108">Create a service host for the service.</span></span>  
  
-   <span data-ttu-id="cd013-109">启用元数据交换。</span><span class="sxs-lookup"><span data-stu-id="cd013-109">Enable metadata exchange.</span></span>  
  
-   <span data-ttu-id="cd013-110">打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="cd013-110">Open the service host.</span></span>  
  
 <span data-ttu-id="cd013-111">在过程后面的以下示例中提供了在此任务中编写的代码的完整清单。</span><span class="sxs-lookup"><span data-stu-id="cd013-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="cd013-112">新建用于承载服务的控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="cd013-112">To create a new console application to host the service</span></span>  
  
1.  <span data-ttu-id="cd013-113">创建新的控制台应用程序项目，方法是：右键单击“入门”解决方案，然后选择“添加”>“新建项目”。</span><span class="sxs-lookup"><span data-stu-id="cd013-113">Create a new Console Application project by right-clicking on the Getting Started solution, selecting, **Add**, **New Project**.</span></span> <span data-ttu-id="cd013-114">在“添加新项目”对话框左侧的“C#”或“VB”下选择“Windows”。</span><span class="sxs-lookup"><span data-stu-id="cd013-114">In the **Add New Project** dialog on the left hand side of the dialog select **Windows** under **C#** or **VB**.</span></span> <span data-ttu-id="cd013-115">在对话框的中心部分选择“控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="cd013-115">In the center section of the dialog select **Console Application**.</span></span> <span data-ttu-id="cd013-116">将项目命名为 GettingStartedHost。</span><span class="sxs-lookup"><span data-stu-id="cd013-116">Name the project GettingStartedHost.</span></span>  
  
2.  <span data-ttu-id="cd013-117">在解决方案资源管理器中右键单击“GettingStartedHost”并选择“属性”，将 GettingStartedHost 项目的目标框架设置为 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="cd013-117">Set the target framework of the GettingStartedHost project to .NET Framework 4.5 by right clicking on **GettingStartedHost** in the Solution Explorer and selecting **Properties**.</span></span> <span data-ttu-id="cd013-118">在标记为“目标框架”的下拉框中，选择“.NET Framework 4.5”。</span><span class="sxs-lookup"><span data-stu-id="cd013-118">In the dropdown box labeled **Target Framework** select **.NET Framework 4.5**.</span></span> <span data-ttu-id="cd013-119">设置 VB 项目的目标框架稍有不同，在 GettingStartedHost 项目属性对话框中，单击屏幕左侧的“编译”选项卡，然后单击对话框左下角的“高级编译选项”按钮。</span><span class="sxs-lookup"><span data-stu-id="cd013-119">Setting the target framework for a VB project is a little different, in the GettingStartedHost project properties dialog, click the **Compile** tab on the left-hand side of the screen, and then click the **Advanced Compile Options** button at the lower left-hand corner of the dialog.</span></span> <span data-ttu-id="cd013-120">然后，在标记为“目标框架”的下拉框中选择“.NET Framework 4.5”。</span><span class="sxs-lookup"><span data-stu-id="cd013-120">Then select **.NET Framework 4.5** in the dropdown box labeled **Target Framework**.</span></span>  
  
     <span data-ttu-id="cd013-121">设置目标框架将导致 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 重新加载解决方案，出现提示后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="cd013-121">Setting the target framework will cause [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] to reload the solution, press **OK** when prompted.</span></span>  
  
3.  <span data-ttu-id="cd013-122">在解决方案资源管理器中右键单击 GettingStartedHost 项目下的“引用”文件夹，并选择“添加引用”，在 GettingStartedHost 项目中添加一个对 GettingStartedLib 项目的引用。</span><span class="sxs-lookup"><span data-stu-id="cd013-122">Add a reference to the GettingStartedLib project to the GettingStartedHost project by right clicking on the **References** folder under the GettingStartedHost project in the solution explorer and select **Add Reference**.</span></span> <span data-ttu-id="cd013-123">在“添加引用”对话框中，选择对话框左侧的“解决方案”，并选择对话框中心的 GettingStartedLib，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="cd013-123">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog and select GettingStartedLib in the center section of the dialog and click **Add**.</span></span> <span data-ttu-id="cd013-124">这使 GettingStartedLib 项目中定义的类型可用于 GettingStartedHost 项目。</span><span class="sxs-lookup"><span data-stu-id="cd013-124">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>  
  
4.  <span data-ttu-id="cd013-125">在解决方案资源管理器中右键单击 GettingStartedHost 项目下的“引用”文件夹，并选择“添加”引用，在 GettingStartedHost 项目中添加一个对 System.ServiceModel 的引用。</span><span class="sxs-lookup"><span data-stu-id="cd013-125">Add a reference to System.ServiceModel to the GettingStartedHost project by right-clicking the **Reference** folder under the GettingStartedHost project in Solution Explorer and select **Add** Reference.</span></span> <span data-ttu-id="cd013-126">在“添加引用”对话框中，选择对话框左侧的“框架”。</span><span class="sxs-lookup"><span data-stu-id="cd013-126">In the **Add Reference** dialog select **Framework** on the left-hand side of the dialog.</span></span> <span data-ttu-id="cd013-127">请在“搜索程序集”文本框中，键入 `System.ServiceModel`。</span><span class="sxs-lookup"><span data-stu-id="cd013-127">In the Search Assemblies textbox, type in `System.ServiceModel`.</span></span> <span data-ttu-id="cd013-128">在对话框的中心部分，选择“System.ServiceModel”，单击“添加”按钮，然后单击“关闭”按钮。</span><span class="sxs-lookup"><span data-stu-id="cd013-128">In the center section of the dialog select **System.ServiceModel**, click the **Add** button, and click the **Close** button.</span></span> <span data-ttu-id="cd013-129">单击主菜单下的“全部保存”按钮，保存解决方案。</span><span class="sxs-lookup"><span data-stu-id="cd013-129">Save the solution by clicking the Save All button below the main menu.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="cd013-130">承载服务</span><span class="sxs-lookup"><span data-stu-id="cd013-130">To host the service</span></span>  
  
-   <span data-ttu-id="cd013-131">打开 Program.cs 或 Module.vb 文件，并输入以下代码：</span><span class="sxs-lookup"><span data-stu-id="cd013-131">Open the Program.cs or Module.vb file and enter the following code:</span></span>  
  
    ```csharp
    // program.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
    using GettingStartedLib;  
    using System.ServiceModel.Description;   
  
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
    'Module1.vb  
    Imports System  
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
  
    1.  <span data-ttu-id="cd013-132">第 1 步 - 创建 Uri 类的实例来保存服务的基址。</span><span class="sxs-lookup"><span data-stu-id="cd013-132">Step 1 - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="cd013-133">服务由包含一个基址和一个可选 URI 的 URL 来标识。</span><span class="sxs-lookup"><span data-stu-id="cd013-133">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="cd013-134">基址的格式如下：[传输协议]://[计算机名或域][:可选端口号]/[可选 URI 段]。计算器服务的基址使用 HTTP 传输协议、本地主机、端口 8000 和 URI 段“GettingStarted”</span><span class="sxs-lookup"><span data-stu-id="cd013-134">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>  
  
    2.  <span data-ttu-id="cd013-135">第 2 步 – 创建 <xref:System.ServiceModel.ServiceHost> 类的实例以承载服务。</span><span class="sxs-lookup"><span data-stu-id="cd013-135">Step 2 – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="cd013-136">构造函数采用两个参数：实现服务协定的类的类型，以及服务的基址。</span><span class="sxs-lookup"><span data-stu-id="cd013-136">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>  
  
    3.  <span data-ttu-id="cd013-137">第 3 步 – 创建 <xref:System.ServiceModel.Description.ServiceEndpoint> 实例。</span><span class="sxs-lookup"><span data-stu-id="cd013-137">Step 3 – Creates a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="cd013-138">服务终结点由地址、绑定和服务协定组成。</span><span class="sxs-lookup"><span data-stu-id="cd013-138">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="cd013-139">因此<xref:System.ServiceModel.Description.ServiceEndpoint> 构造函数采用服务协定接口类型、绑定和地址。</span><span class="sxs-lookup"><span data-stu-id="cd013-139">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="cd013-140">服务协定是在服务类型中定义和实现的 `ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="cd013-140">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="cd013-141">在此示例中使用的绑定是 <xref:System.ServiceModel.WSHttpBinding>，这是用于连接到符合 WS-＊ 规范的终结点的内置绑定。</span><span class="sxs-lookup"><span data-stu-id="cd013-141">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="cd013-142">有关 WCF 绑定的详细信息，请参阅 [WCF 绑定概述](../../../docs/framework/wcf/bindings-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="cd013-142">For more information about WCF bindings, see [WCF Bindings Overview](../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="cd013-143">该地址追加到基址以标识终结点。</span><span class="sxs-lookup"><span data-stu-id="cd013-143">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="cd013-144">此代码中指定的地址为“CalculatorService”，因此终结点的完全限定的地址为 `"http://localhost:8000/GettingStarted/CalculatorService"`。使用 .NET Framework 4.0 或更高版本时，添加服务终结点是可选的。</span><span class="sxs-lookup"><span data-stu-id="cd013-144">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"` Adding a service endpoint is optional when using .NET Framework 4.0 or later.</span></span> <span data-ttu-id="cd013-145">在这些版本中，如果在代码或配置中未添加任何终结点，则 WCF 为该服务实现的基址和协定的每个组合添加一个默认终结点。</span><span class="sxs-lookup"><span data-stu-id="cd013-145">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="cd013-146">有关默认终结点的详细信息，请参阅[指定终结点地址](../../../docs/framework/wcf/specifying-an-endpoint-address.md)。</span><span class="sxs-lookup"><span data-stu-id="cd013-146">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="cd013-147">有关默认终结点、绑定和行为的详细信息，请参阅[简化配置](../../../docs/framework/wcf/simplified-configuration.md)和 [WCF 服务的简化配置](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="cd013-147">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="cd013-148">使用 .NET Framework 4 或更高版本时，添加服务终结点是可选的。</span><span class="sxs-lookup"><span data-stu-id="cd013-148">Adding a service endpoint is optional when using .NET Framework 4 or later.</span></span> <span data-ttu-id="cd013-149">在这些版本中，如果在代码或配置中未添加任何终结点，则 WCF 为该服务实现的基址和协定的每个组合添加一个默认终结点。</span><span class="sxs-lookup"><span data-stu-id="cd013-149">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="cd013-150">有关默认终结点的详细信息，请参阅[指定终结点地址](../../../docs/framework/wcf/specifying-an-endpoint-address.md)。</span><span class="sxs-lookup"><span data-stu-id="cd013-150">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="cd013-151">有关默认终结点、绑定和行为的详细信息，请参阅[简化配置](../../../docs/framework/wcf/simplified-configuration.md)和 [WCF 服务的简化配置](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="cd013-151">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
    4.  <span data-ttu-id="cd013-152">第 4 步 - 启用元数据交换。</span><span class="sxs-lookup"><span data-stu-id="cd013-152">Step 4 – Enable metadata exchange.</span></span> <span data-ttu-id="cd013-153">客户端将使用元数据交换来生成将用于调用服务操作的代理。</span><span class="sxs-lookup"><span data-stu-id="cd013-153">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="cd013-154">要启用元数据交换，请创建 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 实例，将其 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> 属性设置为 `true`，并将行为添加到 <xref:System.ServiceModel.ServiceHost> 实例的 <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` 集合。</span><span class="sxs-lookup"><span data-stu-id="cd013-154">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>  
  
    5.  <span data-ttu-id="cd013-155">第 5 步 – 打开 <xref:System.ServiceModel.ServiceHost>，以侦听传入消息。</span><span class="sxs-lookup"><span data-stu-id="cd013-155">Step 5 – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="cd013-156">注意，代码会等待用户按 Enter。</span><span class="sxs-lookup"><span data-stu-id="cd013-156">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="cd013-157">如果不这样做，应用程序将立即关闭，并且服务将关闭。另请注意，使用了 try/catch 块。</span><span class="sxs-lookup"><span data-stu-id="cd013-157">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="cd013-158">在实例化 <xref:System.ServiceModel.ServiceHost> 后，所有其他代码放置在 try/catch 块中。</span><span class="sxs-lookup"><span data-stu-id="cd013-158">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="cd013-159">有关 <xref:System.ServiceModel.ServiceHost> 引发的安全捕获异常的详细信息，请参阅[避免出现与 Using 语句有关的问题](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span><span class="sxs-lookup"><span data-stu-id="cd013-159">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span></span>  
  
### <a name="to-verify-the-service-is-working"></a><span data-ttu-id="cd013-160">验证服务是否正常运行</span><span class="sxs-lookup"><span data-stu-id="cd013-160">To verify the service is working</span></span>  
  
1.  <span data-ttu-id="cd013-161">从 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 内部运行 GettingStartedHost 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd013-161">Run the GettingStartedHost console application from inside [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="cd013-162">在 [!INCLUDE[wv](../../../includes/wv-md.md)] 以及更高版本的操作系统上运行时，必须使用管理员特权运行该服务。</span><span class="sxs-lookup"><span data-stu-id="cd013-162">When running on [!INCLUDE[wv](../../../includes/wv-md.md)] and later operating systems, the service must be run with administrator privileges.</span></span> <span data-ttu-id="cd013-163">由于 Visual Studio 是使用管理员特权运行的，因此 GettingStartedHost 也是使用管理员特权运行的。</span><span class="sxs-lookup"><span data-stu-id="cd013-163">Because Visual Studio was run with Administrator privileges, GettingStartedHost is also run with Administrator privileges.</span></span> <span data-ttu-id="cd013-164">也可以启动新的命令提示，使用管理员特权运行它，并在其中运行 service.exe。</span><span class="sxs-lookup"><span data-stu-id="cd013-164">You can also start a new command prompt running it with Administrator privileges and run service.exe within it.</span></span>  
  
2.  <span data-ttu-id="cd013-165">打开 Internet Explorer，并浏览到服务的调试页，网址为 `http://localhost:8000/GettingStarted/CalculatorService`。</span><span class="sxs-lookup"><span data-stu-id="cd013-165">Open Internet Explorer and browse to the service's debug page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd013-166">示例</span><span class="sxs-lookup"><span data-stu-id="cd013-166">Example</span></span>  
 <span data-ttu-id="cd013-167">下面的示例包括本教程中前面步骤的服务协定和实现，并将服务承载于控制台应用程序中。</span><span class="sxs-lookup"><span data-stu-id="cd013-167">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>  
  
 <span data-ttu-id="cd013-168">要使用命令行编译器对此进行编译，请将 IService1.cs 和 Service1.cs 编译到引用 `System.ServiceModel.dll` 的类库中。</span><span class="sxs-lookup"><span data-stu-id="cd013-168">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library referencing `System.ServiceModel.dll`.</span></span> <span data-ttu-id="cd013-169">并将 Program.cs 编译到控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd013-169">And compile Program.cs to a console application.</span></span>  
  
```csharp
// IService1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
// Service1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
//Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
using GettingStartedLib;  
using System.ServiceModel.Description;   
  
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
'IService1.vb  
Imports System  
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
'Service1.vb  
Imports System  
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
'Module1.vb  
Imports System  
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
>  <span data-ttu-id="cd013-170">此类服务需要在计算机上注册 HTTP 地址以进行侦听的权限。</span><span class="sxs-lookup"><span data-stu-id="cd013-170">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="cd013-171">管理员帐户具有此权限，但对于非管理员帐户来说，必须授予对 HTTP 命名空间的权限。</span><span class="sxs-lookup"><span data-stu-id="cd013-171">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="cd013-172">有关如何配置命名空间预留的详细信息，请参阅[配置 HTTP 和 HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)。</span><span class="sxs-lookup"><span data-stu-id="cd013-172">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="cd013-173">在 Visual Studio 下运行时，必须使用管理员特权运行 service.exe。</span><span class="sxs-lookup"><span data-stu-id="cd013-173">When running under Visual Studio, the service.exe must be run with administrator privileges.</span></span>  
  
 <span data-ttu-id="cd013-174">此时服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="cd013-174">Now the service is running.</span></span> <span data-ttu-id="cd013-175">转到[如何：创建客户端](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="cd013-175">Proceed to [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="cd013-176">有关疑难解答的信息，请参阅[疑难解答入门教程](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="cd013-176">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd013-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd013-177">See Also</span></span>  
 [<span data-ttu-id="cd013-178">入门</span><span class="sxs-lookup"><span data-stu-id="cd013-178">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="cd013-179">自承载</span><span class="sxs-lookup"><span data-stu-id="cd013-179">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
