---
title: Azure Functions 的无服务器应用
description: Azure functions 提供无服务器功能跨多个语言 （C#、 JavaScript、 Java） 和平台提供事件驱动即时缩放代码。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 2d8729276a5797bd8b89c39d8fb03c6f20646ea0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145158"
---
# <a name="azure-functions"></a><span data-ttu-id="6f744-103">Azure Functions</span><span class="sxs-lookup"><span data-stu-id="6f744-103">Azure Functions</span></span>

<span data-ttu-id="6f744-104">Azure functions 提供无服务器计算体验。</span><span class="sxs-lookup"><span data-stu-id="6f744-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="6f744-105">通过调用函数*触发器*（如访问 HTTP 终结点或计时器） 并执行代码或业务逻辑的块。</span><span class="sxs-lookup"><span data-stu-id="6f744-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="6f744-106">函数还支持专用*绑定*，连接到存储和队列等资源。</span><span class="sxs-lookup"><span data-stu-id="6f744-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure functions 徽标](./media/azure-functions-logo.png)

<span data-ttu-id="6f744-108">有两个版本的 Azure 功能框架。</span><span class="sxs-lookup"><span data-stu-id="6f744-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="6f744-109">旧的版本支持完整的.NET Framework 和新的运行时支持跨平台.NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6f744-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="6f744-110">除了其他语言C#JavaScript 中，如F#，并支持 Java。</span><span class="sxs-lookup"><span data-stu-id="6f744-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="6f744-111">在门户中创建的函数提供了丰富的脚本语法。</span><span class="sxs-lookup"><span data-stu-id="6f744-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="6f744-112">可以使用完整的平台支持和功能部署作为独立项目创建的函数。</span><span class="sxs-lookup"><span data-stu-id="6f744-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="6f744-113">有关详细信息，请参阅[Azure Functions 文档](https://docs.microsoft.com/azure/azure-functions)。</span><span class="sxs-lookup"><span data-stu-id="6f744-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="6f744-114">函数 v1 与 v2</span><span class="sxs-lookup"><span data-stu-id="6f744-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="6f744-115">有两个版本的 Azure Functions 运行时：1.x 和 2.x。</span><span class="sxs-lookup"><span data-stu-id="6f744-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="6f744-116">版本 1.x 已正式推出 (GA)。</span><span class="sxs-lookup"><span data-stu-id="6f744-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="6f744-117">它支持从门户或 Windows 计算机的.NET 开发，并使用.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="6f744-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="6f744-118">1.x 支持C#，JavaScript，和F#，使用 Python、 PHP、 TypeScript、 Batch、 Bash、 和 PowerShell 的实验性支持。</span><span class="sxs-lookup"><span data-stu-id="6f744-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="6f744-119">版本 2.x 处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="6f744-119">Version 2.x is in preview.</span></span> <span data-ttu-id="6f744-120">它利用.NET Core，并支持 Windows、 macOS 和 Linux 计算机上的跨平台开发。</span><span class="sxs-lookup"><span data-stu-id="6f744-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="6f744-121">2.x 添加了适用于 Java 的一流支持，但尚不直接支持的任何实验性语言。</span><span class="sxs-lookup"><span data-stu-id="6f744-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="6f744-122">版本 2.x 使用新的绑定扩展性模型，从而使第三方扩展到平台独立的版本控制的绑定，并更简化的执行环境。</span><span class="sxs-lookup"><span data-stu-id="6f744-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="6f744-123">**与 1.x 中没有的已知的问题[绑定重定向支持](https://github.com/Azure/azure-functions-host/issues/992)。**</span><span class="sxs-lookup"><span data-stu-id="6f744-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="6f744-124">问题是特定于.NET 开发。</span><span class="sxs-lookup"><span data-stu-id="6f744-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="6f744-125">依赖库的运行时中包括的库中的不同版本的项目会受到影响。</span><span class="sxs-lookup"><span data-stu-id="6f744-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="6f744-126">功能团队已致力于具体进度有关的问题。</span><span class="sxs-lookup"><span data-stu-id="6f744-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="6f744-127">它将进入正式发布之前，团队将解决在 2.x 中的绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="6f744-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="6f744-128">此处提供了官方团队语句中使用的建议修补程序和解决方法：[在 Azure Functions 中的程序集解析](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions)。</span><span class="sxs-lookup"><span data-stu-id="6f744-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="6f744-129">有关详细信息，请参阅[比较 1.x 和 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions)。</span><span class="sxs-lookup"><span data-stu-id="6f744-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="6f744-130">编程语言支持</span><span class="sxs-lookup"><span data-stu-id="6f744-130">Programming language support</span></span>

<span data-ttu-id="6f744-131">支持以下语言或者在一般情况下发布 (GA) 预览，或实验性。</span><span class="sxs-lookup"><span data-stu-id="6f744-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="6f744-132">语言</span><span class="sxs-lookup"><span data-stu-id="6f744-132">Language</span></span>      |<span data-ttu-id="6f744-133">1.x</span><span class="sxs-lookup"><span data-stu-id="6f744-133">1.x</span></span>         |<span data-ttu-id="6f744-134">2.x</span><span class="sxs-lookup"><span data-stu-id="6f744-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="6f744-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="6f744-135">**C#**</span></span>        |<span data-ttu-id="6f744-136">GA</span><span class="sxs-lookup"><span data-stu-id="6f744-136">GA</span></span>          |<span data-ttu-id="6f744-137">预览</span><span class="sxs-lookup"><span data-stu-id="6f744-137">Preview</span></span>  |
|<span data-ttu-id="6f744-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="6f744-138">**JavaScript**</span></span>|<span data-ttu-id="6f744-139">GA</span><span class="sxs-lookup"><span data-stu-id="6f744-139">GA</span></span>          |<span data-ttu-id="6f744-140">预览</span><span class="sxs-lookup"><span data-stu-id="6f744-140">Preview</span></span>  |
|<span data-ttu-id="6f744-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="6f744-141">**F#**</span></span>        |<span data-ttu-id="6f744-142">GA</span><span class="sxs-lookup"><span data-stu-id="6f744-142">GA</span></span>          |         |
|<span data-ttu-id="6f744-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="6f744-143">**Java**</span></span>      |            |<span data-ttu-id="6f744-144">预览</span><span class="sxs-lookup"><span data-stu-id="6f744-144">Preview</span></span>  |
|<span data-ttu-id="6f744-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="6f744-145">**Python**</span></span>    |<span data-ttu-id="6f744-146">实验</span><span class="sxs-lookup"><span data-stu-id="6f744-146">Experimental</span></span>|         |
|<span data-ttu-id="6f744-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="6f744-147">**PHP**</span></span>       |<span data-ttu-id="6f744-148">实验</span><span class="sxs-lookup"><span data-stu-id="6f744-148">Experimental</span></span>|         |
|<span data-ttu-id="6f744-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="6f744-149">**TypeScript**</span></span>|<span data-ttu-id="6f744-150">实验</span><span class="sxs-lookup"><span data-stu-id="6f744-150">Experimental</span></span>|         |
|<span data-ttu-id="6f744-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="6f744-151">**Batch**</span></span>     |<span data-ttu-id="6f744-152">实验</span><span class="sxs-lookup"><span data-stu-id="6f744-152">Experimental</span></span>|         |
|<span data-ttu-id="6f744-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="6f744-153">**Bash**</span></span>      |<span data-ttu-id="6f744-154">实验</span><span class="sxs-lookup"><span data-stu-id="6f744-154">Experimental</span></span>|         |
|<span data-ttu-id="6f744-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6f744-155">**PowerShell**</span></span>|<span data-ttu-id="6f744-156">实验</span><span class="sxs-lookup"><span data-stu-id="6f744-156">Experimental</span></span>|         |

<span data-ttu-id="6f744-157">有关详细信息，请参阅[支持的语言](https://docs.microsoft.com/azure/azure-functions/supported-languages)。</span><span class="sxs-lookup"><span data-stu-id="6f744-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="6f744-158">应用服务计划</span><span class="sxs-lookup"><span data-stu-id="6f744-158">App service plans</span></span>

<span data-ttu-id="6f744-159">受支持的函数*应用服务计划*。</span><span class="sxs-lookup"><span data-stu-id="6f744-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="6f744-160">该计划定义的函数应用使用的资源。</span><span class="sxs-lookup"><span data-stu-id="6f744-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="6f744-161">可以将计划分配到某个区域，确定的大小和数量的虚拟机将使用，并选择定价层。</span><span class="sxs-lookup"><span data-stu-id="6f744-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="6f744-162">为 true 的无服务器方案，可以使用函数应用**消耗**计划。</span><span class="sxs-lookup"><span data-stu-id="6f744-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="6f744-163">消耗计划后端根据负载自动缩放。</span><span class="sxs-lookup"><span data-stu-id="6f744-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="6f744-164">有关详细信息，请参阅[应用服务计划](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)。</span><span class="sxs-lookup"><span data-stu-id="6f744-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="6f744-165">创建第一个函数</span><span class="sxs-lookup"><span data-stu-id="6f744-165">Create your first function</span></span>

<span data-ttu-id="6f744-166">有三种常见方法，您可以创建函数应用。</span><span class="sxs-lookup"><span data-stu-id="6f744-166">There are three common ways you can create function apps.</span></span>

* <span data-ttu-id="6f744-167">在门户中的脚本函数。</span><span class="sxs-lookup"><span data-stu-id="6f744-167">Script functions in the portal.</span></span>
* <span data-ttu-id="6f744-168">创建使用 Azure 命令行接口 (CLI) 所需的资源。</span><span class="sxs-lookup"><span data-stu-id="6f744-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
* <span data-ttu-id="6f744-169">生成函数，使用你喜爱的 IDE 在本地，并将其发布到 Azure。</span><span class="sxs-lookup"><span data-stu-id="6f744-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="6f744-170">在门户中创建的脚本化的函数的详细信息，请参阅[Azure 门户中创建第一个函数](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)。</span><span class="sxs-lookup"><span data-stu-id="6f744-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="6f744-171">若要从 Azure CLI 生成，请参阅[创建第一个函数使用 Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)。</span><span class="sxs-lookup"><span data-stu-id="6f744-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="6f744-172">若要从 Visual Studio 创建一个函数，请参阅[创建第一个函数使用 Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="6f744-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="6f744-173">了解触发器和绑定</span><span class="sxs-lookup"><span data-stu-id="6f744-173">Understand triggers and bindings</span></span>

<span data-ttu-id="6f744-174">通过调用函数*触发器*和恰好有一个。</span><span class="sxs-lookup"><span data-stu-id="6f744-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="6f744-175">除了调用函数，某些触发器还充当绑定。</span><span class="sxs-lookup"><span data-stu-id="6f744-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="6f744-176">你还可以定义除了触发器的多个绑定。</span><span class="sxs-lookup"><span data-stu-id="6f744-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="6f744-177">*绑定*提供的声明性方式将数据连接到你的代码。</span><span class="sxs-lookup"><span data-stu-id="6f744-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="6f744-178">它们可以传入 （输入），或接收数据 （输出）。</span><span class="sxs-lookup"><span data-stu-id="6f744-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="6f744-179">触发器和绑定使函数更易使用。</span><span class="sxs-lookup"><span data-stu-id="6f744-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="6f744-180">绑定中删除手动创建数据库或文件系统连接的系统开销。</span><span class="sxs-lookup"><span data-stu-id="6f744-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="6f744-181">所有绑定所需的信息都包含在一个特殊*functions.json*脚本文件，或者使用代码中的属性声明。</span><span class="sxs-lookup"><span data-stu-id="6f744-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="6f744-182">一些常见的触发器包括：</span><span class="sxs-lookup"><span data-stu-id="6f744-182">Some common triggers include:</span></span>

* <span data-ttu-id="6f744-183">Blob 存储： 文件或文件夹上传或在存储中发生更改时调用您的函数。</span><span class="sxs-lookup"><span data-stu-id="6f744-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
* <span data-ttu-id="6f744-184">HTTP： 调用 REST API 等函数。</span><span class="sxs-lookup"><span data-stu-id="6f744-184">HTTP: invoke your function like a REST API.</span></span>
* <span data-ttu-id="6f744-185">队列： 调用函数时队列中存在的项。</span><span class="sxs-lookup"><span data-stu-id="6f744-185">Queue: invoke your function when items exist in a queue.</span></span>
* <span data-ttu-id="6f744-186">计时器： 调用上一般的步调函数。</span><span class="sxs-lookup"><span data-stu-id="6f744-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="6f744-187">绑定的示例包括：</span><span class="sxs-lookup"><span data-stu-id="6f744-187">Examples of bindings include:</span></span>

* <span data-ttu-id="6f744-188">Cosmos Db： 轻松连接到要加载或保存文件的数据库。</span><span class="sxs-lookup"><span data-stu-id="6f744-188">CosmosDB: easily connect to the database to load or save files.</span></span>
* <span data-ttu-id="6f744-189">表存储： 适用于从 function app 的键/值存储。</span><span class="sxs-lookup"><span data-stu-id="6f744-189">Table Storage: work with key/value storage from your function app.</span></span>
* <span data-ttu-id="6f744-190">队列存储： 轻松地从队列中检索项，或将新项放入队列。</span><span class="sxs-lookup"><span data-stu-id="6f744-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="6f744-191">下面的示例*functions.json*文件定义一个触发器和绑定：</span><span class="sxs-lookup"><span data-stu-id="6f744-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

<span data-ttu-id="6f744-192">在此示例中，该函数对 blob 存储中的更改触发`images`容器。</span><span class="sxs-lookup"><span data-stu-id="6f744-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="6f744-193">文件的信息传入，因此触发器还可作为一个绑定。</span><span class="sxs-lookup"><span data-stu-id="6f744-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="6f744-194">存在另一个绑定以将信息到名为的队列上放`images`。</span><span class="sxs-lookup"><span data-stu-id="6f744-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="6f744-195">以下是 C# 脚本函数：</span><span class="sxs-lookup"><span data-stu-id="6f744-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="6f744-196">该示例是采用文件的名称的简单函数已修改或上传到 blob 存储，并将其放置于队列上供以后处理。</span><span class="sxs-lookup"><span data-stu-id="6f744-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="6f744-197">有关触发器和绑定的完整列表，请参阅[Azure Functions 触发器和绑定概念](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)。</span><span class="sxs-lookup"><span data-stu-id="6f744-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="6f744-198">代理</span><span class="sxs-lookup"><span data-stu-id="6f744-198">Proxies</span></span>

<span data-ttu-id="6f744-199">代理为你的应用程序提供重定向功能。</span><span class="sxs-lookup"><span data-stu-id="6f744-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="6f744-200">代理公开一个终结点，并将该终结点映射到另一个资源。</span><span class="sxs-lookup"><span data-stu-id="6f744-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="6f744-201">使用代理，你可以：</span><span class="sxs-lookup"><span data-stu-id="6f744-201">With proxies, you can:</span></span>

* <span data-ttu-id="6f744-202">重新路由到其他终结点的传入请求。</span><span class="sxs-lookup"><span data-stu-id="6f744-202">Reroute an incoming request to another endpoint.</span></span>
* <span data-ttu-id="6f744-203">传递此过程之前，请修改传入的请求。</span><span class="sxs-lookup"><span data-stu-id="6f744-203">Modify the incoming request before it's passed along.</span></span>
* <span data-ttu-id="6f744-204">修改或提供了一个响应。</span><span class="sxs-lookup"><span data-stu-id="6f744-204">Modify or provide a response.</span></span>

<span data-ttu-id="6f744-205">使用代理的方案例如：</span><span class="sxs-lookup"><span data-stu-id="6f744-205">Proxies are used for scenarios such as:</span></span>

* <span data-ttu-id="6f744-206">简化、 缩短，或更改 URL。</span><span class="sxs-lookup"><span data-stu-id="6f744-206">Simplifying, shortening, or changing the URL.</span></span>
* <span data-ttu-id="6f744-207">提供多个后端服务的一致 API 前缀。</span><span class="sxs-lookup"><span data-stu-id="6f744-207">Providing a consistent API prefix to multiple back-end services.</span></span>
* <span data-ttu-id="6f744-208">模拟正在开发的终结点的响应。</span><span class="sxs-lookup"><span data-stu-id="6f744-208">Mocking a response to an endpoint being developed.</span></span>
* <span data-ttu-id="6f744-209">提供的已知终结点的静态响应。</span><span class="sxs-lookup"><span data-stu-id="6f744-209">Providing a static response to a well-known endpoint.</span></span>
* <span data-ttu-id="6f744-210">保持 API 终结点时移动或迁移后端一致。</span><span class="sxs-lookup"><span data-stu-id="6f744-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="6f744-211">代理存储为 JSON 定义。</span><span class="sxs-lookup"><span data-stu-id="6f744-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="6f744-212">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="6f744-212">Here is an example:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

<span data-ttu-id="6f744-213">`Domain Redirect`代理需要缩短的路由并将其映射到更长的函数资源。</span><span class="sxs-lookup"><span data-stu-id="6f744-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="6f744-214">转换如下所示：</span><span class="sxs-lookup"><span data-stu-id="6f744-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="6f744-215">`Root`代理会发送到的根 URL 的任何内容 (`https://--shorturl--/`) 并将它重定向到文档站点。</span><span class="sxs-lookup"><span data-stu-id="6f744-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="6f744-216">使用代理的示例所示视频[Azure:将应用迁移到使用无服务器 Azure Functions 在云中](https://channel9.msdn.com/events/Connect/2017/E102)。</span><span class="sxs-lookup"><span data-stu-id="6f744-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="6f744-217">在真实时间中在本地 SQL Server 上运行的 ASP.NET Core 应用程序迁移到 Azure 云。</span><span class="sxs-lookup"><span data-stu-id="6f744-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="6f744-218">使用代理服务器来帮助重构传统的 Web API 项目以使用函数。</span><span class="sxs-lookup"><span data-stu-id="6f744-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="6f744-219">有关代理的详细信息，请参阅[使用 Azure Functions 代理](https://docs.microsoft.com/azure/azure-functions/functions-proxies)。</span><span class="sxs-lookup"><span data-stu-id="6f744-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6f744-220">[上一页](azure-serverless-platform.md)
>[下一页](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="6f744-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>