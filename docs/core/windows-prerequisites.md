---
title: Windows 上 .NET Core 的先决条件
description: 了解在 Windows 计算机上开发和运行 .NET Core 应用程序所需的依赖项。
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: 6885f6c853efb0dcb2cb64b83f07e12b1dc2e3cf
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771955"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Windows 上 .NET Core 的先决条件

本文介绍在 Windows 上运行 .NET Core 应用程序所支持的 OS 版本。 支持的 OS 版本和依赖项适用于在 Windows 上开发 .NET Core 应用程序的三种方法：

* [命令行](./tutorials/using-with-xplat-cli.md)
* [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [Visual Studio Code](https://code.visualstudio.com/)

此外，如果你正在使用 Visual Studio 开发 Windows，请查看[有关使用 Visual Studio 开发 .NET Core 应用的先决条件](#prerequisites-to-develop-net-core-apps-with-visual-studio)部分，更详细地了解支持 .NET Core 开发的最低版本。

## <a name="net-core-supported-operating-systems"></a>.NET Core 支持的操作系统

以下文章提供了 .NET Core 针对每个版本所支持的操作系统的完整列表：

* [.NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

有关下载链接和详细信息，请参阅 [.NET 下载](https://dotnet.microsoft.com/download)下载最新版本或 [.NET 下载存档](https://dotnet.microsoft.com/download/archives#dotnet-core)下载较旧版本。

## <a name="net-core-dependencies"></a>.NET Core 依赖项

如果出现以下情况，必须手动安装 [Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)：

* 使用[安装程序脚本](./tools/dotnet-install-script.md)安装 .NET Core。
* 部署独立式 .NET Core 应用程序。
* 从源中生成产品。
* 通过 .zip 文件  安装 .NET Core。 这可能包括 build/CI/CD 服务器。

> [!NOTE]
> 对于 Windows 8.1 和更早版本，或 Windows Server 2012 R2 和更早版本： 
>
> 确保 Windows 安装是最新版本，并且包括可通过 Windows 更新安装的 [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)。 如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`
>
> 对于 Windows 7 或 Windows Server 2008 R2： 
>
> 除 KB2999226 以外，请确保还安装了 [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)。 如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`。

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a>有关使用 Visual Studio 开发 .NET Core 应用的先决条件

尽管可使用任意编辑器结合 .NET Core SDK 来开发 .NET Core 应用程序，但 Visual Studio 2017 及更高版本对 Windows 上的 .NET Core 应用提供了一个集成开发环境。

<a name="vs-mapping"></a>

每个 .NET Core 版本都有 Visual Studio 最低版本的要求。 若要验证 Visual Studio 版本，请执行以下操作：

* 在“帮助”  菜单上，选择“关于 Microsoft Visual Studio”  。
* 在“关于 Microsoft Visual Studio”  对话框中，验证版本号。

下表列出了每个 SDK 的最低版本：

| .NET Core SDK 版本 | Visual Studio 版本                      |
| --------------------- | ------------------------------------------ |
| 3.0                   | Visual Studio 2019 版本 16.3 或更高版本。 |
| 2.2                   | Visual Studio 2017 版本 15.9 或更高版本。 |
| 2.1                   | Visual Studio 2017 版本 15.7 或更高版本。 |
| 1.x                   | Visual Studio 2017 版本 15.0 或更高版本。 |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

要使用 .NET Core 3.0 SDK 在 Visual Studio 2019 中开发 .NET Core 应用：

* [下载并安装 Visual Studio 2019 版本 16.3 或更高版本](/visualstudio/install/install-visual-studio)，然后选择下述其中一个包含 .NET Core SDK 的工作负荷（具体取决于你要构建的应用程序类型）：

  * “其他工具集”部分中的“.NET Core 跨平台开发”工作负荷   。
  * “Web 和云”部分中的“ASP.NET 和 Web 开发”工作负荷   。
  * “Windows”部分中的“NET 桌面开发”工作负荷   。

下图显示了已在 Visual Studio UI 中选择“.NET Core 跨平台开发”工作负荷  ：

![Visual Studio 2019 安装的屏幕截图，其中勾选了“.NET Core 跨平台开发”工作负荷](./media/windows-prerequisites/vs-2019-workloads.jpg)

在安装上述任何工作负载后，Visual Studio 2019 版本 16.3 默认使用 .NET Core 3.0 SDK。

如果希望现有项目使用最新的 .NET Core 运行时，请按照下述说明将每个现有的 .NET Core 项目重定目标到 .NET Core 3.0：

* 在 **“项目”** 菜单上，选择 **“属性”** 。
* 在“目标框架”选择菜单上，将值设置为“.NET Core 3.0”   。

![Visual Studio 2019 应用程序项目属性的屏幕截图，其中已勾选“.NET Core 3.0”目标框架菜单项](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

使用 .NET Core 3.0 SDK 配置 Visual Studio 后，可执行以下操作：

* 打开、生成和运行现有 .NET Core 1.x 和 2.x 项目。
* 将 .NET Core 1.x 和 2.x 项目重定目标到 .NET Core 3.0，进行生成，然后运行。
* 新建 .NET Core 3.0 项目。

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

若要使用 .NET Core 2.2 SDK 在 Visual Studio 2017 中开发 .NET Core 应用：

* [下载并安装 Visual Studio 2019 版本 16.3 或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”部分中的“.NET Core 跨平台开发”工作负荷   。
* [下载并安装 Visual Studio 2017 版本 15.9.0 或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”  部分中的“.NET Core 跨平台开发”  工作负载。

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs-2017-workloads.jpg)

安装“.NET Core 跨平台开发”  工具集后，Visual Studio 通常会安装以前版本的 .NET Core SDK。
例如，Visual Studio 2017 版本 15.9 在安装工作负载后默认使用 .NET Core 2.1 SDK。

若要更新 Visual Studio 以使用 .NET Core 2.2 SDK：

 1. 安装 [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)。

 1. 如果希望项目使用最新的 .NET Core 运行时，请按照以下说明将每个现有或新的 .NET Core 项目重定目标到 .NET Core 2.2：

    * 在 **“项目”** 菜单上，选择 **“属性”** 。
    * 在“目标框架”  选择菜单上，将值设置为“.NET Core 2.2”  。

![已选择“.NET Core 2.2”目标框架菜单项的 Visual Studio 2017 应用程序项目属性屏幕截图](./media/windows-prerequisites/targeting-dotnet-core.jpg)

使用 .NET Core 2.2 SDK 配置 Visual Studio 后，可执行以下操作：

* 打开、生成和运行现有 .NET Core 1.x 和 2.x 项目。
* 将 .NET Core 1.x 和 2.x 项目重定目标到 .NET Core 2.2，再生成并运行。
* 新建 .NET Core 2.2 项目。

---
