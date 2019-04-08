---
ms.openlocfilehash: 38dd0b33202b8e8f1708ebec689333bd5367c93f
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760609"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="0079d-101">更改 TextBlock 控件父级的 IsEnabled 属性会影响任何子控件</span><span class="sxs-lookup"><span data-stu-id="0079d-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0079d-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="0079d-102">Details</span></span>|<span data-ttu-id="0079d-103">自 .NET Framework 4.6.2 起，更改 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 控件父级的 <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> 属性会影响 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 控件的任意子控件（例如超链接和按钮）。在 .NET Framework 4.6.1 和更早版本中，<xref:System.Windows.Controls.TextBlock?displayProperty=name> 中的控件并非始终反映 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 父级的 <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> 属性状态。</span><span class="sxs-lookup"><span data-stu-id="0079d-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> parent.</span></span>|
|<span data-ttu-id="0079d-104">建议</span><span class="sxs-lookup"><span data-stu-id="0079d-104">Suggestion</span></span>|<span data-ttu-id="0079d-105">无。</span><span class="sxs-lookup"><span data-stu-id="0079d-105">None.</span></span> <span data-ttu-id="0079d-106">此更改符合 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 控件中各控件的预期行为。</span><span class="sxs-lookup"><span data-stu-id="0079d-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.</span></span>|
|<span data-ttu-id="0079d-107">范围</span><span class="sxs-lookup"><span data-stu-id="0079d-107">Scope</span></span>|<span data-ttu-id="0079d-108">次要</span><span class="sxs-lookup"><span data-stu-id="0079d-108">Minor</span></span>|
|<span data-ttu-id="0079d-109">版本</span><span class="sxs-lookup"><span data-stu-id="0079d-109">Version</span></span>|<span data-ttu-id="0079d-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="0079d-110">4.6.2</span></span>|
|<span data-ttu-id="0079d-111">类型</span><span class="sxs-lookup"><span data-stu-id="0079d-111">Type</span></span>|<span data-ttu-id="0079d-112">运行时</span><span class="sxs-lookup"><span data-stu-id="0079d-112">Runtime</span></span>|
|<span data-ttu-id="0079d-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="0079d-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|

