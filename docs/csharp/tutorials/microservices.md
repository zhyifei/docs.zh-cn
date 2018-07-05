---
title: Docker 中托管的微服务 - C#
description: 了解如何创建在 Docker 容器中运行的 ASP.NET Core 服务
ms.date: 06/08/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: 1f4b38243beb1210b1374bd701fac66b2fa72cc5
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106345"
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="95ac4-103">Docker 中托管的微服务</span><span class="sxs-lookup"><span data-stu-id="95ac4-103">Microservices hosted in Docker</span></span>

<span data-ttu-id="95ac4-104">此教程将详细介绍在 Docker 容器中生成和部署 ASP.NET Core 微服务时必须完成的任务。</span><span class="sxs-lookup"><span data-stu-id="95ac4-104">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="95ac4-105">在此教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="95ac4-105">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="95ac4-106">如何生成 ASP.NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-106">How to generate an ASP.NET Core application.</span></span>
* <span data-ttu-id="95ac4-107">如何创建 Docker 开发环境。</span><span class="sxs-lookup"><span data-stu-id="95ac4-107">How to create a development Docker environment.</span></span>
* <span data-ttu-id="95ac4-108">如何根据现有映像生成 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="95ac4-108">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="95ac4-109">如何将服务部署到 Docker 容器中。</span><span class="sxs-lookup"><span data-stu-id="95ac4-109">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="95ac4-110">与此同时，你还将了解下面这些 C# 语言功能：</span><span class="sxs-lookup"><span data-stu-id="95ac4-110">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="95ac4-111">如何将 C# 对象转换成 JSON 有效负载。</span><span class="sxs-lookup"><span data-stu-id="95ac4-111">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="95ac4-112">如何生成不可变的数据传输对象。</span><span class="sxs-lookup"><span data-stu-id="95ac4-112">How to build immutable Data Transfer Objects.</span></span>
* <span data-ttu-id="95ac4-113">如何处理传入的 HTTP 请求并生成 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="95ac4-113">How to process incoming HTTP Requests and generate the HTTP Response.</span></span>
* <span data-ttu-id="95ac4-114">如何使用可以为 null 的值类型。</span><span class="sxs-lookup"><span data-stu-id="95ac4-114">How to work with nullable value types.</span></span>

<span data-ttu-id="95ac4-115">你可以[查看或下载本主题的示例应用](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice)。</span><span class="sxs-lookup"><span data-stu-id="95ac4-115">You can [view or download the sample app](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="95ac4-116">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="95ac4-116">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="why-docker"></a><span data-ttu-id="95ac4-117">为什么要使用 Docker？</span><span class="sxs-lookup"><span data-stu-id="95ac4-117">Why Docker?</span></span>

<span data-ttu-id="95ac4-118">使用 Docker，可以轻松地创建标准计算机映像，从而在数据中心或公有云中托管服务。</span><span class="sxs-lookup"><span data-stu-id="95ac4-118">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="95ac4-119">使用 Docker，可以配置映像，并根据需要复制映像来扩展应用程序安装。</span><span class="sxs-lookup"><span data-stu-id="95ac4-119">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="95ac4-120">此教程中的所有代码适用于任何 .NET Core 环境。</span><span class="sxs-lookup"><span data-stu-id="95ac4-120">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="95ac4-121">附加 Docker 安装任务适用于 ASP.NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-121">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="95ac4-122">系统必备</span><span class="sxs-lookup"><span data-stu-id="95ac4-122">Prerequisites</span></span>

<span data-ttu-id="95ac4-123">必须将计算机设置为运行 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="95ac4-123">You’ll need to setup your machine to run .NET Core.</span></span> <span data-ttu-id="95ac4-124">有关安装说明，请访问 [.NET Core](https://www.microsoft.com/net/core) 页。</span><span class="sxs-lookup"><span data-stu-id="95ac4-124">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="95ac4-125">可以在 Windows、Linux、macOS 或 Docker 容器中运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-125">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="95ac4-126">必须安装常用的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="95ac4-126">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="95ac4-127">在以下说明中，我们使用的是开放源代码跨平台编辑器 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="95ac4-127">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="95ac4-128">不过，你可以使用习惯使用的任意工具。</span><span class="sxs-lookup"><span data-stu-id="95ac4-128">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="95ac4-129">还必须安装 Docker 引擎。</span><span class="sxs-lookup"><span data-stu-id="95ac4-129">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="95ac4-130">请参阅 [Docker 安装页](http://www.docker.com/products/docker)，了解适用于自己的平台的说明。</span><span class="sxs-lookup"><span data-stu-id="95ac4-130">See the [Docker Installation page](http://www.docker.com/products/docker) for instructions for your platform.</span></span>
<span data-ttu-id="95ac4-131">可以在许多 Linux 发行版本、macOS 或 Windows 中安装 Docker。</span><span class="sxs-lookup"><span data-stu-id="95ac4-131">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="95ac4-132">上面引用的页面分部分提供了各个可安装的版本。</span><span class="sxs-lookup"><span data-stu-id="95ac4-132">The page referenced above contains sections to each of the available installations.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="95ac4-133">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="95ac4-133">Create the Application</span></span>

<span data-ttu-id="95ac4-134">现已安装所有工具，请在喜欢的 shell 中执行以下名称，在名为“WeatherMicroservice”的目录中新建 ASP.NET Core 应用程序：</span><span class="sxs-lookup"><span data-stu-id="95ac4-134">Now that you've installed all the tools, create a new ASP.NET Core application in a directory called "WeatherMicroservice" by executing the following command in your favorite shell:</span></span>

```console
dotnet new web -o WeatherMicroservice
```

<span data-ttu-id="95ac4-135">`dotnet` 命令可运行 .NET 开发所需的工具。</span><span class="sxs-lookup"><span data-stu-id="95ac4-135">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="95ac4-136">每个谓词执行一个不同的命令。</span><span class="sxs-lookup"><span data-stu-id="95ac4-136">Each verb executes a different command.</span></span>

<span data-ttu-id="95ac4-137">`dotnet new` 命令用于创建 .Net Core 项目。</span><span class="sxs-lookup"><span data-stu-id="95ac4-137">The `dotnet new` command is used to create .Net Core projects.</span></span>

<span data-ttu-id="95ac4-138">`dotnet new` 命令后的 `-o WeatherMicroservice` 选项用于提供位置来创建 ASP.NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-138">The `-o WeatherMicroservice` option after the `dotnet new` command is used to give the location to create the ASP.NET Core application.</span></span>

<span data-ttu-id="95ac4-139">对于此微服务，我们需要尽可能简单、轻型的 Web 应用程序，因此我们使用了“ASP.NET Core 空”模板，并指定其短名称为 `web`。</span><span class="sxs-lookup"><span data-stu-id="95ac4-139">For this microservice, we want the simplest, most lightweight web application possible, so we used the "ASP.NET Core Empty" template, by specifying its short name, `web`.</span></span>

<span data-ttu-id="95ac4-140">此模板将为你创建以下四个文件：</span><span class="sxs-lookup"><span data-stu-id="95ac4-140">The template creates four files for you:</span></span>

* <span data-ttu-id="95ac4-141">Startup.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="95ac4-141">A Startup.cs file.</span></span> <span data-ttu-id="95ac4-142">其中包含应用程序的基本内容。</span><span class="sxs-lookup"><span data-stu-id="95ac4-142">This contains the basis of the application.</span></span>
* <span data-ttu-id="95ac4-143">Program.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="95ac4-143">A Program.cs file.</span></span> <span data-ttu-id="95ac4-144">其中包含应用程序的入口点。</span><span class="sxs-lookup"><span data-stu-id="95ac4-144">This contains the entry point of the application.</span></span>
* <span data-ttu-id="95ac4-145">WeatherMicroservice.csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="95ac4-145">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="95ac4-146">这是应用程序的生成文件。</span><span class="sxs-lookup"><span data-stu-id="95ac4-146">This is the build file for the application.</span></span>
* <span data-ttu-id="95ac4-147">Properties/launchSettings.json 文件。</span><span class="sxs-lookup"><span data-stu-id="95ac4-147">A Properties/launchSettings.json file.</span></span> <span data-ttu-id="95ac4-148">其中包含 IDE 使用的调试设置。</span><span class="sxs-lookup"><span data-stu-id="95ac4-148">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="95ac4-149">现在可以运行模板生成的应用程序了：</span><span class="sxs-lookup"><span data-stu-id="95ac4-149">Now you can run the template generated application:</span></span>

```console
dotnet run
```

<span data-ttu-id="95ac4-150">此命令将首先还原生成应用程序所需的依赖项，然后生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-150">This command will first restore dependencies required to build the application and then it will build the application.</span></span>

<span data-ttu-id="95ac4-151">默认配置侦听的是 `http://localhost:5000`。</span><span class="sxs-lookup"><span data-stu-id="95ac4-151">The default configuration listens to `http://localhost:5000`.</span></span> <span data-ttu-id="95ac4-152">可以打开浏览器并转到相应页面，看到的是“Hello World!”</span><span class="sxs-lookup"><span data-stu-id="95ac4-152">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="95ac4-153">消息。</span><span class="sxs-lookup"><span data-stu-id="95ac4-153">message.</span></span>

<span data-ttu-id="95ac4-154">完成后，可以按 <kbd>Ctrl</kbd>+<kbd>C</kbd> 关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-154">When you're done, you can shut down the application by pressing <kbd>Ctrl</kbd>+<kbd>C</kbd>.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="95ac4-155">ASP.NET Core 应用程序剖析</span><span class="sxs-lookup"><span data-stu-id="95ac4-155">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="95ac4-156">至此，已生成应用程序，让我们来看看此应用程序功能是如何实现的。</span><span class="sxs-lookup"><span data-stu-id="95ac4-156">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="95ac4-157">此时，生成的文件中有两个需要特别关注：WeatherMicroservice.csproj 和 Startup.cs。</span><span class="sxs-lookup"><span data-stu-id="95ac4-157">There are two of the generated files that are particularly interesting at this point: WeatherMicroservice.csproj and Startup.cs.</span></span> 

<span data-ttu-id="95ac4-158">.csproj 文件包含项目相关信息。</span><span class="sxs-lookup"><span data-stu-id="95ac4-158">The .csproj file contains information about the project.</span></span>
<span data-ttu-id="95ac4-159">最有趣的两个节点是 `<TargetFramework>` 和 `<PackageReference>`。</span><span class="sxs-lookup"><span data-stu-id="95ac4-159">The two nodes that are most interesting are `<TargetFramework>` and `<PackageReference>`.</span></span>

<span data-ttu-id="95ac4-160">`<TargetFramework>` 节点指定将运行此应用程序的 .NET 版本。</span><span class="sxs-lookup"><span data-stu-id="95ac4-160">The `<TargetFramework>` node specifies the version of .NET that will run this application.</span></span>

<span data-ttu-id="95ac4-161">使用每个 `<PackageReference>` 节点指定此应用程序所需的包。</span><span class="sxs-lookup"><span data-stu-id="95ac4-161">Each `<PackageReference>` node is used to specify a package that is needed for this application.</span></span>

<span data-ttu-id="95ac4-162">此应用程序是在 Startup.cs 中实现。</span><span class="sxs-lookup"><span data-stu-id="95ac4-162">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="95ac4-163">此文件包含启动类。</span><span class="sxs-lookup"><span data-stu-id="95ac4-163">This file contains the startup class.</span></span>

<span data-ttu-id="95ac4-164">ASP.NET Core 基础结构调用两种方法来配置并运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-164">The two methods are called by the ASP.NET Core infrastructure to configure and run the application.</span></span> <span data-ttu-id="95ac4-165">`ConfigureServices` 方法描述了此应用程序所需的服务。</span><span class="sxs-lookup"><span data-stu-id="95ac4-165">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="95ac4-166">由于要生成的是精简的微服务，因此无需配置任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="95ac4-166">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="95ac4-167">`Configure` 方法配置传入 HTTP 请求的处理程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-167">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="95ac4-168">模板生成简单的处理程序来响应所有关于文本“Hello World!”的请求。</span><span class="sxs-lookup"><span data-stu-id="95ac4-168">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="95ac4-169">生成微服务</span><span class="sxs-lookup"><span data-stu-id="95ac4-169">Build a microservice</span></span>

<span data-ttu-id="95ac4-170">要生成的服务将用于传递世界各地的天气预报。</span><span class="sxs-lookup"><span data-stu-id="95ac4-170">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="95ac4-171">在生产应用程序中，需要调用一些服务来检索天气数据。</span><span class="sxs-lookup"><span data-stu-id="95ac4-171">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="95ac4-172">在此示例中，我们将生成随机天气预报服务。</span><span class="sxs-lookup"><span data-stu-id="95ac4-172">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="95ac4-173">需要执行以下许多任务，才能实现随机天气预报服务：</span><span class="sxs-lookup"><span data-stu-id="95ac4-173">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="95ac4-174">分析传入请求，读取经纬度。</span><span class="sxs-lookup"><span data-stu-id="95ac4-174">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="95ac4-175">生成一些随机预报数据。</span><span class="sxs-lookup"><span data-stu-id="95ac4-175">Generate some random forecast data.</span></span>
* <span data-ttu-id="95ac4-176">将随机预报数据从 C# 对象转换成 JSON 数据包。</span><span class="sxs-lookup"><span data-stu-id="95ac4-176">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="95ac4-177">将响应头设置为指示服务发送回 JSON。</span><span class="sxs-lookup"><span data-stu-id="95ac4-177">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="95ac4-178">编写响应。</span><span class="sxs-lookup"><span data-stu-id="95ac4-178">Write the response.</span></span>

<span data-ttu-id="95ac4-179">下面各部分将引导你逐一完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="95ac4-179">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="95ac4-180">分析查询字符串</span><span class="sxs-lookup"><span data-stu-id="95ac4-180">Parsing the Query String</span></span>

<span data-ttu-id="95ac4-181">首先要分析查询字符串。</span><span class="sxs-lookup"><span data-stu-id="95ac4-181">You'll begin by parsing the query string.</span></span> <span data-ttu-id="95ac4-182">此服务接受在以下形式的查询字符串中使用“lat”和“long”自变量：</span><span class="sxs-lookup"><span data-stu-id="95ac4-182">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

```
http://localhost:5000/?lat=-35.55&long=-12.35
```

<span data-ttu-id="95ac4-183">只需更改定义为启动类中 `app.Run` 的自变量的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="95ac4-183">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="95ac4-184">lambda 表达式中的自变量是请求的 `HttpContext`。</span><span class="sxs-lookup"><span data-stu-id="95ac4-184">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="95ac4-185">其属性之一是 `Request` 对象。</span><span class="sxs-lookup"><span data-stu-id="95ac4-185">One of its properties is the `Request` object.</span></span> <span data-ttu-id="95ac4-186">`Request` 对象具有 `Query` 属性，其中包含请求查询字符串中所有值的字典。</span><span class="sxs-lookup"><span data-stu-id="95ac4-186">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="95ac4-187">第一次添加的代码是为了查找经纬度值：</span><span class="sxs-lookup"><span data-stu-id="95ac4-187">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="95ac4-188">`Query` 字典值属于 `StringValue` 类型。</span><span class="sxs-lookup"><span data-stu-id="95ac4-188">The `Query` dictionary values are `StringValue` type.</span></span> <span data-ttu-id="95ac4-189">此类型可以包含一系列字符串。</span><span class="sxs-lookup"><span data-stu-id="95ac4-189">That type can contain a collection of strings.</span></span> <span data-ttu-id="95ac4-190">对于天气服务，每个值都是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="95ac4-190">For your weather service, each value is a single string.</span></span> <span data-ttu-id="95ac4-191">正因如此，上面的代码调用 `FirstOrDefault()`。</span><span class="sxs-lookup"><span data-stu-id="95ac4-191">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="95ac4-192">接下来，需要将字符串转换成双精度类型值。</span><span class="sxs-lookup"><span data-stu-id="95ac4-192">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="95ac4-193">用于将字符串转换成双精度类型值的方法是 `double.TryParse()`：</span><span class="sxs-lookup"><span data-stu-id="95ac4-193">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="95ac4-194">此方法利用 C# out 参数来指示能否将输入字符串转换成双精度类型值。</span><span class="sxs-lookup"><span data-stu-id="95ac4-194">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="95ac4-195">如果字符串确实是双精度类型值的有效表示形式，那么此方法会返回 true，并且 `result` 自变量中包含相应的值。</span><span class="sxs-lookup"><span data-stu-id="95ac4-195">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="95ac4-196">如果字符串不是双精度类型值的有效表示形式，则此方法返回 false。</span><span class="sxs-lookup"><span data-stu-id="95ac4-196">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="95ac4-197">能够使用返回*可以为 null 的双精度类型值*的*扩展方法*来调整此 API。</span><span class="sxs-lookup"><span data-stu-id="95ac4-197">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="95ac4-198">*可以为 null 的值类型*是某种值类型的类型表示形式，还可以保留缺少的值或 null 值。</span><span class="sxs-lookup"><span data-stu-id="95ac4-198">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="95ac4-199">可以为 null 的类型以类型声明中追加的 `?` 字符表示。</span><span class="sxs-lookup"><span data-stu-id="95ac4-199">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="95ac4-200">虽然扩展方法被定义为静态方法，但可以在第一个参数中添加 `this` 修饰符，这样便能调用扩展方法，就像是相应类的成员方法一样。</span><span class="sxs-lookup"><span data-stu-id="95ac4-200">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="95ac4-201">只能在静态类中定义扩展方法。</span><span class="sxs-lookup"><span data-stu-id="95ac4-201">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="95ac4-202">下面定义了包含用于分析的扩展方法的类：</span><span class="sxs-lookup"><span data-stu-id="95ac4-202">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="95ac4-203">调用扩展方法前，将当前区域性更改为固定区域性：</span><span class="sxs-lookup"><span data-stu-id="95ac4-203">Before calling the extension method, change the current culture to invariant:</span></span>

[!code-csharp[SetCulture](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#SetCulture "set current culture to invariant")]

<span data-ttu-id="95ac4-204">这可以确保应用程序在任意服务器上用相同的方式解析数字，而不管其默认区域性。</span><span class="sxs-lookup"><span data-stu-id="95ac4-204">This ensures that your application parses numbers the same on any server, regardless of its default culture.</span></span>

<span data-ttu-id="95ac4-205">现在，可以使用此扩展方法将查询字符串自变量转换成双精度类型：</span><span class="sxs-lookup"><span data-stu-id="95ac4-205">Now you can use the extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="95ac4-206">为了能够轻松测试分析代码，请将响应更新为包含以下自变量值：</span><span class="sxs-lookup"><span data-stu-id="95ac4-206">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="95ac4-207">此时，可以运行 Web 应用程序，并检查分析代码是否有效。</span><span class="sxs-lookup"><span data-stu-id="95ac4-207">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="95ac4-208">在浏览器中向 Web 请求添加值，应该能够看到更新后的结果。</span><span class="sxs-lookup"><span data-stu-id="95ac4-208">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="95ac4-209">生成随机天气预报</span><span class="sxs-lookup"><span data-stu-id="95ac4-209">Build a random weather forecast</span></span>

<span data-ttu-id="95ac4-210">下一个任务是生成随机天气预报。</span><span class="sxs-lookup"><span data-stu-id="95ac4-210">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="95ac4-211">让我们从包含天气预报所需值的数据容器入手：</span><span class="sxs-lookup"><span data-stu-id="95ac4-211">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions =
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HighTemperatureFahrenheit { get; }
    public int LowTemperatureFahrenheit { get; }
    public int AverageWindSpeedMph { get; }
    public string Condition { get; }
}
```

<span data-ttu-id="95ac4-212">接下来，生成用于随机设置这些值的构造函数。</span><span class="sxs-lookup"><span data-stu-id="95ac4-212">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="95ac4-213">此构造函数将经纬度值用作 `Random` 数生成器的源。</span><span class="sxs-lookup"><span data-stu-id="95ac4-213">This constructor uses the values for the latitude and longitude to seed the `Random` number generator.</span></span> <span data-ttu-id="95ac4-214">也就是说，同一地理位置的天气预报也是相同的。</span><span class="sxs-lookup"><span data-stu-id="95ac4-214">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="95ac4-215">如果更改经纬度自变量，将会生成不同的天气预报（因为源不同）。</span><span class="sxs-lookup"><span data-stu-id="95ac4-215">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed).</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="95ac4-216">现在可以在响应方法中生成 5 天的天气预报：</span><span class="sxs-lookup"><span data-stu-id="95ac4-216">You can now generate the 5-day forecast in your response method:</span></span>

```csharp
if (latitude.HasValue && longitude.HasValue)
{
    var forecast = new List<WeatherReport>();
    for (var days = 1; days <= 5; days++)
    {
        forecast.Add(new WeatherReport(latitude.Value, longitude.Value, days));
    }
}
```

### <a name="build-the-json-response"></a><span data-ttu-id="95ac4-217">生成 JSON 响应</span><span class="sxs-lookup"><span data-stu-id="95ac4-217">Build the JSON response</span></span>

<span data-ttu-id="95ac4-218">服务器的最终代码任务是将 `WeatherReport` 列表转换为 JSON 文档并将其发送回客户端。</span><span class="sxs-lookup"><span data-stu-id="95ac4-218">The final code task on the server is to convert the `WeatherReport` list into JSON document, and send that back to the client.</span></span> <span data-ttu-id="95ac4-219">首先，我们要创建 JSON 文档。</span><span class="sxs-lookup"><span data-stu-id="95ac4-219">Let's start by creating the JSON document.</span></span> <span data-ttu-id="95ac4-220">将把 Newtonsoft JSON 序列化程序添加到依赖项列表中。</span><span class="sxs-lookup"><span data-stu-id="95ac4-220">You'll add the Newtonsoft JSON serializer to the list of dependencies.</span></span> <span data-ttu-id="95ac4-221">可以使用以下 `dotnet` 命令执行此操作：</span><span class="sxs-lookup"><span data-stu-id="95ac4-221">You can do that using the following `dotnet` command:</span></span>

```console
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="95ac4-222">然后，可以使用 `JsonConvert` 类将对象写入字符串：</span><span class="sxs-lookup"><span data-stu-id="95ac4-222">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="95ac4-223">上面的代码将 forecast 对象（`WeatherForecast` 对象列表）转换成 JSON 文档。</span><span class="sxs-lookup"><span data-stu-id="95ac4-223">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON document.</span></span> <span data-ttu-id="95ac4-224">构造响应文档后，将内容类型设置为 `application/json`，并编写字符串。</span><span class="sxs-lookup"><span data-stu-id="95ac4-224">After you've constructed the response document, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="95ac4-225">应用程序现在可以运行并返回随机天气预报。</span><span class="sxs-lookup"><span data-stu-id="95ac4-225">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="95ac4-226">生成 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="95ac4-226">Build a Docker image</span></span>

<span data-ttu-id="95ac4-227">最后一项任务是在 Docker 中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-227">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="95ac4-228">我们将创建一个 Docker 容器，用于运行表示此应用程序的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="95ac4-228">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="95ac4-229">***Docker 映像***是定义应用程序运行环境的文件。</span><span class="sxs-lookup"><span data-stu-id="95ac4-229">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="95ac4-230">***Docker 容器***表示正在运行的 Docker 映像实例。</span><span class="sxs-lookup"><span data-stu-id="95ac4-230">A ***Docker Container*** represents a running instance of a Docker Image.</span></span>

<span data-ttu-id="95ac4-231">通过类推，可以将 *Docker 映像*视为*类*，将 *Docker 容器*视为对象或此类的实例。</span><span class="sxs-lookup"><span data-stu-id="95ac4-231">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="95ac4-232">以下 Dockerfile 可供我们自行使用：</span><span class="sxs-lookup"><span data-stu-id="95ac4-232">The following Dockerfile will serve for our purposes:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="95ac4-233">我们先来介绍一下此文件的内容。</span><span class="sxs-lookup"><span data-stu-id="95ac4-233">Let's go over its contents.</span></span>

<span data-ttu-id="95ac4-234">第一行指定用于生成应用程序的源映像：</span><span class="sxs-lookup"><span data-stu-id="95ac4-234">The first line specifies the source image used for building the application:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
```

<span data-ttu-id="95ac4-235">通过 Docker，可以根据源模板配置计算机映像。</span><span class="sxs-lookup"><span data-stu-id="95ac4-235">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="95ac4-236">也就是说，开始时并不需要提供所有计算机参数，只需提供全部更改。</span><span class="sxs-lookup"><span data-stu-id="95ac4-236">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="95ac4-237">此处所说的更改包括我们的应用程序在内。</span><span class="sxs-lookup"><span data-stu-id="95ac4-237">The changes here will be to include our application.</span></span>

<span data-ttu-id="95ac4-238">在此示例中，我们将使用 `dotnet` 映像的 `2.1-sdk` 版本。</span><span class="sxs-lookup"><span data-stu-id="95ac4-238">In this sample, we'll use the `2.1-sdk` version of the `dotnet` image.</span></span> <span data-ttu-id="95ac4-239">这是创建有效 Docker 环境的最简单方式。</span><span class="sxs-lookup"><span data-stu-id="95ac4-239">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="95ac4-240">此映像包括 .NET Core 运行时和 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="95ac4-240">This image includes the .NET Core runtime, and the .NET Core SDK.</span></span>
<span data-ttu-id="95ac4-241">这使得入门和生成更加轻松，但是创建的映像会更大，所以我们将使用此映像生成应用程序，使用另一个映像运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-241">That makes it easier to get started and build, but does create a larger image, so we'll use this image for building the application and a different image to run it.</span></span>

<span data-ttu-id="95ac4-242">下面几行代码用于设置并生成应用程序：</span><span class="sxs-lookup"><span data-stu-id="95ac4-242">The next lines setup and build your application:</span></span>

```
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="95ac4-243">这会将当前目录中的项目文件复制到 Docker VM 中，并还原所有包。</span><span class="sxs-lookup"><span data-stu-id="95ac4-243">This will copy the project file from the  current directory to the Docker VM, and restore all the packages.</span></span> <span data-ttu-id="95ac4-244">使用 .NET CLI 意味着 Docker 映像必须包含 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="95ac4-244">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="95ac4-245">完成上述操作之后，应用程序的其余部分会得到复制，然后 `dotnet
publish` 命令会生成并打包应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-245">After that, the rest of your application gets copied, and the `dotnet
publish` command builds and packages your application.</span></span>

<span data-ttu-id="95ac4-246">最后，我们创建运行应用程序的第二个 Docker 映像：</span><span class="sxs-lookup"><span data-stu-id="95ac4-246">Finally, we create a second Docker image that runs the application:</span></span>

```
# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="95ac4-247">此映像使用 `dotnet` 映像的 `2.1-aspnetcore-runtime` 版本，其中包含运行 ASP.NET Core 应用程序所需的全部内容，但是不包括 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="95ac4-247">This image uses the `2.1-aspnetcore-runtime` version of the `dotnet` image, which contains everything necessary to run ASP.NET Core applications, but does not include the .NET Core SDK.</span></span> <span data-ttu-id="95ac4-248">这意味着，此映像不能用于生成 .NET Core 应用程序，但它可以使最终映像变得更小。</span><span class="sxs-lookup"><span data-stu-id="95ac4-248">This means this image can't be used to build .NET Core applications, but it also makes the final image smaller.</span></span>

<span data-ttu-id="95ac4-249">为了实现此目的，我们将生成的应用程序从第一个映像复制到第二个。</span><span class="sxs-lookup"><span data-stu-id="95ac4-249">To make this work, we copy the built application from the first image to the second one.</span></span>

<span data-ttu-id="95ac4-250">`ENTRYPOINT` 命令通知 Docker 启动服务的命令。</span><span class="sxs-lookup"><span data-stu-id="95ac4-250">The `ENTRYPOINT` command informs Docker what command starts the service.</span></span>

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="95ac4-251">在容器中生成并运行映像</span><span class="sxs-lookup"><span data-stu-id="95ac4-251">Building and running the image in a container</span></span>

<span data-ttu-id="95ac4-252">让我们在 Docker 容器中生成映像并运行服务。</span><span class="sxs-lookup"><span data-stu-id="95ac4-252">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="95ac4-253">不是要将本地目录中的所有文件都复制到映像中，</span><span class="sxs-lookup"><span data-stu-id="95ac4-253">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="95ac4-254">而是要在容器中生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ac4-254">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="95ac4-255">将创建 `.dockerignore` 文件来指定不要复制到映像中的目录。</span><span class="sxs-lookup"><span data-stu-id="95ac4-255">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="95ac4-256">你不想复制任何生成资产。</span><span class="sxs-lookup"><span data-stu-id="95ac4-256">You don't want any of the build assets copied.</span></span> <span data-ttu-id="95ac4-257">请在 `.dockerignore` 文件中指定生成和发布目录：</span><span class="sxs-lookup"><span data-stu-id="95ac4-257">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="95ac4-258">使用 `docker build` 命令生成映像。</span><span class="sxs-lookup"><span data-stu-id="95ac4-258">You build the image using the `docker build` command.</span></span> <span data-ttu-id="95ac4-259">从包含代码的目录运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="95ac4-259">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="95ac4-260">此命令将根据 Dockerfile 中的所有信息生成容器映像。</span><span class="sxs-lookup"><span data-stu-id="95ac4-260">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="95ac4-261">`-t` 自变量提供此容器映像的标记或名称。</span><span class="sxs-lookup"><span data-stu-id="95ac4-261">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="95ac4-262">在上面的命令行中，Docker 容器的标记是 `weather-microservice`。</span><span class="sxs-lookup"><span data-stu-id="95ac4-262">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="95ac4-263">此命令完成后，就生成了一个可用于运行新服务的容器。</span><span class="sxs-lookup"><span data-stu-id="95ac4-263">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="95ac4-264">运行以下命令，启动容器和服务：</span><span class="sxs-lookup"><span data-stu-id="95ac4-264">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:80 --name hello-docker weather-microservice
```

<span data-ttu-id="95ac4-265">`-d` 选项表示运行从当前终端拆离出来的容器。</span><span class="sxs-lookup"><span data-stu-id="95ac4-265">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="95ac4-266">也就是说，终端中不会显示命令输出。</span><span class="sxs-lookup"><span data-stu-id="95ac4-266">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="95ac4-267">`-p` 选项指示服务和主机之间的端口映射。</span><span class="sxs-lookup"><span data-stu-id="95ac4-267">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="95ac4-268">即指应将端口 80 上的所有传入请求都转发到容器上的端口 80。</span><span class="sxs-lookup"><span data-stu-id="95ac4-268">Here it says that any incoming request on port 80 should be forwarded to port 80 on the container.</span></span> <span data-ttu-id="95ac4-269">使用 80 与服务正在侦听的端口相匹配，这是生产应用程序的默认端口。</span><span class="sxs-lookup"><span data-stu-id="95ac4-269">Using 80 matches the port your service is listening on, which is the default port for production applications.</span></span> <span data-ttu-id="95ac4-270">`--name` 自变量用于命名正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="95ac4-270">The `--name` argument names your running container.</span></span> <span data-ttu-id="95ac4-271">此名称可方便与容器结合使用。</span><span class="sxs-lookup"><span data-stu-id="95ac4-271">It's a convenient name you can use to work with that container.</span></span>

<span data-ttu-id="95ac4-272">可以运行以下命令来确定映像能否正常运行：</span><span class="sxs-lookup"><span data-stu-id="95ac4-272">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="95ac4-273">如果容器能正常运行，那么正在运行的进程中就会有一行列出它来</span><span class="sxs-lookup"><span data-stu-id="95ac4-273">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="95ac4-274">（可能是唯一的。）</span><span class="sxs-lookup"><span data-stu-id="95ac4-274">(It may be the only one.)</span></span>

<span data-ttu-id="95ac4-275">可以打开浏览器并转到 localhost，然后指定经纬度，从而测试服务：</span><span class="sxs-lookup"><span data-stu-id="95ac4-275">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="95ac4-276">附加到正在运行的容器</span><span class="sxs-lookup"><span data-stu-id="95ac4-276">Attaching to a running container</span></span>

<span data-ttu-id="95ac4-277">在命令窗口中运行服务时，可以查看针对各个请求打印输出的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="95ac4-277">When you ran your service in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="95ac4-278">如果容器是在拆离模式下运行，则看不到此类信息。</span><span class="sxs-lookup"><span data-stu-id="95ac4-278">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="95ac4-279">使用 Docker 附加命令，可以将窗口附加到正在运行的容器，以便查看日志信息。</span><span class="sxs-lookup"><span data-stu-id="95ac4-279">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="95ac4-280">在命令窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="95ac4-280">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="95ac4-281">`--sig-proxy=false` 自变量表示 <kbd>Ctrl</kbd>+<kbd>C</kbd> 命令未发送到容器进程，而是停止运行 `docker attach` 命令。</span><span class="sxs-lookup"><span data-stu-id="95ac4-281">The `--sig-proxy=false` argument means that <kbd>Ctrl</kbd>+<kbd>C</kbd> commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="95ac4-282">最后的自变量是为 `docker run` 命令中的容器命名的名称。</span><span class="sxs-lookup"><span data-stu-id="95ac4-282">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="95ac4-283">还可以使用 Docker 分配的容器 ID 来引用任何容器。</span><span class="sxs-lookup"><span data-stu-id="95ac4-283">You can also use the Docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="95ac4-284">如果没有在 `docker run` 中指定容器名称，则必须使用容器 ID。</span><span class="sxs-lookup"><span data-stu-id="95ac4-284">If you didn't specify a name for your container in `docker run` you must use the container ID.</span></span>

<span data-ttu-id="95ac4-285">打开浏览器并转到服务。</span><span class="sxs-lookup"><span data-stu-id="95ac4-285">Open a browser and navigate to your service.</span></span> <span data-ttu-id="95ac4-286">将可以在命令窗口中查看附加的正在运行的容器生成的诊断消息。</span><span class="sxs-lookup"><span data-stu-id="95ac4-286">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="95ac4-287">按 <kbd>Ctrl</kbd>+<kbd>C</kbd> 可停止附加进程。</span><span class="sxs-lookup"><span data-stu-id="95ac4-287">Press <kbd>Ctrl</kbd>+<kbd>C</kbd> to stop the attach process.</span></span>

<span data-ttu-id="95ac4-288">使用完后，可以停止运行容器：</span><span class="sxs-lookup"><span data-stu-id="95ac4-288">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="95ac4-289">容器和映像仍可供重启。</span><span class="sxs-lookup"><span data-stu-id="95ac4-289">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="95ac4-290">若要从计算机中删除容器，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="95ac4-290">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="95ac4-291">若要从计算机中删除未使用的映像，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="95ac4-291">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="95ac4-292">结束语</span><span class="sxs-lookup"><span data-stu-id="95ac4-292">Conclusion</span></span> 

<span data-ttu-id="95ac4-293">在此教程中，你生成了 ASP.NET Core 微服务，并添加了一些简单的功能。</span><span class="sxs-lookup"><span data-stu-id="95ac4-293">In this tutorial, you built an ASP.NET Core microservice, and added a few simple features.</span></span>

<span data-ttu-id="95ac4-294">此外，你还生成了此服务的 Docker 容器映像，并在计算机上运行了相应的容器。</span><span class="sxs-lookup"><span data-stu-id="95ac4-294">You built a Docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="95ac4-295">最后，你还将终端窗口附加到了服务中，并查看服务生成的诊断消息。</span><span class="sxs-lookup"><span data-stu-id="95ac4-295">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="95ac4-296">与此同时，你还了解了多项 C# 语言功能的实际运用。</span><span class="sxs-lookup"><span data-stu-id="95ac4-296">Along the way, you saw several features of the C# language in action.</span></span>
