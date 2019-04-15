---
ms.openlocfilehash: 735278848cb7399e414a128afc650a0a1f882337
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235983"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="90a8b-101">更改 TextBlock 控件父级的 IsEnabled 属性会影响任何子控件</span><span class="sxs-lookup"><span data-stu-id="90a8b-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

|   |   |
|---|---|
|<span data-ttu-id="90a8b-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="90a8b-102">Details</span></span>|<span data-ttu-id="90a8b-103">自 .NET Framework 4.6.2 起，更改 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 控件父级的 <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> 属性会影响 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 控件的任意子控件（例如超链接和按钮）。在 .NET Framework 4.6.1 和更早版本中，<xref:System.Windows.Controls.TextBlock?displayProperty=name> 中的控件并非始终反映 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 父级的 <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> 属性状态。</span><span class="sxs-lookup"><span data-stu-id="90a8b-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> parent.</span></span>|
|<span data-ttu-id="90a8b-104">建议</span><span class="sxs-lookup"><span data-stu-id="90a8b-104">Suggestion</span></span>|<span data-ttu-id="90a8b-105">无。</span><span class="sxs-lookup"><span data-stu-id="90a8b-105">None.</span></span> <span data-ttu-id="90a8b-106">此更改符合 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 控件中各控件的预期行为。</span><span class="sxs-lookup"><span data-stu-id="90a8b-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.</span></span>|
|<span data-ttu-id="90a8b-107">范围</span><span class="sxs-lookup"><span data-stu-id="90a8b-107">Scope</span></span>|<span data-ttu-id="90a8b-108">次要</span><span class="sxs-lookup"><span data-stu-id="90a8b-108">Minor</span></span>|
|<span data-ttu-id="90a8b-109">版本</span><span class="sxs-lookup"><span data-stu-id="90a8b-109">Version</span></span>|<span data-ttu-id="90a8b-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="90a8b-110">4.6.2</span></span>|
|<span data-ttu-id="90a8b-111">类型</span><span class="sxs-lookup"><span data-stu-id="90a8b-111">Type</span></span>|<span data-ttu-id="90a8b-112">运行时</span><span class="sxs-lookup"><span data-stu-id="90a8b-112">Runtime</span></span>|
|<span data-ttu-id="90a8b-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="90a8b-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
