---
title: 在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5
description: 了解如何在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5。
author: rlander
ms.author: mairaw
ms.date: 07/16/2018
ms.openlocfilehash: 7b3b7ca5709008260ea284602a3ed8d2b288c410
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245517"
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="bf19b-103">在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="bf19b-103">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="bf19b-104">必须安装 .NET Framework 3.5，才能在 Windows 10、Windows 8.1 和 Windows 8 上运行应用。</span><span class="sxs-lookup"><span data-stu-id="bf19b-104">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="bf19b-105">对于旧版 Windows，也可以按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="bf19b-105">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="bf19b-106">按需安装.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="bf19b-106">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="bf19b-107">如果尝试运行的应用要求安装 .NET Framework 3.5，则会看到以下配置对话框。</span><span class="sxs-lookup"><span data-stu-id="bf19b-107">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="bf19b-108">选择“安装此功能”，启用 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="bf19b-108">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="bf19b-109">此选项需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="bf19b-109">This option requires an Internet connection.</span></span>

![.NET Framework 安装对话框](./media/dotnet-framework-installation-dialog.jpg)

### <a name="why-am-i-getting-this-pop-up"></a><span data-ttu-id="bf19b-111">为什么我会看到此弹出项？</span><span class="sxs-lookup"><span data-stu-id="bf19b-111">Why am I getting this pop-up?</span></span>

<span data-ttu-id="bf19b-112">.NET Framework 是由 Microsoft 创建，用于提供应用程序运行环境。</span><span class="sxs-lookup"><span data-stu-id="bf19b-112">The .NET Framework is created by Microsoft and provides an environment for running applications.</span></span> <span data-ttu-id="bf19b-113">有多种不同版本。</span><span class="sxs-lookup"><span data-stu-id="bf19b-113">There are different versions available.</span></span> <span data-ttu-id="bf19b-114">许多公司都开发使用 .NET Framework 运行的应用程序，并且这些应用都定目标到具体版本。</span><span class="sxs-lookup"><span data-stu-id="bf19b-114">Many companies develop their apps to run using the .NET Framework, and these apps target a specific version.</span></span> <span data-ttu-id="bf19b-115">如果看到此弹出项，表明尝试运行的应用程序需要 .NET Framework 版本 3.5，但未在系统上安装此版本。</span><span class="sxs-lookup"><span data-stu-id="bf19b-115">If you see this pop-up, you're trying to run an application that requires the .NET Framework version 3.5, but that version is not installed on your system.</span></span>

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="bf19b-116">在控制面板中启用 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="bf19b-116">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="bf19b-117">可以通过 Windows 控制面板启用 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="bf19b-117">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="bf19b-118">此选项需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="bf19b-118">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="bf19b-119">按键盘上的 Windows 键 ![Windows 徽标](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg)，键入“Windows 功能”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="bf19b-119">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="bf19b-120">随即显示“打开或关闭 Windows 功能”对话框。</span><span class="sxs-lookup"><span data-stu-id="bf19b-120">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="bf19b-121">如果弹出提示，选择“.NET Framework 3.5 (包括 .NET 2.0 和 3.0)” 复选框，选择“确定”，然后重启计算机。</span><span class="sxs-lookup"><span data-stu-id="bf19b-121">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![使用控制面板安装 .NET](./media/dotnet-control-panel.png)

   <span data-ttu-id="bf19b-123">无需选择“Windows Communication Foundation (WCF) HTTP 激活”和“Windows Communication Foundation (WCF) 非 HTTP 激活”的子项，除非是需要使用此功能的开发者或服务器管理员。</span><span class="sxs-lookup"><span data-stu-id="bf19b-123">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a><span data-ttu-id="bf19b-124">.NET Framework 3.5 安装疑难解答</span><span class="sxs-lookup"><span data-stu-id="bf19b-124">Troubleshoot the installation of the .NET Framework 3.5</span></span>

<span data-ttu-id="bf19b-125">安装过程中，你可能会遇到错误 0x800f0906、0x800f0907、0x800f081f 或 0x800F0922，此时请参阅 [.NET Framework 3.5 安装错误：0x800f0906、0x800f0907 或 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09)，了解如何解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="bf19b-125">During installation, you may encounter error 0x800f0906, 0x800f0907, 0x800f081f, or 0x800F0922, in which case refer to [.NET Framework 3.5 installation error: 0x800f0906, 0x800f0907, or 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) to see how to resolve these issues.</span></span>

<span data-ttu-id="bf19b-126">如果仍无法解决安装问题，或未连接到 Internet，可以尝试使用 Windows 安装介质进行安装。</span><span class="sxs-lookup"><span data-stu-id="bf19b-126">If you still can't resolve your installation issue or you don't have an Internet connection, you can try installing it using your Windows installation media.</span></span> <span data-ttu-id="bf19b-127">有关详细信息，请参阅[使用部署映像服务和管理 (DISM) 部署 .NET Framework 3.5](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism)。</span><span class="sxs-lookup"><span data-stu-id="bf19b-127">For more information, see [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism).</span></span> <span data-ttu-id="bf19b-128">如果没有安装媒体，请参阅[创建适用于 Windows 的安装媒体](https://support.microsoft.com/help/15088/windows-create-installation-media)。</span><span class="sxs-lookup"><span data-stu-id="bf19b-128">If you don't have the installation media, see [Create installation media for Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span></span>

> [!WARNING]
> <span data-ttu-id="bf19b-129">如果不依赖 Windows 更新作为源来安装 .NET Framework 3.5，则必须确保严格使用来自相同的、对应的 Windows 操作系统版本的源。</span><span class="sxs-lookup"><span data-stu-id="bf19b-129">If you're not relying on Windows Update as the source for installing the .NET Framework 3.5, you must ensure to strictly use sources from the same corresponding Windows operating system version.</span></span> <span data-ttu-id="bf19b-130">使用不对应于相同 Windows 版本的源路径并不会阻止安装与 .NET Framework 3.5 不匹配的版本。</span><span class="sxs-lookup"><span data-stu-id="bf19b-130">Using a source path that doesn't correspond to the same version of Windows won't prevent a mismatched version of .NET Framework 3.5 from being installed.</span></span> <span data-ttu-id="bf19b-131">但是，这会导致系统不受支持且无法提供服务。</span><span class="sxs-lookup"><span data-stu-id="bf19b-131">However, this will cause the system to be in an unsupported and unserviceable state.</span></span>
