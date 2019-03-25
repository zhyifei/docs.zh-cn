---
title: 教程：托管并运行基本的 Windows Communication Foundation 服务
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 38fd9b89e2719be8ce4d33b1b50f68171d587369
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410090"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="4559e-102">教程：托管并运行基本的 Windows Communication Foundation 服务</span><span class="sxs-lookup"><span data-stu-id="4559e-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="4559e-103">本教程介绍创建基本 Windows Communication Foundation (WCF) 应用程序所需的五个任务的第三个。</span><span class="sxs-lookup"><span data-stu-id="4559e-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="4559e-104">有关教程的概述，请参阅[教程：开始使用 Windows Communication Foundation 应用程序](getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="4559e-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="4559e-105">下一个任务创建的 WCF 应用程序是托管在一个控制台应用程序中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="4559e-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="4559e-106">WCF 服务公开一个或多个*终结点*，其中每个都公开一个或多个服务操作。</span><span class="sxs-lookup"><span data-stu-id="4559e-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="4559e-107">服务终结点指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="4559e-107">A service endpoint specifies the following information:</span></span> 
- <span data-ttu-id="4559e-108">在哪里可以找到该服务的地址。</span><span class="sxs-lookup"><span data-stu-id="4559e-108">An address where you can find the service.</span></span>
- <span data-ttu-id="4559e-109">一个绑定，它包含描述如何在客户端必须与服务通信的信息。</span><span class="sxs-lookup"><span data-stu-id="4559e-109">A binding that contains the information that describes how a client must communicate with the service.</span></span> 
- <span data-ttu-id="4559e-110">定义服务向其客户端提供的功能的协定。</span><span class="sxs-lookup"><span data-stu-id="4559e-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="4559e-111">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="4559e-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="4559e-112">创建和配置用于承载 WCF 服务的控制台应用项目。</span><span class="sxs-lookup"><span data-stu-id="4559e-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="4559e-113">添加代码以承载 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="4559e-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="4559e-114">更新配置文件。</span><span class="sxs-lookup"><span data-stu-id="4559e-114">Update the configuration file.</span></span>
> - <span data-ttu-id="4559e-115">启动 WCF 服务并验证其是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="4559e-115">Start the WCF service and verify it's running.</span></span>


## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="4559e-116">创建和配置托管服务的一个控制台应用程序项目</span><span class="sxs-lookup"><span data-stu-id="4559e-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="4559e-117">在 Visual Studio 中创建一个控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="4559e-117">Create a console app project in Visual Studio:</span></span> 
 
    1. <span data-ttu-id="4559e-118">从**文件**菜单中，选择**打开** > **项目/解决方案**并浏览到**GettingStarted**解决方案，以前创建的 (*GettingStarted.sln*)。</span><span class="sxs-lookup"><span data-stu-id="4559e-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="4559e-119">选择“打开” 。</span><span class="sxs-lookup"><span data-stu-id="4559e-119">Select **Open**.</span></span>

    2. <span data-ttu-id="4559e-120">从**视图**菜单中，选择**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="4559e-120">From the **View** menu, select **Solution Explorer**.</span></span>
    
    3. <span data-ttu-id="4559e-121">在中**解决方案资源管理器**窗口中，选择**GettingStarted**解决方案 （高层节点），然后选择**添加** > **的新项目**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="4559e-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 

    4. <span data-ttu-id="4559e-122">在中**添加新项目**窗口中的，左侧和右侧，选择**Windows Desktop**类别中的下**Visual C#** 或**Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="4559e-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="4559e-123">选择**控制台应用 (.NET Framework)** 模板，并输入*GettingStartedHost*有关**名称**。</span><span class="sxs-lookup"><span data-stu-id="4559e-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="4559e-124">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="4559e-124">Select **OK**.</span></span>

2. <span data-ttu-id="4559e-125">添加引用**GettingStartedHost**投影到**GettingStartedLib**项目：</span><span class="sxs-lookup"><span data-stu-id="4559e-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span> 

    1. <span data-ttu-id="4559e-126">在中**解决方案资源管理器**窗口中，选择**引用**下的文件夹**GettingStartedHost**项目，，然后选择**添加引用**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="4559e-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="4559e-127">在中**添加引用**对话框下**项目**在窗口的左侧，选择**解决方案**。</span><span class="sxs-lookup"><span data-stu-id="4559e-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span> 
 
    3. <span data-ttu-id="4559e-128">选择**GettingStartedLib**中的窗口中，并选择中心部分**确定**。</span><span class="sxs-lookup"><span data-stu-id="4559e-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span> 

       <span data-ttu-id="4559e-129">此操作使得中定义的类型**GettingStartedLib**项目可供**GettingStartedHost**项目。</span><span class="sxs-lookup"><span data-stu-id="4559e-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="4559e-130">添加引用**GettingStartedHost**投影到<xref:System.ServiceModel>程序集：</span><span class="sxs-lookup"><span data-stu-id="4559e-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="4559e-131">在中**解决方案资源管理器**窗口中，选择**引用**下的文件夹**GettingStartedHost**项目，，然后选择**添加引用**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="4559e-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>
    
    2. <span data-ttu-id="4559e-132">在中**添加引用**窗口下**程序集**在窗口的左侧，选择**Framework**。</span><span class="sxs-lookup"><span data-stu-id="4559e-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span> 

    3. <span data-ttu-id="4559e-133">选择**System.ServiceModel**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="4559e-133">Select **System.ServiceModel**, and then select **OK**.</span></span> 
    
    4. <span data-ttu-id="4559e-134">通过选择保存解决方案**文件** > **全部保存**。</span><span class="sxs-lookup"><span data-stu-id="4559e-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="4559e-135">添加代码以承载服务</span><span class="sxs-lookup"><span data-stu-id="4559e-135">Add code to host the service</span></span>

<span data-ttu-id="4559e-136">若要托管该服务，你可以添加代码以执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4559e-136">To host the service, you add code to do the following steps:</span></span> 
   1. <span data-ttu-id="4559e-137">创建的基址 URI。</span><span class="sxs-lookup"><span data-stu-id="4559e-137">Create a URI for the base address.</span></span>
   2. <span data-ttu-id="4559e-138">创建用于承载服务的类实例。</span><span class="sxs-lookup"><span data-stu-id="4559e-138">Create a class instance for hosting the service.</span></span>
   3. <span data-ttu-id="4559e-139">创建服务终结点。</span><span class="sxs-lookup"><span data-stu-id="4559e-139">Create a service endpoint.</span></span>
   4. <span data-ttu-id="4559e-140">启用元数据交换。</span><span class="sxs-lookup"><span data-stu-id="4559e-140">Enable metadata exchange.</span></span>
   5. <span data-ttu-id="4559e-141">打开服务主机以侦听传入消息。</span><span class="sxs-lookup"><span data-stu-id="4559e-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="4559e-142">对代码进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="4559e-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="4559e-143">打开**Program.cs**或**Module1.vb**文件中**GettingStartedHost**项目，其代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="4559e-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb)    ;

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
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
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```
    
    <span data-ttu-id="4559e-144">有关此代码的工作方式的信息，请参阅[服务托管计划步骤](#service-hosting-program-steps)。</span><span class="sxs-lookup"><span data-stu-id="4559e-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>


2. <span data-ttu-id="4559e-145">更新项目属性：</span><span class="sxs-lookup"><span data-stu-id="4559e-145">Update the project properties:</span></span>

   1. <span data-ttu-id="4559e-146">在中**解决方案资源管理器**窗口中，选择**GettingStartedHost**文件夹，，然后选择**属性**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="4559e-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="4559e-147">上**GettingStartedHost**属性页上，选择**应用程序**选项卡：</span><span class="sxs-lookup"><span data-stu-id="4559e-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="4559e-148">有关C#项目中，选择**GettingStartedHost.Program**从**启动对象**列表。</span><span class="sxs-lookup"><span data-stu-id="4559e-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="4559e-149">对于 Visual Basic 项目中，选择**Service.Program**从**启动对象**列表。</span><span class="sxs-lookup"><span data-stu-id="4559e-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="4559e-150">从**文件**菜单中，选择**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="4559e-150">From the **File** menu, select **Save All**.</span></span>


## <a name="verify-the-service-is-working"></a><span data-ttu-id="4559e-151">验证服务正常工作</span><span class="sxs-lookup"><span data-stu-id="4559e-151">Verify the service is working</span></span>

1. <span data-ttu-id="4559e-152">构建解决方案，然后运行**GettingStartedHost**控制台应用程序从 Visual Studio 内部。</span><span class="sxs-lookup"><span data-stu-id="4559e-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span> 

    <span data-ttu-id="4559e-153">必须使用管理员特权运行服务。</span><span class="sxs-lookup"><span data-stu-id="4559e-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="4559e-154">因为在运行时使用管理员特权打开 Visual Studio **GettingStartedHost**在 Visual Studio 中，应用程序运行使用管理员的权限。</span><span class="sxs-lookup"><span data-stu-id="4559e-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="4559e-155">或者，可以打开新的命令提示符以管理员身份 (选择**更多** > **以管理员身份运行**从快捷菜单) 并运行**GettingStartedHost.exe**其内。</span><span class="sxs-lookup"><span data-stu-id="4559e-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="4559e-156">打开 web 浏览器并浏览到服务的页面在`http://localhost:8000/GettingStarted/CalculatorService`。</span><span class="sxs-lookup"><span data-stu-id="4559e-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>
   
   > [!NOTE]
   > <span data-ttu-id="4559e-157">此类服务需要适当的权限来为要侦听的计算机上注册 HTTP 地址。</span><span class="sxs-lookup"><span data-stu-id="4559e-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="4559e-158">管理员帐户具有此权限，但对于非管理员帐户来说，必须授予对 HTTP 命名空间的权限。</span><span class="sxs-lookup"><span data-stu-id="4559e-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="4559e-159">有关如何配置命名空间预留的详细信息，请参阅[配置 HTTP 和 HTTPS](feature-details/configuring-http-and-https.md)。</span><span class="sxs-lookup"><span data-stu-id="4559e-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> 


## <a name="service-hosting-program-steps"></a><span data-ttu-id="4559e-160">服务宿主程序步骤</span><span class="sxs-lookup"><span data-stu-id="4559e-160">Service hosting program steps</span></span>

<span data-ttu-id="4559e-161">添加到主机服务进行了介绍，如下所示的代码中的步骤：</span><span class="sxs-lookup"><span data-stu-id="4559e-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="4559e-162">**步骤 1**:创建的实例`Uri`类来保存服务的基址。</span><span class="sxs-lookup"><span data-stu-id="4559e-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="4559e-163">包含一个基址的 URL 采用一个可选 URI，这标识服务。</span><span class="sxs-lookup"><span data-stu-id="4559e-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="4559e-164">基址的格式如下： `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`。</span><span class="sxs-lookup"><span data-stu-id="4559e-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="4559e-165">计算器服务的基址使用 HTTP 传输协议、 本地主机、 端口 8000 和 URI 段，GettingStarted。</span><span class="sxs-lookup"><span data-stu-id="4559e-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="4559e-166">**步骤 2**:创建的实例<xref:System.ServiceModel.ServiceHost>类，该类用于承载服务。</span><span class="sxs-lookup"><span data-stu-id="4559e-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="4559e-167">构造函数采用两个参数： 实现服务协定和服务的基址的类的类型。</span><span class="sxs-lookup"><span data-stu-id="4559e-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="4559e-168">**步骤 3**:创建一个 <xref:System.ServiceModel.Description.ServiceEndpoint> 实例。</span><span class="sxs-lookup"><span data-stu-id="4559e-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="4559e-169">服务终结点由地址、绑定和服务协定组成。</span><span class="sxs-lookup"><span data-stu-id="4559e-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="4559e-170"><xref:System.ServiceModel.Description.ServiceEndpoint>构造函数组成的服务协定接口类型、 绑定和地址。</span><span class="sxs-lookup"><span data-stu-id="4559e-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="4559e-171">服务协定是在服务类型中定义和实现的 `ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="4559e-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="4559e-172">为此示例绑定是<xref:System.ServiceModel.WSHttpBinding>，这是一个内置的绑定和连接到终结点符合 WS-\* 规范。</span><span class="sxs-lookup"><span data-stu-id="4559e-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="4559e-173">有关 WCF 绑定的详细信息，请参阅[WCF 绑定概述](bindings-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4559e-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="4559e-174">将追加到基址以标识终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="4559e-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="4559e-175">该代码指定的地址作为 CalculatorService 和作为终结点的完全限定的地址`http://localhost:8000/GettingStarted/CalculatorService`。</span><span class="sxs-lookup"><span data-stu-id="4559e-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4559e-176">针对.NET Framework 版本 4 及更高版本，添加服务终结点是可选的。</span><span class="sxs-lookup"><span data-stu-id="4559e-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="4559e-177">对于这些版本，如果您没有添加您的代码或配置中，WCF 将添加一个默认终结点的基址和协定，该服务实现的每个组合。</span><span class="sxs-lookup"><span data-stu-id="4559e-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="4559e-178">有关默认终结点的详细信息，请参阅[指定的终结点地址](specifying-an-endpoint-address.md)。</span><span class="sxs-lookup"><span data-stu-id="4559e-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="4559e-179">有关默认终结点、 绑定和行为的详细信息，请参阅[简化后的配置](simplified-configuration.md)并[WCF 服务的简化配置](samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="4559e-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="4559e-180">**步骤 4**:启用元数据交换。</span><span class="sxs-lookup"><span data-stu-id="4559e-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="4559e-181">客户端使用元数据交换来调用服务操作的生成代理。</span><span class="sxs-lookup"><span data-stu-id="4559e-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="4559e-182">若要启用元数据交换，创建<xref:System.ServiceModel.Description.ServiceMetadataBehavior>实例，设置其<xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled>属性设置为`true`，并添加`ServiceMetadataBehavior`对象传递给<xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>系列<xref:System.ServiceModel.ServiceHost>实例。</span><span class="sxs-lookup"><span data-stu-id="4559e-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="4559e-183">**步骤 5**:打开<xref:System.ServiceModel.ServiceHost>侦听传入消息。</span><span class="sxs-lookup"><span data-stu-id="4559e-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="4559e-184">应用程序等待用户按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="4559e-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="4559e-185">应用程序实例化后<xref:System.ServiceModel.ServiceHost>，它将执行 try/catch 块。</span><span class="sxs-lookup"><span data-stu-id="4559e-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="4559e-186">有关安全捕获引发的异常详细信息<xref:System.ServiceModel.ServiceHost>，请参阅[使用关闭和中止发布 WCF 客户端资源](samples/use-close-abort-release-wcf-client-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="4559e-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4559e-187">当添加 WCF 服务库时，Visual Studio 承载它为您如果调试通过启动服务主机。</span><span class="sxs-lookup"><span data-stu-id="4559e-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="4559e-188">若要避免冲突，您可防止 Visual Studio 承载 WCF 服务库。</span><span class="sxs-lookup"><span data-stu-id="4559e-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span> 
> 1. <span data-ttu-id="4559e-189">选择**GettingStartedLib**项目中**解决方案资源管理器**，然后选择**属性**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="4559e-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="4559e-190">选择**WCF 选项**并取消选中**启动 WCF 服务主机在调试同一解决方案中的另一个项目时**。</span><span class="sxs-lookup"><span data-stu-id="4559e-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>


## <a name="next-steps"></a><span data-ttu-id="4559e-191">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4559e-191">Next steps</span></span>

<span data-ttu-id="4559e-192">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="4559e-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="4559e-193">创建和配置用于承载 WCF 服务的控制台应用项目。</span><span class="sxs-lookup"><span data-stu-id="4559e-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="4559e-194">添加代码以承载 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="4559e-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="4559e-195">更新配置文件。</span><span class="sxs-lookup"><span data-stu-id="4559e-195">Update the configuration file.</span></span>
> - <span data-ttu-id="4559e-196">启动 WCF 服务并验证其是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="4559e-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="4559e-197">转到下一步的教程，了解如何创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="4559e-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4559e-198">教程：创建 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="4559e-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
