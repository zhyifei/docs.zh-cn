### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="7d228-101">WPF 文本框默认撤消限制是 100</span><span class="sxs-lookup"><span data-stu-id="7d228-101">WPF TextBox defaults to undo limit of 100</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7d228-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="7d228-102">Details</span></span>|<span data-ttu-id="7d228-103">在 .NET Framework 4.5 中，WPF 文本框的默认撤消限制是 100（.NET Framework 4.0 则没有限制）</span><span class="sxs-lookup"><span data-stu-id="7d228-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>|
|<span data-ttu-id="7d228-104">建议</span><span class="sxs-lookup"><span data-stu-id="7d228-104">Suggestion</span></span>|<span data-ttu-id="7d228-105">如果 100 的撤消限制过低，可使用 <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit> 显式设置该限制</span><span class="sxs-lookup"><span data-stu-id="7d228-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>|
|<span data-ttu-id="7d228-106">范围</span><span class="sxs-lookup"><span data-stu-id="7d228-106">Scope</span></span>|<span data-ttu-id="7d228-107">边缘</span><span class="sxs-lookup"><span data-stu-id="7d228-107">Edge</span></span>|
|<span data-ttu-id="7d228-108">版本</span><span class="sxs-lookup"><span data-stu-id="7d228-108">Version</span></span>|<span data-ttu-id="7d228-109">4.5</span><span class="sxs-lookup"><span data-stu-id="7d228-109">4.5</span></span>|
|<span data-ttu-id="7d228-110">类型</span><span class="sxs-lookup"><span data-stu-id="7d228-110">Type</span></span>|<span data-ttu-id="7d228-111">运行时</span><span class="sxs-lookup"><span data-stu-id="7d228-111">Runtime</span></span>|
|<span data-ttu-id="7d228-112">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="7d228-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

