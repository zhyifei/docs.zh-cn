---
title: 使用 .NET Core 创建 REST 客户端
description: 此教程将介绍 .NET Core 和 C# 语言的许多功能。
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 85a3c8e17e14db86786950380ba745ae286dccca
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115868"
---
# <a name="rest-client"></a><span data-ttu-id="629c7-103">REST 客户端</span><span class="sxs-lookup"><span data-stu-id="629c7-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="629c7-104">介绍</span><span class="sxs-lookup"><span data-stu-id="629c7-104">Introduction</span></span>

<span data-ttu-id="629c7-105">此教程将介绍 .NET Core 和 C# 语言的许多功能。</span><span class="sxs-lookup"><span data-stu-id="629c7-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="629c7-106">你将了解：</span><span class="sxs-lookup"><span data-stu-id="629c7-106">You’ll learn:</span></span>

* <span data-ttu-id="629c7-107">.NET Core 命令行接口 (CLI) 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="629c7-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
* <span data-ttu-id="629c7-108">C# 语言功能概述。</span><span class="sxs-lookup"><span data-stu-id="629c7-108">An overview of C# Language features.</span></span>
* <span data-ttu-id="629c7-109">如何使用 NuGet 管理依赖项</span><span class="sxs-lookup"><span data-stu-id="629c7-109">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="629c7-110">HTTP 通信</span><span class="sxs-lookup"><span data-stu-id="629c7-110">HTTP Communications</span></span>
* <span data-ttu-id="629c7-111">如何处理 JSON 信息</span><span class="sxs-lookup"><span data-stu-id="629c7-111">Processing JSON information</span></span>
* <span data-ttu-id="629c7-112">如何管理含特性的配置。</span><span class="sxs-lookup"><span data-stu-id="629c7-112">Managing configuration with Attributes.</span></span>

<span data-ttu-id="629c7-113">将生成一个应用程序，向 GitHub 上的 REST 服务发出 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="629c7-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="629c7-114">需要读取 JSON 格式的信息，并将相应的 JSON 数据包转换成 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="629c7-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="629c7-115">最后将了解如何使用 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="629c7-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="629c7-116">此教程中介绍了多项功能。</span><span class="sxs-lookup"><span data-stu-id="629c7-116">There are many features in this tutorial.</span></span> <span data-ttu-id="629c7-117">我们将逐个生成这些功能。</span><span class="sxs-lookup"><span data-stu-id="629c7-117">Let’s build them one by one.</span></span>

<span data-ttu-id="629c7-118">如果想要按照针对本主题的[最终示例](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)操作，可以下载它。</span><span class="sxs-lookup"><span data-stu-id="629c7-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="629c7-119">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="629c7-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="629c7-120">先决条件</span><span class="sxs-lookup"><span data-stu-id="629c7-120">Prerequisites</span></span>

<span data-ttu-id="629c7-121">必须将计算机设置为运行 .Net Core。</span><span class="sxs-lookup"><span data-stu-id="629c7-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="629c7-122">有关安装说明，请访问 [.NET Core 下载](https://dotnet.microsoft.com/download)页。</span><span class="sxs-lookup"><span data-stu-id="629c7-122">You can find the installation instructions on the [.NET Core Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="629c7-123">可以在 Windows、Linux、macOS 或 Docker 容器中运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="629c7-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="629c7-124">必须安装常用的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="629c7-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="629c7-125">在以下说明中，我们使用的是开放源代码跨平台编辑器 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="629c7-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="629c7-126">不过，你可以使用习惯使用的任意工具。</span><span class="sxs-lookup"><span data-stu-id="629c7-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="629c7-127">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="629c7-127">Create the Application</span></span>

<span data-ttu-id="629c7-128">第一步是新建应用程序。</span><span class="sxs-lookup"><span data-stu-id="629c7-128">The first step is to create a new application.</span></span> <span data-ttu-id="629c7-129">打开命令提示符，然后新建应用程序的目录。</span><span class="sxs-lookup"><span data-stu-id="629c7-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="629c7-130">将新建的目录设为当前目录。</span><span class="sxs-lookup"><span data-stu-id="629c7-130">Make that the current directory.</span></span> <span data-ttu-id="629c7-131">在控制台窗口中输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="629c7-131">Enter the following command in a console window:</span></span>

```dotnetcli
dotnet new console --name WebApiClient
```

<span data-ttu-id="629c7-132">这将为基本的“Hello World”应用程序创建起始文件。</span><span class="sxs-lookup"><span data-stu-id="629c7-132">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="629c7-133">项目名称为“WebApiClient”。</span><span class="sxs-lookup"><span data-stu-id="629c7-133">The project name is "WebApiClient".</span></span> <span data-ttu-id="629c7-134">这是一个新项目，因此没有部署任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="629c7-134">As this is a new project, none of the dependencies are in place.</span></span> <span data-ttu-id="629c7-135">第一次运行时将下载 .NET Core 框架、安装开发证书并运行 NuGet 包管理器来还原缺少的依赖项。</span><span class="sxs-lookup"><span data-stu-id="629c7-135">The first run will download the .NET Core framework, install a development certificate, and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="629c7-136">在开始修改之前，在命令提示符中键入 `dotnet run`（[参见注释](#dotnet-restore-note)）以运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="629c7-136">Before you start making modifications, type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="629c7-137">如果环境缺少依赖项，则 `dotnet run` 会自动执行 `dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="629c7-137">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="629c7-138">如果需要重新生成应用程序，它还会执行 `dotnet build`。</span><span class="sxs-lookup"><span data-stu-id="629c7-138">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="629c7-139">初始设置完成后，只需在对项目有意义的情况下运行 `dotnet restore` 或 `dotnet build`。</span><span class="sxs-lookup"><span data-stu-id="629c7-139">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="629c7-140">添加新的依赖项</span><span class="sxs-lookup"><span data-stu-id="629c7-140">Adding New Dependencies</span></span>

<span data-ttu-id="629c7-141">.NET Core 的主要设计目标之一是最小化 .NET 安装的大小。</span><span class="sxs-lookup"><span data-stu-id="629c7-141">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="629c7-142">如果应用程序需要使用其他库来生成某些功能，请将这些依赖项添加到 C# 项目 (\*.csproj) 文件中。</span><span class="sxs-lookup"><span data-stu-id="629c7-142">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="629c7-143">对于我们的示例，将需要添加 `System.Runtime.Serialization.Json` 包，以便应用程序可以处理 JSON 响应。</span><span class="sxs-lookup"><span data-stu-id="629c7-143">For our example, you'll need to add the `System.Runtime.Serialization.Json` package, so your application can process JSON responses.</span></span>

<span data-ttu-id="629c7-144">你将需要此应用程序的 `System.Runtime.Serialization.Json` 包。</span><span class="sxs-lookup"><span data-stu-id="629c7-144">You'll need the `System.Runtime.Serialization.Json` package for this application.</span></span> <span data-ttu-id="629c7-145">通过运行以下 [.NET CLI](../../core/tools/dotnet-add-package.md) 命令，将其添加到项目：</span><span class="sxs-lookup"><span data-stu-id="629c7-145">Add it to your project by running the following [.NET CLI](../../core/tools/dotnet-add-package.md) command:</span></span>

```console
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a><span data-ttu-id="629c7-146">发出 Web 请求</span><span class="sxs-lookup"><span data-stu-id="629c7-146">Making Web Requests</span></span>

<span data-ttu-id="629c7-147">现在，可以开始检索 Web 数据了。</span><span class="sxs-lookup"><span data-stu-id="629c7-147">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="629c7-148">在此应用程序中，需要读取 [GitHub API](https://developer.github.com/v3/) 返回的信息。</span><span class="sxs-lookup"><span data-stu-id="629c7-148">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="629c7-149">让我们在 [.NET Foundation](https://www.dotnetfoundation.org/) 的保护下读取项目信息。</span><span class="sxs-lookup"><span data-stu-id="629c7-149">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="629c7-150">先向 GitHub API 发出请求，以检索项目信息。</span><span class="sxs-lookup"><span data-stu-id="629c7-150">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="629c7-151">将使用终结点 <https://api.github.com/orgs/dotnet/repos>。</span><span class="sxs-lookup"><span data-stu-id="629c7-151">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="629c7-152">由于要检索这些项目的所有信息，因此将发出 HTTP GET 请求。</span><span class="sxs-lookup"><span data-stu-id="629c7-152">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="629c7-153">此外，浏览器也使用 HTTP GET 请求，以便你可以将相应的 URL 粘贴到浏览器，查看将要收到并处理的信息。</span><span class="sxs-lookup"><span data-stu-id="629c7-153">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="629c7-154">使用 <xref:System.Net.Http.HttpClient> 类发出 Web 请求。</span><span class="sxs-lookup"><span data-stu-id="629c7-154">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="629c7-155">与所有新式 .NET API 一样，<xref:System.Net.Http.HttpClient> 只支持长时间运行 API 的异步方法。</span><span class="sxs-lookup"><span data-stu-id="629c7-155">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="629c7-156">从异步方法入手。</span><span class="sxs-lookup"><span data-stu-id="629c7-156">Start by making an async method.</span></span> <span data-ttu-id="629c7-157">将一边填充实现代码，一边生成应用程序功能。</span><span class="sxs-lookup"><span data-stu-id="629c7-157">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="629c7-158">首先，打开项目目录中的 `program.cs` 文件，然后向 `Program` 类添加以下方法：</span><span class="sxs-lookup"><span data-stu-id="629c7-158">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="629c7-159">需要在 `Main` 方法的最上面添加 `using` 语句，以便 C# 编译器能够识别 <xref:System.Threading.Tasks.Task> 类型：</span><span class="sxs-lookup"><span data-stu-id="629c7-159">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="629c7-160">如果此时生成项目，将会看到系统针对此方法生成的警告，因为其中不含任何 `await` 运算符，将以同步方式运行。</span><span class="sxs-lookup"><span data-stu-id="629c7-160">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="629c7-161">暂且忽略此警告；将在填充方法时添加 `await` 运算符。</span><span class="sxs-lookup"><span data-stu-id="629c7-161">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="629c7-162">接下来，将 `namespace` 语句中定义的命名空间从默认名称 `ConsoleApp` 重命名为 `WebAPIClient`。</span><span class="sxs-lookup"><span data-stu-id="629c7-162">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="629c7-163">我们稍后将在此命名空间中定义 `repo` 类。</span><span class="sxs-lookup"><span data-stu-id="629c7-163">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="629c7-164">接下来，将 `Main` 方法更新为调用此方法。</span><span class="sxs-lookup"><span data-stu-id="629c7-164">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="629c7-165">`ProcessRepositories` 方法会返回一个任务，不得在此任务完成前退出程序。</span><span class="sxs-lookup"><span data-stu-id="629c7-165">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="629c7-166">因此，必须更改 `Main` 的签名。</span><span class="sxs-lookup"><span data-stu-id="629c7-166">Therefore, you must change the signature of `Main`.</span></span> <span data-ttu-id="629c7-167">添加 `async` 修饰符，并将返回类型更改为 `Task`。</span><span class="sxs-lookup"><span data-stu-id="629c7-167">Add the `async` modifier, and change the return type to `Task`.</span></span> <span data-ttu-id="629c7-168">然后，在方法的主体中，添加对 `ProcessRepositories` 的调用。</span><span class="sxs-lookup"><span data-stu-id="629c7-168">Then, in the body of the method, add a call to `ProcessRepositories`.</span></span> <span data-ttu-id="629c7-169">在添加对该方法的调用时添加 `await` 关键字：</span><span class="sxs-lookup"><span data-stu-id="629c7-169">Add the `await` keyword when to that method call:</span></span>

```csharp
static Task Main(string[] args)
{
    await ProcessRepositories();
}
```

<span data-ttu-id="629c7-170">现在，生成了一个不执行任何操作但具备异步功能的程序。</span><span class="sxs-lookup"><span data-stu-id="629c7-170">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="629c7-171">现在进行改进。</span><span class="sxs-lookup"><span data-stu-id="629c7-171">Let's improve it.</span></span>

<span data-ttu-id="629c7-172">首先需要一个能从 Web 检索数据的对象；可使用 <xref:System.Net.Http.HttpClient> 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="629c7-172">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="629c7-173">此对象负责处理请求和响应。</span><span class="sxs-lookup"><span data-stu-id="629c7-173">This object handles the request and the responses.</span></span> <span data-ttu-id="629c7-174">在 Program.cs 文件内的 `Program` 类中初始化该类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="629c7-174">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static Task Main(string[] args)
        {
            //...
        }
    }
}
```

<span data-ttu-id="629c7-175">让我们回到 `ProcessRepositories` 方法，并填充它的第一个版本：</span><span class="sxs-lookup"><span data-stu-id="629c7-175">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="629c7-176">此外，为了让编译能够顺利进行，还需要在文件的最上面添加两个新的 using 语句：</span><span class="sxs-lookup"><span data-stu-id="629c7-176">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="629c7-177">第一个版本发出 Web 请求来读取 .NET Foundation 组织下的所有存储库列表。</span><span class="sxs-lookup"><span data-stu-id="629c7-177">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="629c7-178">（.NET Foundation 的 gitHub ID 为“dotnet”）。</span><span class="sxs-lookup"><span data-stu-id="629c7-178">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="629c7-179">前几行代码针对该请求设置 <xref:System.Net.Http.HttpClient>。</span><span class="sxs-lookup"><span data-stu-id="629c7-179">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="629c7-180">在第一行中，它被配置为接受 GitHub JSON 响应。</span><span class="sxs-lookup"><span data-stu-id="629c7-180">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="629c7-181">此格式仅为 JSON。</span><span class="sxs-lookup"><span data-stu-id="629c7-181">This format is simply JSON.</span></span> <span data-ttu-id="629c7-182">下一代码行将用户代理标头添加到此对象发出的所有请求中。</span><span class="sxs-lookup"><span data-stu-id="629c7-182">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="629c7-183">这两个标头均由 GitHub 服务器代码进行检查，必须使用它们，才能检索 GitHub 中的信息。</span><span class="sxs-lookup"><span data-stu-id="629c7-183">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="629c7-184">配置 <xref:System.Net.Http.HttpClient> 后，发出 Web 请求并检索响应。</span><span class="sxs-lookup"><span data-stu-id="629c7-184">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="629c7-185">在此第一个版本中，将使用 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> 便捷方法。</span><span class="sxs-lookup"><span data-stu-id="629c7-185">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="629c7-186">此便捷方法先执行发出 Web 请求的任务，然后当返回请求时读取响应流，并从流中提取内容。</span><span class="sxs-lookup"><span data-stu-id="629c7-186">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="629c7-187">响应正文以 <xref:System.String> 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="629c7-187">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="629c7-188">此字符串在任务完成时可用。</span><span class="sxs-lookup"><span data-stu-id="629c7-188">The string is available when the task completes.</span></span>

<span data-ttu-id="629c7-189">此方法的最后两行代码用于等待任务完成，然后在控制台中打印输出响应。</span><span class="sxs-lookup"><span data-stu-id="629c7-189">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="629c7-190">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="629c7-190">Build the app, and run it.</span></span> <span data-ttu-id="629c7-191">此时，生成警告不再显示，因为 `ProcessRepositories` 现在的确包含 `await` 运算符。</span><span class="sxs-lookup"><span data-stu-id="629c7-191">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="629c7-192">将看到很长的 JSON 格式文本。</span><span class="sxs-lookup"><span data-stu-id="629c7-192">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="629c7-193">处理 JSON 结果</span><span class="sxs-lookup"><span data-stu-id="629c7-193">Processing the JSON Result</span></span>

<span data-ttu-id="629c7-194">此时，你已编写用于检索来自 Web 服务器的响应，并显示响应文本的代码。</span><span class="sxs-lookup"><span data-stu-id="629c7-194">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="629c7-195">接下来，让我们将相应的 JSON 响应转换成 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="629c7-195">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="629c7-196"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> 类将对象序列化为 JSON，并将 JSON 反序列化为对象。</span><span class="sxs-lookup"><span data-stu-id="629c7-196">The <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> class serializes objects to JSON and deserializes JSON into objects.</span></span> <span data-ttu-id="629c7-197">首先定义一个类，用于表示从 GitHub API 返回的 `repo` JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="629c7-197">Start by defining a class to represent the `repo` JSON object returned from the GitHub API:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; };
    }
}
```

<span data-ttu-id="629c7-198">将以上代码添加到“repo.cs”新文件中。</span><span class="sxs-lookup"><span data-stu-id="629c7-198">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="629c7-199">此版本的类表示处理 JSON 数据的最简单路径。</span><span class="sxs-lookup"><span data-stu-id="629c7-199">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="629c7-200">类名和成员名称与 JSON 数据包中使用的名称一致，而不是遵循以下 C# 约定。</span><span class="sxs-lookup"><span data-stu-id="629c7-200">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="629c7-201">稍后将通过提供某些配置特性进行修复。</span><span class="sxs-lookup"><span data-stu-id="629c7-201">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="629c7-202">此类展示了 JSON 序列化和反序列化的另一个重要功能：并非 JSON 数据包中的所有字段都属于此类。</span><span class="sxs-lookup"><span data-stu-id="629c7-202">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="629c7-203">JSON 序列化程序将忽略所使用的类类型未包含的信息。</span><span class="sxs-lookup"><span data-stu-id="629c7-203">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="629c7-204">借助此功能，可更轻松地创建仅处理一部分 JSON 数据包字段的类型。</span><span class="sxs-lookup"><span data-stu-id="629c7-204">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="629c7-205">至此，你已创建类型，让我们来进行反序列化吧。</span><span class="sxs-lookup"><span data-stu-id="629c7-205">Now that you've created the type, let's deserialize it.</span></span> 

<span data-ttu-id="629c7-206">接下来，使用序列化程序将 JSON 转换成 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="629c7-206">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="629c7-207">使用以下三行代码替换 `ProcessRepositories` 方法中对 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> 的调用：</span><span class="sxs-lookup"><span data-stu-id="629c7-207">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following three lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

<span data-ttu-id="629c7-208">你使用的是新命名空间，因此，还需要将其添加到文件顶部：</span><span class="sxs-lookup"><span data-stu-id="629c7-208">You're using a new namespace, so you'll need to add it at the top of the file as well:</span></span>

```csharp
using System.Text.Json;
```

<span data-ttu-id="629c7-209">请注意，现使用 <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)>，而不是 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>。</span><span class="sxs-lookup"><span data-stu-id="629c7-209">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="629c7-210">序列化程序使用流（而不是字符串）作为其源。</span><span class="sxs-lookup"><span data-stu-id="629c7-210">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="629c7-211">让我们来看看前面第二行代码段中所使用的多项 C# 语言功能。</span><span class="sxs-lookup"><span data-stu-id="629c7-211">Let's explain a couple features of the C# language that are being used in the second line of the preceding code snippet.</span></span> <span data-ttu-id="629c7-212"><xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> 的第一个自变量是 `await` 表达式。</span><span class="sxs-lookup"><span data-stu-id="629c7-212">The first argument to <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> is an `await` expression.</span></span> <span data-ttu-id="629c7-213">（其他两个参数为可选，并在代码段中省略。）Await 表达式可以出现在代码中的几乎任何位置，尽管到目前为止，你只在赋值语句中看到过它们。</span><span class="sxs-lookup"><span data-stu-id="629c7-213">(The other two parameters are optional and are omitted in the code snippet.) Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span> <span data-ttu-id="629c7-214">`Deserialize` 方法为泛型  ，这意味着必须为应从 JSON 文本创建的对象的类型提供类型参数。</span><span class="sxs-lookup"><span data-stu-id="629c7-214">The `Deserialize` method is *generic*, which means you must supply type arguments for what kind of objects should be created from the JSON text.</span></span> <span data-ttu-id="629c7-215">在此示例中，你要反序列化到 `List<Repository>`，这是另一个泛型对象，即 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="629c7-215">In this example, you're deserializing to a `List<Repository>`, which is another generic object, the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="629c7-216">`List<>` 类存储对象的集合。</span><span class="sxs-lookup"><span data-stu-id="629c7-216">The `List<>` class stores a collection of objects.</span></span> <span data-ttu-id="629c7-217">类型参数声明存储在 `List<>` 中的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="629c7-217">The type argument declares the type of objects stored in the `List<>`.</span></span> <span data-ttu-id="629c7-218">JSON 文本表示存储库对象的集合，因此类型参数为 `Repository`。</span><span class="sxs-lookup"><span data-stu-id="629c7-218">The JSON text represents a collection of repo objects, so the type argument is `Repository`.</span></span>

<span data-ttu-id="629c7-219">即将完成此部分的操作。</span><span class="sxs-lookup"><span data-stu-id="629c7-219">You're almost done with this section.</span></span> <span data-ttu-id="629c7-220">至此，你已将 JSON 数据转换成 C# 对象，让我们来显示每个存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="629c7-220">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="629c7-221">将以下代码行：</span><span class="sxs-lookup"><span data-stu-id="629c7-221">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="629c7-222">替换为：</span><span class="sxs-lookup"><span data-stu-id="629c7-222">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="629c7-223">编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="629c7-223">Compile and run the application.</span></span> <span data-ttu-id="629c7-224">将打印输出属于 .NET Foundation 的存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="629c7-224">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="629c7-225">控制序列化</span><span class="sxs-lookup"><span data-stu-id="629c7-225">Controlling Serialization</span></span>

<span data-ttu-id="629c7-226">在添加更多功能之前，让我们通过使用 `[JsonPropertyName]` 特性来处理 `name` 属性。</span><span class="sxs-lookup"><span data-stu-id="629c7-226">Before you add more features, let's address the `name` property by using the `[JsonPropertyName]` attribute.</span></span> <span data-ttu-id="629c7-227">对 repo.cs 中的 `name` 字段声明执行以下更改：</span><span class="sxs-lookup"><span data-stu-id="629c7-227">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

<span data-ttu-id="629c7-228">此更改意味着需要更改用于在 program.cs 中写入每个存储库名称的代码：</span><span class="sxs-lookup"><span data-stu-id="629c7-228">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="629c7-229">执行 `dotnet run`，以确保生成正确映射。</span><span class="sxs-lookup"><span data-stu-id="629c7-229">Execute `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="629c7-230">应能看到与之前一样的输出。</span><span class="sxs-lookup"><span data-stu-id="629c7-230">You should see the same output as before.</span></span>

<span data-ttu-id="629c7-231">让我们在添加新功能前执行另一项更改。</span><span class="sxs-lookup"><span data-stu-id="629c7-231">Let's make one more change before adding new features.</span></span> <span data-ttu-id="629c7-232">`ProcessRepositories` 方法可以执行异步工作，并返回一组存储库。</span><span class="sxs-lookup"><span data-stu-id="629c7-232">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="629c7-233">我们将使用此方法返回 `List<Repository>`，并将用于写入信息的代码移到 `Main` 方法中。</span><span class="sxs-lookup"><span data-stu-id="629c7-233">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="629c7-234">更改 `ProcessRepositories` 的签名，以返回可生成 `Repository` 对象列表的任务：</span><span class="sxs-lookup"><span data-stu-id="629c7-234">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="629c7-235">然后，在处理 JSON 响应后仅返回存储库：</span><span class="sxs-lookup"><span data-stu-id="629c7-235">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="629c7-236">编译器将生成返回内容的 `Task<T>` 对象，因为你已将此方法标记为 `async`。</span><span class="sxs-lookup"><span data-stu-id="629c7-236">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="629c7-237">然后，我们将把 `Main` 方法修改为，捕获这些结果并将每个存储库名称写入控制台。</span><span class="sxs-lookup"><span data-stu-id="629c7-237">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="629c7-238">现在，`Main` 方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="629c7-238">Your `Main` method now looks like this:</span></span>

```csharp
public static Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a><span data-ttu-id="629c7-239">读取详细信息</span><span class="sxs-lookup"><span data-stu-id="629c7-239">Reading More Information</span></span>

<span data-ttu-id="629c7-240">最后，让我们来处理 GitHub API 发送的 JSON 数据包中的其他一些属性。</span><span class="sxs-lookup"><span data-stu-id="629c7-240">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="629c7-241">虽然你不想面面俱到，但添加其他一些属性将展示更多的 C# 语言功能。</span><span class="sxs-lookup"><span data-stu-id="629c7-241">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="629c7-242">首先，将其他一些简单类型添加到 `Repository` 类定义中。</span><span class="sxs-lookup"><span data-stu-id="629c7-242">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="629c7-243">将这些属性添加到此类：</span><span class="sxs-lookup"><span data-stu-id="629c7-243">Add these properties to that class:</span></span>

```csharp
[JsonPropertyName(Name="description")]
public string Description { get; set; }

[JsonPropertyName(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName(Name="homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="629c7-244">这些属性内置转换功能，可从字符串类型（即 JSON 数据包所含）转换成目标类型。</span><span class="sxs-lookup"><span data-stu-id="629c7-244">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="629c7-245">你可能是刚开始接触 <xref:System.Uri> 类型。</span><span class="sxs-lookup"><span data-stu-id="629c7-245">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="629c7-246">它代表 URI（或在此示例中，代表 URL）。</span><span class="sxs-lookup"><span data-stu-id="629c7-246">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="629c7-247">在有 `Uri` 和 `int` 类型的情况下，如果 JSON 数据包内的数据未转换成目标类型，那么序列化操作将会抛出异常。</span><span class="sxs-lookup"><span data-stu-id="629c7-247">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="629c7-248">添加这些元素后，将 `Main` 方法更新为显示它们：</span><span class="sxs-lookup"><span data-stu-id="629c7-248">Once you've added these, update the `Main` method to display those elements:</span></span>

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```

<span data-ttu-id="629c7-249">最后一步，让我们添加最后一次推送操作的信息。</span><span class="sxs-lookup"><span data-stu-id="629c7-249">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="629c7-250">此信息按如下方式在 JSON 响应中进行格式化：</span><span class="sxs-lookup"><span data-stu-id="629c7-250">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="629c7-251">此格式不符合任何标准 .NET <xref:System.DateTime> 格式。</span><span class="sxs-lookup"><span data-stu-id="629c7-251">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="629c7-252">因此，需要编写一个自定义转换方法。</span><span class="sxs-lookup"><span data-stu-id="629c7-252">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="629c7-253">你可能也不希望向 `Repository` 类的用户公开原始字符串。</span><span class="sxs-lookup"><span data-stu-id="629c7-253">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="629c7-254">特性还有助于控制此情况。</span><span class="sxs-lookup"><span data-stu-id="629c7-254">Attributes can help control that as well.</span></span> <span data-ttu-id="629c7-255">首先，定义一个 `public` 属性，该属性将保存 `Repository` 类中日期和时间的字符串表示形式，并定义一个 `LastPush` `readonly` 属性，该属性返回表示返回日期的格式化字符串：</span><span class="sxs-lookup"><span data-stu-id="629c7-255">First, define a `public` property that will hold the string representation of the date and time in your `Repository` class and a `LastPush` `readonly` property that returns a formatted string that represents the returned date:</span></span>

```csharp
[JsonPropertyName(Name="pushed_at")]
public string JsonDate { get; set; }

public DateTime LastPush =>
    DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
```

<span data-ttu-id="629c7-256">让我们来看一下刚定义的新构造。</span><span class="sxs-lookup"><span data-stu-id="629c7-256">Let's go over the new constructs we just defined.</span></span> <span data-ttu-id="629c7-257">`LastPush` 属性使用 `get` 访问器的 expression-bodied member  进行定义。</span><span class="sxs-lookup"><span data-stu-id="629c7-257">The `LastPush` property is defined using an *expression-bodied member* for the `get` accessor.</span></span> <span data-ttu-id="629c7-258">不存在 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="629c7-258">There is no `set` accessor.</span></span> <span data-ttu-id="629c7-259">省略 `set` 访问器就是在 C# 中定义只读  属性的方式。</span><span class="sxs-lookup"><span data-stu-id="629c7-259">Omitting the `set` accessor is how you define a *read-only* property in C#.</span></span> <span data-ttu-id="629c7-260">（是的，可以在 C# 中创建*只写*属性，但属性值受限。）<xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> 方法分析字符串，并使用提供的日期格式创建 <xref:System.DateTime> 对象，然后使用 `CultureInfo` 对象将其他元数据添加到 `DateTime` 中。</span><span class="sxs-lookup"><span data-stu-id="629c7-260">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="629c7-261">如果分析操作失败，那么属性访问器会抛出异常。</span><span class="sxs-lookup"><span data-stu-id="629c7-261">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="629c7-262">若要使用 <xref:System.Globalization.CultureInfo.InvariantCulture> ，需要将 <xref:System.Globalization> 命名空间添加到 `repo.cs` 中的 `using` 语句：</span><span class="sxs-lookup"><span data-stu-id="629c7-262">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="629c7-263">最后，在控制台中再添加一个输出语句，然后就可以再次生成并运行此应用程序：</span><span class="sxs-lookup"><span data-stu-id="629c7-263">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="629c7-264">你的版本现在应与[已完成的示例](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)匹配。</span><span class="sxs-lookup"><span data-stu-id="629c7-264">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="629c7-265">结束语</span><span class="sxs-lookup"><span data-stu-id="629c7-265">Conclusion</span></span>

<span data-ttu-id="629c7-266">此教程介绍了如何发出 Web 请求、分析结果，以及如何显示这些结果的属性。</span><span class="sxs-lookup"><span data-stu-id="629c7-266">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="629c7-267">你也已经在项目中将新的包添加为依赖项，</span><span class="sxs-lookup"><span data-stu-id="629c7-267">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="629c7-268">并已了解一些支持面向对象的技术的 C# 语言功能。</span><span class="sxs-lookup"><span data-stu-id="629c7-268">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
