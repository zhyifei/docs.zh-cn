---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379532"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="41806-101">WPF 文本框选定文本在文本框处于非活动状态时，将显示其他颜色</span><span class="sxs-lookup"><span data-stu-id="41806-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

|   |   |
|---|---|
|<span data-ttu-id="41806-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="41806-102">Details</span></span>|<span data-ttu-id="41806-103">在 .NET Framework 4.5 中，当 WPF 文本框控件处于非活动状态（该控件没有焦点）时，文本框中选定文本所显示的颜色与该控件处于活动状态时所显示的颜色不同。</span><span class="sxs-lookup"><span data-stu-id="41806-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>|
|<span data-ttu-id="41806-104">建议</span><span class="sxs-lookup"><span data-stu-id="41806-104">Suggestion</span></span>|<span data-ttu-id="41806-105">可通过将 <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> 属性设置为 <code>false</code> 来还原以前的 (.NET Framework 4.0) 行为。</span><span class="sxs-lookup"><span data-stu-id="41806-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>|
|<span data-ttu-id="41806-106">范围</span><span class="sxs-lookup"><span data-stu-id="41806-106">Scope</span></span>|<span data-ttu-id="41806-107">边缘</span><span class="sxs-lookup"><span data-stu-id="41806-107">Edge</span></span>|
|<span data-ttu-id="41806-108">版本</span><span class="sxs-lookup"><span data-stu-id="41806-108">Version</span></span>|<span data-ttu-id="41806-109">4.5</span><span class="sxs-lookup"><span data-stu-id="41806-109">4.5</span></span>|
|<span data-ttu-id="41806-110">类型</span><span class="sxs-lookup"><span data-stu-id="41806-110">Type</span></span>|<span data-ttu-id="41806-111">运行时</span><span class="sxs-lookup"><span data-stu-id="41806-111">Runtime</span></span>|
|<span data-ttu-id="41806-112">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="41806-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
