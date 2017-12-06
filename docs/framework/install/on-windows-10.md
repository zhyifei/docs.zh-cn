---
title: "在 Windows 10 上安装 .NET Framework"
description: "了解如何在 Windows 10 或 Windows Server 2016 上安装 .NET Framework。"
author: rlander
ms.author: mairaw
keywords: ".NET Framework, 安装"
ms.date: 11/17/2017
ms.topic: article
ms.custom: updateeachrelease
ms.prod: .net-framework
ms.openlocfilehash: ff4867c74b4477a0407126833f30941426d4a33a
ms.sourcegitcommit: 7296449e03f747528f9bc59954c74bf4e359cc1e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="install-the-net-framework-on-windows-10-and-windows-server-2016"></a><span data-ttu-id="b966a-104">在 Windows 10 和 Windows Server 2016 上安装 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b966a-104">Install the .NET Framework on Windows 10 and Windows Server 2016</span></span>

<span data-ttu-id="b966a-105">在 Windows 上运行许多应用程序需要 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="b966a-105">The .NET Framework is required to run many applications on Windows.</span></span> <span data-ttu-id="b966a-106">本文中的相关说明可帮助你安装所需的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="b966a-106">The instructions in this article should help you install the .NET Framework versions that you need.</span></span> <span data-ttu-id="b966a-107">[.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) 是可用的最新版本。</span><span class="sxs-lookup"><span data-stu-id="b966a-107">The [.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) is the latest available version.</span></span>

<span data-ttu-id="b966a-108">在尝试运行应用程序后，你可能转到了此页并在计算机上看到一个对话框，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b966a-108">You may have arrived on this page after trying to run an application and seeing a dialog on your machine similar to the following one:</span></span>

![无法启动此应用程序](./media/this-application-could-not-be-started.png)

## <a name="net-framework-471"></a><span data-ttu-id="b966a-110">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="b966a-110">.NET Framework 4.7.1</span></span>

<span data-ttu-id="b966a-111">.NET Framework 4.7.1 随附：</span><span class="sxs-lookup"><span data-stu-id="b966a-111">The .NET Framework 4.7.1 is included with:</span></span>

* [<span data-ttu-id="b966a-112">Windows 10 Fall Creators Update（版本 1709）</span><span class="sxs-lookup"><span data-stu-id="b966a-112">Windows 10 Fall Creators Update (version 1709)</span></span>](https://www.microsoft.com/software-download/windows10)
* [<span data-ttu-id="b966a-113">Windows Server 2016（版本 1709）</span><span class="sxs-lookup"><span data-stu-id="b966a-113">Windows Server 2016 (version 1709)</span></span>](https://docs.microsoft.com/windows-server/get-started/get-started-with-1709)

> [!div class="button"]
[<span data-ttu-id="b966a-114">下载 .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="b966a-114">Download .NET Framework 4.7.1</span></span>](https://www.microsoft.com/net/download/thank-you/net471?utm_source=ms-docs&utm_medium=referral)

<span data-ttu-id="b966a-115">[.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) 可用于运行针对 .NET Framework 4.0-4.7.1 生成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b966a-115">The [.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) can be used to run applications built for the .NET Framework 4.0 through 4.7.1.</span></span>

<span data-ttu-id="b966a-116">[.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47) 可安装于：</span><span class="sxs-lookup"><span data-stu-id="b966a-116">You can install the [.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47) on:</span></span>

* <span data-ttu-id="b966a-117">Windows 10 创意者更新（版本 1703）</span><span class="sxs-lookup"><span data-stu-id="b966a-117">Windows 10 Creators Update (version 1703)</span></span>
* <span data-ttu-id="b966a-118">Windows 10 周年更新（版本 1607）</span><span class="sxs-lookup"><span data-stu-id="b966a-118">Windows 10 Anniversary Update (version 1607)</span></span>
* <span data-ttu-id="b966a-119">Windows 2016 Server</span><span class="sxs-lookup"><span data-stu-id="b966a-119">Windows Server 2016</span></span>

<span data-ttu-id="b966a-120">以下系统不支持 .NET Framework 4.7.1：</span><span class="sxs-lookup"><span data-stu-id="b966a-120">The .NET Framework 4.7.1 is not supported on:</span></span>

* <span data-ttu-id="b966a-121">Windows 10 1507</span><span class="sxs-lookup"><span data-stu-id="b966a-121">Windows 10 1507</span></span>
* <span data-ttu-id="b966a-122">Windows 10 1511</span><span class="sxs-lookup"><span data-stu-id="b966a-122">Windows 10 1511</span></span>

<span data-ttu-id="b966a-123">如果正在使用 Windows 10 1507 或 1511，且想要安装 .NET Framework 4.7.1，首先需要升级到较新的 Windows 10 版本。</span><span class="sxs-lookup"><span data-stu-id="b966a-123">If you're using Windows 10 1507 or 1511 and you want to install the .NET Framework 4.7.1, you first need to upgrade to a later Windows 10 version.</span></span>

## <a name="net-framework-462"></a><span data-ttu-id="b966a-124">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="b966a-124">.NET Framework 4.6.2</span></span>

<span data-ttu-id="b966a-125">[.NET Framework 4.6.2](https://www.microsoft.com/en-us/download/details.aspx?id=53345) 是 Windows 10 1507 和 1511 上支持的最新 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="b966a-125">The [.NET Framework 4.6.2](https://www.microsoft.com/en-us/download/details.aspx?id=53345) is the latest supported .NET Framework version on Windows 10 1507 and 1511.</span></span>

<span data-ttu-id="b966a-126">.NET Framework 4.6.2 支持针对 .NET Framework 4.0 到 4.6.2 生成的应用。</span><span class="sxs-lookup"><span data-stu-id="b966a-126">The .NET Framework 4.6.2 supports apps built for the .NET Framework 4.0 through 4.6.2.</span></span>

## <a name="net-framework-35"></a><span data-ttu-id="b966a-127">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="b966a-127">.NET Framework 3.5</span></span>

<span data-ttu-id="b966a-128">请按照说明操作，[在 Windows 10 上安装 .NET Framework 3.5](dotnet-35-windows-10.md)。</span><span class="sxs-lookup"><span data-stu-id="b966a-128">Follow the instructions to install the [.NET Framework 3.5 on Windows 10](dotnet-35-windows-10.md).</span></span>

<span data-ttu-id="b966a-129">.NET Framework 3.5 支持针对 .NET Framework 1.0 到 3.5 生成的应用。</span><span class="sxs-lookup"><span data-stu-id="b966a-129">The .NET Framework 3.5 supports apps built for the .NET Framework 1.0 through 3.5.</span></span>

## <a name="additional-information"></a><span data-ttu-id="b966a-130">其他信息</span><span class="sxs-lookup"><span data-stu-id="b966a-130">Additional information</span></span>

<span data-ttu-id="b966a-131">.NET Framework 4.x 版本是早期版本的就地更新版。</span><span class="sxs-lookup"><span data-stu-id="b966a-131">.NET Framework 4.x versions are in-place updates to earlier versions.</span></span> <span data-ttu-id="b966a-132">这意味着：</span><span class="sxs-lookup"><span data-stu-id="b966a-132">That means the following:</span></span>

- <span data-ttu-id="b966a-133">计算机上只能安装一个版本的 .NET Framework 4.x。</span><span class="sxs-lookup"><span data-stu-id="b966a-133">You can only have one version of the .NET Framework 4.x installed on your machine.</span></span>

- <span data-ttu-id="b966a-134">如果计算机上已安装更高版本，则不能安装 .NET Framework 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="b966a-134">You cannot install an earlier version of the .NET Framework on your machine if a later version is already installed.</span></span>

- <span data-ttu-id="b966a-135">.NET Framework 4.x 版本可用于运行针对 .NET Framework 4.0 到该版本生成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b966a-135">4.x versions of the .NET Framework can be used to run applications built for the .NET Framework 4.0 through that version.</span></span> <span data-ttu-id="b966a-136">例如，.NET Framework 4.7 可用于运行针对 .NET Framework 4.0-4.7 生成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b966a-136">For example, .NET Framework 4.7 can be used to run applications built for the .NET Framework 4.0 through 4.7.</span></span> <span data-ttu-id="b966a-137">最新版本（即 .NET Framework 4.7.1）可用于运行针对从 .NET Framework 4.0 开始的 .NET Framework 的所有版本生成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b966a-137">The latest version (the .NET Framework 4.7.1) can be used to run applications built will all versions of the .NET Framework starting with 4.0.</span></span>

<span data-ttu-id="b966a-138">如需可供下载的 .NET Framework 所有版本的列表，请参阅 [.NET 下载](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral)页。</span><span class="sxs-lookup"><span data-stu-id="b966a-138">For a list of all the versions of the .NET Framework available to download, see the [.NET Downloads](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) page.</span></span>

## <a name="help"></a><span data-ttu-id="b966a-139">帮助</span><span class="sxs-lookup"><span data-stu-id="b966a-139">Help</span></span>

<span data-ttu-id="b966a-140">如果无法确定已安装 .NET Framework 的正确版本，可以[联系 Microsoft 获取帮助](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help)。</span><span class="sxs-lookup"><span data-stu-id="b966a-140">If you cannot get the correct version of the .NET Framework installed, you can [contact Microsoft for help](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help).</span></span>

## <a name="see-also"></a><span data-ttu-id="b966a-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="b966a-141">See also</span></span>

<span data-ttu-id="b966a-142">[.NET 下载](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) </span><span class="sxs-lookup"><span data-stu-id="b966a-142">[.NET Downloads](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) </span></span>  
<span data-ttu-id="b966a-143">[安装和卸载 .NET Framework 受阻疑难解答](troubleshoot-blocked-installations-and-uninstallations.md) </span><span class="sxs-lookup"><span data-stu-id="b966a-143">[Troubleshoot blocked .NET Framework installations and uninstallations](troubleshoot-blocked-installations-and-uninstallations.md) </span></span>  
[<span data-ttu-id="b966a-144">安装面向开发者的 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b966a-144">Install the .NET Framework for developers</span></span>](guide-for-developers.md)