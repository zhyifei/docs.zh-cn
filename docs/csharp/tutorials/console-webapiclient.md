---
title: 使用 .NET Core 创建 REST 客户端
description: 此教程将介绍 .NET Core 和 C# 语言的许多功能。
ms.date: 03/06/2017
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: f6e3371a72810b30f804169be4025360aa10c477
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063882"
---
# <a name="rest-client"></a><span data-ttu-id="bd3e5-103">REST 客户端</span><span class="sxs-lookup"><span data-stu-id="bd3e5-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="bd3e5-104">介绍</span><span class="sxs-lookup"><span data-stu-id="bd3e5-104">Introduction</span></span>

<span data-ttu-id="bd3e5-105">此教程将介绍 .NET Core 和 C# 语言的许多功能。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="bd3e5-106">你将了解：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-106">You’ll learn:</span></span>

* <span data-ttu-id="bd3e5-107">.NET Core 命令行接口 (CLI) 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
* <span data-ttu-id="bd3e5-108">C# 语言功能概述。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-108">An overview of C# Language features.</span></span>
* <span data-ttu-id="bd3e5-109">如何使用 NuGet 管理依赖项</span><span class="sxs-lookup"><span data-stu-id="bd3e5-109">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="bd3e5-110">HTTP 通信</span><span class="sxs-lookup"><span data-stu-id="bd3e5-110">HTTP Communications</span></span>
* <span data-ttu-id="bd3e5-111">如何处理 JSON 信息</span><span class="sxs-lookup"><span data-stu-id="bd3e5-111">Processing JSON information</span></span>
* <span data-ttu-id="bd3e5-112">如何管理含特性的配置。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-112">Managing configuration with Attributes.</span></span>

<span data-ttu-id="bd3e5-113">将生成一个应用程序，向 GitHub 上的 REST 服务发出 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="bd3e5-114">需要读取 JSON 格式的信息，并将相应的 JSON 数据包转换成 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="bd3e5-115">最后将了解如何使用 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="bd3e5-116">此教程将介绍许多功能。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-116">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="bd3e5-117">我们将逐个生成这些功能。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-117">Let’s build them one by one.</span></span>

<span data-ttu-id="bd3e5-118">如果想要按照针对本主题的[最终示例](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)操作，可以下载它。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="bd3e5-119">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bd3e5-120">系统必备</span><span class="sxs-lookup"><span data-stu-id="bd3e5-120">Prerequisites</span></span>

<span data-ttu-id="bd3e5-121">必须将计算机设置为运行 .Net Core。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="bd3e5-122">有关安装说明，请访问 [.NET Core](https://www.microsoft.com/net/core) 页。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-122">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="bd3e5-123">可以在 Windows、Linux、macOS 或 Docker 容器中运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="bd3e5-124">必须安装常用的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="bd3e5-125">在以下说明中，我们使用的是开放源代码跨平台编辑器 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="bd3e5-126">不过，你可以使用习惯使用的任意工具。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="bd3e5-127">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="bd3e5-127">Create the Application</span></span>

<span data-ttu-id="bd3e5-128">第一步是新建应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-128">The first step is to create a new application.</span></span> <span data-ttu-id="bd3e5-129">打开命令提示符，然后新建应用程序的目录。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="bd3e5-130">将新建的目录设为当前目录。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-130">Make that the current directory.</span></span> <span data-ttu-id="bd3e5-131">在命令提示符处，键入命令 `dotnet new console`。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="bd3e5-132">这将为基本的“Hello World”应用程序创建起始文件。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-132">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="bd3e5-133">因为这是新项目，所有没有任何依赖项，第一次运行时将下载 .NET Core 框架、安装开发证书并运行 NuGet 包管理器来还原缺少的依赖项。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-133">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework, install a development certificate and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="bd3e5-134">在开始修改之前，在命令提示符中键入 `dotnet run`（[参见注释](#dotnet-restore-note)）以运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-134">Before you start making modifications, type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="bd3e5-135">如果环境缺少依赖项，则 `dotnet run` 会自动执行 `dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-135">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="bd3e5-136">如果需要重新生成应用程序，它还会执行 `dotnet build`。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-136">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="bd3e5-137">初始设置完成后，只需在对项目有意义的情况下运行 `dotnet restore` 或 `dotnet build`。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-137">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="bd3e5-138">添加新的依赖项</span><span class="sxs-lookup"><span data-stu-id="bd3e5-138">Adding New Dependencies</span></span>

<span data-ttu-id="bd3e5-139">.NET Core 的主要设计目标之一是最小化 .NET 安装的大小。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-139">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="bd3e5-140">如果应用程序需要使用其他库来生成某些功能，请将这些依赖项添加到 C# 项目 (\*.csproj) 文件中。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-140">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="bd3e5-141">对于我们的示例，将需要添加 `System.Runtime.Serialization.Json` 包，以便应用程序可以处理 JSON 响应。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-141">For our example, you'll need to add the `System.Runtime.Serialization.Json` package so your application can process JSON responses.</span></span>

<span data-ttu-id="bd3e5-142">打开 `csproj` 项目文件。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-142">Open your `csproj` project file.</span></span> <span data-ttu-id="bd3e5-143">此文件的第一行应如下所示：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-143">The first line of the file should appear as:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

<span data-ttu-id="bd3e5-144">在这行后面紧接着添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-144">Add the following immediately after this line:</span></span>

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup>
```

<span data-ttu-id="bd3e5-145">大多数代码编辑器都会完成这些库的不同版本。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-145">Most code editors will provide completion for different versions of these libraries.</span></span> <span data-ttu-id="bd3e5-146">通常需要使用所添加的任意包的最新版本。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-146">You'll usually want to use the latest version of any package that you add.</span></span> <span data-ttu-id="bd3e5-147">不过，请务必确保所有包的版本均一致，且与 .NET Core 应用程序框架的版本一致。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-147">However, it is important to make sure that the versions of all packages match, and that they also match the version of the .NET Core Application framework.</span></span>

<span data-ttu-id="bd3e5-148">完成这些更改后，执行 `dotnet restore`（[参见注释](#dotnet-restore-note)），以便在系统上安装包。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-148">After you've made these changes, execute `dotnet restore` ([see note](#dotnet-restore-note)) so that the package is installed on your system.</span></span>

## <a name="making-web-requests"></a><span data-ttu-id="bd3e5-149">发出 Web 请求</span><span class="sxs-lookup"><span data-stu-id="bd3e5-149">Making Web Requests</span></span>

<span data-ttu-id="bd3e5-150">现在，可以开始检索 Web 数据了。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-150">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="bd3e5-151">在此应用程序中，需要读取 [GitHub API](https://developer.github.com/v3/) 返回的信息。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-151">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="bd3e5-152">让我们在 [.NET Foundation](https://www.dotnetfoundation.org/) 的保护下读取项目信息。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-152">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="bd3e5-153">先向 GitHub API 发出请求，以检索项目信息。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-153">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="bd3e5-154">将使用终结点 <https://api.github.com/orgs/dotnet/repos>。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-154">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="bd3e5-155">由于要检索这些项目的所有信息，因此将发出 HTTP GET 请求。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-155">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="bd3e5-156">此外，浏览器也使用 HTTP GET 请求，以便你可以将相应的 URL 粘贴到浏览器，查看将要收到并处理的信息。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-156">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="bd3e5-157">使用 <xref:System.Net.Http.HttpClient> 类发出 Web 请求。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-157">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="bd3e5-158">与所有新式 .NET API 一样，<xref:System.Net.Http.HttpClient> 只支持长时间运行 API 的异步方法。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-158">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="bd3e5-159">从异步方法入手。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-159">Start by making an async method.</span></span> <span data-ttu-id="bd3e5-160">将一边填充实现代码，一边生成应用程序功能。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-160">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="bd3e5-161">首先，打开项目目录中的 `program.cs` 文件，然后向 `Program` 类添加以下方法：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-161">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="bd3e5-162">需要在 `Main` 方法的最上面添加 `using` 语句，以便 C# 编译器能够识别 <xref:System.Threading.Tasks.Task> 类型：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-162">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="bd3e5-163">如果此时生成项目，将会看到系统针对此方法生成的警告，因为其中不含任何 `await` 运算符，将以同步方式运行。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-163">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="bd3e5-164">暂且忽略此警告；将在填充方法时添加 `await` 运算符。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-164">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="bd3e5-165">接下来，将 `namespace` 语句中定义的命名空间从默认名称 `ConsoleApp` 重命名为 `WebAPIClient`。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-165">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="bd3e5-166">我们稍后将在此命名空间中定义 `repo` 类。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-166">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="bd3e5-167">接下来，将 `Main` 方法更新为调用此方法。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-167">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="bd3e5-168">`ProcessRepositories` 方法会返回一个任务，不得在此任务完成前退出程序。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-168">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="bd3e5-169">因此，必须使用 `Wait` 方法来阻止退出并等待任务完成：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-169">Therefore, you must use the `Wait` method to block and wait for the task to finish:</span></span>

```csharp
static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

<span data-ttu-id="bd3e5-170">现在，生成了一个不执行任何操作但具备异步功能的程序。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-170">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="bd3e5-171">现在进行改进。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-171">Let's improve it.</span></span>

<span data-ttu-id="bd3e5-172">首先需要一个能从 Web 检索数据的对象；可使用 <xref:System.Net.Http.HttpClient> 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-172">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="bd3e5-173">此对象负责处理请求和响应。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-173">This object handles the request and the responses.</span></span> <span data-ttu-id="bd3e5-174">在 Program.cs 文件内的 `Program` 类中初始化该类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-174">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static void Main(string[] args)
        {
            //...
        }
    }
}
```

<span data-ttu-id="bd3e5-175">让我们回到 `ProcessRepositories` 方法，并填充它的第一个版本：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-175">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

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

<span data-ttu-id="bd3e5-176">此外，为了让编译能够顺利进行，还需要在文件的最上面添加两个新的 using 语句：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-176">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="bd3e5-177">第一个版本发出 Web 请求来读取 .NET Foundation 组织下的所有存储库列表。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-177">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="bd3e5-178">（.NET Foundation 的 gitHub ID 为“dotnet”）。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-178">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="bd3e5-179">前几行代码针对该请求设置 <xref:System.Net.Http.HttpClient>。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-179">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="bd3e5-180">在第一行中，它被配置为接受 GitHub JSON 响应。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-180">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="bd3e5-181">此格式仅为 JSON。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-181">This format is simply JSON.</span></span> <span data-ttu-id="bd3e5-182">下一代码行将用户代理标头添加到此对象发出的所有请求中。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-182">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="bd3e5-183">这两个标头均由 GitHub 服务器代码进行检查，必须使用它们，才能检索 GitHub 中的信息。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-183">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="bd3e5-184">配置 <xref:System.Net.Http.HttpClient> 后，发出 Web 请求并检索响应。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-184">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="bd3e5-185">在此第一个版本中，将使用 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> 便捷方法。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-185">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="bd3e5-186">此便捷方法先执行发出 Web 请求的任务，然后当返回请求时读取响应流，并从流中提取内容。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-186">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="bd3e5-187">响应正文以 <xref:System.String> 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-187">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="bd3e5-188">此字符串在任务完成时可用。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-188">The string is available when the task completes.</span></span>

<span data-ttu-id="bd3e5-189">此方法的最后两行代码用于等待任务完成，然后在控制台中打印输出响应。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-189">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="bd3e5-190">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-190">Build the app, and run it.</span></span> <span data-ttu-id="bd3e5-191">此时，生成警告不再显示，因为 `ProcessRepositories` 现在的确包含 `await` 运算符。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-191">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="bd3e5-192">将看到很长的 JSON 格式文本。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-192">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="bd3e5-193">处理 JSON 结果</span><span class="sxs-lookup"><span data-stu-id="bd3e5-193">Processing the JSON Result</span></span>

<span data-ttu-id="bd3e5-194">此时，你已编写用于检索来自 Web 服务器的响应，并显示响应文本的代码。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-194">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="bd3e5-195">接下来，让我们将相应的 JSON 响应转换成 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-195">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="bd3e5-196">JSON 序列化程序将 JSON 数据转换成 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-196">The JSON Serializer converts JSON data into C# Objects.</span></span> <span data-ttu-id="bd3e5-197">首要任务是定义 C# 类类型来包含要使用的此响应信息。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-197">Your first task is to define a C# class type to contain the information you use from this response.</span></span> <span data-ttu-id="bd3e5-198">我们将慢慢生成，所以从包含存储库名称的简单 C# 类型入手：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-198">Let's build this slowly, so start with a simple C# type that contains the name of the repository:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class repo
    {
        public string name;
    }
}
```

<span data-ttu-id="bd3e5-199">将以上代码添加到“repo.cs”新文件中。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-199">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="bd3e5-200">此版本的类表示处理 JSON 数据的最简单路径。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-200">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="bd3e5-201">类名和成员名称与 JSON 数据包中使用的名称一致，而不是遵循以下 C# 约定。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-201">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="bd3e5-202">稍后将通过提供某些配置特性进行修复。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-202">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="bd3e5-203">此类展示了 JSON 序列化和反序列化的另一个重要功能：并非 JSON 数据包中的所有字段都属于此类。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-203">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="bd3e5-204">JSON 序列化程序将忽略所使用的类类型未包含的信息。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-204">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="bd3e5-205">借助此功能，可更轻松地创建仅处理一部分 JSON 数据包字段的类型。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-205">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="bd3e5-206">至此，你已创建类型，让我们来进行反序列化吧。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-206">Now that you've created the type, let's deserialize it.</span></span> <span data-ttu-id="bd3e5-207">需要创建 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 对象。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-207">You'll need to create a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object.</span></span> <span data-ttu-id="bd3e5-208">此对象必须知道它检索的 JSON 数据包的预期 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-208">This object must know the CLR type expected for the JSON packet it retrieves.</span></span> <span data-ttu-id="bd3e5-209">GitHub 发送的数据包中有一系列存储库，所以正确的类型是 `List<repo>`。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-209">The packet from GitHub contains a sequence of repositories, so a `List<repo>` is the correct type.</span></span> <span data-ttu-id="bd3e5-210">将下面这行代码添加到 `ProcessRepositories` 方法中：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-210">Add the following line to your `ProcessRepositories` method:</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

<span data-ttu-id="bd3e5-211">由于要使用两个新的命名空间，因此还需要添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-211">You're using two new namespaces, so you'll need to add those as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

<span data-ttu-id="bd3e5-212">接下来，使用序列化程序将 JSON 转换成 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-212">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="bd3e5-213">使用以下两行代码替换 `ProcessRepositories` 方法中对 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> 的调用：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-213">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following two lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

<span data-ttu-id="bd3e5-214">请注意，现使用 <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)>，而不是 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-214">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="bd3e5-215">序列化程序使用流（而不是字符串）作为其源。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-215">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="bd3e5-216">让我们来看看上面第二行代码所使用的两项 C# 语言功能。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-216">Let's explain a couple features of the C# language that are being used in the second line above.</span></span> <span data-ttu-id="bd3e5-217"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> 的自变量是一个 `await` 表达式。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-217">The argument to <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> is an `await` expression.</span></span> <span data-ttu-id="bd3e5-218">Await 表达式可以出现在代码中的几乎任何位置，尽管到目前为止，你只在赋值语句中看到过它们。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-218">Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span>

<span data-ttu-id="bd3e5-219">其次，`as` 运算符将编译时类型 `object` 转换成 `List<repo>`。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-219">Secondly, the `as` operator converts from the compile time type of `object` to `List<repo>`.</span></span>
<span data-ttu-id="bd3e5-220"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> 的声明会声明其返回 <xref:System.Object?displayProperty=nameWithType> 类型的对象。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-220">The declaration of <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declares that it returns an object of type <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bd3e5-221"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> 将返回你在构造它时指定的类型（在此教程中为 `List<repo>`）。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-221"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> will return the type you specified when you constructed it (`List<repo>` in this tutorial).</span></span> <span data-ttu-id="bd3e5-222">如果转换失败，那么 `as` 运算符的计算结果为 `null`，而不是抛出异常。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-222">If the conversion does not succeed, the `as` operator evaluates to `null`, instead of throwing an exception.</span></span>

<span data-ttu-id="bd3e5-223">即将完成此部分的操作。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-223">You're almost done with this section.</span></span> <span data-ttu-id="bd3e5-224">至此，你已将 JSON 数据转换成 C# 对象，让我们来显示每个存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-224">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="bd3e5-225">将以下代码行：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-225">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="bd3e5-226">替换为：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-226">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="bd3e5-227">编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-227">Compile and run the application.</span></span> <span data-ttu-id="bd3e5-228">将打印输出属于 .NET Foundation 的存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-228">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="bd3e5-229">控制序列化</span><span class="sxs-lookup"><span data-stu-id="bd3e5-229">Controlling Serialization</span></span>

<span data-ttu-id="bd3e5-230">在添加更多功能之前，让我们来处理一下 `repo` 类型，使其更加遵循标准的 C# 约定。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-230">Before you add more features, let's address the `repo` type and make it follow more standard C# conventions.</span></span> <span data-ttu-id="bd3e5-231">为此，使用可控制 JSON 序列化程序的工作方式的*特性*对 `repo` 类型添加批注。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-231">You'll do this by annotating the `repo` type with *attributes* that control how the JSON Serializer works.</span></span> <span data-ttu-id="bd3e5-232">在此示例中，将使用这些特性来定义 JSON 键名和 C# 类名及成员名称之间的映射。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-232">In your case, you'll use these attributes to define a mapping between the JSON key names and the C# class and member names.</span></span> <span data-ttu-id="bd3e5-233">使用的是 <xref:System.Runtime.Serialization.DataContractAttribute> 和 <xref:System.Runtime.Serialization.DataMemberAttribute> 两个特性。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-233">The two attributes used are the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes.</span></span> <span data-ttu-id="bd3e5-234">按照约定，所有特性类均以后缀 `Attribute` 结尾。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-234">By convention, all Attribute classes end in the suffix `Attribute`.</span></span> <span data-ttu-id="bd3e5-235">不过，在应用特性时无需使用此后缀。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-235">However, you do not need to use that suffix when you apply an attribute.</span></span>

<span data-ttu-id="bd3e5-236">由于 <xref:System.Runtime.Serialization.DataContractAttribute> 和 <xref:System.Runtime.Serialization.DataMemberAttribute> 特性位于不同的库中，因此需要将相应的库作为依赖项添加到 C# 项目文件中。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-236">The <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are in a different library, so you'll need to add that library to your C# project file as a dependency.</span></span> <span data-ttu-id="bd3e5-237">将下面这行代码添加到项目文件的 `<ItemGroup>` 部分中：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-237">Add the following line to the `<ItemGroup>` section of your project file:</span></span>

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

<span data-ttu-id="bd3e5-238">保存文件后，运行 `dotnet restore`（[请参阅备注](#dotnet-restore-note)）来检索此包。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-238">After you save the file, run `dotnet restore` ([see note](#dotnet-restore-note)) to retrieve this package.</span></span>

<span data-ttu-id="bd3e5-239">接下来，打开 `repo.cs` 文件。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-239">Next, open the `repo.cs` file.</span></span> <span data-ttu-id="bd3e5-240">让我们改用 Pascal 命名法，完整拼写出全称 `Repository`。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-240">Let's change the name to use Pascal Case, and fully spell out the name `Repository`.</span></span> <span data-ttu-id="bd3e5-241">我们仍要将 JSON“repo”节点映射到此类型，所以需要将 <xref:System.Runtime.Serialization.DataContractAttribute> 特性添加到类声明。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-241">We still want to map JSON 'repo' nodes to this type, so you'll need to add the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class declaration.</span></span> <span data-ttu-id="bd3e5-242">将特性的 `Name` 属性设置为映射到此类型的 JSON 节点的名称：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-242">You'll set the `Name` property of the attribute to the name of the JSON nodes that map to this type:</span></span>

```csharp
[DataContract(Name="repo")]
public class Repository
```

<span data-ttu-id="bd3e5-243">由于 <xref:System.Runtime.Serialization.DataContractAttribute> 属于 <xref:System.Runtime.Serialization> 命名空间，因此需要在文件的最上面添加适当的 `using` 语句：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-243">The <xref:System.Runtime.Serialization.DataContractAttribute> is a member of the <xref:System.Runtime.Serialization> namespace, so you'll need to add the appropriate `using` statement at the top of the file:</span></span>

```csharp
using System.Runtime.Serialization;
```

<span data-ttu-id="bd3e5-244">由于已将 `repo` 类名更改为 `Repository`，因此需要在 Program.cs 中执行相同的名称更改（某些编辑器可能支持重命名重构，这样就可以自动执行此更改了）：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-244">You changed the name of the `repo` class to `Repository`, so you'll need to make the same name change in Program.cs (some editors may support a rename refactoring that will make this change automatically:)</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

<span data-ttu-id="bd3e5-245">接下来，让我们使用 <xref:System.Runtime.Serialization.DataMemberAttribute> 类对 `name` 字段执行相同的更改。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-245">Next, let's make the same change with the `name` field by using the <xref:System.Runtime.Serialization.DataMemberAttribute> class.</span></span> <span data-ttu-id="bd3e5-246">对 repo.cs 中的 `name` 字段声明执行以下更改：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-246">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[DataMember(Name="name")]
public string Name;
```

<span data-ttu-id="bd3e5-247">此更改意味着需要更改用于在 program.cs 中写入每个存储库名称的代码：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-247">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="bd3e5-248">依次执行 `dotnet build` 和 `dotnet run`，以确保生成正确映射。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-248">Do a `dotnet build` followed by a `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="bd3e5-249">应能看到与之前一样的输出。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-249">You should see the same output as before.</span></span> <span data-ttu-id="bd3e5-250">让我们先对 `Repository` 类执行另一项更改，然后再处理更多 Web 服务器属性。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-250">Before we process more properties from the web server, let's make one more change to the `Repository` class.</span></span> <span data-ttu-id="bd3e5-251">`Name` 成员是可公开访问的字段。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-251">The `Name` member is a publicly accessible field.</span></span> <span data-ttu-id="bd3e5-252">这不是一种很好的面向对象的做法，因此，让我们将其更改为属性。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-252">That's not a good object-oriented practice, so let's change it to a property.</span></span> <span data-ttu-id="bd3e5-253">鉴于我们的目的，获取或设置属性时，我们不需要运行任何特定代码，但更改为属性，稍后就可以更加轻松地添加这些更改，同时还不会破坏任何使用 `Repository` 类的代码。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-253">For our purposes, we don't need any specific code to run when getting or setting the property, but changing to a property makes it easier to add those changes later without breaking any code that uses the `Repository` class.</span></span>

<span data-ttu-id="bd3e5-254">删除字段定义，然后将其替换为[自动实现的属性](../programming-guide/classes-and-structs/auto-implemented-properties.md)：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-254">Remove the field definition, and replace it with an [auto-implemented property](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span></span>

```csharp
public string Name { get; set; }
```

<span data-ttu-id="bd3e5-255">编译器生成 `get` 和 `set` 访问器的主体，以及用于存储名称的专用字段。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-255">The compiler generates the body of the `get` and `set` accessors, as well as a private field to store the name.</span></span> <span data-ttu-id="bd3e5-256">代码如下（可以手动键入）：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-256">It would be similar to the following code that you could type by hand:</span></span>

```csharp
public string Name
{
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

<span data-ttu-id="bd3e5-257">让我们在添加新功能前执行另一项更改。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-257">Let's make one more change before adding new features.</span></span> <span data-ttu-id="bd3e5-258">`ProcessRepositories` 方法可以执行异步工作，并返回一组存储库。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-258">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="bd3e5-259">我们将使用此方法返回 `List<Repository>`，并将用于写入信息的代码移到 `Main` 方法中。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-259">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="bd3e5-260">更改 `ProcessRepositories` 的签名，以返回可生成 `Repository` 对象列表的任务：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-260">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="bd3e5-261">然后，在处理 JSON 响应后仅返回存储库：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-261">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="bd3e5-262">编译器将生成返回内容的 `Task<T>` 对象，因为你已将此方法标记为 `async`。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-262">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="bd3e5-263">然后，我们将把 `Main` 方法修改为，捕获这些结果并将每个存储库名称写入控制台。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-263">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="bd3e5-264">现在，`Main` 方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-264">Your `Main` method now looks like this:</span></span>

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

<span data-ttu-id="bd3e5-265">只有在任务完成后，才能访问任务的 `Result` 属性。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-265">Accessing the `Result` property of a Task blocks until the task has completed.</span></span> <span data-ttu-id="bd3e5-266">通常情况下，在 `ProcessRepositories` 方法中，你倾向于 `await`（等待）任务完成，但在 `Main` 方法中这是不允许的。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-266">Normally, you would prefer to `await` the completion of the task, as in the `ProcessRepositories` method, but that isn't allowed in the `Main` method.</span></span>

## <a name="reading-more-information"></a><span data-ttu-id="bd3e5-267">读取详细信息</span><span class="sxs-lookup"><span data-stu-id="bd3e5-267">Reading More Information</span></span>

<span data-ttu-id="bd3e5-268">最后，让我们来处理 GitHub API 发送的 JSON 数据包中的其他一些属性。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-268">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="bd3e5-269">虽然你不想面面俱到，但添加其他一些属性将展示更多的 C# 语言功能。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-269">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="bd3e5-270">首先，将其他一些简单类型添加到 `Repository` 类定义中。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-270">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="bd3e5-271">将这些属性添加到此类：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-271">Add these properties to that class:</span></span>

```csharp
[DataMember(Name="description")]
public string Description { get; set; }

[DataMember(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[DataMember(Name="homepage")]
public Uri Homepage { get; set; }

[DataMember(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="bd3e5-272">这些属性内置转换功能，可从字符串类型（即 JSON 数据包所含）转换成目标类型。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-272">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="bd3e5-273">你可能是刚开始接触 <xref:System.Uri> 类型。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-273">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="bd3e5-274">它代表 URI（或在此示例中，代表 URL）。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-274">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="bd3e5-275">在有 `Uri` 和 `int` 类型的情况下，如果 JSON 数据包内的数据未转换成目标类型，那么序列化操作将会抛出异常。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-275">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="bd3e5-276">添加这些元素后，将 `Main` 方法更新为显示它们：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-276">Once you've added these, update the `Main` method to display those elements:</span></span>

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

<span data-ttu-id="bd3e5-277">最后一步，让我们添加最后一次推送操作的信息。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-277">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="bd3e5-278">此信息按如下方式在 JSON 响应中进行格式化：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-278">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="bd3e5-279">此格式不符合任何标准 .NET <xref:System.DateTime> 格式。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-279">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="bd3e5-280">因此，需要编写一个自定义转换方法。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-280">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="bd3e5-281">你可能也不希望向 `Repository` 类的用户公开原始字符串。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-281">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="bd3e5-282">特性还有助于控制此情况。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-282">Attributes can help control that as well.</span></span> <span data-ttu-id="bd3e5-283">首先，定义 `private` 属性，用于在 `Repository` 类中保存日期时间的字符串表示形式：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-283">First, define a `private` property that will hold the string representation of the date time in your `Repository` class:</span></span>

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

<span data-ttu-id="bd3e5-284"><xref:System.Runtime.Serialization.DataMemberAttribute> 特性指示序列化程序应对此进行处理，即使不是公共成员，也不例外。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-284">The <xref:System.Runtime.Serialization.DataMemberAttribute> attribute informs the serializer that this should be processed, even though it is not a public member.</span></span> <span data-ttu-id="bd3e5-285">接下来，需要编写一个公共只读属性，用于将字符串转换成有效的 <xref:System.DateTime> 对象，并返回 <xref:System.DateTime>：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-285">Next, you need to write a public read-only property that converts the string to a valid <xref:System.DateTime> object, and returns that <xref:System.DateTime>:</span></span>

```csharp
[IgnoreDataMember]
public DateTime LastPush
{
    get
    {
        return DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
    }
}
```

<span data-ttu-id="bd3e5-286">让我们来看一下上面的新构造。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-286">Let's go over the new constructs above.</span></span> <span data-ttu-id="bd3e5-287">`IgnoreDataMember` 特性指示序列化程序，不得将此类型读入任何 JSON 对象，也不得从中写入此类型。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-287">The `IgnoreDataMember` attribute instructs the serializer that this type should not be read to or written from any JSON object.</span></span> <span data-ttu-id="bd3e5-288">此属性只包含 `get` 访问器。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-288">This property contains only a `get` accessor.</span></span> <span data-ttu-id="bd3e5-289">不存在 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-289">There is no `set` accessor.</span></span> <span data-ttu-id="bd3e5-290">这就是在 C# 中定义*只读*属性的方式。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-290">That's how you define a *read-only* property in C#.</span></span> <span data-ttu-id="bd3e5-291">（是的，可以在 C# 中创建*只写*属性，但属性值受限。）<xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> 方法分析字符串，并使用提供的日期格式创建 <xref:System.DateTime> 对象，然后使用 `CultureInfo` 对象将其他元数据添加到 `DateTime` 中。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-291">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="bd3e5-292">如果分析操作失败，那么属性访问器会抛出异常。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-292">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="bd3e5-293">若要使用 <xref:System.Globalization.CultureInfo.InvariantCulture> ，需要将 <xref:System.Globalization> 命名空间添加到 `repo.cs` 中的 `using` 语句：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-293">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="bd3e5-294">最后，在控制台中再添加一个输出语句，然后就可以再次生成并运行此应用程序：</span><span class="sxs-lookup"><span data-stu-id="bd3e5-294">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="bd3e5-295">你的版本现在应与[已完成的示例](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)匹配。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-295">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="bd3e5-296">结束语</span><span class="sxs-lookup"><span data-stu-id="bd3e5-296">Conclusion</span></span>

<span data-ttu-id="bd3e5-297">此教程介绍了如何发出 Web 请求、分析结果，以及如何显示这些结果的属性。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-297">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="bd3e5-298">你也已经在项目中将新的包添加为依赖项，</span><span class="sxs-lookup"><span data-stu-id="bd3e5-298">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="bd3e5-299">并已了解一些支持面向对象的技术的 C# 语言功能。</span><span class="sxs-lookup"><span data-stu-id="bd3e5-299">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
