---
ms.openlocfilehash: de79182e326082786c1e0691f8888e30cd410f5d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235072"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="52308-101">WPF 文本框默认撤消限制是 100</span><span class="sxs-lookup"><span data-stu-id="52308-101">WPF TextBox defaults to undo limit of 100</span></span>

|   |   |
|---|---|
|<span data-ttu-id="52308-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="52308-102">Details</span></span>|<span data-ttu-id="52308-103">在 .NET Framework 4.5 中，WPF 文本框的默认撤消限制是 100（.NET Framework 4.0 则没有限制）</span><span class="sxs-lookup"><span data-stu-id="52308-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>|
|<span data-ttu-id="52308-104">建议</span><span class="sxs-lookup"><span data-stu-id="52308-104">Suggestion</span></span>|<span data-ttu-id="52308-105">如果 100 的撤消限制过低，可使用 <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit> 显式设置该限制</span><span class="sxs-lookup"><span data-stu-id="52308-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>|
|<span data-ttu-id="52308-106">范围</span><span class="sxs-lookup"><span data-stu-id="52308-106">Scope</span></span>|<span data-ttu-id="52308-107">边缘</span><span class="sxs-lookup"><span data-stu-id="52308-107">Edge</span></span>|
|<span data-ttu-id="52308-108">版本</span><span class="sxs-lookup"><span data-stu-id="52308-108">Version</span></span>|<span data-ttu-id="52308-109">4.5</span><span class="sxs-lookup"><span data-stu-id="52308-109">4.5</span></span>|
|<span data-ttu-id="52308-110">类型</span><span class="sxs-lookup"><span data-stu-id="52308-110">Type</span></span>|<span data-ttu-id="52308-111">运行时</span><span class="sxs-lookup"><span data-stu-id="52308-111">Runtime</span></span>|
|<span data-ttu-id="52308-112">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="52308-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
