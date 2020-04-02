---
title: 在 Windows 8、Windows 8.1 或 Windows 10 上运行 .NET Framework 1.1 应用
description: 介绍如何适应需要在许多版本的 Windows 操作系统上不再受支持的 .NET Framework 1.1 的应用程序。
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
ms.openlocfilehash: 6d1cb2f9251bba96d0a378bf4dbab9f7da267037
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111785"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a><span data-ttu-id="ad061-103">在 Windows 8、Windows 8.1 或 Windows 10 上运行 .NET Framework 1.1 应用</span><span class="sxs-lookup"><span data-stu-id="ad061-103">Run .NET Framework 1.1 apps on Windows 8, Windows 8.1, or Windows 10</span></span>

<span data-ttu-id="ad061-104">Windows 8、Windows 8.1、Windows Server 2012、Windows Server 2012 R2 或 Windows 10 操作系统上不支持 .NET Framework 1.1。</span><span class="sxs-lookup"><span data-stu-id="ad061-104">.NET Framework 1.1 is not supported on the Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2, or the Windows 10 operating systems.</span></span> <span data-ttu-id="ad061-105">在某些情况下，运行应用需要 .NET Framework 1.1。</span><span class="sxs-lookup"><span data-stu-id="ad061-105">In some cases, .NET Framework 1.1 is required for an app to run.</span></span> <span data-ttu-id="ad061-106">这时，请联系独立软件供应商 (ISV) 以升级该应用，使其可在 .NET Framework 3.5 SP1 或更高版本上运行。</span><span class="sxs-lookup"><span data-stu-id="ad061-106">In those cases, contact your independent software vendor (ISV) to have the app upgraded to run on .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="ad061-107">有关详细信息，请参阅[从 .NET Framework 1.1 迁移](../migration-guide/migrating-from-the-net-framework-1-1.md)。</span><span class="sxs-lookup"><span data-stu-id="ad061-107">For more information, see [Migrating from .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md).</span></span>

## <a name="install-net-framework-11-from-a-cd-or-download-center"></a><span data-ttu-id="ad061-108">从 CD 或下载中心安装 .NET Framework 1.1</span><span class="sxs-lookup"><span data-stu-id="ad061-108">Install .NET Framework 1.1 from a CD or download center</span></span>

<span data-ttu-id="ad061-109">在 Windows 8、Windows 8.1、Windows Server 2012、Windows Server 2012 R2 或 Windows 10 上，无法从 CD 或下载中心手动安装 .NET Framework 1.1。</span><span class="sxs-lookup"><span data-stu-id="ad061-109">It isn't possible to manually install .NET Framework 1.1 on Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2, or Windows 10 from a CD or download center.</span></span> <span data-ttu-id="ad061-110">这种做法不再受支持。</span><span class="sxs-lookup"><span data-stu-id="ad061-110">It's no longer supported.</span></span> <span data-ttu-id="ad061-111">如果尝试安装包，会显示以下错误消息：“无法继续执行安装程序，因为此版本的 .NET Framework 与以前安装的某个版本不兼容。”</span><span class="sxs-lookup"><span data-stu-id="ad061-111">If you try to install the package, the following error message is displayed: "Setup cannot continue because this version of the .NET Framework is incompatible with a previously installed one."</span></span> <span data-ttu-id="ad061-112">若要解决此问题，请安装 [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22)。</span><span class="sxs-lookup"><span data-stu-id="ad061-112">To solve this problem, install [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22).</span></span> <span data-ttu-id="ad061-113">此版本包括 Windows 8、Windows 8.1 和 Windows 10 上支持的 .NET Framework 2.0（.NET Framework 1.1 的后续版本）。</span><span class="sxs-lookup"><span data-stu-id="ad061-113">This version includes .NET Framework 2.0 (the release that follows .NET Framework 1.1), which is supported on Windows 8, Windows 8.1, and Windows 10.</span></span> <span data-ttu-id="ad061-114">应始终先尝试安装应用，确定它是否会自动更新到 .NET Framework 的更高版本。</span><span class="sxs-lookup"><span data-stu-id="ad061-114">You should always try to install the app first to determine if it will automatically be updated to a later version of .NET Framework.</span></span> <span data-ttu-id="ad061-115">如果不会这样，请与你的 ISV 联系以更新应用。</span><span class="sxs-lookup"><span data-stu-id="ad061-115">If it doesn't, contact your ISV for an app update.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad061-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad061-116">See also</span></span>

- [<span data-ttu-id="ad061-117">从 .NET Framework 1.1 迁移</span><span class="sxs-lookup"><span data-stu-id="ad061-117">Migrating from the .NET Framework 1.1</span></span>](../migration-guide/migrating-from-the-net-framework-1-1.md)
- [<span data-ttu-id="ad061-118">在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="ad061-118">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>](dotnet-35-windows-10.md)
