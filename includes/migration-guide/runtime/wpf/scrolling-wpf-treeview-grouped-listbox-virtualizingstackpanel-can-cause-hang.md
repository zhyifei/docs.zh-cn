---
ms.openlocfilehash: 0887379fb23e9e66c6cc55a3774545162634c3f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236683"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="a9b6f-101">在 VirtualizingStackPanel 中滚动 WPF TreeView 或分组的 ListBox 可能导致暂停</span><span class="sxs-lookup"><span data-stu-id="a9b6f-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a9b6f-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="a9b6f-102">Details</span></span>|<span data-ttu-id="a9b6f-103">在 .NET Framework v4.5 中，如果视区中存在边距（例如在 <xref:System.Windows.Controls.TreeView?displayProperty=name> 的项目之间或在 ItemsPresenter 元素上），则在虚拟化堆叠面板中滚动 WPF <xref:System.Windows.Controls.TreeView?displayProperty=name> 可能会导致暂停。</span><span class="sxs-lookup"><span data-stu-id="a9b6f-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=name> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=name>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="a9b6f-104">此外，在某些情况下，即使没有边距，视图中不同大小的项目也可能会导致不稳定性。</span><span class="sxs-lookup"><span data-stu-id="a9b6f-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>|
|<span data-ttu-id="a9b6f-105">建议</span><span class="sxs-lookup"><span data-stu-id="a9b6f-105">Suggestion</span></span>|<span data-ttu-id="a9b6f-106">升级到 .NET Framework 4.5.1 可避免此 bug 出现。</span><span class="sxs-lookup"><span data-stu-id="a9b6f-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="a9b6f-107">或者，如果包含的所有项目大小相同，可从虚拟化堆叠面板的视图集合（例如 <xref:System.Windows.Controls.TreeView?displayProperty=name>）中删除边距。</span><span class="sxs-lookup"><span data-stu-id="a9b6f-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=name>s) within virtualized stack panels if all contained items are the same size.</span></span>|
|<span data-ttu-id="a9b6f-108">范围</span><span class="sxs-lookup"><span data-stu-id="a9b6f-108">Scope</span></span>|<span data-ttu-id="a9b6f-109">主要</span><span class="sxs-lookup"><span data-stu-id="a9b6f-109">Major</span></span>|
|<span data-ttu-id="a9b6f-110">版本</span><span class="sxs-lookup"><span data-stu-id="a9b6f-110">Version</span></span>|<span data-ttu-id="a9b6f-111">4.5</span><span class="sxs-lookup"><span data-stu-id="a9b6f-111">4.5</span></span>|
|<span data-ttu-id="a9b6f-112">类型</span><span class="sxs-lookup"><span data-stu-id="a9b6f-112">Type</span></span>|<span data-ttu-id="a9b6f-113">运行时</span><span class="sxs-lookup"><span data-stu-id="a9b6f-113">Runtime</span></span>|
|<span data-ttu-id="a9b6f-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="a9b6f-114">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
