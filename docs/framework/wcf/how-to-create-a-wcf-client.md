---
title: 教程：创建 Windows Communication Foundation 客户端
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: a16a0ccabfd0f9fbe69db1ea88d4613185f3c1da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174364"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="f4ead-102">教程：创建 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="f4ead-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="f4ead-103">本教程介绍创建基本 Windows Communication Foundation (WCF) 应用程序所需的五个任务的第四个。</span><span class="sxs-lookup"><span data-stu-id="f4ead-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="f4ead-104">有关教程的概述，请参阅[教程：开始使用 Windows Communication Foundation 应用程序](getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="f4ead-105">创建 WCF 应用程序的下一个任务是通过从 WCF 服务检索元数据创建客户端。</span><span class="sxs-lookup"><span data-stu-id="f4ead-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="f4ead-106">使用 Visual Studio 添加服务引用，它将从服务的 MEX 终结点获取元数据。</span><span class="sxs-lookup"><span data-stu-id="f4ead-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="f4ead-107">Visual Studio 然后为你选择的语言中的客户端代理生成托管的源代码文件。</span><span class="sxs-lookup"><span data-stu-id="f4ead-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="f4ead-108">它还会创建客户端配置文件 (*App.config*)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="f4ead-109">此文件使客户端应用程序连接到终结点的服务。</span><span class="sxs-lookup"><span data-stu-id="f4ead-109">This file enables the client application to connect to the service at an endpoint.</span></span> 

> [!NOTE]
> <span data-ttu-id="f4ead-110">如果从一个在 Visual Studio 类库项目调用 WCF 服务，使用**添加服务引用**功能来自动生成代理和关联的配置文件。</span><span class="sxs-lookup"><span data-stu-id="f4ead-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="f4ead-111">但是，因为在类库项目不使用此配置文件，您需要在生成的配置文件中添加设置*App.config*调用该类库的可执行文件的文件。</span><span class="sxs-lookup"><span data-stu-id="f4ead-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="f4ead-112">或者，使用[ServiceModel 元数据实用工具工具](#servicemodel-metadata-utility-tool)而不是 Visual Studio 生成代理类和配置文件。</span><span class="sxs-lookup"><span data-stu-id="f4ead-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="f4ead-113">客户端应用程序使用生成的代理类与服务通信。</span><span class="sxs-lookup"><span data-stu-id="f4ead-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="f4ead-114">此过程所述[教程：使用客户端](how-to-use-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="f4ead-115">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="f4ead-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="f4ead-116">创建和配置 WCF 客户端的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="f4ead-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="f4ead-117">添加到 WCF 服务生成代理类和配置文件的服务引用。</span><span class="sxs-lookup"><span data-stu-id="f4ead-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="f4ead-118">创建 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="f4ead-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="f4ead-119">在 Visual Studio 中创建一个控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="f4ead-119">Create a console app project in Visual Studio:</span></span> 

    1. <span data-ttu-id="f4ead-120">从**文件**菜单中，选择**打开** > **项目/解决方案**并浏览到**GettingStarted**解决方案，以前创建的 (*GettingStarted.sln*)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="f4ead-121">选择“打开” 。</span><span class="sxs-lookup"><span data-stu-id="f4ead-121">Select **Open**.</span></span>

    2. <span data-ttu-id="f4ead-122">从**视图**菜单中，选择**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="f4ead-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="f4ead-123">在中**解决方案资源管理器**窗口中，选择**GettingStarted**解决方案 （高层节点），然后选择**添加** > **的新项目**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="f4ead-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 
    
    4. <span data-ttu-id="f4ead-124">在中**添加新项目**窗口中的，左侧和右侧，选择**Windows Desktop**类别中的下**Visual C#** 或**Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="f4ead-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="f4ead-125">选择**控制台应用 (.NET Framework)** 模板，并输入*GettingStartedClient*有关**名称**。</span><span class="sxs-lookup"><span data-stu-id="f4ead-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="f4ead-126">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="f4ead-126">Select **OK**.</span></span>

2. <span data-ttu-id="f4ead-127">添加引用**GettingStartedClient**投影到<xref:System.ServiceModel>程序集：</span><span class="sxs-lookup"><span data-stu-id="f4ead-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1.  <span data-ttu-id="f4ead-128">在中**解决方案资源管理器**窗口中，选择**引用**下的文件夹**GettingStartedClient**项目，，然后选择**添加引用**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="f4ead-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="f4ead-129">在中**添加引用**窗口下**程序集**在窗口的左侧，选择**Framework**。</span><span class="sxs-lookup"><span data-stu-id="f4ead-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>
    
    3. <span data-ttu-id="f4ead-130">找到并选择**System.ServiceModel**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="f4ead-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> 

    4. <span data-ttu-id="f4ead-131">通过选择保存解决方案**文件** > **全部保存**。</span><span class="sxs-lookup"><span data-stu-id="f4ead-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="f4ead-132">添加到计算器服务的服务引用：</span><span class="sxs-lookup"><span data-stu-id="f4ead-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="f4ead-133">在中**解决方案资源管理器**窗口中，选择**引用**下的文件夹**GettingStartedClient**项目，，然后选择**添加服务引用**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="f4ead-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="f4ead-134">在中**添加服务引用**窗口中，选择**Discover**。</span><span class="sxs-lookup"><span data-stu-id="f4ead-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="f4ead-135">CalculatorService 服务启动和 Visual Studio 将显示在**Services**框。</span><span class="sxs-lookup"><span data-stu-id="f4ead-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="f4ead-136">选择**CalculatorService**以将其展开并显示由该服务实现的服务协定。</span><span class="sxs-lookup"><span data-stu-id="f4ead-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="f4ead-137">保留默认值**Namespace** ，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="f4ead-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="f4ead-138">Visual Studio 会添加新项下的**连接的服务**中的文件夹**GettingStartedClient**项目。</span><span class="sxs-lookup"><span data-stu-id="f4ead-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span> 

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="f4ead-139">ServiceModel 元数据实用工具工具</span><span class="sxs-lookup"><span data-stu-id="f4ead-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="f4ead-140">下面的示例演示如何根据需要使用[ServiceModel 元数据实用工具工具 (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)生成代理类文件。</span><span class="sxs-lookup"><span data-stu-id="f4ead-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="f4ead-141">此工具生成代理类文件和*App.config*文件。</span><span class="sxs-lookup"><span data-stu-id="f4ead-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="f4ead-142">以下示例演示如何生成中的代理C#和 Visual Basic 中，分别：</span><span class="sxs-lookup"><span data-stu-id="f4ead-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="f4ead-143">客户端配置文件</span><span class="sxs-lookup"><span data-stu-id="f4ead-143">Client configuration file</span></span>

<span data-ttu-id="f4ead-144">创建客户端后，Visual Studio 将创建**App.config**中的配置文件**GettingStartedClient**项目，它应类似于下面的示例：</span><span class="sxs-lookup"><span data-stu-id="f4ead-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="f4ead-145">下[ \<system.serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md)部分中，请注意[\<终结点 >](../configure-apps/file-schema/wcf/endpoint-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f4ead-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="f4ead-146">**&lt;终结点&gt;** 元素定义的终结点的客户端用于访问该服务，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f4ead-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>
- <span data-ttu-id="f4ead-147">地址： `http://localhost:8000/GettingStarted/CalculatorService`。</span><span class="sxs-lookup"><span data-stu-id="f4ead-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="f4ead-148">终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="f4ead-148">The address of the endpoint.</span></span>
- <span data-ttu-id="f4ead-149">服务协定： `ServiceReference1.ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="f4ead-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="f4ead-150">服务协定处理 WCF 客户端和服务之间的通信。</span><span class="sxs-lookup"><span data-stu-id="f4ead-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="f4ead-151">在使用时，visual Studio 将生成此协定及其**添加服务引用**函数。</span><span class="sxs-lookup"><span data-stu-id="f4ead-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="f4ead-152">它是约定的实质上是约定的在 GettingStartedLib 项目中定义的副本。</span><span class="sxs-lookup"><span data-stu-id="f4ead-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span> 
- <span data-ttu-id="f4ead-153">绑定： <xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="f4ead-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="f4ead-154">绑定指定 HTTP 作为传输协议、 可互操作安全性和其他配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4ead-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f4ead-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f4ead-155">Next steps</span></span>

<span data-ttu-id="f4ead-156">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="f4ead-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="f4ead-157">创建和配置 WCF 客户端的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="f4ead-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="f4ead-158">添加到 WCF 服务，以生成客户端应用程序的代理类和配置文件的服务引用。</span><span class="sxs-lookup"><span data-stu-id="f4ead-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="f4ead-159">转到下一步的教程，了解如何使用生成的客户端。</span><span class="sxs-lookup"><span data-stu-id="f4ead-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f4ead-160">教程：使用 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="f4ead-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
