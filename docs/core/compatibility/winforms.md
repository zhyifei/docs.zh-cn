---
title: Windows 窗体重大更改
description: 列出适用于 .NET Core 的 Windows 窗体中的中断性变更。
ms.date: 01/08/2020
ms.openlocfilehash: 7fba78382d011bc9d489924fa185a44e598c5a76
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398009"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="29256-103">Windows 窗体中的中断性变更</span><span class="sxs-lookup"><span data-stu-id="29256-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="29256-104">已在 .NET Core 的版本 3.0 中添加 Windows 窗体支持。</span><span class="sxs-lookup"><span data-stu-id="29256-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="29256-105">本文按引入中断性变更的 .NET Core 版本列出了 Windows 窗体的中断性变更。</span><span class="sxs-lookup"><span data-stu-id="29256-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="29256-106">如果要从 .NET Framework 或 .NET Core 的早期版本（3.0 或更高版本）升级 Windows 窗体应用，本文能为你提供帮助。</span><span class="sxs-lookup"><span data-stu-id="29256-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="29256-107">本页记录了以下中断性变更：</span><span class="sxs-lookup"><span data-stu-id="29256-107">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="29256-108">已删除的控件</span><span class="sxs-lookup"><span data-stu-id="29256-108">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="29256-109">如果显示工具提示，则不引发 CellFormatting 事件</span><span class="sxs-lookup"><span data-stu-id="29256-109">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="29256-110">Control.DefaultFont 已更改为 Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="29256-110">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="29256-111">FolderBrowserDialog 的现代化</span><span class="sxs-lookup"><span data-stu-id="29256-111">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="29256-112">已从一些 Windows 窗体类型中删除 SerializableAttribute</span><span class="sxs-lookup"><span data-stu-id="29256-112">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="29256-113">不支持 AllowUpdateChildControlIndexForTabControls 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="29256-113">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="29256-114">不支持 DomainUpDown.UseLegacyScrolling 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="29256-114">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="29256-115">不支持 DoNotLoadLatestRichEditControl 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="29256-115">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="29256-116">不支持 DoNotSupportSelectAllShortcutInMultilineTextBox 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="29256-116">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="29256-117">不支持 DontSupportReentrantFilterMessage 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="29256-117">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="29256-118">不支持 EnableVisualStyleValidation 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="29256-118">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="29256-119">不支持 UseLegacyContextMenuStripSourceControlValue 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="29256-119">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="29256-120">不支持 UseLegacyImages 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="29256-120">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)
- [<span data-ttu-id="29256-121">更改 AccessibleObject.RuntimeIDFirstItem 的访问权限</span><span class="sxs-lookup"><span data-stu-id="29256-121">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [<span data-ttu-id="29256-122">已 Windows 窗体中删除重复的 API</span><span class="sxs-lookup"><span data-stu-id="29256-122">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms)

## <a name="net-core-31"></a><span data-ttu-id="29256-123">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="29256-123">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="29256-124">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="29256-124">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a><span data-ttu-id="29256-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29256-125">See also</span></span>

- [<span data-ttu-id="29256-126">将 Windows 窗体应用移植到 .NET Core</span><span class="sxs-lookup"><span data-stu-id="29256-126">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
