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
# <a name="install-the-net-framework-on-windows-10-and-windows-server-2016"></a><span data-ttu-id="c8dce-104">在 Windows 10 和 Windows Server 2016 上安装.NET Framework</span><span class="sxs-lookup"><span data-stu-id="c8dce-104">Install the .NET Framework on Windows 10 and Windows Server 2016</span></span>

<span data-ttu-id="c8dce-105">在 Windows 上运行许多应用程序需要.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="c8dce-105">The .NET Framework is required to run many applications on Windows.</span></span> <span data-ttu-id="c8dce-106">此文章中的说明应帮助你安装需要的.NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="c8dce-106">The instructions in this article should help you install the .NET Framework versions that you need.</span></span> <span data-ttu-id="c8dce-107">[.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47)是最新的可用版本。</span><span class="sxs-lookup"><span data-stu-id="c8dce-107">The [.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) is the latest available version.</span></span>

<span data-ttu-id="c8dce-108">你可能已到达此页上尝试运行应用程序和类似于以下计算机上看到一个对话框后：</span><span class="sxs-lookup"><span data-stu-id="c8dce-108">You may have arrived on this page after trying to run an application and seeing a dialog on your machine similar to the following one:</span></span>

![无法启动此应用程序](./media/this-application-could-not-be-started.png)

## <a name="net-framework-471"></a><span data-ttu-id="c8dce-110">.NET framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="c8dce-110">.NET Framework 4.7.1</span></span>

<span data-ttu-id="c8dce-111">.NET Framework 4.7.1 是附带的：</span><span class="sxs-lookup"><span data-stu-id="c8dce-111">The .NET Framework 4.7.1 is included with:</span></span>

* [<span data-ttu-id="c8dce-112">Windows 10 秋季创建者更新 （版本 1709年）</span><span class="sxs-lookup"><span data-stu-id="c8dce-112">Windows 10 Fall Creators Update (version 1709)</span></span>](https://www.microsoft.com/software-download/windows10)
* [<span data-ttu-id="c8dce-113">Windows Server 2016 （版本 1709年）</span><span class="sxs-lookup"><span data-stu-id="c8dce-113">Windows Server 2016 (version 1709)</span></span>](https://docs.microsoft.com/windows-server/get-started/get-started-with-1709)

> [!div class="button"]
[<span data-ttu-id="c8dce-114">下载.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="c8dce-114">Download .NET Framework 4.7.1</span></span>](https://www.microsoft.com/net/download/thank-you/net471?utm_source=ms-docs&utm_medium=referral)

<span data-ttu-id="c8dce-115">[.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47)可以用于运行 for 4.7.1 通过.NET Framework 4.0 生成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8dce-115">The [.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) can be used to run applications built for the .NET Framework 4.0 through 4.7.1.</span></span>

<span data-ttu-id="c8dce-116">你可以安装[.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47)上：</span><span class="sxs-lookup"><span data-stu-id="c8dce-116">You can install the [.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47) on:</span></span>

* <span data-ttu-id="c8dce-117">Windows 10 创建者更新 （版本 1703年）</span><span class="sxs-lookup"><span data-stu-id="c8dce-117">Windows 10 Creators Update (version 1703)</span></span>
* <span data-ttu-id="c8dce-118">Windows 10 周年日更新 （版本 1607年）</span><span class="sxs-lookup"><span data-stu-id="c8dce-118">Windows 10 Anniversary Update (version 1607)</span></span>
* <span data-ttu-id="c8dce-119">Windows 2016 Server</span><span class="sxs-lookup"><span data-stu-id="c8dce-119">Windows Server 2016</span></span>

<span data-ttu-id="c8dce-120">不支持.NET Framework 4.7.1:</span><span class="sxs-lookup"><span data-stu-id="c8dce-120">The .NET Framework 4.7.1 is not supported on:</span></span>

* <span data-ttu-id="c8dce-121">Windows 10 1507</span><span class="sxs-lookup"><span data-stu-id="c8dce-121">Windows 10 1507</span></span>
* <span data-ttu-id="c8dce-122">Windows 10 1511</span><span class="sxs-lookup"><span data-stu-id="c8dce-122">Windows 10 1511</span></span>

<span data-ttu-id="c8dce-123">如果你使用的 Windows 10 1507年或 1511年，并且你想要安装.NET Framework 4.7.1，首先需要升级到更高版本的 Windows 10 版本。</span><span class="sxs-lookup"><span data-stu-id="c8dce-123">If you're using Windows 10 1507 or 1511 and you want to install the .NET Framework 4.7.1, you first need to upgrade to a later Windows 10 version.</span></span>

## <a name="net-framework-461"></a><span data-ttu-id="c8dce-124">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="c8dce-124">.NET Framework 4.6.1</span></span>

<span data-ttu-id="c8dce-125">[.NET Framework 4.6.1](https://www.microsoft.com/download/details.aspx?id=49981)是最新支持.NET Framework 版本上 Windows 10 1507年和 1511年。</span><span class="sxs-lookup"><span data-stu-id="c8dce-125">The [.NET Framework 4.6.1](https://www.microsoft.com/download/details.aspx?id=49981) is the latest supported .NET Framework version on Windows 10 1507 and 1511.</span></span>

<span data-ttu-id="c8dce-126">.NET Framework 4.6.1 支持用于通过 4.6.1 的.NET Framework 4.0 生成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8dce-126">The .NET Framework 4.6.1 supports apps built for the .NET Framework 4.0 through 4.6.1.</span></span>

## <a name="net-framework-35"></a><span data-ttu-id="c8dce-127">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="c8dce-127">.NET Framework 3.5</span></span>

<span data-ttu-id="c8dce-128">请按照说明操作，[在 Windows 10 上安装 .NET Framework 3.5](dotnet-35-windows-10.md)。</span><span class="sxs-lookup"><span data-stu-id="c8dce-128">Follow the instructions to install the [.NET Framework 3.5 on Windows 10](dotnet-35-windows-10.md).</span></span>

<span data-ttu-id="c8dce-129">.NET Framework 3.5 支持为.NET Framework 1.0 到 3.5 生成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8dce-129">The .NET Framework 3.5 supports apps built for the .NET Framework 1.0 through 3.5.</span></span>

## <a name="additional-information"></a><span data-ttu-id="c8dce-130">其他信息</span><span class="sxs-lookup"><span data-stu-id="c8dce-130">Additional information</span></span>

<span data-ttu-id="c8dce-131">.NET framework 4.x 版本是早期版本的就地更新。</span><span class="sxs-lookup"><span data-stu-id="c8dce-131">.NET Framework 4.x versions are in-place updates to earlier versions.</span></span> <span data-ttu-id="c8dce-132">这意味着以下：</span><span class="sxs-lookup"><span data-stu-id="c8dce-132">That means the following:</span></span>

- <span data-ttu-id="c8dce-133">只能有一个版本的.NET framework 4.x 安装您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="c8dce-133">You can only have one version of the .NET Framework 4.x installed on your machine.</span></span>

- <span data-ttu-id="c8dce-134">如果已安装的更高版本的情况下，不能在您的计算机上安装.NET Framework 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="c8dce-134">You cannot install an earlier version of the .NET Framework on your machine if a later version is already installed.</span></span>

- <span data-ttu-id="c8dce-135">.NET framework 4.x 版本可以用于运行.NET Framework 4.0，通过该版本的生成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8dce-135">4.x versions of the .NET Framework can be used to run applications built for the .NET Framework 4.0 through that version.</span></span> <span data-ttu-id="c8dce-136">例如，.NET Framework 4.7 可用来运行用于通过 4.7.NET Framework 4.0 生成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8dce-136">For example, .NET Framework 4.7 can be used to run applications built for the .NET Framework 4.0 through 4.7.</span></span> <span data-ttu-id="c8dce-137">最新版本 (.NET Framework 4.7.1) 可用来运行生成的应用程序将从 4.0 的.NET framework 的所有版本。</span><span class="sxs-lookup"><span data-stu-id="c8dce-137">The latest version (the .NET Framework 4.7.1) can be used to run applications built will all versions of the .NET Framework starting with 4.0.</span></span>

<span data-ttu-id="c8dce-138">有关可供下载的.NET framework 的所有版本的列表，请参阅[.NET 下载](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral)页。</span><span class="sxs-lookup"><span data-stu-id="c8dce-138">For a list of all the versions of the .NET Framework available to download, see the [.NET Downloads](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) page.</span></span>

## <a name="help"></a><span data-ttu-id="c8dce-139">帮助</span><span class="sxs-lookup"><span data-stu-id="c8dce-139">Help</span></span>

<span data-ttu-id="c8dce-140">如果无法获取安装了.NET Framework 的正确版本，则可以[联系 Microsoft 寻求帮助](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help)。</span><span class="sxs-lookup"><span data-stu-id="c8dce-140">If you cannot get the correct version of the .NET Framework installed, you can [contact Microsoft for help](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8dce-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8dce-141">See also</span></span>

<span data-ttu-id="c8dce-142">[.NET 下载](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) </span><span class="sxs-lookup"><span data-stu-id="c8dce-142">[.NET Downloads](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) </span></span>  
<span data-ttu-id="c8dce-143">[安装和卸载 .NET Framework 受阻疑难解答](troubleshoot-blocked-installations-and-uninstallations.md) </span><span class="sxs-lookup"><span data-stu-id="c8dce-143">[Troubleshoot blocked .NET Framework installations and uninstallations](troubleshoot-blocked-installations-and-uninstallations.md) </span></span>  
[<span data-ttu-id="c8dce-144">安装.NET Framework 为开发人员</span><span class="sxs-lookup"><span data-stu-id="c8dce-144">Install the .NET Framework for developers</span></span>](guide-for-developers.md)