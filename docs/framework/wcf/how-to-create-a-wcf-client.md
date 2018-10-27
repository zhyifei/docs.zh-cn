---
title: 如何：创建 Windows Communication Foundation 客户端
ms.date: 09/14/2018
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 9572f3e2c0cddf75daf343f250b16e94bc2b0dbf
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181665"
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a><span data-ttu-id="8b99b-102">如何：创建 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="8b99b-102">How to: Create a Windows Communication Foundation Client</span></span>

<span data-ttu-id="8b99b-103">这是创建 Windows Communication Foundation (WCF) 应用程序所需的六项任务的第四个。</span><span class="sxs-lookup"><span data-stu-id="8b99b-103">This is the fourth of six tasks required to create a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="8b99b-104">有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。</span><span class="sxs-lookup"><span data-stu-id="8b99b-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="8b99b-105">本主题介绍如何从 WCF 服务检索元数据和使用它来创建可以访问该服务的 WCF 代理。</span><span class="sxs-lookup"><span data-stu-id="8b99b-105">This topic describes how to retrieve metadata from a WCF service and use it to create a WCF proxy that can access the service.</span></span> <span data-ttu-id="8b99b-106">完成此任务是借助**添加服务引用**Visual Studio 提供的功能。</span><span class="sxs-lookup"><span data-stu-id="8b99b-106">This task is completed by using the **Add Service Reference** functionality provided by Visual Studio.</span></span> <span data-ttu-id="8b99b-107">此工具从服务的 MEX 终结点获取元数据，并以所选语言（默认情况下为 C#）为客户端代理生成托管源代码文件。</span><span class="sxs-lookup"><span data-stu-id="8b99b-107">This tool obtains the metadata from the service’s MEX endpoint and generates a managed source code file for a client proxy in the language you have chosen (C# by default).</span></span> <span data-ttu-id="8b99b-108">除了创建客户端代理外，该工具还会创建或更新客户端配置文件，以使客户端应用程序能够连接至其某个终结点上的服务。</span><span class="sxs-lookup"><span data-stu-id="8b99b-108">In addition to creating the client proxy, the tool also creates or updates the client configuration file which enables the client application to connect to the service at one of its endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="8b99b-109">此外可以使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)工具生成的代理类和配置而不是使用**添加服务引用**Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="8b99b-109">You can also use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool to generate the proxy class and configuration instead of using **Add Service Reference** in Visual Studio.</span></span>

> [!NOTE]
> <span data-ttu-id="8b99b-110">当从一个在 Visual Studio 类库项目中调用 WCF 服务，可以使用**添加服务引用**功能来自动生成代理和关联的配置文件。</span><span class="sxs-lookup"><span data-stu-id="8b99b-110">When calling a WCF service from a class library project in Visual Studio, you can use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="8b99b-111">该类库项目不会使用配置文件。</span><span class="sxs-lookup"><span data-stu-id="8b99b-111">The configuration file will not be used by the class library project.</span></span> <span data-ttu-id="8b99b-112">您需要向调用该类库的可执行文件的 app.config 文件中生成的配置文件添加设置。</span><span class="sxs-lookup"><span data-stu-id="8b99b-112">You need to add the settings in the generated configuration file to the app.config file for the executable that calls the class library.</span></span>

<span data-ttu-id="8b99b-113">客户端应用程序使用生成的代理类与服务通信。</span><span class="sxs-lookup"><span data-stu-id="8b99b-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="8b99b-114">此过程所述[如何： 使用客户端](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="8b99b-114">This procedure is described in [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>

## <a name="to-create-a-windows-communication-foundation-client"></a><span data-ttu-id="8b99b-115">创建 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="8b99b-115">To create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="8b99b-116">在 Visual Studio 中创建新的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="8b99b-116">Create a new console application project in Visual Studio.</span></span> <span data-ttu-id="8b99b-117">右键单击入门解决方案中**解决方案资源管理器**，然后选择**添加** > **新建项目**。</span><span class="sxs-lookup"><span data-stu-id="8b99b-117">Right-click on the Getting Started solution in **Solution Explorer** and select **Add** > **New Project**.</span></span> <span data-ttu-id="8b99b-118">在**添加新项目**对话框中的，在左侧，选择**Windows Desktop**类别中的下**Visual C#** 或者**Visual Basic**。</span><span class="sxs-lookup"><span data-stu-id="8b99b-118">In the **Add New Project** dialog, on the left-hand side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> <span data-ttu-id="8b99b-119">选择**控制台应用 (.NET Framework)** 模板，然后命名项目**GettingStartedClient**。</span><span class="sxs-lookup"><span data-stu-id="8b99b-119">Select the **Console App (.NET Framework)** template, and then name the project **GettingStartedClient**.</span></span>

2. <span data-ttu-id="8b99b-120">将对 System.ServiceModel 的引用添加到 GettingStartedClient 项目。</span><span class="sxs-lookup"><span data-stu-id="8b99b-120">Add a reference to System.ServiceModel to the GettingStartedClient project.</span></span> <span data-ttu-id="8b99b-121">右键单击**引用**GettingStartedClient 项目下的文件夹**解决方案资源管理器**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="8b99b-121">Right-click on the **References** folder under the GettingStartedClient project in **Solution Explorer**, and then select **Add Reference**.</span></span> <span data-ttu-id="8b99b-122">在中**添加引用**对话框中，选择**Framework**下的对话框左侧**程序集**。</span><span class="sxs-lookup"><span data-stu-id="8b99b-122">In the **Add Reference** dialog, select **Framework** on the left-hand side of the dialog under **Assemblies**.</span></span> <span data-ttu-id="8b99b-123">找到并选择**System.ServiceModel**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b99b-123">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> <span data-ttu-id="8b99b-124">通过选择保存解决方案**文件** > **全部保存**。</span><span class="sxs-lookup"><span data-stu-id="8b99b-124">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="8b99b-125">添加到计算器服务的服务引用。</span><span class="sxs-lookup"><span data-stu-id="8b99b-125">Add a service reference to the Calculator Service.</span></span>

   1. <span data-ttu-id="8b99b-126">首先，启动 GettingStartedHost 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b99b-126">First, start up the GettingStartedHost console application.</span></span>

   2. <span data-ttu-id="8b99b-127">主机运行后，右键单击**引用**GettingStartedClient 项目下的文件夹**解决方案资源管理器**，然后选择**添加** >  **服务引用**。</span><span class="sxs-lookup"><span data-stu-id="8b99b-127">Once the host is running, right-click the **References** folder under the GettingStartedClient project in **Solution Explorer** and select **Add** > **Service Reference**.</span></span>

   3. <span data-ttu-id="8b99b-128">在的地址框中输入以下 URL**添加服务引用**对话框： [http://localhost:8000/GettingStarted/CalculatorService](http://localhost:8000/GettingStarted/CalculatorService)</span><span class="sxs-lookup"><span data-stu-id="8b99b-128">Enter the following URL in the address box of the **Add Service Reference** dialog: [http://localhost:8000/GettingStarted/CalculatorService](http://localhost:8000/GettingStarted/CalculatorService)</span></span>

   4. <span data-ttu-id="8b99b-129">选择**转**。</span><span class="sxs-lookup"><span data-stu-id="8b99b-129">Choose **Go**.</span></span>

   <span data-ttu-id="8b99b-130">中显示 CalculatorService **Services**列表框。</span><span class="sxs-lookup"><span data-stu-id="8b99b-130">The CalculatorService is displayed in the **Services** list box.</span></span> <span data-ttu-id="8b99b-131">双击 CalculatorService 可展开它并显示由该服务实现的服务协定。</span><span class="sxs-lookup"><span data-stu-id="8b99b-131">Double-click CalculatorService to expand it and show the service contracts implemented by the service.</span></span> <span data-ttu-id="8b99b-132">保留为默认命名空间的并选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b99b-132">Leave the default namespace as-is and choose **OK**.</span></span>

    <span data-ttu-id="8b99b-133">在出现新项时添加到使用 Visual Studio 服务的引用，请**解决方案资源管理器**下**服务引用**GettingStartedClient 项目下的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b99b-133">When you add a reference to a service using Visual Studio, a new item appears in **Solution Explorer** under the **Service References** folder under the GettingStartedClient project.</span></span> <span data-ttu-id="8b99b-134">如果您使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)生成工具、 源代码文件和 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="8b99b-134">If you use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool, a source code file and app.config file are generated.</span></span>

    <span data-ttu-id="8b99b-135">您还可以使用命令行工具[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)使用适当的开关来创建客户端代码。</span><span class="sxs-lookup"><span data-stu-id="8b99b-135">You can also use the command-line tool [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) with the appropriate switches to create the client code.</span></span> <span data-ttu-id="8b99b-136">下面的示例生成服务的代码文件和配置文件。</span><span class="sxs-lookup"><span data-stu-id="8b99b-136">The following example generates a code file and a configuration file for the service.</span></span> <span data-ttu-id="8b99b-137">第一个示例演示如何在 VB 中生成代理，并第二个演示如何在 C# 中生成代理：</span><span class="sxs-lookup"><span data-stu-id="8b99b-137">The first example shows how to generate the proxy in VB, and the second shows how to generate the proxy in C#:</span></span>

    ```shell
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
    ```

    ```shell
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
    ```

## <a name="next-steps"></a><span data-ttu-id="8b99b-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8b99b-138">Next steps</span></span>

<span data-ttu-id="8b99b-139">你已创建客户端应用程序将用于调用计算器服务的代理。</span><span class="sxs-lookup"><span data-stu-id="8b99b-139">You've created the proxy that the client application will use to call the calculator service.</span></span> <span data-ttu-id="8b99b-140">请转到序列中下一主题。</span><span class="sxs-lookup"><span data-stu-id="8b99b-140">Proceed to the next topic in the series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8b99b-141">如何：配置客户端</span><span class="sxs-lookup"><span data-stu-id="8b99b-141">How to: Configure a Client</span></span>](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

## <a name="see-also"></a><span data-ttu-id="8b99b-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b99b-142">See also</span></span>

- [<span data-ttu-id="8b99b-143">ServiceModel 元数据实用工具 (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="8b99b-143">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="8b99b-144">入门</span><span class="sxs-lookup"><span data-stu-id="8b99b-144">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="8b99b-145">自承载</span><span class="sxs-lookup"><span data-stu-id="8b99b-145">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="8b99b-146">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="8b99b-146">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="8b99b-147">如何：使用 Svcutil.exe 下载元数据文档</span><span class="sxs-lookup"><span data-stu-id="8b99b-147">How to: Use Svcutil.exe to Download Metadata Documents</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
