---
title: .NET Framework 到 .NET Core 3.0 的重大变更 - .NET Core
description: 列出了 Windows 窗体和 Windows Presentation Foundation 的从 .NET Framework 到 .NET Core 3.0 的重大变更。
ms.date: 09/10/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c658c5bce7a2554bba83f2779a73d9d6af01a342
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "71151537"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a><span data-ttu-id="b11b4-103">从 .NET Framework 迁移到 .NET Core 3.0 的重大变更</span><span class="sxs-lookup"><span data-stu-id="b11b4-103">Breaking changes for migration from .NET Framework to .NET Core 3.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b11b4-104">本文正在构建中。</span><span class="sxs-lookup"><span data-stu-id="b11b4-104">This article is under construction.</span></span> <span data-ttu-id="b11b4-105">这并不是 .NET Core 中断性变更的完整列表。</span><span class="sxs-lookup"><span data-stu-id="b11b4-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="b11b4-106">如需详细了解 .NET Core 重大变更，请参阅 GitHub 上 dotnet/docs 存储库中的各个[重大变更问题](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change)。</span><span class="sxs-lookup"><span data-stu-id="b11b4-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="b11b4-107">如果要将 Windows 窗体或 Windows Presentation Foundation 应用程序从 .NET Framework 迁移到 .NET Core 3.0，请查看以下主题，了解可能影响你的应用的重大变更：</span><span class="sxs-lookup"><span data-stu-id="b11b4-107">If you are migrating a Windows Forms or Windows Presentation Foundation application from .NET Framework to .NET Core 3.0, review the following topics for breaking changes that may affect your app:</span></span>

## <a name="windows-forms"></a><span data-ttu-id="b11b4-108">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="b11b4-108">Windows Forms</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyimages.md)]
