---
ms.openlocfilehash: e2d63d85adce64db6e00b62ec17f55ae71ce3052
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235201"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="e052e-101">从 CellEditEnding 处理程序调用 DataGrid.CommitEdit 将丢失焦点</span><span class="sxs-lookup"><span data-stu-id="e052e-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e052e-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="e052e-102">Details</span></span>|<span data-ttu-id="e052e-103">从 <xref:System.Windows.Controls.DataGrid?displayProperty=name> 的一个 <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> 事件处理程序中调用 <xref:System.Windows.Controls.DataGrid.CommitEdit> 导致 <xref:System.Windows.Controls.DataGrid?displayProperty=name> 失去焦点。</span><span class="sxs-lookup"><span data-stu-id="e052e-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=name>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=name> to lose focus.</span></span>|
|<span data-ttu-id="e052e-104">建议</span><span class="sxs-lookup"><span data-stu-id="e052e-104">Suggestion</span></span>|<span data-ttu-id="e052e-105">此 bug 已在 .NET Framework 4.5.2 中得到修复，因此升级 .NET Framework 可避免出现此问题。</span><span class="sxs-lookup"><span data-stu-id="e052e-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="e052e-106">或者，可通过在调用 <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name> 后显式重新选择 <xref:System.Windows.Controls.DataGrid?displayProperty=name> 避免出现此问题。</span><span class="sxs-lookup"><span data-stu-id="e052e-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=name> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>.</span></span>|
|<span data-ttu-id="e052e-107">范围</span><span class="sxs-lookup"><span data-stu-id="e052e-107">Scope</span></span>|<span data-ttu-id="e052e-108">边缘</span><span class="sxs-lookup"><span data-stu-id="e052e-108">Edge</span></span>|
|<span data-ttu-id="e052e-109">版本</span><span class="sxs-lookup"><span data-stu-id="e052e-109">Version</span></span>|<span data-ttu-id="e052e-110">4.5</span><span class="sxs-lookup"><span data-stu-id="e052e-110">4.5</span></span>|
|<span data-ttu-id="e052e-111">类型</span><span class="sxs-lookup"><span data-stu-id="e052e-111">Type</span></span>|<span data-ttu-id="e052e-112">运行时</span><span class="sxs-lookup"><span data-stu-id="e052e-112">Runtime</span></span>|
|<span data-ttu-id="e052e-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="e052e-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
