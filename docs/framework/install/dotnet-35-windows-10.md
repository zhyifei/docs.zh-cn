---
title: "在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5"
description: "了解如何在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5。"
author: rlander
ms.author: mairaw
ms.date: 11/27/2017
ms.topic: article
ms.prod: .net-framework
ms.workload: dotnet
ms.openlocfilehash: ca56bfb37cee60ab014dada7b5d72b74b375dd7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5

必须安装 .NET Framework 3.5，才能在 Windows 10、Windows 8.1 和 Windows 8 上运行应用。 对于旧版 Windows，也可以按照以下说明操作。

## <a name="install-the-net-framework-35-on-demand"></a>按需安装.NET Framework 3.5

如果尝试运行的应用要求安装 .NET Framework 3.5，则会看到以下配置对话框。 选择“安装此功能”，启用 .NET Framework 3.5。 此选项需要 Internet 连接。

![.NET Framework 安装对话框](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a>在控制面板中启用 .NET Framework 3.5

可以通过 Windows 控制面板启用 .NET Framework 3.5。 此选项需要 Internet 连接。

1. 按键盘上的 Windows 键 ![Windows 徽标](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg)，键入“Windows 功能”，然后按 Enter。 随即显示“打开或关闭 Windows 功能”对话框。

2. 如果弹出提示，选择“.NET Framework 3.5 (包括 .NET 2.0 和 3.0)” 复选框，选择“确定”，然后重启计算机。

   ![使用控制面板安装 .NET](./media/dotnet-control-panel.png)

   无需选择“Windows Communication Foundation (WCF) HTTP 激活”和“Windows Communication Foundation (WCF) 非 HTTP 激活”的子项，除非是需要使用此功能的开发者或服务器管理员。

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a>.NET Framework 3.5 安装疑难解答

安装过程中，你可能会遇到错误 0x800f0906、0x800f0907、0x800f081f 或 0x800F0922，此时请参阅 [.NET Framework 3.5 安装错误：0x800f0906、0x800f0907 或 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09)，了解如何解决这些问题。

如果前文中介绍的所有方法无效，或如果你没有 Internet 连接，则需要使用 Windows 安装媒体。 有关详细信息，请参阅[使用部署映像服务和管理 (DISM) 部署 .NET Framework 3.5](https://technet.microsoft.com/library/Dn482069.aspx)。 如果没有安装媒体，请参阅[创建适用于 Windows 的安装媒体](https://support.microsoft.com/help/15088/windows-create-installation-media)。