---
title: "在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5"
description: "了解如何在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5。"
author: rlander
ms.author: mairaw
ms.date: 11/27/2017
ms.topic: article
ms.prod: .net-framework
ms.workload:
- dotnet
ms.openlocfilehash: e81008eca3019860789db548d40998a7a7565d31
ms.sourcegitcommit: cec0525b2121c36198379525e69aa5388266db5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2018
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="cd02f-103">在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="cd02f-103">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="cd02f-104">必须安装 .NET Framework 3.5，才能在 Windows 10、Windows 8.1 和 Windows 8 上运行应用。</span><span class="sxs-lookup"><span data-stu-id="cd02f-104">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="cd02f-105">对于旧版 Windows，也可以按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="cd02f-105">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="cd02f-106">按需安装.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="cd02f-106">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="cd02f-107">如果尝试运行的应用要求安装 .NET Framework 3.5，则会看到以下配置对话框。</span><span class="sxs-lookup"><span data-stu-id="cd02f-107">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="cd02f-108">选择“安装此功能”，启用 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="cd02f-108">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="cd02f-109">此选项需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="cd02f-109">This option requires an Internet connection.</span></span>

![.NET Framework 安装对话框](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="cd02f-111">在控制面板中启用 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="cd02f-111">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="cd02f-112">可以通过 Windows 控制面板启用 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="cd02f-112">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="cd02f-113">此选项需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="cd02f-113">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="cd02f-114">按键盘上的 Windows 键 ![Windows 徽标](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg)，键入“Windows 功能”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="cd02f-114">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="cd02f-115">随即显示“打开或关闭 Windows 功能”对话框。</span><span class="sxs-lookup"><span data-stu-id="cd02f-115">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="cd02f-116">如果弹出提示，选择“.NET Framework 3.5 (包括 .NET 2.0 和 3.0)” 复选框，选择“确定”，然后重启计算机。</span><span class="sxs-lookup"><span data-stu-id="cd02f-116">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![使用控制面板安装 .NET](./media/dotnet-control-panel.png)

   <span data-ttu-id="cd02f-118">无需选择“Windows Communication Foundation (WCF) HTTP 激活”和“Windows Communication Foundation (WCF) 非 HTTP 激活”的子项，除非是需要使用此功能的开发者或服务器管理员。</span><span class="sxs-lookup"><span data-stu-id="cd02f-118">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a><span data-ttu-id="cd02f-119">.NET Framework 3.5 安装疑难解答</span><span class="sxs-lookup"><span data-stu-id="cd02f-119">Troubleshoot the installation of the .NET Framework 3.5</span></span>

<span data-ttu-id="cd02f-120">安装过程中，你可能会遇到错误 0x800f0906、0x800f0907、0x800f081f 或 0x800F0922，此时请参阅 [.NET Framework 3.5 安装错误：0x800f0906、0x800f0907 或 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09)，了解如何解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="cd02f-120">During installation, you may encounter error 0x800f0906, 0x800f0907, 0x800f081f, or 0x800F0922, in which case refer to [.NET Framework 3.5 installation error: 0x800f0906, 0x800f0907, or 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) to see how to resolve these issues.</span></span>

<span data-ttu-id="cd02f-121">如果前文中介绍的所有方法无效，或如果你没有 Internet 连接，则需要使用 Windows 安装媒体。</span><span class="sxs-lookup"><span data-stu-id="cd02f-121">If any of the methods discussed in the previous article fail or if you don't have an Internet connection, it's necessary to use your Windows installation media.</span></span> <span data-ttu-id="cd02f-122">有关详细信息，请参阅[使用部署映像服务和管理 (DISM) 部署 .NET Framework 3.5](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism)。</span><span class="sxs-lookup"><span data-stu-id="cd02f-122">For more information, see [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism).</span></span> <span data-ttu-id="cd02f-123">如果没有安装媒体，请参阅[创建适用于 Windows 的安装媒体](https://support.microsoft.com/help/15088/windows-create-installation-media)。</span><span class="sxs-lookup"><span data-stu-id="cd02f-123">If you don't have the installation media, see [Create installation media for Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span></span>
