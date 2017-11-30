---
title: "在 Windows 10 上安装 .NET Framework"
description: "了解如何在 Windows 10 或 Windows Server 2016 上安装.NET Framework。"
author: rlander
ms.author: mairaw
keywords: ".NET Framework, 安装"
ms.date: 11/17/2017
ms.topic: article
ms.custom: updateeachrelease
ms.prod: .net-framework
ms.openlocfilehash: d7f8dd4c6ee9f7eeda389a955f806a5765876ea7
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2017
---
# <a name="install-the-net-framework-on-windows-10-and-windows-server-2016"></a>在 Windows 10 和 Windows Server 2016 上安装.NET Framework

在 Windows 上运行许多应用程序需要.NET Framework。 此文章中的说明应帮助你安装需要的.NET Framework 版本。 [.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47)是最新的可用版本。

你可能已到达此页上尝试运行应用程序和类似于以下计算机上看到一个对话框后：

![无法启动此应用程序](./media/this-application-could-not-be-started.png)

## <a name="net-framework-471"></a>.NET framework 4.7.1

.NET Framework 4.7.1 是附带的：

* [Windows 10 秋季创建者更新 （版本 1709年）](https://www.microsoft.com/software-download/windows10)
* [Windows Server 2016 （版本 1709年）](https://docs.microsoft.com/windows-server/get-started/get-started-with-1709)

> [!div class="button"]
[下载.NET Framework 4.7.1](https://www.microsoft.com/net/download/thank-you/net471?utm_source=ms-docs&utm_medium=referral)

[.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47)可以用于运行 for 4.7.1 通过.NET Framework 4.0 生成的应用程序。

你可以安装[.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47)上：

* Windows 10 创建者更新 （版本 1703年）
* Windows 10 周年日更新 （版本 1607年）
* Windows 2016 Server

不支持.NET Framework 4.7.1:

* Windows 10 1507
* Windows 10 1511

如果你使用的 Windows 10 1507年或 1511年，并且你想要安装.NET Framework 4.7.1，首先需要升级到更高版本的 Windows 10 版本。

## <a name="net-framework-461"></a>.NET Framework 4.6.1

[.NET Framework 4.6.1](https://www.microsoft.com/download/details.aspx?id=49981)是最新支持.NET Framework 版本上 Windows 10 1507年和 1511年。

.NET Framework 4.6.1 支持用于通过 4.6.1 的.NET Framework 4.0 生成的应用程序。

## <a name="net-framework-35"></a>.NET Framework 3.5

请按照说明操作，[在 Windows 10 上安装 .NET Framework 3.5](dotnet-35-windows-10.md)。

.NET Framework 3.5 支持为.NET Framework 1.0 到 3.5 生成的应用程序。

## <a name="additional-information"></a>其他信息

.NET framework 4.x 版本是早期版本的就地更新。 这意味着以下：

- 只能有一个版本的.NET framework 4.x 安装您的计算机上。

- 如果已安装的更高版本的情况下，不能在您的计算机上安装.NET Framework 的早期版本。

- .NET framework 4.x 版本可以用于运行.NET Framework 4.0，通过该版本的生成的应用程序。 例如，.NET Framework 4.7 可用来运行用于通过 4.7.NET Framework 4.0 生成的应用程序。 最新版本 (.NET Framework 4.7.1) 可用来运行生成的应用程序将从 4.0 的.NET framework 的所有版本。

有关可供下载的.NET framework 的所有版本的列表，请参阅[.NET 下载](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral)页。

## <a name="help"></a>帮助

如果无法获取安装了.NET Framework 的正确版本，则可以[联系 Microsoft 寻求帮助](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help)。

## <a name="see-also"></a>请参阅

[.NET 下载](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral)   
[安装和卸载 .NET Framework 受阻疑难解答](troubleshoot-blocked-installations-and-uninstallations.md)   
[安装.NET Framework 为开发人员](guide-for-developers.md)