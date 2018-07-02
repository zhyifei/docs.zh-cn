---
title: Microsoft WCF dotnet-svcutil 工具
description: Microsoft WCF dotnet-svcutil 工具概述，该工具添加了 .NET Core 和 ASP.NET Core 项目的功能，类似于 .NET Framework 项目的 WCF svcutil 工具。
author: mlacouture
ms.author: jralexander
ms.date: 06/04/2018
ms.openlocfilehash: c40dd9b437afe7381244b944228b6b2efe046eb2
ms.sourcegitcommit: d8bf4976eafe3289275be3811e7cb721bfff7e1e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753417"
---
# <a name="microsoft-wcf-dotnet-svcutil-tool"></a><span data-ttu-id="d6089-103">Microsoft WCF dotnet-svcutil 工具</span><span class="sxs-lookup"><span data-stu-id="d6089-103">Microsoft WCF dotnet-svcutil tool</span></span>

<span data-ttu-id="d6089-104">Windows Communication Foundation (WCF) dotnet-svcutil 工具是一种 .NET Core CLI 工具，此工具从网络位置上的 Web 服务中或从 WSDL 文件中检索元数据，并生成包含访问 Web 服务操作的客户端代理方法的 WCF 类。</span><span class="sxs-lookup"><span data-stu-id="d6089-104">The Windows Communication Foundation (WCF) **dotnet-svcutil** tool is a .NET Core CLI tool that retrieves metadata from a web service on a network location or from a WSDL file, and generates a WCF class containing client proxy methods that access the web service operations.</span></span>

<span data-ttu-id="d6089-105">类似于 .NET Framework 项目的[服务模型元数据 - svcutil](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 工具，dotnet svcutil 是用于生成 Web 服务引用的命令行工具，与 .NET Core 和 .NET Standard 项目兼容。</span><span class="sxs-lookup"><span data-stu-id="d6089-105">Similar to the [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool for .NET Framework projects, the **dotnet-svcutil** is a command-line tool for generating a web service reference compatible with .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="d6089-106">dotnet-svcutil 工具是 [WCF Web 服务引用](wcf-web-service-reference-guide.md) Visual Studio 连接服务提供程序（随 Visual Studio 2017 v15.5 首次推出）的替代选项。</span><span class="sxs-lookup"><span data-stu-id="d6089-106">The **dotnet-svcutil** tool is an alternative option to the [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio connected service provider that first shipped with Visual Studio 2017 v15.5.</span></span> <span data-ttu-id="d6089-107">dotnet-svcutil 工具作为一种 .NET Core CLI 工具，可跨平台地用于 Linux、macOS 和 Windows。</span><span class="sxs-lookup"><span data-stu-id="d6089-107">The **dotnet-svcutil** tool as a .NET Core CLI tool, is available cross-platform on Linux, macOS, and Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6089-108">应仅从受信任源引用服务。</span><span class="sxs-lookup"><span data-stu-id="d6089-108">You should only reference services from a trusted source.</span></span> <span data-ttu-id="d6089-109">从不受信任的源添加引用可能会危及安全性。</span><span class="sxs-lookup"><span data-stu-id="d6089-109">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6089-110">系统必备</span><span class="sxs-lookup"><span data-stu-id="d6089-110">Prerequisites</span></span>

* <span data-ttu-id="d6089-111">[.NET Core SDK](https://www.microsoft.com/net/download) 版本 1.0.4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d6089-111">[.NET Core SDK](https://www.microsoft.com/net/download) v1.0.4 or later versions</span></span>
* <span data-ttu-id="d6089-112">你最喜欢的代码编辑器</span><span class="sxs-lookup"><span data-stu-id="d6089-112">Your favorite code editor</span></span>

## <a name="getting-started"></a><span data-ttu-id="d6089-113">入门</span><span class="sxs-lookup"><span data-stu-id="d6089-113">Getting started</span></span>

<span data-ttu-id="d6089-114">下面的示例将指导你完成将 Web 服务引用添加到 .NET Core 控制台项目并调用该服务所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="d6089-114">The following example walks you through the steps required to add a web service reference to a .NET Core console project and invoke the service.</span></span> <span data-ttu-id="d6089-115">你将创建名为“HelloSvcutil”的 .NET Core 控制台应用程序，并将引用添加到实现以下协定的 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="d6089-115">You will create a .NET Core console application named _HelloSvcutil_ and will add a reference to a web service that implements the following contract:</span></span>

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

<span data-ttu-id="d6089-116">在此示例中，将假定 Web 服务托管在以下地址中：`http://contoso.com/SayHello.svc`</span><span class="sxs-lookup"><span data-stu-id="d6089-116">For this example, the web service will be assumed to be hosted at the following address: `http://contoso.com/SayHello.svc`</span></span>

<span data-ttu-id="d6089-117">从 Windows、macOS 或 Linux 命令窗口执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d6089-117">From a Windows, macOS, or Linux command window perform the following steps:</span></span>

1. <span data-ttu-id="d6089-118">为项目创建一个名为“HelloSvcutil”的目录，并将其设置为当前目录，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="d6089-118">Create a directory named _HelloSvcutil_ for your project and make it your current directory, as in the following example:</span></span>

```console
mkdir HelloSvcutil
cd HelloSvcutil
```

2. <span data-ttu-id="d6089-119">在该目录中使用 [`dotnet new`](../tools/dotnet-new.md) 命令创建新的 C# 控制台项目项目，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6089-119">Create a new C# console project in that directory using the [`dotnet new`](../tools/dotnet-new.md) command as follows:</span></span>

```console
dotnet new console
```

3. <span data-ttu-id="d6089-120">在编辑器中打开 `HelloSvcutil.csproj` 项目文件，编辑 `Project` 元素，并使用下面的代码添加 [`dotnet-svcutil` NuGet 包](https://nuget.org/packages/dotnet-svcutil)作为 CLI 工具引用：</span><span class="sxs-lookup"><span data-stu-id="d6089-120">Open the `HelloSvcutil.csproj` project file in your editor, edit the `Project` element, and add the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool reference, using the following code:</span></span>

```xml
<ItemGroup>
  <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.0" />
</ItemGroup>
```

4. <span data-ttu-id="d6089-121">使用 [`dotnet restore`](../tools/dotnet-restore.md) 命令还原 dotnet-svcutil 包，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6089-121">Restore the _dotnet-svcutil_ package using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

```console
dotnet restore
```

5. <span data-ttu-id="d6089-122">运行 _dotnet_ 与 _svcutil_ 命令生成 Web 服务引用文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6089-122">Run _dotnet_ with the _svcutil_ command to generate the web service reference file as follows:</span></span>

```console
dotnet svcutil http://contoso.com/SayHello.svc
```
<span data-ttu-id="d6089-123">生成的文件保存为 _HelloSvcutil/ServiceReference1/Reference.cs_。</span><span class="sxs-lookup"><span data-stu-id="d6089-123">The generated file is saved as _HelloSvcutil/ServiceReference1/Reference.cs_.</span></span> <span data-ttu-id="d6089-124">_dotnet_svcutil_ 工具还向项目添加代理代码所需的适当 WCF 包作为包引用。</span><span class="sxs-lookup"><span data-stu-id="d6089-124">The _dotnet_svcutil_ tool also adds to the project the appropriate WCF packages required by the proxy code as package references.</span></span>

6. <span data-ttu-id="d6089-125">使用 [`dotnet restore`](../tools/dotnet-restore.md) 命令还原 WCF 包，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6089-125">Restore the WCF packages using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

```console
dotnet restore
```

7. <span data-ttu-id="d6089-126">在编辑器中打开 `Program.cs` 文件，编辑 `Main()` 方法，然后使用下列代码替换自动生成的代码来调用 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="d6089-126">Open the `Program.cs` file in your editor, edit the `Main()` method, and replace the auto-generated code with the following code to invoke the web service:</span></span>

```csharp
static void Main(string[] args)
{
    var client = new SayHelloClient();
    Console.WriteLine(client.HelloAsync("dotnet-svcutil").Result);
}
```

8. <span data-ttu-id="d6089-127">使用 [`dotnet run`](../tools/dotnet-run.md) 命令运行应用程序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6089-127">Run the application using the [`dotnet run`](../tools/dotnet-run.md) command as follows:</span></span>

```console
dotnet run
```
<span data-ttu-id="d6089-128">你将看到以下输出：“Hello dotnet-svcutil!”</span><span class="sxs-lookup"><span data-stu-id="d6089-128">You should see the following output: "Hello dotnet-svcutil!"</span></span>

<span data-ttu-id="d6089-129">有关 `dotnet-svcutil` 工具参数的详细说明，请调用传递帮助参数的工具，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6089-129">For a detailed description of the `dotnet-svcutil` tool parameters, invoke the tool passing the help parameter as follows:</span></span>

```console
dotnet svcutil --help
```

## <a name="next-steps"></a><span data-ttu-id="d6089-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d6089-130">Next steps</span></span>

### <a name="feedback--questions"></a><span data-ttu-id="d6089-131">反馈和问题</span><span class="sxs-lookup"><span data-stu-id="d6089-131">Feedback & questions</span></span>

<span data-ttu-id="d6089-132">如果有任何问题或反馈，请[在 GitHub 上提问](https://github.com/dotnet/wcf/issues/new)。</span><span class="sxs-lookup"><span data-stu-id="d6089-132">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="d6089-133">也可以在 [GitHub 上的 WCF 存储库](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling)中查看任何现有问题。</span><span class="sxs-lookup"><span data-stu-id="d6089-133">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

### <a name="release-notes"></a><span data-ttu-id="d6089-134">发行说明</span><span class="sxs-lookup"><span data-stu-id="d6089-134">Release notes</span></span>

* <span data-ttu-id="d6089-135">请参阅[发行说明](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md)，了解更新的版本信息（包括已知问题）。</span><span class="sxs-lookup"><span data-stu-id="d6089-135">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) for updated release information, including known issues.</span></span>

### <a name="information"></a><span data-ttu-id="d6089-136">信息</span><span class="sxs-lookup"><span data-stu-id="d6089-136">Information</span></span>

* [<span data-ttu-id="d6089-137">dotnet-svcutil NuGet 包</span><span class="sxs-lookup"><span data-stu-id="d6089-137">dotnet-svcutil NuGet Package</span></span>](https://nuget.org/packages/dotnet-svcutil)
