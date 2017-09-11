---
title: "在 Windows 8、Windows 8.1 和 Windows 10 上安装 .NET Framework 3.5"
ms.date: 05/26/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework 3.5, installing on Windows 8
- Windows 8, installing .NET Framework 3.5
ms.assetid: 3eab3eb4-4573-42ac-98f8-36fb2c22c7d5
caps.latest.revision: 69
author: mairaw
ms.author: mairaw
ms.translationtype: HT
ms.sourcegitcommit: 20b0c1b36f705deb2f46ef4ab23653f829faf7ca
ms.openlocfilehash: 8a0395e28c01363eed27f327ea623feb4832c844
ms.contentlocale: zh-cn
ms.lasthandoff: 08/08/2017

---

# <a name="install-the-net-framework-35-on-windows-8-windows-81-and-windows-10"></a><span data-ttu-id="c9fd1-102">在 Windows 8、Windows 8.1 和 Windows 10 上安装 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="c9fd1-102">Install the .NET Framework 3.5 on Windows 8, Windows 8.1, and Windows 10</span></span>

<span data-ttu-id="c9fd1-103">.NET Framework 是在 Windows 上运行的多个应用不可缺少的一部分，并且对这些应用运行发挥着同样的功能。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-103">The .NET Framework is an integral part of many apps running on Windows and provides common functionality for those apps to run.</span></span> <span data-ttu-id="c9fd1-104">对开发人员而言，.NET Framework 提供了一个用于构建应用的一致的编程模型。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-104">For developers, the .NET Framework provides a consistent programming model for building apps.</span></span> <span data-ttu-id="c9fd1-105">如果你使用的是 Windows 操作系统，则你的计算机上可能已安装 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-105">If you're using the Windows operating system, the .NET Framework may already be installed on your computer.</span></span> <span data-ttu-id="c9fd1-106">具体而言， [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 包含于 [!INCLUDE[win8](../../../includes/win8-md.md)]， [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 包含于 [!INCLUDE[win81](../../../includes/win81-md.md)] ，而 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 包含于 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-106">Specifically, the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is included with [!INCLUDE[win8](../../../includes/win8-md.md)], the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] is included with [!INCLUDE[win81](../../../includes/win81-md.md)], and the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] is included with Windows 10.</span></span>  
  
<span data-ttu-id="c9fd1-107">但是，.NET Framework 3.5 不会随 [!INCLUDE[win8](../../../includes/win8-md.md)]、 [!INCLUDE[win81](../../../includes/win81-md.md)] 或 Windows 10 自动安装，而必须单独启用才能运行依赖它的应用。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-107">The .NET Framework 3.5, however, is not automatically installed with [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], or Windows 10, and must be separately enabled to run apps that depend on it.</span></span> <span data-ttu-id="c9fd1-108">此操作必须通过 Windows 更新进行，它可以使用以下三种方法之一进行调用。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-108">This must happen through Windows Update, which is invoked in one of three ways.</span></span> <span data-ttu-id="c9fd1-109">以下所有操作都需要 Internet 连接：</span><span class="sxs-lookup"><span data-stu-id="c9fd1-109">All of these require an Internet connection:</span></span>  
  
- [<span data-ttu-id="c9fd1-110">按需安装.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="c9fd1-110">Install the .NET Framework 3.5 on Demand</span></span>](#OnDemand)  
  
- [<span data-ttu-id="c9fd1-111">在控制面板中启用 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="c9fd1-111">Enable the .NET Framework 3.5 in Control Panel</span></span>](#ControlPanel)  
  
- <span data-ttu-id="c9fd1-112">[下载 .NET Framework 3.5 安装程序](http://www.microsoft.com/en-us/download/details.aspx?id=21)（注意：这不会直接下载 .NET Framework；它是调用 Windows Update 的安装程序。）</span><span class="sxs-lookup"><span data-stu-id="c9fd1-112">[Download the .NET Framework 3.5 installer](http://www.microsoft.com/en-us/download/details.aspx?id=21) (Note: This does not download the .NET Framework directly; it is an installer that invokes Windows Update.)</span></span>  
  
<span data-ttu-id="c9fd1-113">安装过程中，你可能会遇到错误 0x800f0906、0x800f0907 或 0x800f081f，此时请参阅 [.NET Framework 3.5 安装错误：0x800f0906、0x800f0907 或 0x800f081f](https://support.microsoft.com/en-us/kb/2734782)。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-113">During installation, you may encounter error 0x800f0906, 0x800f0907, or 0x800f081f, in which case refer to [.NET Framework 3.5 installation error: 0x800f0906, 0x800f0907, or 0x800f081f](https://support.microsoft.com/en-us/kb/2734782).</span></span> <span data-ttu-id="c9fd1-114">注意，这些错误可能可以通过安装 [安全更新 3005628](https://support.microsoft.com/kb/3005628)解决。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-114">Note that these are possibly resolved by installing [security update 3005628](https://support.microsoft.com/kb/3005628).</span></span>  
  
<span data-ttu-id="c9fd1-115">如果上述任何方法失败，或如果你没有 Internet 连接，则需要使用 Windows 安装媒体。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-115">If any of the above methods fail or if you do not have an Internet connection, it's necessary to use your Windows installation media.</span></span> <span data-ttu-id="c9fd1-116">有关详细信息，请参阅 [.NET Framework 3.5 安装错误文章](https://support.microsoft.com/en-us/kb/2734782)中错误 0x800f0906 的方法 3。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-116">For details, see Method 3 for error 0x800f0906 in the [.NET Framework 3.5 installation error article](https://support.microsoft.com/en-us/kb/2734782).</span></span> <span data-ttu-id="c9fd1-117">如果没有安装媒体，请参阅[为 Windows 8.1 创建安装媒体](http://windows.microsoft.com/en-US/windows-8/create-reset-refresh-media?woldogcb=0)。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-117">If you don't have installation media, see [Create Installation media for Windows 8.1](http://windows.microsoft.com/en-US/windows-8/create-reset-refresh-media?woldogcb=0).</span></span>  
  
<span data-ttu-id="c9fd1-118">**重要说明：**</span><span class="sxs-lookup"><span data-stu-id="c9fd1-118">**Important notes:**</span></span>
  
- <span data-ttu-id="c9fd1-119">一般情况下，请勿卸载计算机上的任何 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-119">In general, don't uninstall any versions of the .NET Framework from your computer.</span></span> <span data-ttu-id="c9fd1-120">不同的应用程序依赖于不同的 Framework 版本，并且一台计算机上可共存多个版本的 NET Framework。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-120">Different apps depend on different versions of the framework, and multiple versions of the .NET Framework can coexist on a single computer at the same time.</span></span>  
  
- <span data-ttu-id="c9fd1-121">针对版本 2.0 和 3.0 构建的应用程序也可以使用.NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-121">The .NET Framework 3.5 is also used by apps built for versions 2.0 and 3.0.</span></span>  
  
- <span data-ttu-id="c9fd1-122">在安装 .NET Framework 3.5 之前安装 Windows 语言包可能会导致 .NET Framework 3.5 安装失败。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-122">Installing a Windows language pack before installing the .NET Framework 3.5 may cause the .NET Framework 3.5 installation to fail.</span></span> <span data-ttu-id="c9fd1-123">在安装任何 Windows 语言包之前，请安装 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-123">Install the .NET Framework 3.5 before installing any Windows language packs.</span></span>  
  
- <span data-ttu-id="c9fd1-124">Windows CardSpace 不随 [!INCLUDE[win8](../../../includes/win8-md.md)]上的 .NET Framework 3.5 提供。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-124">Windows CardSpace is not available with the .NET Framework 3.5 on [!INCLUDE[win8](../../../includes/win8-md.md)].</span></span>  
  
- <span data-ttu-id="c9fd1-125">由于安装 .NET Framework 3.5 所必须采用的方法十分复杂，很遗憾不能提供可以独立于 Windows 更新运行的单独的独立安装程序。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-125">Because of complications around how the .NET Framework 3.5 must be installed, it's unfortunately not possible to provide a separate, standalone installer that can run independently of Windows Update.</span></span> <span data-ttu-id="c9fd1-126">如果其他所有方法都失败，则如之前所述，必须使用安装媒体。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-126">If all other methods fail, you must resort to installation media as described earlier.</span></span>  
  
<a name="OnDemand"></a>   
## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="c9fd1-127">按需安装.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="c9fd1-127">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="c9fd1-128">如果应用程序需要 .NET Framework 3.5，但没有在你的计算机上找到启用的版本，则在安装时或在首次运行该应用程序时，将显示以下消息框。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-128">If an app requires the .NET Framework 3.5 but doesn't find that version enabled on your computer, it displays the following message box, either during installation or when you run the app for the first time.</span></span> <span data-ttu-id="c9fd1-129">在消息框中，选择 **“安装此功能”** 可启用 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-129">In the message box, choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="c9fd1-130">此选项需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-130">This option requires an Internet connection.</span></span>  
  
<span data-ttu-id="c9fd1-131">![在 Windows 8 上安装 .NET Framework 3.5 的对话框](../../../docs/framework/deployment/media/installdialog.png "installdialog")</span><span class="sxs-lookup"><span data-stu-id="c9fd1-131">![Dialog box for 3.5 install on Windows 8](../../../docs/framework/deployment/media/installdialog.png "installdialog")</span></span>  
  
<a name="ControlPanel"></a>   
## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="c9fd1-132">在控制面板中启用 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="c9fd1-132">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="c9fd1-133">可通过控制面板启用 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-133">You can enable the .NET Framework 3.5 through Control Panel.</span></span> <span data-ttu-id="c9fd1-134">此选项需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-134">This option requires an Internet connection.</span></span>  
  
1. <span data-ttu-id="c9fd1-135">按键盘上的 Windows 键 ![Windows 徽标](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-135">Press the Windows key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard.</span></span> <span data-ttu-id="c9fd1-136">键入“Windows 功能”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-136">Type "Windows Features" and press Enter.</span></span> <span data-ttu-id="c9fd1-137">这将显示“打开或关闭 Windows 功能”  对话框。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-137">This brings up the **Turn Windows features on or off** dialog box.</span></span> <span data-ttu-id="c9fd1-138">或者，打开“控制面板”，单击“程序”项，然后选择“程序和功能”下的“启用或禁用 Windows 功能”。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-138">Alternately, open Control Panel, click on the **Programs** items, and then select **Turn Windows features on or off** under **Programs and Features**.</span></span>  
  
2. <span data-ttu-id="c9fd1-139">如果弹出提示，选择“.NET Framework 3.5 (包括 .NET 2.0 和 3.0)” 复选框，选择“确定”，然后重启计算机。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-139">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>  
  
<span data-ttu-id="c9fd1-140">无需选择“Windows Communication Foundation (WCF) HTTP 激活”的子项，除非你是需要 WCF 脚本和处理程序映射功能的开发人员。</span><span class="sxs-lookup"><span data-stu-id="c9fd1-140">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP activation** unless you're a developer who requires WCF script and handler mapping functionality.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c9fd1-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9fd1-141">See also</span></span>

[<span data-ttu-id="c9fd1-142">安装指南</span><span class="sxs-lookup"><span data-stu-id="c9fd1-142">Installation Guide</span></span>](../../../docs/framework/get-started/index.md)

