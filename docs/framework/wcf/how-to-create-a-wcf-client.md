---
title: 教程：创建 Windows Communication Foundation 客户端
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: ddb5167c7f71a263377fb465ec44ee21057fbf4a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928905"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="22b01-102">教程：创建 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="22b01-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="22b01-103">本教程介绍创建基本 Windows Communication Foundation （WCF）应用程序所需的五个任务中的第四个。</span><span class="sxs-lookup"><span data-stu-id="22b01-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="22b01-104">有关教程的概述，请参阅[教程：开始 Windows Communication Foundation 应用程序](getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="22b01-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="22b01-105">用于创建 WCF 应用程序的下一个任务是通过从 WCF 服务中检索元数据来创建客户端。</span><span class="sxs-lookup"><span data-stu-id="22b01-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="22b01-106">使用 Visual Studio 添加服务引用，后者从服务的 MEX 终结点中获取元数据。</span><span class="sxs-lookup"><span data-stu-id="22b01-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="22b01-107">然后，Visual Studio 将使用你选择的语言生成客户端代理的托管源代码文件。</span><span class="sxs-lookup"><span data-stu-id="22b01-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="22b01-108">它还会创建一个客户端配置文件（*app.config*）。</span><span class="sxs-lookup"><span data-stu-id="22b01-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="22b01-109">此文件使客户端应用程序能够连接到终结点上的服务。</span><span class="sxs-lookup"><span data-stu-id="22b01-109">This file enables the client application to connect to the service at an endpoint.</span></span> 

> [!NOTE]
> <span data-ttu-id="22b01-110">如果从 Visual Studio 中的类库项目调用 WCF 服务，请使用**添加服务引用**功能自动生成代理和关联的配置文件。</span><span class="sxs-lookup"><span data-stu-id="22b01-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="22b01-111">但是，由于类库项目不使用此配置文件，因此需要将生成的配置文件中的设置添加到调用类库的可执行文件的*app.config*文件中。</span><span class="sxs-lookup"><span data-stu-id="22b01-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="22b01-112">作为替代方法，请使用 "配置[元数据" 实用工具](#servicemodel-metadata-utility-tool)（而不是 Visual Studio）生成代理类和配置文件。</span><span class="sxs-lookup"><span data-stu-id="22b01-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="22b01-113">客户端应用程序使用生成的代理类与服务通信。</span><span class="sxs-lookup"><span data-stu-id="22b01-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="22b01-114">本过程在教程中[进行了介绍：使用客户端](how-to-use-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="22b01-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="22b01-115">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="22b01-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="22b01-116">创建并配置 WCF 客户端的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="22b01-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="22b01-117">将服务引用添加到 WCF 服务，以生成代理类和配置文件。</span><span class="sxs-lookup"><span data-stu-id="22b01-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="22b01-118">创建 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="22b01-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="22b01-119">在 Visual Studio 中创建控制台应用项目：</span><span class="sxs-lookup"><span data-stu-id="22b01-119">Create a console app project in Visual Studio:</span></span> 

    1. <span data-ttu-id="22b01-120">从 "**文件**" 菜单中，选择 "**打开** > **项目/解决方案**"，并浏览到前面创建的**GettingStarted**解决方案（*GettingStarted*）。</span><span class="sxs-lookup"><span data-stu-id="22b01-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="22b01-121">选择“打开”。</span><span class="sxs-lookup"><span data-stu-id="22b01-121">Select **Open**.</span></span>

    2. <span data-ttu-id="22b01-122">从 "**视图**" 菜单中选择 "**解决方案资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="22b01-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="22b01-123">在 "**解决方案资源管理器**" 窗口中，选择 " **GettingStarted** " 解决方案（顶级节点），然后从快捷菜单中选择 "**添加** > **新项目**"。</span><span class="sxs-lookup"><span data-stu-id="22b01-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 
    
    4. <span data-ttu-id="22b01-124">在 "**添加新项目**" 窗口的左侧，选择 "**视觉对象C#**  " 或**Visual Basic**下的 " **Windows 桌面**" 类别。</span><span class="sxs-lookup"><span data-stu-id="22b01-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="22b01-125">选择 "**控制台应用（.NET Framework）** " 模板，然后输入 " *GettingStartedClient* " 作为 "**名称**"。</span><span class="sxs-lookup"><span data-stu-id="22b01-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="22b01-126">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="22b01-126">Select **OK**.</span></span>

2. <span data-ttu-id="22b01-127">将**GettingStartedClient**项目中的引用添加到<xref:System.ServiceModel>程序集：</span><span class="sxs-lookup"><span data-stu-id="22b01-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="22b01-128">在 "**解决方案资源管理器**" 窗口中，选择 " **GettingStartedClient** " 项目下的 "**引用**" 文件夹，然后从快捷菜单中选择 "**添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="22b01-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="22b01-129">在 "**添加引用**" 窗口中窗口左侧的 "**程序集**" 下，选择 "**框架**"。</span><span class="sxs-lookup"><span data-stu-id="22b01-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>
    
    3. <span data-ttu-id="22b01-130">找到并选择 " **system.servicemodel**"，然后选择 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="22b01-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> 

    4. <span data-ttu-id="22b01-131">通过选择 "**文件** > " "**全部保存**" 保存解决方案。</span><span class="sxs-lookup"><span data-stu-id="22b01-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="22b01-132">将服务引用添加到计算器服务：</span><span class="sxs-lookup"><span data-stu-id="22b01-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="22b01-133">在 "**解决方案资源管理器**" 窗口中，选择 " **GettingStartedClient** " 项目下的 "**引用**" 文件夹，然后从快捷菜单中选择 "**添加服务引用**"。</span><span class="sxs-lookup"><span data-stu-id="22b01-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="22b01-134">在 "**添加服务引用**" 窗口中，选择 "**发现**"。</span><span class="sxs-lookup"><span data-stu-id="22b01-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="22b01-135">CalculatorService 服务启动，Visual Studio 会将其显示在 "**服务**" 框中。</span><span class="sxs-lookup"><span data-stu-id="22b01-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="22b01-136">选择 " **CalculatorService** " 以将其展开并显示服务实现的服务协定。</span><span class="sxs-lookup"><span data-stu-id="22b01-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="22b01-137">保留默认**命名空间**，然后选择 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="22b01-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="22b01-138">Visual Studio 将在**GettingStartedClient**项目中的**连接的服务**文件夹下添加一个新项。</span><span class="sxs-lookup"><span data-stu-id="22b01-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span> 

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="22b01-139">System.servicemodel 元数据实用工具</span><span class="sxs-lookup"><span data-stu-id="22b01-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="22b01-140">下面的示例演示如何选择性地使用带[元数据实用工具（svcutil.exe）](servicemodel-metadata-utility-tool-svcutil-exe.md)生成代理类文件。</span><span class="sxs-lookup"><span data-stu-id="22b01-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="22b01-141">此工具将生成代理类文件和*app.config*文件。</span><span class="sxs-lookup"><span data-stu-id="22b01-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="22b01-142">下面的示例演示如何分别在和 Visual Basic 中C#生成代理：</span><span class="sxs-lookup"><span data-stu-id="22b01-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="22b01-143">客户端配置文件</span><span class="sxs-lookup"><span data-stu-id="22b01-143">Client configuration file</span></span>

<span data-ttu-id="22b01-144">创建客户端后，Visual Studio 将在**GettingStartedClient**项目中创建**app.config**配置文件，该文件应类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="22b01-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

<span data-ttu-id="22b01-145">在 " [ \<system.servicemodel >](../configure-apps/file-schema/wcf/system-servicemodel.md) " [ \<](../configure-apps/file-schema/wcf/endpoint-element.md)部分下，注意终结点 > 元素。</span><span class="sxs-lookup"><span data-stu-id="22b01-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="22b01-146">**终结点元素&gt;定义客户端用于访问服务的终结点，如下所示： &lt;**</span><span class="sxs-lookup"><span data-stu-id="22b01-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="22b01-147">地址： `http://localhost:8000/GettingStarted/CalculatorService`。</span><span class="sxs-lookup"><span data-stu-id="22b01-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="22b01-148">终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="22b01-148">The address of the endpoint.</span></span>
- <span data-ttu-id="22b01-149">服务协定： `ServiceReference1.ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="22b01-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="22b01-150">服务协定处理 WCF 客户端和服务之间的通信。</span><span class="sxs-lookup"><span data-stu-id="22b01-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="22b01-151">使用其**添加服务引用**函数时，Visual Studio 会生成此约定。</span><span class="sxs-lookup"><span data-stu-id="22b01-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="22b01-152">它实质上是在 GettingStartedLib 项目中定义的协定副本。</span><span class="sxs-lookup"><span data-stu-id="22b01-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span> 
- <span data-ttu-id="22b01-153">绑定： <xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="22b01-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="22b01-154">绑定将 HTTP 指定为传输、可互操作的安全性和其他配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="22b01-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="22b01-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="22b01-155">Next steps</span></span>

<span data-ttu-id="22b01-156">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="22b01-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="22b01-157">创建并配置 WCF 客户端的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="22b01-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="22b01-158">将服务引用添加到 WCF 服务，以生成客户端应用程序的代理类和配置文件。</span><span class="sxs-lookup"><span data-stu-id="22b01-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="22b01-159">转到下一教程，了解如何使用生成的客户端。</span><span class="sxs-lookup"><span data-stu-id="22b01-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="22b01-160">教程：使用 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="22b01-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
