---
ms.openlocfilehash: 9631e64bb403a3fe7b1b91e8ac592b57ce8068d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937068"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a><span data-ttu-id="68f6e-101">不支持 DoNotSupportSelectAllShortcutInMultilineTextBox 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="68f6e-101">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>

<span data-ttu-id="68f6e-102">已在 .NET Framework 4.6.1 中引入 `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` 兼容性开关，但它在 .NET Core 3.0 上的 Windows 窗体中尚不受支持。</span><span class="sxs-lookup"><span data-stu-id="68f6e-102">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="68f6e-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="68f6e-103">Change description</span></span>

<span data-ttu-id="68f6e-104">自 .NET Framework 4.6.1 起，在 <xref:System.Windows.Forms.TextBox> 控件中选择 <kbd>Ctrl</kbd> + <kbd>A</kbd> 快捷键会选中所有文本。</span><span class="sxs-lookup"><span data-stu-id="68f6e-104">Starting with .NET Framework 4.6.1, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key in a <xref:System.Windows.Forms.TextBox> control selected all text.</span></span> <span data-ttu-id="68f6e-105">在 .NET Framework 4.6 及更低版本中，如果 [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) 和 <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> 属性都设置为 `true`，则选择 <kbd>Ctrl</kbd> + <kbd>A</kbd> 快捷键没法选中全部文本。</span><span class="sxs-lookup"><span data-stu-id="68f6e-105">In .NET Framework 4.6 and previous versions, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key failed to select all text if the [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) and <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> properties were both set to `true`.</span></span> <span data-ttu-id="68f6e-106">为保留原始行为，已在 .NET Framework 4.6.1 中引入 `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` 兼容性开关。</span><span class="sxs-lookup"><span data-stu-id="68f6e-106">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch was introduced in .NET Framework 4.6.1 to retain the original behavior.</span></span> <span data-ttu-id="68f6e-107">有关更多信息，请参见<xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="68f6e-107">For more information see <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="68f6e-108">.NET Core 中尚不支持 `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` 开关。</span><span class="sxs-lookup"><span data-stu-id="68f6e-108">In .NET Core, the `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="68f6e-109">引入的版本</span><span class="sxs-lookup"><span data-stu-id="68f6e-109">Version introduced</span></span>

<span data-ttu-id="68f6e-110">3.0 预览版 9</span><span class="sxs-lookup"><span data-stu-id="68f6e-110">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="68f6e-111">建议操作</span><span class="sxs-lookup"><span data-stu-id="68f6e-111">Recommended action</span></span>

<span data-ttu-id="68f6e-112">删除此开关。</span><span class="sxs-lookup"><span data-stu-id="68f6e-112">Remove the switch.</span></span> <span data-ttu-id="68f6e-113">此开关不受支持，且未提供替代功能。</span><span class="sxs-lookup"><span data-stu-id="68f6e-113">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="68f6e-114">类别</span><span class="sxs-lookup"><span data-stu-id="68f6e-114">Category</span></span>

<span data-ttu-id="68f6e-115">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="68f6e-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="68f6e-116">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="68f6e-116">Affected APIs</span></span>

- <span data-ttu-id="68f6e-117">None</span><span class="sxs-lookup"><span data-stu-id="68f6e-117">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
