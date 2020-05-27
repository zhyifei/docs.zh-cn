---
ms.openlocfilehash: 4a34a64eba72ea24c1d830566565ce4fbee8e5b7
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720946"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a><span data-ttu-id="a27c7-101">如果显示工具提示，则不引发 CellFormatting 事件</span><span class="sxs-lookup"><span data-stu-id="a27c7-101">CellFormatting event not raised if tooltip is shown</span></span>

<span data-ttu-id="a27c7-102">现在，当鼠标悬停和通过键盘选择时，<xref:System.Windows.Forms.DataGridView> 将显示单元格的文本和错误工具提示。</span><span class="sxs-lookup"><span data-stu-id="a27c7-102">A <xref:System.Windows.Forms.DataGridView> now shows a cell's text and error tooltips when hovered by a mouse and when selected via the keyboard.</span></span> <span data-ttu-id="a27c7-103">如果显示工具提示，则不会引发 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 事件。</span><span class="sxs-lookup"><span data-stu-id="a27c7-103">If a tooltip is shown, the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event is not raised.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a27c7-104">更改描述</span><span class="sxs-lookup"><span data-stu-id="a27c7-104">Change description</span></span>

<span data-ttu-id="a27c7-105">在 .NET Core 3.1 之前，将 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> 属性设置为 `true` 的 <xref:System.Windows.Forms.DataGridView> 会在鼠标悬停在单元格上方时显示单元格文本和错误的工具提示。</span><span class="sxs-lookup"><span data-stu-id="a27c7-105">Prior to .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that had the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` showed a tooltip for a cell's text and errors when the cell was hovered by a mouse.</span></span> <span data-ttu-id="a27c7-106">之前，通过键盘选择单元格时（例如通过使用 Tab 键、快捷键或箭头导航），不显示工具提示。</span><span class="sxs-lookup"><span data-stu-id="a27c7-106">Tooltips were not shown when a cell was selected via the keyboard (for example, by using the Tab key, shortcut keys, or arrow navigation).</span></span> <span data-ttu-id="a27c7-107">如果用户编辑了单元格，然后在 <xref:System.Windows.Forms.DataGridView> 仍处于编辑模式时将鼠标悬停在未设置 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> 属性的单元格上，则会引发 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件，对要在单元格中显示的单元格文本进行格式化。</span><span class="sxs-lookup"><span data-stu-id="a27c7-107">If the user edited a cell, and then, while the <xref:System.Windows.Forms.DataGridView> was still in edit mode, hovered over a cell that did not have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set, a <xref:System.Windows.Forms.DataGridView.CellFormatting> event was raised to format the cell's text for display in the cell.</span></span>

<span data-ttu-id="a27c7-108">为满足辅助功能标准，自 .NET Core 3.1 起，将 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> 属性设置为 `true` 的 <xref:System.Windows.Forms.DataGridView> 不仅在鼠标悬停在单元格上时会显示单元格文本和错误的工具提示，而且在通过键盘选择单元格时也会显示。</span><span class="sxs-lookup"><span data-stu-id="a27c7-108">To meet accessibility standards, starting in .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that has the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` shows tooltips for a cell's text and errors not only when the cell is hovered, but also when it's selected via the keyboard.</span></span> <span data-ttu-id="a27c7-109">由于这一变更，如果鼠标在 <xref:System.Windows.Forms.DataGridView> 处于编辑模式时悬停在未设置 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> 属性的单元格上，不会引发 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件  。</span><span class="sxs-lookup"><span data-stu-id="a27c7-109">As a consequence of this change, the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is *not* raised when cells that don't have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set are hovered while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span> <span data-ttu-id="a27c7-110">不引发该事件的原因是鼠标悬停的单元格的内容显示为工具提示，而不是显示在单元格中。</span><span class="sxs-lookup"><span data-stu-id="a27c7-110">The event is not raised because the content of the hovered cell is shown as a tooltip instead of being displayed in the cell.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a27c7-111">引入的版本</span><span class="sxs-lookup"><span data-stu-id="a27c7-111">Version introduced</span></span>

<span data-ttu-id="a27c7-112">3.1</span><span class="sxs-lookup"><span data-stu-id="a27c7-112">3.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a27c7-113">建议操作</span><span class="sxs-lookup"><span data-stu-id="a27c7-113">Recommended action</span></span>

<span data-ttu-id="a27c7-114">当 <xref:System.Windows.Forms.DataGridView> 处于编辑模式时，对依赖 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件的所有代码进行重构。</span><span class="sxs-lookup"><span data-stu-id="a27c7-114">Refactor any code that depends on the <xref:System.Windows.Forms.DataGridView.CellFormatting> event while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span>

#### <a name="category"></a><span data-ttu-id="a27c7-115">类别</span><span class="sxs-lookup"><span data-stu-id="a27c7-115">Category</span></span>

<span data-ttu-id="a27c7-116">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="a27c7-116">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a27c7-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="a27c7-117">Affected APIs</span></span>

<span data-ttu-id="a27c7-118">None</span><span class="sxs-lookup"><span data-stu-id="a27c7-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
