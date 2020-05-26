---
ms.openlocfilehash: ab8d801f3cdcfbeb6de20146754b26e3713d7dd6
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702454"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="2059e-101">WinForms 方法现在会引发 ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="2059e-101">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="2059e-102">某些 Windows 窗体方法现在将针对 null 参数引发 <xref:System.ArgumentNullException>，而之前它们会引发 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="2059e-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2059e-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="2059e-103">Change description</span></span>

<span data-ttu-id="2059e-104">以前，如果传递 null 参数，某些 Windows 窗体方法将引发 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="2059e-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="2059e-105">从 .NET 5.0 开始，这些方法现在将针对 null 参数引发 <xref:System.ArgumentNullException>。</span><span class="sxs-lookup"><span data-stu-id="2059e-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments instead.</span></span>

<span data-ttu-id="2059e-106">引发 <xref:System.ArgumentNullException> 符合 .NET 运行时的行为。</span><span class="sxs-lookup"><span data-stu-id="2059e-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="2059e-107">它还通过清楚地指示参数为 null 和具体参数来改进调试体验。</span><span class="sxs-lookup"><span data-stu-id="2059e-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2059e-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="2059e-108">Version introduced</span></span>

<span data-ttu-id="2059e-109">.NET 5.0 预览版 1</span><span class="sxs-lookup"><span data-stu-id="2059e-109">.NET 5.0 Preview 1</span></span>\
<span data-ttu-id="2059e-110">.NET 5.0 预览版 2</span><span class="sxs-lookup"><span data-stu-id="2059e-110">.NET 5.0 Preview 2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2059e-111">建议操作</span><span class="sxs-lookup"><span data-stu-id="2059e-111">Recommended action</span></span>

<span data-ttu-id="2059e-112">如果调用这些方法中的任何一种，你的代码当前都会针对 null 参数捕获 <xref:System.NullReferenceException>，请改为捕获 <xref:System.ArgumentNullException>。</span><span class="sxs-lookup"><span data-stu-id="2059e-112">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="2059e-113">此外，请考虑更新代码，以避免将 null 参数传递到列出的方法。</span><span class="sxs-lookup"><span data-stu-id="2059e-113">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="2059e-114">类别</span><span class="sxs-lookup"><span data-stu-id="2059e-114">Category</span></span>

<span data-ttu-id="2059e-115">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="2059e-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2059e-116">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="2059e-116">Affected APIs</span></span>

<span data-ttu-id="2059e-117">从 .NET 5.0 预览版 1 开始：</span><span class="sxs-lookup"><span data-stu-id="2059e-117">Starting in .NET 5.0 Preview 1:</span></span>

- <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)>
- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType>

<span data-ttu-id="2059e-118">从 .NET 5.0 预览版 2 开始：</span><span class="sxs-lookup"><span data-stu-id="2059e-118">Starting in .NET 5.0 Preview 2:</span></span>

- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType>
- <span data-ttu-id="2059e-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType>（仅适用于 <xref:System.IO.Stream> 参数）</span><span class="sxs-lookup"><span data-stu-id="2059e-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (for the <xref:System.IO.Stream> parameter only)</span></span>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.Control.ControlCollection.#ctor(System.Windows.Forms.Control)`
- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.TableLayoutControlCollection.#ctor(System.Windows.Forms.TableLayoutPanel)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)`
- `M:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)`
- `M:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)`

-->
