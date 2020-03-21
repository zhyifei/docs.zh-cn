---
title: 教程：托管并运行基本的 Windows 通信基础服务
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184074"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="d0f9e-102">教程：托管并运行基本的 Windows 通信基础服务</span><span class="sxs-lookup"><span data-stu-id="d0f9e-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="d0f9e-103">本教程介绍创建基本 Windows 通信基础 （WCF） 应用程序所需的五个任务中的第三个。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="d0f9e-104">有关教程的概述，请参阅[教程：开始使用 Windows 通信基础应用程序](getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="d0f9e-105">创建 WCF 应用程序的下一个任务是在控制台应用程序中托管 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="d0f9e-106">WCF 服务公开一个或多个终结点，每个*终结点*公开一个或多个服务操作。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="d0f9e-107">服务终结点指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-107">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="d0f9e-108">您可以在其中找到服务的地址。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-108">An address where you can find the service.</span></span>
- <span data-ttu-id="d0f9e-109">包含描述客户端必须如何与服务通信的信息的绑定。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-109">A binding that contains the information that describes how a client must communicate with the service.</span></span>
- <span data-ttu-id="d0f9e-110">定义服务为其客户端提供的功能的协定。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="d0f9e-111">在本教程中，你将了解如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="d0f9e-112">创建和配置用于托管 WCF 服务的控制台应用项目。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="d0f9e-113">添加代码以承载 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="d0f9e-114">更新配置文件。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-114">Update the configuration file.</span></span>
> - <span data-ttu-id="d0f9e-115">启动 WCF 服务并验证其正在运行。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="d0f9e-116">创建和配置托管服务的控制台应用项目</span><span class="sxs-lookup"><span data-stu-id="d0f9e-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="d0f9e-117">在可视化工作室中创建控制台应用项目：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-117">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="d0f9e-118">在 **"文件"** 菜单中，选择 **"打开** > **项目/解决方案**"并浏览到您以前创建的**入门**解决方案 （*获取入门.sln*）。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="d0f9e-119">选择“打开”。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-119">Select **Open**.</span></span>

    2. <span data-ttu-id="d0f9e-120">在 **"查看"** 菜单中，选择 **"解决方案资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-120">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="d0f9e-121">在 **"解决方案资源管理器"** 窗口中，选择 **"入门"** 解决方案（顶部节点），然后从快捷菜单中选择 **"添加新** > **项目**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="d0f9e-122">在左侧的 **"添加新项目**"窗口中，在 **"可视 C#"** 或"**可视基本**"下选择**Windows 桌面**类别。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="d0f9e-123">选择**控制台应用 （.NET 框架）** 模板，然后输入"*入门主机*"**的名称**。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="d0f9e-124">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-124">Select **OK**.</span></span>

2. <span data-ttu-id="d0f9e-125">在**入门主机**项目中向**入门项目**添加引用：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span>

    1. <span data-ttu-id="d0f9e-126">在 **"解决方案资源管理器"** 窗口中，选择 **"入门主机**"项目下的 **"参考"** 文件夹，然后从快捷菜单中选择 **"添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="d0f9e-127">在"**添加参考**"对话框中，在窗口左侧**的项目**下，选择 **"解决方案**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span>

    3. <span data-ttu-id="d0f9e-128">在窗口的中心部分选择 **"获取开始Lib"，** 然后选择 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span>

       <span data-ttu-id="d0f9e-129">此操作使**入门项目**中定义的类型可供**入门主机项目使用**。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="d0f9e-130">在**入门主机**项目中向<xref:System.ServiceModel>程序集添加引用：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="d0f9e-131">在 **"解决方案资源管理器"** 窗口中，选择 **"入门主机**"项目下的 **"参考"** 文件夹，然后从快捷菜单中选择 **"添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="d0f9e-132">在"**添加引用**"窗口中，在窗口左侧的 **"程序集**"下，选择 **"框架**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="d0f9e-133">选择 **"系统.服务模式"，** 然后选择 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-133">Select **System.ServiceModel**, and then select **OK**.</span></span>

    4. <span data-ttu-id="d0f9e-134">通过选择 **"全部保存文件** > **"保存**解决方案。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="d0f9e-135">添加代码以承载服务</span><span class="sxs-lookup"><span data-stu-id="d0f9e-135">Add code to host the service</span></span>

<span data-ttu-id="d0f9e-136">要托管服务，请添加代码以执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-136">To host the service, you add code to do the following steps:</span></span>

1. <span data-ttu-id="d0f9e-137">为基本地址创建 URI。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-137">Create a URI for the base address.</span></span>
2. <span data-ttu-id="d0f9e-138">创建用于托管服务的类实例。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-138">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="d0f9e-139">创建服务终结点。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-139">Create a service endpoint.</span></span>
4. <span data-ttu-id="d0f9e-140">启用元数据交换。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-140">Enable metadata exchange.</span></span>
5. <span data-ttu-id="d0f9e-141">打开服务主机以侦听传入消息。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="d0f9e-142">对代码进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="d0f9e-143">打开**入门霍斯特**项目中**的Program.cs**或**Module1.vb**文件，并将其代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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

    <span data-ttu-id="d0f9e-144">有关此代码的工作原理的信息，请参阅[服务托管程序步骤](#service-hosting-program-steps)。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="d0f9e-145">更新项目属性：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-145">Update the project properties:</span></span>

   1. <span data-ttu-id="d0f9e-146">在 **"解决方案资源管理器"** 窗口中，选择 **"入门主机"** 文件夹，然后从快捷菜单中选择 **"属性**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="d0f9e-147">在 **"入门主机"** 属性页上，选择"**应用程序**"选项卡：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="d0f9e-148">对于 C# 项目，从**启动对象**列表中选择 **"入门主机.程序"。**</span><span class="sxs-lookup"><span data-stu-id="d0f9e-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="d0f9e-149">对于可视化基本项目，从**启动对象**列表中选择 **"服务.程序**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="d0f9e-150">在 **"文件"** 菜单中，选择 **"全部保存**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="d0f9e-151">验证服务是否正常工作</span><span class="sxs-lookup"><span data-stu-id="d0f9e-151">Verify the service is working</span></span>

1. <span data-ttu-id="d0f9e-152">构建解决方案，然后从 Visual Studio 内部运行**入门主机**控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span>

    <span data-ttu-id="d0f9e-153">服务必须具有管理员权限运行。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="d0f9e-154">由于您使用管理员权限打开了 Visual Studio，因此在可视化工作室中运行 **"入门主机"** 时，应用程序也具有管理员权限运行。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="d0f9e-155">作为替代方法，您可以以管理员身份打开新的命令提示符（从快捷菜单中选择 **"以管理员身份运行"），** > **Run as administrator**并在其中运行 **"获取启动Host.exe"。**</span><span class="sxs-lookup"><span data-stu-id="d0f9e-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="d0f9e-156">打开 Web 浏览器，然后浏览到 服务页面`http://localhost:8000/GettingStarted/CalculatorService`。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d0f9e-157">此类服务需要适当的权限才能在计算机上注册 HTTP 地址以进行侦听。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="d0f9e-158">管理员帐户具有此权限，但对于非管理员帐户来说，必须授予对 HTTP 命名空间的权限。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="d0f9e-159">有关如何配置命名空间预留的详细信息，请参阅[配置 HTTP 和 HTTPS](feature-details/configuring-http-and-https.md)。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span>

## <a name="service-hosting-program-steps"></a><span data-ttu-id="d0f9e-160">服务托管程序步骤</span><span class="sxs-lookup"><span data-stu-id="d0f9e-160">Service hosting program steps</span></span>

<span data-ttu-id="d0f9e-161">添加到托管服务的代码中的步骤描述如下：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="d0f9e-162">**步骤 1：** 创建类的`Uri`实例以保存服务的基本地址。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="d0f9e-163">包含基本地址的 URL 具有标识服务的可选 URI。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="d0f9e-164">基本地址的格式如下： `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="d0f9e-165">计算器服务的基本地址使用 HTTP 传输、本地主机、端口 8000 和 URI 段"入门"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="d0f9e-166">**步骤 2：** 创建类的<xref:System.ServiceModel.ServiceHost>实例，用于托管服务。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="d0f9e-167">构造函数采用两个参数：实现服务协定的类类型和服务的基本地址。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="d0f9e-168">**步骤 3**：<xref:System.ServiceModel.Description.ServiceEndpoint>创建实例。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="d0f9e-169">服务终结点由地址、绑定和服务协定组成。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="d0f9e-170"><xref:System.ServiceModel.Description.ServiceEndpoint>构造函数由服务协定接口类型、绑定和地址组成。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="d0f9e-171">服务协定是在服务类型中定义和实现的 `ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="d0f9e-172">此示例的绑定是<xref:System.ServiceModel.WSHttpBinding>，这是一个内置绑定，并连接到符合 WS-\* 规范的终结点。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="d0f9e-173">有关 WCF 绑定的详细信息，请参阅[WCF 绑定概述](bindings-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="d0f9e-174">将地址追加到基本地址以标识终结点。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="d0f9e-175">代码将地址指定为计算器服务，终结点的完全限定地址为`http://localhost:8000/GettingStarted/CalculatorService`。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d0f9e-176">对于 .NET 框架版本 4 及更高版本，添加服务终结点是可选的。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="d0f9e-177">对于这些版本，如果不添加代码或配置，WCF 会为服务实现的每个基本地址和协定组合添加一个默认终结点。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="d0f9e-178">有关默认终结点的详细信息，请参阅[指定终结点地址](specifying-an-endpoint-address.md)。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="d0f9e-179">有关默认终结点、绑定和行为的详细信息，请参阅[WCF 服务的](samples/simplified-configuration-for-wcf-services.md)[简化配置](simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="d0f9e-180">**步骤 4**：启用元数据交换。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="d0f9e-181">客户端使用元数据交换生成用于调用服务操作的代理。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="d0f9e-182">要启用元数据交换，请创建<xref:System.ServiceModel.Description.ServiceMetadataBehavior>实例，将其<xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled>属性设置为`true`，并将`ServiceMetadataBehavior`对象添加到<xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A><xref:System.ServiceModel.ServiceHost>实例的集合中。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="d0f9e-183">**步骤 5** <xref:System.ServiceModel.ServiceHost> ： 打开以侦听传入的消息。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="d0f9e-184">应用程序等待您按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="d0f9e-185">应用程序实例化后<xref:System.ServiceModel.ServiceHost>，它执行一个 try/catch 块。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="d0f9e-186">有关安全捕获引发<xref:System.ServiceModel.ServiceHost>异常的详细信息，请参阅[使用关闭和中止来释放 WCF 客户端资源](samples/use-close-abort-release-wcf-client-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0f9e-187">添加 WCF 服务库时，如果通过启动服务主机来调试它，Visual Studio 会为您托管它。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="d0f9e-188">为了避免冲突，您可以阻止 Visual Studio 托管 WCF 服务库。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span>
>
> 1. <span data-ttu-id="d0f9e-189">在**解决方案资源管理器**中选择**入门项目**，然后从快捷菜单中选择 **"属性**"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="d0f9e-190">在同**一解决方案中调试另一个项目时**，选择**WCF 选项**并取消选中"启动 WCF 服务主机"。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d0f9e-191">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d0f9e-191">Next steps</span></span>

<span data-ttu-id="d0f9e-192">在本教程中，你了解了如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0f9e-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="d0f9e-193">创建和配置用于托管 WCF 服务的控制台应用项目。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="d0f9e-194">添加代码以承载 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="d0f9e-195">更新配置文件。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-195">Update the configuration file.</span></span>
> - <span data-ttu-id="d0f9e-196">启动 WCF 服务并验证其正在运行。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="d0f9e-197">进入下一个教程，了解如何创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="d0f9e-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d0f9e-198">教程：创建 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="d0f9e-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
