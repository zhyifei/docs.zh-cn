---
title: 教程：创建 Windows 通信基础客户端
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184100"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="dd63b-102">教程：创建 Windows 通信基础客户端</span><span class="sxs-lookup"><span data-stu-id="dd63b-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="dd63b-103">本教程介绍创建基本 Windows 通信基础 （WCF） 应用程序所需的五项任务中的第四个。</span><span class="sxs-lookup"><span data-stu-id="dd63b-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="dd63b-104">有关教程的概述，请参阅[教程：开始使用 Windows 通信基础应用程序](getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="dd63b-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="dd63b-105">创建 WCF 应用程序的下一个任务是通过从 WCF 服务检索元数据来创建客户端。</span><span class="sxs-lookup"><span data-stu-id="dd63b-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="dd63b-106">您可以使用 Visual Studio 添加服务引用，该服务引用从服务的 MEX 终结点获取元数据。</span><span class="sxs-lookup"><span data-stu-id="dd63b-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="dd63b-107">然后，Visual Studio 会以您选择的语言为客户端代理生成托管源代码文件。</span><span class="sxs-lookup"><span data-stu-id="dd63b-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="dd63b-108">它还创建一个客户端配置文件 *（App.config*）。</span><span class="sxs-lookup"><span data-stu-id="dd63b-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="dd63b-109">此文件使客户端应用程序能够在终结点连接到服务。</span><span class="sxs-lookup"><span data-stu-id="dd63b-109">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="dd63b-110">如果从 Visual Studio 中的类库项目调用 WCF 服务，请使用 **"添加服务参考"** 功能自动生成代理和相关配置文件。</span><span class="sxs-lookup"><span data-stu-id="dd63b-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="dd63b-111">但是，由于类库项目不使用此配置文件，因此您需要将生成的配置文件中的设置添加到调用类库的可执行文件*App.config*文件中。</span><span class="sxs-lookup"><span data-stu-id="dd63b-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="dd63b-112">作为替代方法，请使用[ServiceModel 元数据实用程序工具](#servicemodel-metadata-utility-tool)而不是 Visual Studio 来生成代理类和配置文件。</span><span class="sxs-lookup"><span data-stu-id="dd63b-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="dd63b-113">客户端应用程序使用生成的代理类与服务通信。</span><span class="sxs-lookup"><span data-stu-id="dd63b-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="dd63b-114">此过程在教程中描述[：使用客户端](how-to-use-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="dd63b-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="dd63b-115">在本教程中，你将了解如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dd63b-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="dd63b-116">为 WCF 客户端创建和配置控制台应用项目。</span><span class="sxs-lookup"><span data-stu-id="dd63b-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="dd63b-117">向 WCF 服务添加服务引用以生成代理类和配置文件。</span><span class="sxs-lookup"><span data-stu-id="dd63b-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="dd63b-118">创建 Windows 通信基础客户端</span><span class="sxs-lookup"><span data-stu-id="dd63b-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="dd63b-119">在可视化工作室中创建控制台应用项目：</span><span class="sxs-lookup"><span data-stu-id="dd63b-119">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="dd63b-120">在 **"文件"** 菜单中，选择 **"打开** > **项目/解决方案**"并浏览到您以前创建的**入门**解决方案 （*获取入门.sln*）。</span><span class="sxs-lookup"><span data-stu-id="dd63b-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="dd63b-121">选择“打开”。</span><span class="sxs-lookup"><span data-stu-id="dd63b-121">Select **Open**.</span></span>

    2. <span data-ttu-id="dd63b-122">在 **"查看"** 菜单中，选择 **"解决方案资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="dd63b-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="dd63b-123">在 **"解决方案资源管理器"** 窗口中，选择 **"入门"** 解决方案（顶部节点），然后从快捷菜单中选择 **"添加新** > **项目**"。</span><span class="sxs-lookup"><span data-stu-id="dd63b-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="dd63b-124">在左侧的 **"添加新项目**"窗口中，在 **"可视 C#"** 或"**可视基本**"下选择**Windows 桌面**类别。</span><span class="sxs-lookup"><span data-stu-id="dd63b-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="dd63b-125">选择**控制台应用 （.NET 框架）** 模板，然后输入"*开始客户端*"**名称**。</span><span class="sxs-lookup"><span data-stu-id="dd63b-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="dd63b-126">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="dd63b-126">Select **OK**.</span></span>

2. <span data-ttu-id="dd63b-127">在**入门客户端**项目中向<xref:System.ServiceModel>程序集添加引用：</span><span class="sxs-lookup"><span data-stu-id="dd63b-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="dd63b-128">在 **"解决方案资源管理器"** 窗口中，选择 **"入门客户端**"项目下的 **"参考"** 文件夹，然后从快捷菜单中选择 **"添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="dd63b-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="dd63b-129">在"**添加引用**"窗口中，在窗口左侧的 **"程序集**"下，选择 **"框架**"。</span><span class="sxs-lookup"><span data-stu-id="dd63b-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="dd63b-130">查找并选择 **"系统.服务模式**"，然后选择 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="dd63b-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="dd63b-131">通过选择 **"全部保存文件** > **"保存**解决方案。</span><span class="sxs-lookup"><span data-stu-id="dd63b-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="dd63b-132">向计算器服务添加服务引用：</span><span class="sxs-lookup"><span data-stu-id="dd63b-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="dd63b-133">在 **"解决方案资源管理器"** 窗口中，选择 **"入门客户端**"项目下的 **"参考"** 文件夹，然后从快捷菜单中选择 **"添加服务参考**"。</span><span class="sxs-lookup"><span data-stu-id="dd63b-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="dd63b-134">在 **"添加服务参考"** 窗口中，选择 **"发现**"。</span><span class="sxs-lookup"><span data-stu-id="dd63b-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="dd63b-135">计算器服务启动，可视化工作室在 **"服务**"框中显示它。</span><span class="sxs-lookup"><span data-stu-id="dd63b-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="dd63b-136">选择**计算器服务**以展开它并显示服务实现的服务协定。</span><span class="sxs-lookup"><span data-stu-id="dd63b-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="dd63b-137">保留默认**命名空间**并选择 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="dd63b-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="dd63b-138">Visual Studio 在 **"入门客户端**"项目中的 **"已连接服务**"文件夹下添加新项目。</span><span class="sxs-lookup"><span data-stu-id="dd63b-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="dd63b-139">服务模型元数据实用程序工具</span><span class="sxs-lookup"><span data-stu-id="dd63b-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="dd63b-140">以下示例演示如何选择使用[ServiceModel 元数据实用程序工具 （Svcutil.exe）](servicemodel-metadata-utility-tool-svcutil-exe.md)来生成代理类文件。</span><span class="sxs-lookup"><span data-stu-id="dd63b-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="dd63b-141">此工具生成代理类文件和*App.config*文件。</span><span class="sxs-lookup"><span data-stu-id="dd63b-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="dd63b-142">以下示例分别演示如何在 C# 和 Visual Basic 中生成代理：</span><span class="sxs-lookup"><span data-stu-id="dd63b-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="dd63b-143">客户端配置文件</span><span class="sxs-lookup"><span data-stu-id="dd63b-143">Client configuration file</span></span>

<span data-ttu-id="dd63b-144">创建客户端后，Visual Studio 将在 **"入门Client"** 项目中创建**App.config**配置文件，该文件应类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="dd63b-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="dd63b-145">在[\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md)部分下，请注意[\<终结点>](../configure-apps/file-schema/wcf/endpoint-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="dd63b-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="dd63b-146">**&lt;终结点&gt;** 元素定义客户端用于访问服务的终结点，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dd63b-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="dd63b-147">地址： `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="dd63b-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="dd63b-148">终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="dd63b-148">The address of the endpoint.</span></span>
- <span data-ttu-id="dd63b-149">服务合同： `ServiceReference1.ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="dd63b-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="dd63b-150">服务协定处理 WCF 客户端和服务之间的通信。</span><span class="sxs-lookup"><span data-stu-id="dd63b-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="dd63b-151">当您使用其 **"添加服务参考"** 功能时，Visual Studio 生成了此协定。</span><span class="sxs-lookup"><span data-stu-id="dd63b-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="dd63b-152">它实质上是您在入门项目中定义的合同副本。</span><span class="sxs-lookup"><span data-stu-id="dd63b-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="dd63b-153">绑定： <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="dd63b-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="dd63b-154">绑定指定 HTTP 作为传输、可互操作的安全性和其他配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="dd63b-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dd63b-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dd63b-155">Next steps</span></span>

<span data-ttu-id="dd63b-156">在本教程中，你了解了如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dd63b-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="dd63b-157">为 WCF 客户端创建和配置控制台应用项目。</span><span class="sxs-lookup"><span data-stu-id="dd63b-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="dd63b-158">向 WCF 服务添加服务引用，以生成客户端应用程序的代理类和配置文件。</span><span class="sxs-lookup"><span data-stu-id="dd63b-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="dd63b-159">前进至下一个教程，了解如何使用生成的客户端。</span><span class="sxs-lookup"><span data-stu-id="dd63b-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="dd63b-160">教程：使用 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="dd63b-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
