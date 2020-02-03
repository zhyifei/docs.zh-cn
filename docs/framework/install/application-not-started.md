---
title: 排查“无法启动此应用程序”
description: 了解在出现“无法启动此应用程序”对话框时如何应对。
ms.date: 09/05/2019
ms.openlocfilehash: 864c6ea23e9a048f060eee39d904bd4377be5084
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965901"
---
# <a name="troubleshooting-a-this-application-could-not-be-started-error-message"></a><span data-ttu-id="9ae5b-103">排查“无法启动此应用程序”错误消息</span><span class="sxs-lookup"><span data-stu-id="9ae5b-103">Troubleshooting a 'This application could not be started' error message</span></span>

<span data-ttu-id="9ae5b-104">为 .NET Framework 开发的应用程序通常需要在系统上安装 .NET Framework 的特定版本。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-104">Applications that are developed for the .NET Framework typically require that a specific version of the .NET Framework be installed on your system.</span></span> <span data-ttu-id="9ae5b-105">在某些情况下，你可能会尝试运行应用程序，而不使用已安装的 .NET Framework 版本或所需版本。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-105">In some cases, you may attempt to run an application without either an installed version or the expected version of the .NET Framework present.</span></span> <span data-ttu-id="9ae5b-106">这通常会产生如下错误对话框：</span><span class="sxs-lookup"><span data-stu-id="9ae5b-106">This often produces an error dialog box like the following:</span></span>

![无法启动此应用程序](media/application-not-started/app-could-not-be-started.png)

<span data-ttu-id="9ae5b-108">这通常表示存在以下情况之一：</span><span class="sxs-lookup"><span data-stu-id="9ae5b-108">This typically indicates one of the following conditions:</span></span>

- <span data-ttu-id="9ae5b-109">系统上的 .NET Framework 安装已损坏。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-109">A .NET Framework installation on your system has become corrupted.</span></span>

- <span data-ttu-id="9ae5b-110">无法检测到应用程序所需的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-110">The version of the .NET Framework needed by your application cannot be detected.</span></span>

<span data-ttu-id="9ae5b-111">若要解决此问题以便可以运行应用程序，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9ae5b-111">To address this issue so that you can run your application, do the following:</span></span>

1. <span data-ttu-id="9ae5b-112">下载 [.NET Framework Repair Tool (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135)。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-112">Download the [.NET Framework Repair Tool (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135).</span></span> <span data-ttu-id="9ae5b-113">该工具会在下载完成后自动运行。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-113">The tool runs automatically when the download completes.</span></span>

1. <span data-ttu-id="9ae5b-114">如果 .NET Framework Repair Tool 建议执行任何其他操作，例如下图所示的操作，请选择“下一步”  。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-114">If the .NET Framework Repair Tool recommends any additional action, such as those shown in the following figure, select **Next**.</span></span>

   ![建议的更改](media/application-not-started/repair-tool-recommended-changes.png)

1. <span data-ttu-id="9ae5b-116">.NET Framework Repair Tool 会显示一个对话框，如下图所示，指出更改已完成。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-116">The .NET Framework Repair Tools displays a dialog box shown in the following figure to indicate that changes are complete.</span></span> <span data-ttu-id="9ae5b-117">当尝试重新运行应用程序时，请保持该对话框处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-117">Leave the dialog box open while you to try rerun your application.</span></span> <span data-ttu-id="9ae5b-118">如果 .NET Framework Repair Tool 已识别并更正损坏的 .NET Framework 安装，则应该会成功运行。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-118">This should succeed if the .NET Framework Repair Tool has identified and corrected a corrupted .NET Framework installation.</span></span>

   ![建议的更改](media/application-not-started/repair-tool-changes-complete.png)

1. <span data-ttu-id="9ae5b-120">如果应用程序成功运行，请选择“完成”  按钮。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-120">If your application runs successfully, select the **Finish** button.</span></span> <span data-ttu-id="9ae5b-121">否则，请选择“下一步”  按钮。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-121">Otherwise, select the **Next** button.</span></span>

1. <span data-ttu-id="9ae5b-122">如果选择了“下一步”  按钮，则 .NET Framework 修复工具会显示如下所示的对话框。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-122">If you selected the **Next** button, the .NET Framework Repair Tool displays a dialog box like the following.</span></span> <span data-ttu-id="9ae5b-123">选择“完成”  按钮，将诊断信息发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-123">Select the **Finish** button to send diagnostic information to Microsoft.</span></span>

   ![无法解决问题](media/application-not-started/repair-tool-no-resolution.png)

1. <span data-ttu-id="9ae5b-125">如果仍无法运行应用程序，请安装 Windows 版本支持的最新版本 .NET Framework，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-125">If you still cannot run the application, install the latest version of the .NET Framework supported by your version of Windows, as shown in the following table.</span></span>

   |<span data-ttu-id="9ae5b-126">Windows 版本</span><span class="sxs-lookup"><span data-stu-id="9ae5b-126">Windows version</span></span>|<span data-ttu-id="9ae5b-127">.NET Framework 安装</span><span class="sxs-lookup"><span data-stu-id="9ae5b-127">.NET Framework installation</span></span>|
   |---|---|
   |<span data-ttu-id="9ae5b-128">Windows 10 周年更新及更高版本</span><span class="sxs-lookup"><span data-stu-id="9ae5b-128">Windows 10 Anniversary Update and later versions</span></span>|[<span data-ttu-id="9ae5b-129">.NET Framework 4.8 Runtime</span><span class="sxs-lookup"><span data-stu-id="9ae5b-129">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="9ae5b-130">Windows 10、Windows 10 11 月更新</span><span class="sxs-lookup"><span data-stu-id="9ae5b-130">Windows 10, Windows 10 November Update</span></span>|[<span data-ttu-id="9ae5b-131">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9ae5b-131">.NET Framework 4.6.2</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net462)|
   |<span data-ttu-id="9ae5b-132">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="9ae5b-132">Windows 8.1</span></span>|[<span data-ttu-id="9ae5b-133">.NET Framework 4.8 Runtime</span><span class="sxs-lookup"><span data-stu-id="9ae5b-133">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="9ae5b-134">Windows 8</span><span class="sxs-lookup"><span data-stu-id="9ae5b-134">Windows 8</span></span>|[<span data-ttu-id="9ae5b-135">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="9ae5b-135">.NET Framework 4.6.1</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net461)|
   |<span data-ttu-id="9ae5b-136">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="9ae5b-136">Windows 7 SP1</span></span>|[<span data-ttu-id="9ae5b-137">.NET Framework 4.8 Runtime</span><span class="sxs-lookup"><span data-stu-id="9ae5b-137">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="9ae5b-138">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="9ae5b-138">Windows Vista SP2</span></span>|[<span data-ttu-id="9ae5b-139">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="9ae5b-139">.NET Framework 4.6</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net46)|

   > [!NOTE]
   > <span data-ttu-id="9ae5b-140">.NET Framework 4.8 预安装在 Windows 10 2019 年 5 月更新上。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-140">.NET Framework 4.8 is preinstalled on Windows 10 May 2019 Update.</span></span>

1. <span data-ttu-id="9ae5b-141">尝试启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-141">Attempt to launch the application.</span></span>

1. <span data-ttu-id="9ae5b-142">在某些情况下，可能会显示如下所示的对话框，要求你安装 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-142">In some cases, you may see a dialog box like the following, which asks you to install the .NET Framework 3.5.</span></span> <span data-ttu-id="9ae5b-143">选择“下载并安装此功能”  以安装 .NET Framework 3.5，然后重新启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="9ae5b-143">Select **Download and install this feature** to install the .NET Framework 3.5, then launch the application again.</span></span>

   ![无法解决问题](media/application-not-started/install-3-5.png)

## <a name="see-also"></a><span data-ttu-id="9ae5b-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ae5b-145">See also</span></span>

- [<span data-ttu-id="9ae5b-146">.NET Framework 系统要求</span><span class="sxs-lookup"><span data-stu-id="9ae5b-146">.NET Framework System Requirements</span></span>](../get-started/system-requirements.md)
- [<span data-ttu-id="9ae5b-147">.NET Framework 安装指南</span><span class="sxs-lookup"><span data-stu-id="9ae5b-147">.NET Framework installation guide</span></span>](index.md)
- [<span data-ttu-id="9ae5b-148">安装和卸载 .NET Framework 受阻疑难解答</span><span class="sxs-lookup"><span data-stu-id="9ae5b-148">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](troubleshoot-blocked-installations-and-uninstallations.md)
