---
title: "迁移到.NET 核心-使用 Windows 兼容性包"
description: "了解有关 Windows 兼容性包的信息和你使用它的方式对端口到.NET 核心的现有.NET Framework 代码"
keywords: ".NET、.NET 核心、 Windows、 兼容性"
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 5094baee77aba4d1e148f807d842a4a2d3405cf7
ms.sourcegitcommit: 86cf9b4c7104485a9870645705b9a1a4b6ca8e2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2017
---
# <a name="using-the-windows-compatibility-pack"></a><span data-ttu-id="d5af7-104">使用 Windows 兼容性包</span><span class="sxs-lookup"><span data-stu-id="d5af7-104">Using the Windows Compatibility Pack</span></span>

<span data-ttu-id="d5af7-105">开发人员面临移植到.NET 核心其现有代码时最常见的问题之一是它们依赖于 Api 以及仅存在于.NET Framework 中的技术。</span><span class="sxs-lookup"><span data-stu-id="d5af7-105">One of the most common issues that developers face when porting their existing code to .NET Core is that they depend on APIs and technologies that only exist in the .NET Framework.</span></span> <span data-ttu-id="d5af7-106">*Windows 兼容性包*即将提供其中许多技术，以便构建.NET Core 应用程序，以及标准.NET 库变为为现有代码更为可行。</span><span class="sxs-lookup"><span data-stu-id="d5af7-106">The *Windows Compatibility Pack* is about providing many of these technologies so that building .NET Core applications as well as .NET Standard libraries becomes much more viable for existing code.</span></span>

<span data-ttu-id="d5af7-107">此包的逻辑[.NET 标准 2.0 扩展](../whats-new/index.md#api-changes-and-library-support)，显著增加 API 集和现有的代码使用编译几乎无需进行修改。</span><span class="sxs-lookup"><span data-stu-id="d5af7-107">This package is a logical [extension of .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="d5af7-108">不过，若要保留的承诺的标准.NET （"它是一组的所有.NET 实现都提供的 Api"），这不包括无法跨所有平台工作，如注册表中，Windows Management Instrumentation (WMI) 的技术或反射发出Api。</span><span class="sxs-lookup"><span data-stu-id="d5af7-108">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="d5af7-109">*Windows 兼容性包*位于顶部.NET 标准并提供到仅是窗口的技术的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d5af7-109">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="d5af7-110">它是特别有用的客户而言，想要将移动到.NET 核心但停留在第一步的 Windows 的计划。</span><span class="sxs-lookup"><span data-stu-id="d5af7-110">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="d5af7-111">在该方案中，无法使用仅 Windows 技术是仅迁移障碍零体系结构的优势。</span><span class="sxs-lookup"><span data-stu-id="d5af7-111">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="d5af7-112">包内容</span><span class="sxs-lookup"><span data-stu-id="d5af7-112">Package contents</span></span>

<span data-ttu-id="d5af7-113">*Windows 兼容性包*通过 NuGet 程序包提供[Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) ，可以从面向.NET 核心或标准.NET 项目引用。</span><span class="sxs-lookup"><span data-stu-id="d5af7-113">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="d5af7-114">它提供了有关 20000 Api，包括仅 Windows，以及跨平台的 Api，从以下技术几个方面：</span><span class="sxs-lookup"><span data-stu-id="d5af7-114">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="d5af7-115">代码页</span><span class="sxs-lookup"><span data-stu-id="d5af7-115">Code Pages</span></span>
* <span data-ttu-id="d5af7-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="d5af7-116">CodeDom</span></span>
* <span data-ttu-id="d5af7-117">配置</span><span class="sxs-lookup"><span data-stu-id="d5af7-117">Configuration</span></span>
* <span data-ttu-id="d5af7-118">目录服务</span><span class="sxs-lookup"><span data-stu-id="d5af7-118">Directory Services</span></span>
* <span data-ttu-id="d5af7-119">绘制</span><span class="sxs-lookup"><span data-stu-id="d5af7-119">Drawing</span></span>
* <span data-ttu-id="d5af7-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="d5af7-120">ODBC</span></span>
* <span data-ttu-id="d5af7-121">权限</span><span class="sxs-lookup"><span data-stu-id="d5af7-121">Permissions</span></span>
* <span data-ttu-id="d5af7-122">端口</span><span class="sxs-lookup"><span data-stu-id="d5af7-122">Ports</span></span>
* <span data-ttu-id="d5af7-123">Windows 访问控制列表 (ACL)</span><span class="sxs-lookup"><span data-stu-id="d5af7-123">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="d5af7-124">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="d5af7-124">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="d5af7-125">Windows 加密</span><span class="sxs-lookup"><span data-stu-id="d5af7-125">Windows Cryptography</span></span>
* <span data-ttu-id="d5af7-126">Windows 事件日志</span><span class="sxs-lookup"><span data-stu-id="d5af7-126">Windows EventLog</span></span>
* <span data-ttu-id="d5af7-127">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="d5af7-127">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="d5af7-128">Windows 性能计数器</span><span class="sxs-lookup"><span data-stu-id="d5af7-128">Windows Performance Counters</span></span>
* <span data-ttu-id="d5af7-129">Windows 注册表</span><span class="sxs-lookup"><span data-stu-id="d5af7-129">Windows Registry</span></span>
* <span data-ttu-id="d5af7-130">Windows 运行时缓存</span><span class="sxs-lookup"><span data-stu-id="d5af7-130">Windows Runtime Caching</span></span>
* <span data-ttu-id="d5af7-131">Windows 服务</span><span class="sxs-lookup"><span data-stu-id="d5af7-131">Windows Services</span></span>

<span data-ttu-id="d5af7-132">有关详细信息，请参阅[规范的兼容性包](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md)。</span><span class="sxs-lookup"><span data-stu-id="d5af7-132">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="d5af7-133">入门</span><span class="sxs-lookup"><span data-stu-id="d5af7-133">Get started</span></span>

1. <span data-ttu-id="d5af7-134">移植之前, 一定要看一看[移植过程](index.md)。</span><span class="sxs-lookup"><span data-stu-id="d5af7-134">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="d5af7-135">在现有将代码移植到.NET 核心或标准.NET，安装此 NuGet 程序包[Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)。</span><span class="sxs-lookup"><span data-stu-id="d5af7-135">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="d5af7-136">如果你想要保持在 Windows 上，您都准备。</span><span class="sxs-lookup"><span data-stu-id="d5af7-136">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="d5af7-137">如果你想要在 Linux 或 macOS 上运行的.NET Core 应用程序或标准.NET 库，使用[API 分析器](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/)查找不起作用，跨平台的 Api 的使用情况。</span><span class="sxs-lookup"><span data-stu-id="d5af7-137">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="d5af7-138">可以删除这些 Api 的用法，将它们替换为跨平台的替代，或者保护它们使用的平台检查，如：</span><span class="sxs-lookup"><span data-stu-id="d5af7-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

<span data-ttu-id="d5af7-139">有关演示，请查看[Windows 兼容性包的第 9 频道视频](https://channel9.msdn.com/Events/Connect/2017/T123)。</span><span class="sxs-lookup"><span data-stu-id="d5af7-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

