---
ms.openlocfilehash: e600b8249096eecb13f63ea00343a771a8c12b60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804502"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="b078d-101">HtmlTextWriter 未正确呈现 `<br/>` 元素</span><span class="sxs-lookup"><span data-stu-id="b078d-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b078d-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="b078d-102">Details</span></span>|<span data-ttu-id="b078d-103">从 .NET Framework 4.6 开始，调用带有 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> 的 <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> 和 <code>&lt;BR /&gt;</code> 将正确插入唯一 <code>&lt;BR /&gt;</code>（而非两个）</span><span class="sxs-lookup"><span data-stu-id="b078d-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a <code>&lt;BR /&gt;</code> element will correctly insert only one <code>&lt;BR /&gt;</code> (instead of two)</span></span>|
|<span data-ttu-id="b078d-104">建议</span><span class="sxs-lookup"><span data-stu-id="b078d-104">Suggestion</span></span>|<span data-ttu-id="b078d-105">如果应用依赖于多余的 <code>&lt;BR /&gt;</code> 标记，应再次调用 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)>。</span><span class="sxs-lookup"><span data-stu-id="b078d-105">If an app depended on the extra <code>&lt;BR /&gt;</code> tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="b078d-106">请注意，此行为更改仅影响面向 .NET Framework 4.6 或更高版本的应用，因此另一选项是面向以前版本的 .NET Framework 以便获取旧行为。</span><span class="sxs-lookup"><span data-stu-id="b078d-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>|
|<span data-ttu-id="b078d-107">范围</span><span class="sxs-lookup"><span data-stu-id="b078d-107">Scope</span></span>|<span data-ttu-id="b078d-108">边缘</span><span class="sxs-lookup"><span data-stu-id="b078d-108">Edge</span></span>|
|<span data-ttu-id="b078d-109">Version</span><span class="sxs-lookup"><span data-stu-id="b078d-109">Version</span></span>|<span data-ttu-id="b078d-110">4.6</span><span class="sxs-lookup"><span data-stu-id="b078d-110">4.6</span></span>|
|<span data-ttu-id="b078d-111">类型</span><span class="sxs-lookup"><span data-stu-id="b078d-111">Type</span></span>|<span data-ttu-id="b078d-112">重定目标</span><span class="sxs-lookup"><span data-stu-id="b078d-112">Retargeting</span></span>|
|<span data-ttu-id="b078d-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="b078d-113">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|
