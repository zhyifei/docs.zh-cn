---
title: 在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5
description: 了解如何在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5。
author: rlander
ms.author: mairaw
ms.date: 03/30/2018
ms.openlocfilehash: 226449b8ee7c9360e6bfdc5bfa5dfeb59f19bd2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5

必须安装 .NET Framework 3.5，才能在 Windows 10、Windows 8.1 和 Windows 8 上运行应用。 对于旧版 Windows，也可以按照以下说明操作。

## <a name="install-the-net-framework-35-on-demand"></a>按需安装.NET Framework 3.5

如果尝试运行的应用要求安装 .NET Framework 3.5，则会看到以下配置对话框。 选择“安装此功能”，启用 .NET Framework 3.5。 此选项需要 Internet 连接。

![.NET Framework 安装对话框](./media/dotnet-framework-installation-dialog.jpg)

### <a name="why-am-i-getting-this-pop-up"></a>为什么我会看到此弹出项？

.NET Framework 是由 Microsoft 创建，用于提供应用程序运行环境。 有多种不同版本。 许多公司都开发使用 .NET Framework 运行的应用程序，并且这些应用都定目标到具体版本。 如果看到此弹出项，表明尝试运行的应用程序需要 .NET Framework 版本 3.5，但未在系统上安装此版本。

## <a name="enable-the-net-framework-35-in-control-panel"></a>在控制面板中启用 .NET Framework 3.5

可以通过 Windows 控制面板启用 .NET Framework 3.5。 此选项需要 Internet 连接。

1. 按键盘上的 Windows 键 ![Windows 徽标](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg)，键入“Windows 功能”，然后按 Enter。 随即显示“打开或关闭 Windows 功能”对话框。

2. 如果弹出提示，选择“.NET Framework 3.5 (包括 .NET 2.0 和 3.0)” 复选框，选择“确定”，然后重启计算机。

   ![使用控制面板安装 .NET](./media/dotnet-control-panel.png)

   无需选择“Windows Communication Foundation (WCF) HTTP 激活”和“Windows Communication Foundation (WCF) 非 HTTP 激活”的子项，除非是需要使用此功能的开发者或服务器管理员。

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a>.NET Framework 3.5 安装疑难解答

安装过程中，你可能会遇到错误 0x800f0906、0x800f0907、0x800f081f 或 0x800F0922，此时请参阅 [.NET Framework 3.5 安装错误：0x800f0906、0x800f0907 或 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09)，了解如何解决这些问题。

如果仍无法解决安装问题，或未连接到 Internet，可以尝试使用 Windows 安装介质进行安装。 有关详细信息，请参阅[使用部署映像服务和管理 (DISM) 部署 .NET Framework 3.5](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism)。 如果没有安装媒体，请参阅[创建适用于 Windows 的安装媒体](https://support.microsoft.com/help/15088/windows-create-installation-media)。
