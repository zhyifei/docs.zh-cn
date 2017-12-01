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
# <a name="using-the-windows-compatibility-pack"></a>使用 Windows 兼容性包

开发人员面临移植到.NET 核心其现有代码时最常见的问题之一是它们依赖于 Api 以及仅存在于.NET Framework 中的技术。 *Windows 兼容性包*即将提供其中许多技术，以便构建.NET Core 应用程序，以及标准.NET 库变为为现有代码更为可行。

此包的逻辑[.NET 标准 2.0 扩展](../whats-new/index.md#api-changes-and-library-support)，显著增加 API 集和现有的代码使用编译几乎无需进行修改。 不过，若要保留的承诺的标准.NET （"它是一组的所有.NET 实现都提供的 Api"），这不包括无法跨所有平台工作，如注册表中，Windows Management Instrumentation (WMI) 的技术或反射发出Api。

*Windows 兼容性包*位于顶部.NET 标准并提供到仅是窗口的技术的访问权限。 它是特别有用的客户而言，想要将移动到.NET 核心但停留在第一步的 Windows 的计划。 在该方案中，无法使用仅 Windows 技术是仅迁移障碍零体系结构的优势。

## <a name="package-contents"></a>包内容

*Windows 兼容性包*通过 NuGet 程序包提供[Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) ，可以从面向.NET 核心或标准.NET 项目引用。

它提供了有关 20000 Api，包括仅 Windows，以及跨平台的 Api，从以下技术几个方面：

* 代码页
* CodeDom
* 配置
* 目录服务
* 绘制
* ODBC
* 权限
* 端口
* Windows 访问控制列表 (ACL)
* Windows Communication Foundation (WCF)
* Windows 加密
* Windows 事件日志
* Windows Management Instrumentation (WMI)
* Windows 性能计数器
* Windows 注册表
* Windows 运行时缓存
* Windows 服务

有关详细信息，请参阅[规范的兼容性包](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md)。

## <a name="get-started"></a>入门

1. 移植之前, 一定要看一看[移植过程](index.md)。

2. 在现有将代码移植到.NET 核心或标准.NET，安装此 NuGet 程序包[Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)。

3. 如果你想要保持在 Windows 上，您都准备。

4. 如果你想要在 Linux 或 macOS 上运行的.NET Core 应用程序或标准.NET 库，使用[API 分析器](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/)查找不起作用，跨平台的 Api 的使用情况。

5. 可以删除这些 Api 的用法，将它们替换为跨平台的替代，或者保护它们使用的平台检查，如：

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

有关演示，请查看[Windows 兼容性包的第 9 频道视频](https://channel9.msdn.com/Events/Connect/2017/T123)。

