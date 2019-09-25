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
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a>从 .NET Framework 迁移到 .NET Core 3.0 的重大变更

> [!IMPORTANT]
> 本文正在构建中。 这并不是 .NET Core 中断性变更的完整列表。 如需详细了解 .NET Core 重大变更，请参阅 GitHub 上 dotnet/docs 存储库中的各个[重大变更问题](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change)。 

如果要将 Windows 窗体或 Windows Presentation Foundation 应用程序从 .NET Framework 迁移到 .NET Core 3.0，请查看以下主题，了解可能影响你的应用的重大变更：

## <a name="windows-forms"></a>Windows 窗体

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyimages.md)]
