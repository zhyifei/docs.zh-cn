---
title: 使用 Windows 兼容性包将代码移植到 .NET Core
description: 了解有关 Windows 兼容性包以及如何使用它将现有 .NET Framework 代码移植到 .NET Core 的信息
author: terrajobst
ms.date: 11/13/2017
ms.custom: seodec18
ms.openlocfilehash: 0a409c953ce38ed4c2959adaf4de9d3730ce37f4
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169932"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a><span data-ttu-id="ca6e8-103">使用 Windows 兼容性包将代码移植到 .NET Core</span><span class="sxs-lookup"><span data-stu-id="ca6e8-103">Use the Windows Compatibility Pack to port code to .NET Core</span></span>

<span data-ttu-id="ca6e8-104">将现有代码移植到 .NET Core 时发现的一些最常见问题依赖于仅在 .NET Framework 中找到的 API 和技术。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-104">Some of the most common issues found when porting existing code to .NET Core are dependencies on APIs and technologies that are only found in the .NET Framework.</span></span> <span data-ttu-id="ca6e8-105">Windows 兼容性包提供许多这些技术，因此可以更轻松地生成 .NET Core 应用程序和 .NET Standard 库。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-105">The *Windows Compatibility Pack* provides many of these technologies, so it's much easier to build .NET Core applications and .NET Standard libraries.</span></span>

<span data-ttu-id="ca6e8-106">此包是 [.NET Standard 2.0 的逻辑扩展](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support)，显著增加了 API 集和现有代码编译，而几乎无需进行任何修改。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-106">This package is a logical [extension of .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="ca6e8-107">但为了信守 .NET Standard 的承诺（“它是一组所有 .NET 实现都提供的 API”），这不包括无法跨所有平台工作的技术，如注册表、Windows Management Instrumentation (WMI) 或反射发出 API。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-107">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="ca6e8-108">Windows 兼容性包 位于 .NET Standard 顶部，提供对仅用于 Windows 的技术的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-108">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="ca6e8-109">它对于第一步想要移动到 .NET Core 但仍计划停留在 Windows 上的客户尤其有用。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-109">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="ca6e8-110">在这种情况下，无法使用仅限 Windows 的技术只会造成迁移障碍，没有任何体系结构优势。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-110">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="ca6e8-111">包内容</span><span class="sxs-lookup"><span data-stu-id="ca6e8-111">Package contents</span></span>

<span data-ttu-id="ca6e8-112">Windows 兼容性包通过 NuGet 包 [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) 提供，可从面向 .NET Core 或 .NET Standard 的项目引用。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-112">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="ca6e8-113">它提供了约 20,000 个 API，包括仅 Windows API 以及以下技术领域中的跨平台 API：</span><span class="sxs-lookup"><span data-stu-id="ca6e8-113">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="ca6e8-114">代码页</span><span class="sxs-lookup"><span data-stu-id="ca6e8-114">Code Pages</span></span>
* <span data-ttu-id="ca6e8-115">CodeDom</span><span class="sxs-lookup"><span data-stu-id="ca6e8-115">CodeDom</span></span>
* <span data-ttu-id="ca6e8-116">配置</span><span class="sxs-lookup"><span data-stu-id="ca6e8-116">Configuration</span></span>
* <span data-ttu-id="ca6e8-117">目录服务</span><span class="sxs-lookup"><span data-stu-id="ca6e8-117">Directory Services</span></span>
* <span data-ttu-id="ca6e8-118">绘图</span><span class="sxs-lookup"><span data-stu-id="ca6e8-118">Drawing</span></span>
* <span data-ttu-id="ca6e8-119">ODBC</span><span class="sxs-lookup"><span data-stu-id="ca6e8-119">ODBC</span></span>
* <span data-ttu-id="ca6e8-120">权限</span><span class="sxs-lookup"><span data-stu-id="ca6e8-120">Permissions</span></span>
* <span data-ttu-id="ca6e8-121">端口</span><span class="sxs-lookup"><span data-stu-id="ca6e8-121">Ports</span></span>
* <span data-ttu-id="ca6e8-122">Windows 访问控制列表 (ACL)</span><span class="sxs-lookup"><span data-stu-id="ca6e8-122">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="ca6e8-123">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="ca6e8-123">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="ca6e8-124">Windows 加密</span><span class="sxs-lookup"><span data-stu-id="ca6e8-124">Windows Cryptography</span></span>
* <span data-ttu-id="ca6e8-125">Windows 事件日志</span><span class="sxs-lookup"><span data-stu-id="ca6e8-125">Windows EventLog</span></span>
* <span data-ttu-id="ca6e8-126">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="ca6e8-126">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="ca6e8-127">Windows 性能计数器</span><span class="sxs-lookup"><span data-stu-id="ca6e8-127">Windows Performance Counters</span></span>
* <span data-ttu-id="ca6e8-128">Windows 注册表</span><span class="sxs-lookup"><span data-stu-id="ca6e8-128">Windows Registry</span></span>
* <span data-ttu-id="ca6e8-129">Windows 运行时缓存</span><span class="sxs-lookup"><span data-stu-id="ca6e8-129">Windows Runtime Caching</span></span>
* <span data-ttu-id="ca6e8-130">Windows 服务</span><span class="sxs-lookup"><span data-stu-id="ca6e8-130">Windows Services</span></span>

<span data-ttu-id="ca6e8-131">有关详细信息，请参阅[兼容性包规范](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md)。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-131">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="ca6e8-132">入门</span><span class="sxs-lookup"><span data-stu-id="ca6e8-132">Get started</span></span>

1. <span data-ttu-id="ca6e8-133">移植之前，请确保查看[移植过程](index.md)。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-133">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="ca6e8-134">将现有代码移植到 .NET Core 或 .NET Standard 时，请安装 NuGet 包 [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-134">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="ca6e8-135">如果要停留在 Windows 上，则已准备完毕。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-135">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="ca6e8-136">如果要在 Linux 或 macOS 上运行 .NET Core 应用程序或 .NET Standard 库，请使用 [API 分析器](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/)查找不会跨平台工作的 API 的使用情况。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-136">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="ca6e8-137">删除这些 API 的使用情况、将其替换为跨平台替代项，或使用平台检查对其实施保护，例如：</span><span class="sxs-lookup"><span data-stu-id="ca6e8-137">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

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

<span data-ttu-id="ca6e8-138">有关演示，请查看 [Windows 兼容性包的第 9 频道视频](https://channel9.msdn.com/Events/Connect/2017/T123)。</span><span class="sxs-lookup"><span data-stu-id="ca6e8-138">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

