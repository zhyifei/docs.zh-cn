---
title: "Docker 中托管的微服务 - C#"
description: "了解如何创建在 Docker 容器中运行的 ASP.NET Core 服务"
keywords: ".NET, .NET Core, Docker, C#, ASP.NET, 微服务"
author: BillWagner
ms.author: wiwagn
ms.date: 02/03/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: csharp
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: d399cdce81350356b71e21d879a4f5b5079f98d8
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2018
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="358cb-104">Docker 中托管的微服务</span><span class="sxs-lookup"><span data-stu-id="358cb-104">Microservices hosted in Docker</span></span>

<span data-ttu-id="358cb-105">此教程将详细介绍在 Docker 容器中生成和部署 ASP.NET Core 微服务时必须完成的任务。</span><span class="sxs-lookup"><span data-stu-id="358cb-105">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="358cb-106">在此教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="358cb-106">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="358cb-107">如何使用 Yeoman 生成 ASP.NET Core 应用程序</span><span class="sxs-lookup"><span data-stu-id="358cb-107">How to generate an ASP.NET Core application using Yeoman</span></span>
* <span data-ttu-id="358cb-108">如何创建 Docker 开发环境</span><span class="sxs-lookup"><span data-stu-id="358cb-108">How to create a development Docker environment</span></span>
* <span data-ttu-id="358cb-109">如何根据现有映像生成 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="358cb-109">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="358cb-110">如何将服务部署到 Docker 容器中。</span><span class="sxs-lookup"><span data-stu-id="358cb-110">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="358cb-111">与此同时，你还将了解下面这些 C# 语言功能：</span><span class="sxs-lookup"><span data-stu-id="358cb-111">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="358cb-112">如何将 C# 对象转换成 JSON 有效负载。</span><span class="sxs-lookup"><span data-stu-id="358cb-112">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="358cb-113">如何生成不可变的数据传输对象</span><span class="sxs-lookup"><span data-stu-id="358cb-113">How to build immutable Data Transfer Objects</span></span>
* <span data-ttu-id="358cb-114">如何处理传入的 HTTP 请求并生成 HTTP 响应</span><span class="sxs-lookup"><span data-stu-id="358cb-114">How to process incoming HTTP Requests and generate the HTTP Response</span></span>
* <span data-ttu-id="358cb-115">如何使用可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="358cb-115">How to work with nullable value types</span></span>

<span data-ttu-id="358cb-116">你可以[查看或下载本主题的示例应用](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice)。</span><span class="sxs-lookup"><span data-stu-id="358cb-116">You can [view or download the sample app](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="358cb-117">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="358cb-117">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="why-docker"></a><span data-ttu-id="358cb-118">为什么要使用 Docker？</span><span class="sxs-lookup"><span data-stu-id="358cb-118">Why Docker?</span></span>

<span data-ttu-id="358cb-119">使用 Docker，可以轻松地创建标准计算机映像，从而在数据中心或公有云中托管服务。</span><span class="sxs-lookup"><span data-stu-id="358cb-119">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="358cb-120">使用 Docker，可以配置映像，并根据需要复制映像来扩展应用程序安装。</span><span class="sxs-lookup"><span data-stu-id="358cb-120">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="358cb-121">此教程中的所有代码适用于任何 .NET Core 环境。</span><span class="sxs-lookup"><span data-stu-id="358cb-121">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="358cb-122">附加 Docker 安装任务适用于 ASP.NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="358cb-122">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="358cb-123">系统必备</span><span class="sxs-lookup"><span data-stu-id="358cb-123">Prerequisites</span></span>
<span data-ttu-id="358cb-124">必须将计算机设置为运行 .Net Core。</span><span class="sxs-lookup"><span data-stu-id="358cb-124">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="358cb-125">有关安装说明，请访问 [.NET Core](https://www.microsoft.com/net/core) 页。</span><span class="sxs-lookup"><span data-stu-id="358cb-125">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="358cb-126">可以在 Windows、Ubuntu Linux、macOS 或 Docker 容器中运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="358cb-126">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="358cb-127">必须安装常用的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="358cb-127">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="358cb-128">在以下说明中，我们使用的是开放源代码跨平台编辑器 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="358cb-128">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="358cb-129">不过，你可以使用习惯使用的任意工具。</span><span class="sxs-lookup"><span data-stu-id="358cb-129">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="358cb-130">还必须安装 Docker 引擎。</span><span class="sxs-lookup"><span data-stu-id="358cb-130">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="358cb-131">请参阅 [Docker 安装页](http://www.docker.com/products/docker)，了解适用于自己的平台的说明。</span><span class="sxs-lookup"><span data-stu-id="358cb-131">See the [Docker Installation page](http://www.docker.com/products/docker) for instructions for your platform.</span></span>
<span data-ttu-id="358cb-132">可以在许多 Linux 发行版本、macOS 或 Windows 中安装 Docker。</span><span class="sxs-lookup"><span data-stu-id="358cb-132">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="358cb-133">上面引用的页面分部分提供了各个可安装的版本。</span><span class="sxs-lookup"><span data-stu-id="358cb-133">The page referenced above contains sections to each of the available installations.</span></span>

<span data-ttu-id="358cb-134">大多数组件的安装是通过程序包管理器完成的。</span><span class="sxs-lookup"><span data-stu-id="358cb-134">Most components to be installed are done by a package manager.</span></span> <span data-ttu-id="358cb-135">如果已安装 node.js 的程序包管理器 `npm`，可跳过这一步。</span><span class="sxs-lookup"><span data-stu-id="358cb-135">If you have node.js's package manager `npm` installed you can skip this step.</span></span> <span data-ttu-id="358cb-136">否则，请从 [nodejs.org](https://nodejs.org) 下载并安装最新的 NodeJs，即会安装 npm 程序包管理器。</span><span class="sxs-lookup"><span data-stu-id="358cb-136">Otherwise install the latest NodeJs from [nodejs.org](https://nodejs.org) which will install the npm package manager.</span></span> 

<span data-ttu-id="358cb-137">此时，需要安装许多支持 ASP.NET Core 开发的命令行工具。</span><span class="sxs-lookup"><span data-stu-id="358cb-137">At this point you will need to install a number of command line tools that support ASP.NET core development.</span></span> <span data-ttu-id="358cb-138">命令行模板使用 Yeoman、Bower、Grunt、和 Gulp。</span><span class="sxs-lookup"><span data-stu-id="358cb-138">The command line templates use Yeoman, Bower, Grunt, and Gulp.</span></span> <span data-ttu-id="358cb-139">如果已全部安装，可继续执行其他操作；否则，请在常用的命令行管理程序中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="358cb-139">If you have them installed that is good, otherwise type the following into your favorite shell:</span></span>

`npm install -g yo bower grunt-cli gulp`

<span data-ttu-id="358cb-140">`-g` 选项指明此为全局安装，这些工具可在整个系统范围内使用。</span><span class="sxs-lookup"><span data-stu-id="358cb-140">The `-g` option indicates that it is a global install, and those tools are available system wide.</span></span> <span data-ttu-id="358cb-141">（本地安装将包限定为只能供一个项目使用。）</span><span class="sxs-lookup"><span data-stu-id="358cb-141">(A local install scopes the package to a single project).</span></span> <span data-ttu-id="358cb-142">安装这些核心工具后，必须安装 Yeoman ASP.NET 模板生成器：</span><span class="sxs-lookup"><span data-stu-id="358cb-142">Once you've installed those core tools, you need to install the yeoman ASP.NET template generators:</span></span>

`npm install -g generator-aspnet`

## <a name="create-the-application"></a><span data-ttu-id="358cb-143">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="358cb-143">Create the Application</span></span>

<span data-ttu-id="358cb-144">至此，你已安装所有工具，是时候新建 ASP.NET Core 应用程序了。</span><span class="sxs-lookup"><span data-stu-id="358cb-144">Now that you've installed all the tools, create a new ASP.NET Core application.</span></span> <span data-ttu-id="358cb-145">若要使用命令行生成器，请在常用的命令行管理程序中执行以下 Yeoman 命令：</span><span class="sxs-lookup"><span data-stu-id="358cb-145">To use the command line generator, execute the following yeoman command in your favorite shell:</span></span>

`yo aspnet`

<span data-ttu-id="358cb-146">此命令会提示你选择要创建的应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="358cb-146">This command prompts you to select what Type of application you want to create.</span></span> <span data-ttu-id="358cb-147">对于此微服务，需要的是最简单最轻量级的 Web 应用程序，因此选择“空 Web 应用程序”。</span><span class="sxs-lookup"><span data-stu-id="358cb-147">For this microservice, you want the simplest, most lightweight web application possible, so select 'Empty Web Application'.</span></span> <span data-ttu-id="358cb-148">此模板会提示你选择名称。</span><span class="sxs-lookup"><span data-stu-id="358cb-148">The template will prompt you for a name.</span></span> <span data-ttu-id="358cb-149">选择“WeatherMicroservice”。</span><span class="sxs-lookup"><span data-stu-id="358cb-149">Select 'WeatherMicroservice'.</span></span> 

<span data-ttu-id="358cb-150">此模板将为你创建以下八个文件：</span><span class="sxs-lookup"><span data-stu-id="358cb-150">The template creates eight files for you:</span></span>

* <span data-ttu-id="358cb-151">为 ASP.NET Core 应用程序定制的 .gitignore 文件。</span><span class="sxs-lookup"><span data-stu-id="358cb-151">A .gitignore, customized for ASP.NET Core applications.</span></span>
* <span data-ttu-id="358cb-152">Startup.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="358cb-152">A Startup.cs file.</span></span> <span data-ttu-id="358cb-153">其中包含应用程序的基本内容。</span><span class="sxs-lookup"><span data-stu-id="358cb-153">This contains the basis of the application.</span></span>
* <span data-ttu-id="358cb-154">Program.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="358cb-154">A Program.cs file.</span></span> <span data-ttu-id="358cb-155">其中包含应用程序的入口点。</span><span class="sxs-lookup"><span data-stu-id="358cb-155">This contains the entry point of the application.</span></span>
* <span data-ttu-id="358cb-156">WeatherMicroservice.csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="358cb-156">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="358cb-157">这是应用程序的生成文件。</span><span class="sxs-lookup"><span data-stu-id="358cb-157">This is the build file for the application.</span></span>
* <span data-ttu-id="358cb-158">Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="358cb-158">A Dockerfile.</span></span> <span data-ttu-id="358cb-159">此脚本将创建应用程序的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="358cb-159">This script creates a Docker image for the application.</span></span>
* <span data-ttu-id="358cb-160">README.md 文件。</span><span class="sxs-lookup"><span data-stu-id="358cb-160">A README.md.</span></span> <span data-ttu-id="358cb-161">其中包含指向其他 ASP.NET Core 资源的链接。</span><span class="sxs-lookup"><span data-stu-id="358cb-161">This contains links to other ASP.NET Core resources.</span></span>
* <span data-ttu-id="358cb-162">web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="358cb-162">A web.config file.</span></span> <span data-ttu-id="358cb-163">其中包含基本配置信息。</span><span class="sxs-lookup"><span data-stu-id="358cb-163">This contains basic configuration information.</span></span>
* <span data-ttu-id="358cb-164">runtimeconfig.template.json 文件。</span><span class="sxs-lookup"><span data-stu-id="358cb-164">A runtimeconfig.template.json file.</span></span> <span data-ttu-id="358cb-165">其中包含 IDE 使用的调试设置。</span><span class="sxs-lookup"><span data-stu-id="358cb-165">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="358cb-166">现在可以运行模板生成的应用程序了。</span><span class="sxs-lookup"><span data-stu-id="358cb-166">Now you can run the template generated application.</span></span> <span data-ttu-id="358cb-167">为此，可通过命令行使用一系列工具。</span><span class="sxs-lookup"><span data-stu-id="358cb-167">That's done using a series of tools from the command line.</span></span> <span data-ttu-id="358cb-168">`dotnet` 命令可运行 .NET 开发所需的工具。</span><span class="sxs-lookup"><span data-stu-id="358cb-168">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="358cb-169">每个谓词执行一个不同的命令</span><span class="sxs-lookup"><span data-stu-id="358cb-169">Each verb executes a different command</span></span>

<span data-ttu-id="358cb-170">第一步是还原所有依赖项：</span><span class="sxs-lookup"><span data-stu-id="358cb-170">The first step is to restore all the dependencies:</span></span>

```console
dotnet restore
```

<span data-ttu-id="358cb-171">dotnet restore 使用 NuGet 程序包管理器将所有必需包安装到应用程序目录中。</span><span class="sxs-lookup"><span data-stu-id="358cb-171">Dotnet restore uses the NuGet package manager to install all the necessary packages into the application directory.</span></span> <span data-ttu-id="358cb-172">还将生成 project.json.lock 文件。</span><span class="sxs-lookup"><span data-stu-id="358cb-172">It also generates a project.json.lock file.</span></span> <span data-ttu-id="358cb-173">此文件包含引用的各个包的相关信息。</span><span class="sxs-lookup"><span data-stu-id="358cb-173">This file contains information about each package that is referenced.</span></span> <span data-ttu-id="358cb-174">还原所有依赖项后，生成应用程序：</span><span class="sxs-lookup"><span data-stu-id="358cb-174">After restoring all the dependencies, you build the application:</span></span>

```console
dotnet build
```
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="358cb-175">生成应用程序后，使用命令行运行程序：</span><span class="sxs-lookup"><span data-stu-id="358cb-175">And once you build the application, you run it from the command line:</span></span>

```console
dotnet run
```

<span data-ttu-id="358cb-176">默认配置侦听的是 http://localhost:5000 。</span><span class="sxs-lookup"><span data-stu-id="358cb-176">The default configuration listens to http://localhost:5000.</span></span> <span data-ttu-id="358cb-177">可以打开浏览器并转到相应页面，看到的是“Hello World!”</span><span class="sxs-lookup"><span data-stu-id="358cb-177">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="358cb-178">消息。</span><span class="sxs-lookup"><span data-stu-id="358cb-178">message.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="358cb-179">ASP.NET Core 应用程序剖析</span><span class="sxs-lookup"><span data-stu-id="358cb-179">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="358cb-180">至此，已生成应用程序，让我们来看看此应用程序功能是如何实现的。</span><span class="sxs-lookup"><span data-stu-id="358cb-180">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="358cb-181">此时，生成的文件中有两个需要特别关注：project.json 和 Startup.cs。</span><span class="sxs-lookup"><span data-stu-id="358cb-181">There are two of the generated files that are particularly interesting at this point: project.json and Startup.cs.</span></span> 

<span data-ttu-id="358cb-182">Project.json 包含项目相关信息。</span><span class="sxs-lookup"><span data-stu-id="358cb-182">Project.json contains information about the project.</span></span> <span data-ttu-id="358cb-183">经常要用到的两个节点是“依赖项”和“框架”。</span><span class="sxs-lookup"><span data-stu-id="358cb-183">The two nodes you'll often work with are 'dependencies' and 'frameworks'.</span></span> <span data-ttu-id="358cb-184">“依赖项”节点列出了此应用程序需要的所有包。</span><span class="sxs-lookup"><span data-stu-id="358cb-184">The dependencies node lists all the packages that are needed for this application.</span></span>
<span data-ttu-id="358cb-185">此时，这是一个小型节点，只需要列出运行 Web 服务器的包。</span><span class="sxs-lookup"><span data-stu-id="358cb-185">At the moment, this is a small node, needing only the packages that run the web server.</span></span>

<span data-ttu-id="358cb-186">“框架”节点指定了将运行此应用程序的 .NET Framework 的版本和配置。</span><span class="sxs-lookup"><span data-stu-id="358cb-186">The 'frameworks' node specifies the versions and configurations of the .NET framework that will run this application.</span></span>

<span data-ttu-id="358cb-187">此应用程序是在 Startup.cs 中实现。</span><span class="sxs-lookup"><span data-stu-id="358cb-187">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="358cb-188">此文件包含启动类。</span><span class="sxs-lookup"><span data-stu-id="358cb-188">This file contains the startup class.</span></span>

<span data-ttu-id="358cb-189">ASP.NET Core 基础结构调用两种方法来配置并运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="358cb-189">The two methods are called by the ASP.NET Core infrastructure to configure and run the application.</span></span> <span data-ttu-id="358cb-190">`ConfigureServices` 方法描述了此应用程序所需的服务。</span><span class="sxs-lookup"><span data-stu-id="358cb-190">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="358cb-191">由于要生成的是精简的微服务，因此无需配置任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="358cb-191">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="358cb-192">`Configure` 方法配置传入 HTTP 请求的处理程序。</span><span class="sxs-lookup"><span data-stu-id="358cb-192">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="358cb-193">模板生成简单的处理程序来响应所有关于文本“Hello World!”的请求。</span><span class="sxs-lookup"><span data-stu-id="358cb-193">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="358cb-194">生成微服务</span><span class="sxs-lookup"><span data-stu-id="358cb-194">Build a microservice</span></span>

<span data-ttu-id="358cb-195">要生成的服务将用于传递世界各地的天气预报。</span><span class="sxs-lookup"><span data-stu-id="358cb-195">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="358cb-196">在生产应用程序中，需要调用一些服务来检索天气数据。</span><span class="sxs-lookup"><span data-stu-id="358cb-196">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="358cb-197">在此示例中，我们将生成随机天气预报服务。</span><span class="sxs-lookup"><span data-stu-id="358cb-197">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="358cb-198">需要执行以下许多任务，才能实现随机天气预报服务：</span><span class="sxs-lookup"><span data-stu-id="358cb-198">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="358cb-199">分析传入请求，读取经纬度。</span><span class="sxs-lookup"><span data-stu-id="358cb-199">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="358cb-200">生成一些随机预报数据。</span><span class="sxs-lookup"><span data-stu-id="358cb-200">Generate some random forecast data.</span></span>
* <span data-ttu-id="358cb-201">将随机预报数据从 C# 对象转换成 JSON 数据包。</span><span class="sxs-lookup"><span data-stu-id="358cb-201">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="358cb-202">将响应头设置为指示服务发送回 JSON。</span><span class="sxs-lookup"><span data-stu-id="358cb-202">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="358cb-203">编写响应。</span><span class="sxs-lookup"><span data-stu-id="358cb-203">Write the response.</span></span>

<span data-ttu-id="358cb-204">下面各部分将引导你逐一完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="358cb-204">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="358cb-205">分析查询字符串。</span><span class="sxs-lookup"><span data-stu-id="358cb-205">Parsing the Query String.</span></span>

<span data-ttu-id="358cb-206">首先要分析查询字符串。</span><span class="sxs-lookup"><span data-stu-id="358cb-206">You'll begin by parsing the query string.</span></span> <span data-ttu-id="358cb-207">此服务接受在以下形式的查询字符串中使用“lat”和“long”自变量：</span><span class="sxs-lookup"><span data-stu-id="358cb-207">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

`http://localhost:5000/?lat=-35.55&long=-12.35`  

<span data-ttu-id="358cb-208">只需更改定义为启动类中 `app.Run` 的自变量的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="358cb-208">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="358cb-209">lambda 表达式中的自变量是请求的 `HttpContext`。</span><span class="sxs-lookup"><span data-stu-id="358cb-209">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="358cb-210">其属性之一是 `Request` 对象。</span><span class="sxs-lookup"><span data-stu-id="358cb-210">One of its properties is the `Request` object.</span></span> <span data-ttu-id="358cb-211">`Request` 对象具有 `Query` 属性，其中包含请求查询字符串中所有值的字典。</span><span class="sxs-lookup"><span data-stu-id="358cb-211">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="358cb-212">第一次添加的代码是为了查找经纬度值：</span><span class="sxs-lookup"><span data-stu-id="358cb-212">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="358cb-213">查询字典值属于 `StringValue` 类型。</span><span class="sxs-lookup"><span data-stu-id="358cb-213">The Query dictionary values are `StringValue` type.</span></span> <span data-ttu-id="358cb-214">此类型可以包含一系列字符串。</span><span class="sxs-lookup"><span data-stu-id="358cb-214">That type can contain a collection of strings.</span></span> <span data-ttu-id="358cb-215">对于天气服务，每个值都是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="358cb-215">For your weather service, each value is a single string.</span></span> <span data-ttu-id="358cb-216">正因如此，上面的代码调用 `FirstOrDefault()`。</span><span class="sxs-lookup"><span data-stu-id="358cb-216">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="358cb-217">接下来，需要将字符串转换成双精度类型值。</span><span class="sxs-lookup"><span data-stu-id="358cb-217">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="358cb-218">用于将字符串转换成双精度类型值的方法是 `double.TryParse()`：</span><span class="sxs-lookup"><span data-stu-id="358cb-218">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="358cb-219">此方法利用 C# out 参数来指示能否将输入字符串转换成双精度类型值。</span><span class="sxs-lookup"><span data-stu-id="358cb-219">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="358cb-220">如果字符串确实是双精度类型值的有效表示形式，那么此方法会返回 true，并且 `result` 自变量中包含相应的值。</span><span class="sxs-lookup"><span data-stu-id="358cb-220">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="358cb-221">如果字符串不是双精度类型值的有效表示形式，则此方法返回 false。</span><span class="sxs-lookup"><span data-stu-id="358cb-221">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="358cb-222">能够使用返回*可以为 null 的双精度类型值*的*扩展方法*来调整此 API。</span><span class="sxs-lookup"><span data-stu-id="358cb-222">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="358cb-223">*可以为 null 的值类型*是某种值类型的类型表示形式，还可以保留缺少的值或 null 值。</span><span class="sxs-lookup"><span data-stu-id="358cb-223">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="358cb-224">可以为 null 的类型以类型声明中追加的 `?` 字符表示。</span><span class="sxs-lookup"><span data-stu-id="358cb-224">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="358cb-225">虽然扩展方法被定义为静态方法，但可以在第一个参数中添加 `this` 修饰符，这样便能调用扩展方法，就像是相应类的成员方法一样。</span><span class="sxs-lookup"><span data-stu-id="358cb-225">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="358cb-226">只能在静态类中定义扩展方法。</span><span class="sxs-lookup"><span data-stu-id="358cb-226">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="358cb-227">下面定义了包含用于分析的扩展方法的类：</span><span class="sxs-lookup"><span data-stu-id="358cb-227">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="358cb-228">`default(double?)` 表达式返回 `double?` 类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="358cb-228">The `default(double?)` expression returns the default value for the `double?` type.</span></span> <span data-ttu-id="358cb-229">默认值是 null（或缺少的）值。</span><span class="sxs-lookup"><span data-stu-id="358cb-229">That default value is the null (or missing) value.</span></span>

<span data-ttu-id="358cb-230">可以使用此扩展方法将查询字符串自变量转换成双精度类型：</span><span class="sxs-lookup"><span data-stu-id="358cb-230">You can use this extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="358cb-231">为了能够轻松测试分析代码，请将响应更新为包含以下自变量值：</span><span class="sxs-lookup"><span data-stu-id="358cb-231">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="358cb-232">此时，可以运行 Web 应用程序，并检查分析代码是否有效。</span><span class="sxs-lookup"><span data-stu-id="358cb-232">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="358cb-233">在浏览器中向 Web 请求添加值，应该能够看到更新后的结果。</span><span class="sxs-lookup"><span data-stu-id="358cb-233">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="358cb-234">生成随机天气预报</span><span class="sxs-lookup"><span data-stu-id="358cb-234">Build a random weather forecast</span></span>

<span data-ttu-id="358cb-235">下一个任务是生成随机天气预报。</span><span class="sxs-lookup"><span data-stu-id="358cb-235">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="358cb-236">让我们从包含天气预报所需值的数据容器入手：</span><span class="sxs-lookup"><span data-stu-id="358cb-236">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions = new string[]
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HiTemperature { get; }
    public int LoTemperature { get; }
    public int AverageWindSpeed { get; }
    public string Conditions { get; }
}
```

<span data-ttu-id="358cb-237">接下来，生成用于随机设置这些值的构造函数。</span><span class="sxs-lookup"><span data-stu-id="358cb-237">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="358cb-238">此构造函数将经纬度值用作随机数生成器的源。</span><span class="sxs-lookup"><span data-stu-id="358cb-238">This constructor uses the values for the latitude and longitude to seed the Random number generator.</span></span> <span data-ttu-id="358cb-239">也就是说，同一地理位置的天气预报也是相同的。</span><span class="sxs-lookup"><span data-stu-id="358cb-239">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="358cb-240">如果更改经纬度自变量，将会生成不同的天气预报（因为源不同）。</span><span class="sxs-lookup"><span data-stu-id="358cb-240">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed.)</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="358cb-241">现在可以在响应方法中生成 5 天的天气预报：</span><span class="sxs-lookup"><span data-stu-id="358cb-241">You can now generate the 5-day forecast in your response method:</span></span>

[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generate a random weather report")]

### <a name="build-the-json-response"></a><span data-ttu-id="358cb-242">生成 JSON 响应</span><span class="sxs-lookup"><span data-stu-id="358cb-242">Build the JSON response.</span></span>

<span data-ttu-id="358cb-243">服务器上的最后一项代码任务是，将 WeatherReport 数组转换成 JSON 数据包，然后将其发送回客户端。</span><span class="sxs-lookup"><span data-stu-id="358cb-243">The final code task on the server is to convert the WeatherReport array into a JSON packet, and send that back to the client.</span></span> <span data-ttu-id="358cb-244">首先，我们要创建 JSON 数据包。</span><span class="sxs-lookup"><span data-stu-id="358cb-244">Let's start by creating the JSON packet.</span></span> <span data-ttu-id="358cb-245">将把 NewtonSoft JSON 序列化程序添加到依赖项列表中。</span><span class="sxs-lookup"><span data-stu-id="358cb-245">You'll add the NewtonSoft JSON Serializer to the list of dependencies.</span></span> <span data-ttu-id="358cb-246">为此，请使用 `dotnet` CLI：</span><span class="sxs-lookup"><span data-stu-id="358cb-246">You can do that using the `dotnet` CLI:</span></span>

```
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="358cb-247">然后，可以使用 `JsonConvert` 类将对象写入字符串：</span><span class="sxs-lookup"><span data-stu-id="358cb-247">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="358cb-248">上面的代码将 forecast 对象（`WeatherForecast` 对象列表）转换成 JSON 数据包。</span><span class="sxs-lookup"><span data-stu-id="358cb-248">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON packet.</span></span> <span data-ttu-id="358cb-249">构造响应数据包后，将内容类型设置为 `application/json`，并编写字符串。</span><span class="sxs-lookup"><span data-stu-id="358cb-249">After you've constructed the response packet, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="358cb-250">应用程序现在可以运行并返回随机天气预报。</span><span class="sxs-lookup"><span data-stu-id="358cb-250">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="358cb-251">生成 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="358cb-251">Build a Docker image</span></span>

<span data-ttu-id="358cb-252">最后一项任务是在 Docker 中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="358cb-252">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="358cb-253">我们将创建一个 Docker 容器，用于运行表示此应用程序的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="358cb-253">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="358cb-254">***Docker 映像***是定义应用程序运行环境的文件。</span><span class="sxs-lookup"><span data-stu-id="358cb-254">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="358cb-255">***Docker 容器***表示 Docker 映像的正在运行实例。</span><span class="sxs-lookup"><span data-stu-id="358cb-255">A ***Docker Container*** represents a running instance of a Docker image.</span></span>

<span data-ttu-id="358cb-256">通过类推，可以将 *Docker 映像*视为*类*，将 *Docker 容器*视为对象或此类的实例。</span><span class="sxs-lookup"><span data-stu-id="358cb-256">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="358cb-257">ASP.NET 模板创建的 Dockerfile 可供我们自行使用。</span><span class="sxs-lookup"><span data-stu-id="358cb-257">The Dockerfile created by the ASP.NET template will serve for our purposes.</span></span> <span data-ttu-id="358cb-258">我们先来介绍一下此文件的内容。</span><span class="sxs-lookup"><span data-stu-id="358cb-258">Let's go over its contents.</span></span>

<span data-ttu-id="358cb-259">第一行指定的是源映像：</span><span class="sxs-lookup"><span data-stu-id="358cb-259">The first line specifies the source image:</span></span>

```
FROM microsoft/dotnet:1.1-sdk-msbuild
```

<span data-ttu-id="358cb-260">通过 Docker，可以根据源模板配置计算机映像。</span><span class="sxs-lookup"><span data-stu-id="358cb-260">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="358cb-261">也就是说，开始时并不需要提供所有计算机参数，只需提供全部更改。</span><span class="sxs-lookup"><span data-stu-id="358cb-261">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="358cb-262">此处所说的更改包括我们的应用程序在内。</span><span class="sxs-lookup"><span data-stu-id="358cb-262">The changes here will be to include our application.</span></span>

<span data-ttu-id="358cb-263">在这第一个示例中，我们将使用 .NET 映像的 `1.1-sdk-msbuild` 版本。</span><span class="sxs-lookup"><span data-stu-id="358cb-263">In this first sample, we'll use the `1.1-sdk-msbuild` version of the dotnet image.</span></span> <span data-ttu-id="358cb-264">这是创建有效 Docker 环境的最简单方式。</span><span class="sxs-lookup"><span data-stu-id="358cb-264">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="358cb-265">此映像包括 .NET Core 运行时和 .NET SDK。</span><span class="sxs-lookup"><span data-stu-id="358cb-265">This image include the dotnet core runtime, and the dotnet SDK.</span></span> <span data-ttu-id="358cb-266">这样更便于着手生成映像，但创建的映像会比较大。</span><span class="sxs-lookup"><span data-stu-id="358cb-266">That makes it easier to get started and build, but does create a larger image.</span></span>

<span data-ttu-id="358cb-267">接下来的五行代码用于设置并生成应用程序：</span><span class="sxs-lookup"><span data-stu-id="358cb-267">The next five lines setup and build your application:</span></span>

```
WORKDIR /app

# copy csproj and restore as distinct layers

COPY WeatherMicroservice.csproj .
RUN dotnet restore 

# copy and build everything else

COPY . .

# RUN dotnet restore
RUN dotnet publish -c Release -o out
```

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="358cb-268">这会将当前目录中的项目文件复制到 Docker VM 中，并还原所有包。</span><span class="sxs-lookup"><span data-stu-id="358cb-268">This will copy the project file from the  current directory to the Docker VM, and restore all the packages.</span></span> <span data-ttu-id="358cb-269">使用 .NET CLI 意味着 Docker 映像必须包含 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="358cb-269">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="358cb-270">完成上述操作之后，应用程序的其余部分会得到复制，然后 .NET 发布命令会生成并打包应用程序。</span><span class="sxs-lookup"><span data-stu-id="358cb-270">After that, the rest of your application gets copied, and the dotnet publish command builds and packages your application.</span></span>

<span data-ttu-id="358cb-271">此文件的最后一行代码用于运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="358cb-271">The final line of the file runs the application:</span></span>

```
ENTRYPOINT ["dotnet", "out/WeatherMicroservice.dll", "--server.urls", "http://0.0.0.0:5000"]
```

<span data-ttu-id="358cb-272">Dockerfile 最后一行代码中 `dotnet` 的 `--server.urls` 自变量引用此配置端口。</span><span class="sxs-lookup"><span data-stu-id="358cb-272">This configured port is referenced in the `--server.urls` argument to `dotnet` on the last  line of the Dockerfile.</span></span> <span data-ttu-id="358cb-273">`ENTRYPOINT` 命令用于指示 Docker 哪些命令和命令行选项启动了服务。</span><span class="sxs-lookup"><span data-stu-id="358cb-273">The `ENTRYPOINT` command informs Docker what command and command-line options start the service.</span></span> 

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="358cb-274">在容器中生成并运行映像</span><span class="sxs-lookup"><span data-stu-id="358cb-274">Building and running the image in a container.</span></span>

<span data-ttu-id="358cb-275">让我们在 Docker 容器中生成映像并运行服务。</span><span class="sxs-lookup"><span data-stu-id="358cb-275">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="358cb-276">不是要将本地目录中的所有文件都复制到映像中，</span><span class="sxs-lookup"><span data-stu-id="358cb-276">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="358cb-277">而是要在容器中生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="358cb-277">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="358cb-278">将创建 `.dockerignore` 文件来指定不要复制到映像中的目录。</span><span class="sxs-lookup"><span data-stu-id="358cb-278">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="358cb-279">你不想复制任何生成资产。</span><span class="sxs-lookup"><span data-stu-id="358cb-279">You don't want any of the build assets copied.</span></span> <span data-ttu-id="358cb-280">请在 `.dockerignore` 文件中指定生成和发布目录：</span><span class="sxs-lookup"><span data-stu-id="358cb-280">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="358cb-281">使用 `docker build` 命令生成映像。</span><span class="sxs-lookup"><span data-stu-id="358cb-281">You build the image using the `docker build` command.</span></span> <span data-ttu-id="358cb-282">从包含代码的目录运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="358cb-282">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="358cb-283">此命令将根据 Dockerfile 中的所有信息生成容器映像。</span><span class="sxs-lookup"><span data-stu-id="358cb-283">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="358cb-284">`-t` 自变量提供此容器映像的标记或名称。</span><span class="sxs-lookup"><span data-stu-id="358cb-284">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="358cb-285">在上面的命令行中，Docker 容器的标记是 `weather-microservice`。</span><span class="sxs-lookup"><span data-stu-id="358cb-285">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="358cb-286">此命令完成后，就生成了一个可用于运行新服务的容器。</span><span class="sxs-lookup"><span data-stu-id="358cb-286">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="358cb-287">运行以下命令，启动容器和服务：</span><span class="sxs-lookup"><span data-stu-id="358cb-287">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:5000 --name hello-docker weather-microservice
```

<span data-ttu-id="358cb-288">`-d` 选项表示运行从当前终端拆离出来的容器。</span><span class="sxs-lookup"><span data-stu-id="358cb-288">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="358cb-289">也就是说，终端中不会显示命令输出。</span><span class="sxs-lookup"><span data-stu-id="358cb-289">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="358cb-290">`-p` 选项指示服务和主机之间的端口映射。</span><span class="sxs-lookup"><span data-stu-id="358cb-290">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="358cb-291">即指应将端口 80 上的所有传入请求都转发到容器上的端口 5000。</span><span class="sxs-lookup"><span data-stu-id="358cb-291">Here it says that any incoming request on port 80 should be forwarded to port 5000 on the container.</span></span> <span data-ttu-id="358cb-292">在上面的 Dockerfile 中指定的命令行自变量中，使用 5000 匹配服务要侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="358cb-292">Using 5000 matches the port your service is listening on from the command line arguments specified in the Dockerfile above.</span></span> <span data-ttu-id="358cb-293">`--name` 自变量用于命名正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="358cb-293">The `--name` argument names your running container.</span></span> <span data-ttu-id="358cb-294">此名称可方便与容器结合使用。</span><span class="sxs-lookup"><span data-stu-id="358cb-294">It's a convenient name you can use to work with that container.</span></span> 

<span data-ttu-id="358cb-295">可以运行以下命令来确定映像能否正常运行：</span><span class="sxs-lookup"><span data-stu-id="358cb-295">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="358cb-296">如果容器能正常运行，那么正在运行的进程中就会有一行列出它来</span><span class="sxs-lookup"><span data-stu-id="358cb-296">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="358cb-297">（可能是唯一一行）。</span><span class="sxs-lookup"><span data-stu-id="358cb-297">(It may be the only one).</span></span>

<span data-ttu-id="358cb-298">可以打开浏览器并转到 localhost，然后指定经纬度，从而测试服务：</span><span class="sxs-lookup"><span data-stu-id="358cb-298">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="358cb-299">附加到正在运行的容器</span><span class="sxs-lookup"><span data-stu-id="358cb-299">Attaching to a running container</span></span>

<span data-ttu-id="358cb-300">在命令窗口中运行服务时，可以查看针对各个请求打印输出的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="358cb-300">When you ran your sevice in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="358cb-301">如果容器是在拆离模式下运行，则看不到此类信息。</span><span class="sxs-lookup"><span data-stu-id="358cb-301">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="358cb-302">使用 Docker 附加命令，可以将窗口附加到正在运行的容器，以便查看日志信息。</span><span class="sxs-lookup"><span data-stu-id="358cb-302">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="358cb-303">在命令窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="358cb-303">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="358cb-304">`--sig-proxy=false` 自变量表示 `Ctrl-C` 命令未发送到容器进程，而是停止运行 `docker attach` 命令。</span><span class="sxs-lookup"><span data-stu-id="358cb-304">The `--sig-proxy=false` argument means that `Ctrl-C` commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="358cb-305">最后的自变量是为 `docker run` 命令中的容器命名的名称。</span><span class="sxs-lookup"><span data-stu-id="358cb-305">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="358cb-306">还可以使用 Docker 分配的容器 ID 来引用任何容器。</span><span class="sxs-lookup"><span data-stu-id="358cb-306">You can also use the Docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="358cb-307">如果没有在 `docker run` 中命名容器，必须使用容器 ID。</span><span class="sxs-lookup"><span data-stu-id="358cb-307">If you didn't specify a name for your container in `docker run` you must use the container id.</span></span>

<span data-ttu-id="358cb-308">打开浏览器并转到服务。</span><span class="sxs-lookup"><span data-stu-id="358cb-308">Open a browser and navigate to your service.</span></span> <span data-ttu-id="358cb-309">将可以在命令窗口中查看附加的正在运行的容器生成的诊断消息。</span><span class="sxs-lookup"><span data-stu-id="358cb-309">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="358cb-310">按 `Ctrl-C` 可停止附加进程。</span><span class="sxs-lookup"><span data-stu-id="358cb-310">Press `Ctrl-C` to stop the attach process.</span></span>

<span data-ttu-id="358cb-311">使用完后，可以停止运行容器：</span><span class="sxs-lookup"><span data-stu-id="358cb-311">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="358cb-312">容器和映像仍可供重启。</span><span class="sxs-lookup"><span data-stu-id="358cb-312">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="358cb-313">若要从计算机中删除容器，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="358cb-313">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="358cb-314">若要从计算机中删除未使用的映像，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="358cb-314">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="358cb-315">结束语</span><span class="sxs-lookup"><span data-stu-id="358cb-315">Conclusion</span></span> 

<span data-ttu-id="358cb-316">在此教程中，你生成了 ASP.NET Core 微服务，并添加了一些简单的功能。</span><span class="sxs-lookup"><span data-stu-id="358cb-316">In this tutorial, you built an ASP.NET Core microservice, and added a few simple features.</span></span>

<span data-ttu-id="358cb-317">此外，你还生成了此服务的 Docker 容器映像，并在计算机上运行了相应的容器。</span><span class="sxs-lookup"><span data-stu-id="358cb-317">You built a Docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="358cb-318">最后，你还将终端窗口附加到了服务中，并查看服务生成的诊断消息。</span><span class="sxs-lookup"><span data-stu-id="358cb-318">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="358cb-319">与此同时，你还了解了多项 C# 语言功能的实际运用。</span><span class="sxs-lookup"><span data-stu-id="358cb-319">Along the way, you saw several features of the C# language in action.</span></span>
