---
title: Azure Functions-无服务器应用
description: Azure 函数提供跨多种语言 (C#、JavaScript、Java) 和平台的无服务器功能, 以提供事件驱动的即时缩放代码。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4febcc01eebf3efce3fc1eb42e19c2ec6c0baa52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577600"
---
# <a name="azure-functions"></a><span data-ttu-id="5d231-103">Azure Functions</span><span class="sxs-lookup"><span data-stu-id="5d231-103">Azure Functions</span></span>

<span data-ttu-id="5d231-104">Azure 函数提供无服务器的计算体验。</span><span class="sxs-lookup"><span data-stu-id="5d231-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="5d231-105">函数由*触发器*调用 (如访问 HTTP 终结点或计时器), 并执行代码块或业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="5d231-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="5d231-106">函数还支持连接到存储和队列等资源的专用*绑定*。</span><span class="sxs-lookup"><span data-stu-id="5d231-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure 函数徽标](./media/azure-functions-logo.png)

<span data-ttu-id="5d231-108">Azure Functions 框架有两个版本。</span><span class="sxs-lookup"><span data-stu-id="5d231-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="5d231-109">旧版本支持完整 .NET Framework, 而新的运行时支持跨平台的 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5d231-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="5d231-110">支持除 JavaScript C# 、 F#和 Java 之外的其他语言。</span><span class="sxs-lookup"><span data-stu-id="5d231-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="5d231-111">在门户中创建的函数提供丰富的脚本编写语法。</span><span class="sxs-lookup"><span data-stu-id="5d231-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="5d231-112">可以通过完全的平台支持和功能来部署作为独立项目创建的函数。</span><span class="sxs-lookup"><span data-stu-id="5d231-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="5d231-113">有关详细信息, 请参阅[Azure Functions 文档](https://docs.microsoft.com/azure/azure-functions)。</span><span class="sxs-lookup"><span data-stu-id="5d231-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="5d231-114">函数 v1 与 v2</span><span class="sxs-lookup"><span data-stu-id="5d231-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="5d231-115">Azure Functions 运行时有两个版本:1.x 和2.x。</span><span class="sxs-lookup"><span data-stu-id="5d231-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="5d231-116">版本1.x 正式发布 (GA)。</span><span class="sxs-lookup"><span data-stu-id="5d231-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="5d231-117">它通过门户或 Windows 计算机支持 .NET 开发, 并使用 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="5d231-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="5d231-118">1.x 支持C#、JavaScript 和, 并F#提供对 Python、PHP、TypeScript、Batch、Bash 和 PowerShell 的实验性支持。</span><span class="sxs-lookup"><span data-stu-id="5d231-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="5d231-119">[版本2.x 现已正式发布](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/)。</span><span class="sxs-lookup"><span data-stu-id="5d231-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="5d231-120">它利用 .NET Core, 并支持在 Windows、macOS 和 Linux 计算机上进行跨平台开发。</span><span class="sxs-lookup"><span data-stu-id="5d231-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="5d231-121">2.x 为 Java 添加一流的支持, 但并不直接支持任何实验性语言。</span><span class="sxs-lookup"><span data-stu-id="5d231-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="5d231-122">版本2.x 使用新的绑定扩展性模型, 该模型启用平台的第三方扩展、独立的绑定版本控制和更精简的执行环境。</span><span class="sxs-lookup"><span data-stu-id="5d231-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="5d231-123">**在1.x 中存在一个已知问题, 其中包含[绑定重定向支持](https://github.com/Azure/azure-functions-host/issues/992)。**</span><span class="sxs-lookup"><span data-stu-id="5d231-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="5d231-124">此问题特定于 .NET 开发。</span><span class="sxs-lookup"><span data-stu-id="5d231-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="5d231-125">对于依赖于运行时中包含的库不同版本的库, 具有依赖项的项目会受到影响。</span><span class="sxs-lookup"><span data-stu-id="5d231-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="5d231-126">函数团队已致力于对问题进行具体的进度。</span><span class="sxs-lookup"><span data-stu-id="5d231-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="5d231-127">团队将在2.x 中处理绑定重定向, 然后再将其公开上市。</span><span class="sxs-lookup"><span data-stu-id="5d231-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="5d231-128">可在此处获取带有建议的修补程序和解决方法的官方团队声明:[Azure Functions 中的程序集解析](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions)。</span><span class="sxs-lookup"><span data-stu-id="5d231-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="5d231-129">有关详细信息, 请参阅[比较1.x 和](https://docs.microsoft.com/azure/azure-functions/functions-versions)2.x。</span><span class="sxs-lookup"><span data-stu-id="5d231-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="5d231-130">编程语言支持</span><span class="sxs-lookup"><span data-stu-id="5d231-130">Programming language support</span></span>

<span data-ttu-id="5d231-131">公开上市 (GA)、预览或实验支持以下语言。</span><span class="sxs-lookup"><span data-stu-id="5d231-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="5d231-132">语言</span><span class="sxs-lookup"><span data-stu-id="5d231-132">Language</span></span>      |<span data-ttu-id="5d231-133">1.x</span><span class="sxs-lookup"><span data-stu-id="5d231-133">1.x</span></span>         |<span data-ttu-id="5d231-134">2.x</span><span class="sxs-lookup"><span data-stu-id="5d231-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="5d231-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="5d231-135">**C#**</span></span>        |<span data-ttu-id="5d231-136">GA</span><span class="sxs-lookup"><span data-stu-id="5d231-136">GA</span></span>          |<span data-ttu-id="5d231-137">预览</span><span class="sxs-lookup"><span data-stu-id="5d231-137">Preview</span></span>  |
|<span data-ttu-id="5d231-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="5d231-138">**JavaScript**</span></span>|<span data-ttu-id="5d231-139">GA</span><span class="sxs-lookup"><span data-stu-id="5d231-139">GA</span></span>          |<span data-ttu-id="5d231-140">预览</span><span class="sxs-lookup"><span data-stu-id="5d231-140">Preview</span></span>  |
|<span data-ttu-id="5d231-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="5d231-141">**F#**</span></span>        |<span data-ttu-id="5d231-142">GA</span><span class="sxs-lookup"><span data-stu-id="5d231-142">GA</span></span>          |         |
|<span data-ttu-id="5d231-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="5d231-143">**Java**</span></span>      |            |<span data-ttu-id="5d231-144">预览</span><span class="sxs-lookup"><span data-stu-id="5d231-144">Preview</span></span>  |
|<span data-ttu-id="5d231-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="5d231-145">**Python**</span></span>    |<span data-ttu-id="5d231-146">实验</span><span class="sxs-lookup"><span data-stu-id="5d231-146">Experimental</span></span>|         |
|<span data-ttu-id="5d231-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="5d231-147">**PHP**</span></span>       |<span data-ttu-id="5d231-148">实验</span><span class="sxs-lookup"><span data-stu-id="5d231-148">Experimental</span></span>|         |
|<span data-ttu-id="5d231-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="5d231-149">**TypeScript**</span></span>|<span data-ttu-id="5d231-150">实验</span><span class="sxs-lookup"><span data-stu-id="5d231-150">Experimental</span></span>|         |
|<span data-ttu-id="5d231-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="5d231-151">**Batch**</span></span>     |<span data-ttu-id="5d231-152">实验</span><span class="sxs-lookup"><span data-stu-id="5d231-152">Experimental</span></span>|         |
|<span data-ttu-id="5d231-153">**狂欢**</span><span class="sxs-lookup"><span data-stu-id="5d231-153">**Bash**</span></span>      |<span data-ttu-id="5d231-154">实验</span><span class="sxs-lookup"><span data-stu-id="5d231-154">Experimental</span></span>|         |
|<span data-ttu-id="5d231-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5d231-155">**PowerShell**</span></span>|<span data-ttu-id="5d231-156">实验</span><span class="sxs-lookup"><span data-stu-id="5d231-156">Experimental</span></span>|         |

<span data-ttu-id="5d231-157">有关详细信息, 请参阅[支持的语言](https://docs.microsoft.com/azure/azure-functions/supported-languages)。</span><span class="sxs-lookup"><span data-stu-id="5d231-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="5d231-158">应用服务计划</span><span class="sxs-lookup"><span data-stu-id="5d231-158">App service plans</span></span>

<span data-ttu-id="5d231-159">函数由*应用服务计划*支持。</span><span class="sxs-lookup"><span data-stu-id="5d231-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="5d231-160">计划定义函数应用使用的资源。</span><span class="sxs-lookup"><span data-stu-id="5d231-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="5d231-161">你可以将计划分配给某个区域, 确定将使用的虚拟机的大小和数量, 并选择定价层。</span><span class="sxs-lookup"><span data-stu-id="5d231-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="5d231-162">对于真正无服务器方法, 函数应用可以使用**消耗**计划。</span><span class="sxs-lookup"><span data-stu-id="5d231-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="5d231-163">消耗计划将根据负载自动缩放后端。</span><span class="sxs-lookup"><span data-stu-id="5d231-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="5d231-164">有关详细信息, 请参阅[应用服务计划](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)。</span><span class="sxs-lookup"><span data-stu-id="5d231-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="5d231-165">创建第一个函数</span><span class="sxs-lookup"><span data-stu-id="5d231-165">Create your first function</span></span>

<span data-ttu-id="5d231-166">可以通过三种常用方法创建函数应用。</span><span class="sxs-lookup"><span data-stu-id="5d231-166">There are three common ways you can create function apps.</span></span>

* <span data-ttu-id="5d231-167">在门户中编写函数脚本。</span><span class="sxs-lookup"><span data-stu-id="5d231-167">Script functions in the portal.</span></span>
* <span data-ttu-id="5d231-168">使用 Azure 命令行接口 (CLI) 创建必要的资源。</span><span class="sxs-lookup"><span data-stu-id="5d231-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
* <span data-ttu-id="5d231-169">使用最喜欢的 IDE 在本地生成函数并将其发布到 Azure。</span><span class="sxs-lookup"><span data-stu-id="5d231-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="5d231-170">有关在门户中创建脚本函数的详细信息, 请参阅在[Azure 门户中创建第一个函数](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)。</span><span class="sxs-lookup"><span data-stu-id="5d231-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="5d231-171">若要从 Azure CLI 生成, 请参阅[使用 Azure CLI 创建第一个函数](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)。</span><span class="sxs-lookup"><span data-stu-id="5d231-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="5d231-172">若要从 Visual Studio 创建函数, 请参阅[使用 Visual Studio 创建第一个函数](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="5d231-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="5d231-173">了解触发器和绑定</span><span class="sxs-lookup"><span data-stu-id="5d231-173">Understand triggers and bindings</span></span>

<span data-ttu-id="5d231-174">函数由*触发器*调用, 只能有一个。</span><span class="sxs-lookup"><span data-stu-id="5d231-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="5d231-175">除了调用函数外, 某些触发器还用作绑定。</span><span class="sxs-lookup"><span data-stu-id="5d231-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="5d231-176">除了触发器外, 还可以定义多个绑定。</span><span class="sxs-lookup"><span data-stu-id="5d231-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="5d231-177">*绑定*提供了将数据连接到代码的声明性方式。</span><span class="sxs-lookup"><span data-stu-id="5d231-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="5d231-178">它们可以传入 (输入) 或接收数据 (输出)。</span><span class="sxs-lookup"><span data-stu-id="5d231-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="5d231-179">触发器和绑定使函数易于使用。</span><span class="sxs-lookup"><span data-stu-id="5d231-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="5d231-180">绑定消除了手动创建数据库或文件系统连接的系统开销。</span><span class="sxs-lookup"><span data-stu-id="5d231-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="5d231-181">绑定所需的所有信息都包含在脚本中的特殊*函数 json*文件中, 或在代码中用特性声明。</span><span class="sxs-lookup"><span data-stu-id="5d231-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="5d231-182">一些常见触发器包括:</span><span class="sxs-lookup"><span data-stu-id="5d231-182">Some common triggers include:</span></span>

* <span data-ttu-id="5d231-183">Blob 存储: 在存储中上载或更改文件或文件夹时调用函数。</span><span class="sxs-lookup"><span data-stu-id="5d231-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
* <span data-ttu-id="5d231-184">HTTP: 调用函数, 如 REST API。</span><span class="sxs-lookup"><span data-stu-id="5d231-184">HTTP: invoke your function like a REST API.</span></span>
* <span data-ttu-id="5d231-185">Queue: 在队列中存在项时调用函数。</span><span class="sxs-lookup"><span data-stu-id="5d231-185">Queue: invoke your function when items exist in a queue.</span></span>
* <span data-ttu-id="5d231-186">Timer: 对定期节奏调用函数。</span><span class="sxs-lookup"><span data-stu-id="5d231-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="5d231-187">绑定示例包括:</span><span class="sxs-lookup"><span data-stu-id="5d231-187">Examples of bindings include:</span></span>

* <span data-ttu-id="5d231-188">CosmosDB: 轻松连接到数据库以加载或保存文件。</span><span class="sxs-lookup"><span data-stu-id="5d231-188">CosmosDB: easily connect to the database to load or save files.</span></span>
* <span data-ttu-id="5d231-189">表存储: 使用函数应用中的键/值存储。</span><span class="sxs-lookup"><span data-stu-id="5d231-189">Table Storage: work with key/value storage from your function app.</span></span>
* <span data-ttu-id="5d231-190">队列存储: 轻松地从队列中检索项, 或在队列中放置新项。</span><span class="sxs-lookup"><span data-stu-id="5d231-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="5d231-191">下面的示例*函数 json*文件定义了触发器和绑定:</span><span class="sxs-lookup"><span data-stu-id="5d231-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="5d231-192">在此示例中, 该函数是通过对`images`容器中的 blob 存储的更改触发的。</span><span class="sxs-lookup"><span data-stu-id="5d231-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="5d231-193">传递文件的信息, 因此触发器也充当绑定。</span><span class="sxs-lookup"><span data-stu-id="5d231-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="5d231-194">另一个绑定用于将信息放到名为`images`的队列。</span><span class="sxs-lookup"><span data-stu-id="5d231-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="5d231-195">下面是该C#函数的脚本:</span><span class="sxs-lookup"><span data-stu-id="5d231-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="5d231-196">该示例是一个简单的函数, 该函数采用已修改或已上传到 blob 存储的文件的名称, 并将其放在队列中供以后处理。</span><span class="sxs-lookup"><span data-stu-id="5d231-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="5d231-197">有关触发器和绑定的完整列表, 请参阅[Azure Functions 触发器和绑定概念](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)。</span><span class="sxs-lookup"><span data-stu-id="5d231-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="5d231-198">代理</span><span class="sxs-lookup"><span data-stu-id="5d231-198">Proxies</span></span>

<span data-ttu-id="5d231-199">代理为应用程序提供重定向功能。</span><span class="sxs-lookup"><span data-stu-id="5d231-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="5d231-200">代理公开终结点, 并将该终结点映射到另一个资源。</span><span class="sxs-lookup"><span data-stu-id="5d231-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="5d231-201">对于代理, 你可以:</span><span class="sxs-lookup"><span data-stu-id="5d231-201">With proxies, you can:</span></span>

* <span data-ttu-id="5d231-202">将传入请求重新路由到另一个终结点。</span><span class="sxs-lookup"><span data-stu-id="5d231-202">Reroute an incoming request to another endpoint.</span></span>
* <span data-ttu-id="5d231-203">在传递请求之前修改传入请求。</span><span class="sxs-lookup"><span data-stu-id="5d231-203">Modify the incoming request before it's passed along.</span></span>
* <span data-ttu-id="5d231-204">修改或提供响应。</span><span class="sxs-lookup"><span data-stu-id="5d231-204">Modify or provide a response.</span></span>

<span data-ttu-id="5d231-205">代理用于以下方案:</span><span class="sxs-lookup"><span data-stu-id="5d231-205">Proxies are used for scenarios such as:</span></span>

* <span data-ttu-id="5d231-206">简化、缩短或更改 URL。</span><span class="sxs-lookup"><span data-stu-id="5d231-206">Simplifying, shortening, or changing the URL.</span></span>
* <span data-ttu-id="5d231-207">为多个后端服务提供一致的 API 前缀。</span><span class="sxs-lookup"><span data-stu-id="5d231-207">Providing a consistent API prefix to multiple back-end services.</span></span>
* <span data-ttu-id="5d231-208">模拟响应正在开发的终结点。</span><span class="sxs-lookup"><span data-stu-id="5d231-208">Mocking a response to an endpoint being developed.</span></span>
* <span data-ttu-id="5d231-209">提供对已知终结点的静态响应。</span><span class="sxs-lookup"><span data-stu-id="5d231-209">Providing a static response to a well-known endpoint.</span></span>
* <span data-ttu-id="5d231-210">在移动或迁移后端时保持 API 终结点的一致性。</span><span class="sxs-lookup"><span data-stu-id="5d231-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="5d231-211">代理存储为 JSON 定义。</span><span class="sxs-lookup"><span data-stu-id="5d231-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="5d231-212">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="5d231-212">Here is an example:</span></span>

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

<span data-ttu-id="5d231-213">`Domain Redirect`代理采用一个缩短的路由, 并将其映射到较长的函数资源。</span><span class="sxs-lookup"><span data-stu-id="5d231-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="5d231-214">转换如下所示:</span><span class="sxs-lookup"><span data-stu-id="5d231-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="5d231-215">代理使用发送到根 URL (`https://--shorturl--/`) 的任何内容, 并将其重定向到文档站点。 `Root`</span><span class="sxs-lookup"><span data-stu-id="5d231-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="5d231-216">视频[Azure 中显示了使用代理的示例:利用无服务器 Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102)将你的应用引入云。</span><span class="sxs-lookup"><span data-stu-id="5d231-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="5d231-217">在本地 SQL Server 上运行的 ASP.NET Core 应用程序将被迁移到 Azure 云。</span><span class="sxs-lookup"><span data-stu-id="5d231-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="5d231-218">代理用于帮助重构传统 Web API 项目, 以使用函数。</span><span class="sxs-lookup"><span data-stu-id="5d231-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="5d231-219">有关代理的详细信息, 请参阅[使用 Azure Functions 代理](https://docs.microsoft.com/azure/azure-functions/functions-proxies)。</span><span class="sxs-lookup"><span data-stu-id="5d231-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5d231-220">[上一页](azure-serverless-platform.md)
>[下一页](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="5d231-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
