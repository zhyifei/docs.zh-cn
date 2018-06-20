---
title: Microsoft WCF Web Service Reference Provider 工具
description: Microsoft WCF Web Service Reference Provider 工具概述，该工具添加了 .NET Core 和 ASP.NET Core 项目的功能，类似于 .NET Framework 项目的添加服务引用。
author: mlacouture
ms.author: johalex
ms.date: 04/19/2018
ms.custom: mvc
ms.openlocfilehash: 416ca4dbedcf6e610aa5307c87934c0cb18be749
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215373"
---
# <a name="microsoft-wcf-web-service-reference-provider-tool"></a><span data-ttu-id="2322a-103">Microsoft WCF Web Service Reference Provider 工具</span><span class="sxs-lookup"><span data-stu-id="2322a-103">Microsoft WCF Web Service Reference Provider Tool</span></span>

<span data-ttu-id="2322a-104">多年来，许多 Visual Studio 开发者在其. NET Framework 项目需要访问 Web 服务时，都享受到了[添加服务引用](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)工具所带来的工作效率。</span><span class="sxs-lookup"><span data-stu-id="2322a-104">Over the years, many Visual Studio developers have enjoyed the productivity that the [**Add Service Reference**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) tool provided when their .NET Framework projects needed to access web services.</span></span>  <span data-ttu-id="2322a-105">WCF Web 服务引用工具是 Visual Studio 连接服务的扩展，提供了类似于 .NET Core 和 ASP.NET Core 项目的“添加服务引用”功能的体验。</span><span class="sxs-lookup"><span data-stu-id="2322a-105">The **WCF Web Service Reference** tool is a Visual Studio connected service extension that provides an experience like the Add Service Reference functionality for .NET Core and ASP.NET Core projects.</span></span> <span data-ttu-id="2322a-106">此工具可从网络位置的当前解决方案的 web 服务中或从 WSDL 文件中检索元数据，并生成包含可用于访问 web 服务的 Windows Communication Foundation (WCF) 客户端代理代码的可兼容 .NET Core 的源文件。</span><span class="sxs-lookup"><span data-stu-id="2322a-106">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2322a-107">应仅从受信任源引用服务。</span><span class="sxs-lookup"><span data-stu-id="2322a-107">You should only reference services from a trusted source.</span></span> <span data-ttu-id="2322a-108">从不受信任的源添加引用可能会危及安全性。</span><span class="sxs-lookup"><span data-stu-id="2322a-108">Adding references from an untrusted source may compromise security.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2322a-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="2322a-109">Prerequisites</span></span>

* <span data-ttu-id="2322a-110">[Visual Studio 2017 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2322a-110">[Visual Studio 2017 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) or later versions</span></span>

## <a name="how-to-use-the-extension"></a><span data-ttu-id="2322a-111">如何使用扩展</span><span class="sxs-lookup"><span data-stu-id="2322a-111">How to use the extension</span></span>

> [!NOTE]
> <span data-ttu-id="2322a-112">“WCF Web 服务引用”选项适用于使用以下项目模板创建的项目：</span><span class="sxs-lookup"><span data-stu-id="2322a-112">The **WCF Web Service Reference** option is applicable to projects created using the following project templates:</span></span>
> * <span data-ttu-id="2322a-113">Visual C# > .NET Core</span><span class="sxs-lookup"><span data-stu-id="2322a-113">**Visual C#** > **.NET Core**</span></span>
> * <span data-ttu-id="2322a-114">Visual C# > .NET Standard</span><span class="sxs-lookup"><span data-stu-id="2322a-114">**Visual C#** > **.NET Standard**</span></span>
> * <span data-ttu-id="2322a-115">Visual C# > Web > ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="2322a-115">**Visual C#** > **Web** > **ASP.NET Core Web Application**</span></span>

<span data-ttu-id="2322a-116">以“ASP.NET Core Web 应用程序”项目模板为例，本文将介绍如何向该项目中添加 WCF 服务引用：</span><span class="sxs-lookup"><span data-stu-id="2322a-116">Using the **ASP.NET Core Web Application** project template as an example, this article walks you through adding a WCF service reference to the project:</span></span>

1. <span data-ttu-id="2322a-117">在解决方案资源管理器中，双击项目的“连接的服务”节点（对于 .NET Core 或 .NET Standard 项目，当在解决方案资源管理器中右键单击项目的“依赖项”节点时，该选项可用）。</span><span class="sxs-lookup"><span data-stu-id="2322a-117">In Solution Explorer, double-click the **Connected Services** node of the project (for a .NET Core or .NET Standard project this option is available when you right-click on the **Dependencies** node of the project in Solution Explorer).</span></span>

<span data-ttu-id="2322a-118">随即显示“连接的服务”页，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="2322a-118">The **Connected Services** page appears as shown in the following image:</span></span>

![“连接的服务”选项卡](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. <span data-ttu-id="2322a-120">在“连接的服务”页上，单击“Microsoft WCF Web Service Reference Provider”。</span><span class="sxs-lookup"><span data-stu-id="2322a-120">On the **Connected Services** page, click **Microsoft WCF Web Service Reference Provider**.</span></span> <span data-ttu-id="2322a-121">此操作将显示“配置 WCF Web 服务引用”向导：</span><span class="sxs-lookup"><span data-stu-id="2322a-121">This brings up the **Configure WCF Web Service Reference** wizard:</span></span>

![“服务终结点”选项卡](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. <span data-ttu-id="2322a-123">选择服务。</span><span class="sxs-lookup"><span data-stu-id="2322a-123">Select a service.</span></span>

    <span data-ttu-id="2322a-124">3a.</span><span class="sxs-lookup"><span data-stu-id="2322a-124">3a.</span></span> <span data-ttu-id="2322a-125">“配置 WCF Web 服务引用”向导中提供了多个服务搜索选项：</span><span class="sxs-lookup"><span data-stu-id="2322a-125">There are several services search options available within the **Configure WCF Web Service Reference** wizard:</span></span>
    
     * <span data-ttu-id="2322a-126">要搜索当前解决方案中定义的服务，请单击“发现”按钮。</span><span class="sxs-lookup"><span data-stu-id="2322a-126">To search for services defined in the current solution, click the **Discover** button.</span></span> 
     * <span data-ttu-id="2322a-127">要搜索在指定地址托管的服务，请在“地址”框中输入服务 URL，然后单击“转到”按钮。</span><span class="sxs-lookup"><span data-stu-id="2322a-127">To search for services hosted at a specified address, enter a service URL in the **Address** box and click the **Go** button.</span></span>
     * <span data-ttu-id="2322a-128">要选择包含 Web 服务元数据信息的 WSDL 文件，请单击“浏览”按钮。</span><span class="sxs-lookup"><span data-stu-id="2322a-128">To select a WSDL file that contains the web service metadata information, click the **Browse** button.</span></span> 
     
    <span data-ttu-id="2322a-129">3b.</span><span class="sxs-lookup"><span data-stu-id="2322a-129">3b.</span></span> <span data-ttu-id="2322a-130">从“服务”框内的搜索结果列表中选择服务。</span><span class="sxs-lookup"><span data-stu-id="2322a-130">Select the service from the search results list in the **Services** box.</span></span> <span data-ttu-id="2322a-131">如果需要，请在相应的“名称空间”文本框中为生成的代码输入命名空间。</span><span class="sxs-lookup"><span data-stu-id="2322a-131">If needed, enter the namespace for the generated code in the corresponding **Namespace** text box.</span></span>
    
    <span data-ttu-id="2322a-132">3c.</span><span class="sxs-lookup"><span data-stu-id="2322a-132">3c.</span></span> <span data-ttu-id="2322a-133">单击“下一步”按钮，打开“数据类型选项”页和“客户端选项”页。</span><span class="sxs-lookup"><span data-stu-id="2322a-133">Click the **Next** button to open the **Data Type Options** and the **Client Options** pages.</span></span> <span data-ttu-id="2322a-134">或者，单击“完成”按钮，使用默认选项。</span><span class="sxs-lookup"><span data-stu-id="2322a-134">Alternatively, click the **Finish** button to use the default options.</span></span>


4. <span data-ttu-id="2322a-135">“数据类型选项”窗体可用于优化生成的服务引用配置设置：</span><span class="sxs-lookup"><span data-stu-id="2322a-135">The **Data Type Options** form enables you to refine the generated service reference configuration settings:</span></span>

![“数据类型选项”选项卡](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

> [!NOTE]
> <span data-ttu-id="2322a-137">如果在项目的引用程序集中定义了服务引用代码生成所需的数据类型，则“重新使用引用程序集中的类型”复选框选项将非常有用。</span><span class="sxs-lookup"><span data-stu-id="2322a-137">The **Reuse types in referenced assemblies** check box option is useful when data types needed for service reference code generation are defined in one of your project's referenced assemblies.</span></span>  <span data-ttu-id="2322a-138">重新使用这些现有数据类型，从而避免编译时类型冲突或运行时问题，这是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="2322a-138">It's important to reuse those existing data types to avoid compile-time type clash or runtime issues.</span></span>

<span data-ttu-id="2322a-139">加载类型信息时可能会有延迟，具体取决于项目依赖项和其他系统性能因素的数量。</span><span class="sxs-lookup"><span data-stu-id="2322a-139">There may be a delay while type information is loaded, depending on the number of project dependencies and other system performance factors.</span></span> <span data-ttu-id="2322a-140">加载过程中，“完成”按钮被禁用，除非未选中“重新使用引用程序集中的类型”复选框。</span><span class="sxs-lookup"><span data-stu-id="2322a-140">The **Finish** button is disabled during loading unless the **Reuse types in referenced assemblies** check box is unchecked.</span></span>

5. <span data-ttu-id="2322a-141">完成后，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="2322a-141">Click **Finish** when you are done.</span></span>


<span data-ttu-id="2322a-142">在显示进度的同时，工具：</span><span class="sxs-lookup"><span data-stu-id="2322a-142">While displaying progress, the tool:</span></span>

* <span data-ttu-id="2322a-143">从 WCF 服务下载元数据。</span><span class="sxs-lookup"><span data-stu-id="2322a-143">Downloads metadata from the WCF service.</span></span> 
* <span data-ttu-id="2322a-144">在名为“reference.cs”的文件中生成服务引用代码，并将其添加到“连接的服务”节点下的项目。</span><span class="sxs-lookup"><span data-stu-id="2322a-144">Generates the service reference code in a file named *reference.cs*, and adds it to your project under the **Connected Services** node.</span></span> 
* <span data-ttu-id="2322a-145">使用在目标平台上编译和运行所需的 NuGet 包引用更新项目文件 (.csproj)。</span><span class="sxs-lookup"><span data-stu-id="2322a-145">Updates the project file (.csproj) with NuGet package references required to compile and run on the target platform.</span></span>

![进度窗口](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

<span data-ttu-id="2322a-147">进度完成后，可创建生成的 WCF 客户端类型的实例并调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="2322a-147">When these processes complete, you can create an instance of the generated WCF client type and invoke the service operations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2322a-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2322a-148">Next steps</span></span>

### <a name="feedback--questions"></a><span data-ttu-id="2322a-149">反馈和问题</span><span class="sxs-lookup"><span data-stu-id="2322a-149">Feedback & questions</span></span>
<span data-ttu-id="2322a-150">如果有任何问题或反馈，请[在 GitHub 上提问](https://github.com/dotnet/wcf/issues/new)。</span><span class="sxs-lookup"><span data-stu-id="2322a-150">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="2322a-151">也可以在 [GitHub 上的 WCF 存储库](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling)中查看任何现有问题。</span><span class="sxs-lookup"><span data-stu-id="2322a-151">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

### <a name="release-notes"></a><span data-ttu-id="2322a-152">发行说明</span><span class="sxs-lookup"><span data-stu-id="2322a-152">Release notes</span></span>
* <span data-ttu-id="2322a-153">请参阅[发行说明](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md)，了解更新的版本信息（包括已知问题）。</span><span class="sxs-lookup"><span data-stu-id="2322a-153">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) for updated release information, including known issues.</span></span> 
