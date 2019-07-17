---
ms.openlocfilehash: e605e0f2636d83745815ec4ed27bf72692f18d15
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802579"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a><span data-ttu-id="a60c8-101">ASP.NET 修复了处理 WebForms CheckBox 控件的 InputAttributes 和 LabelAttributes 的问题</span><span class="sxs-lookup"><span data-stu-id="a60c8-101">ASP.NET Fix handling of InputAttributes and LabelAttributes for WebForms CheckBox control</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a60c8-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="a60c8-102">Details</span></span>|<span data-ttu-id="a60c8-103">对于面向 .NET Framework 4.7.2 及更低版本的应用程序，以编程方式添加到 WebForms <xref:System.Web.UI.WebControls.CheckBox> 控件的 <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> 和 <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> 将在回发后丢失。</span><span class="sxs-lookup"><span data-stu-id="a60c8-103">For applications that target .NET Framework 4.7.2 and earlier versions, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> that are programmatically added to a WebForms <xref:System.Web.UI.WebControls.CheckBox> control are lost after postback.</span></span> <span data-ttu-id="a60c8-104">对于面向 .NET Framework 4.8 或更高版本的应用程序，它们会在回发后保留。</span><span class="sxs-lookup"><span data-stu-id="a60c8-104">For applications that target .NET Framework 4.8 or later versions, they are preserved after postback.</span></span>|
|<span data-ttu-id="a60c8-105">建议</span><span class="sxs-lookup"><span data-stu-id="a60c8-105">Suggestion</span></span>|<span data-ttu-id="a60c8-106">要在回发时还原属性的正确行为，请将 <code>targetFrameworkVersion</code> 设置为 4.8 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a60c8-106">For the correct behavior for restoring attributes on postback, set the <code>targetFrameworkVersion</code> to 4.8 or higher.</span></span> <span data-ttu-id="a60c8-107">例如:</span><span class="sxs-lookup"><span data-stu-id="a60c8-107">For example:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="a60c8-108">将其设置为更低版本或根本不设置会保留旧的错误行为。</span><span class="sxs-lookup"><span data-stu-id="a60c8-108">Setting it lower, or not at all, preserves the old incorrect behavior.</span></span>|
|<span data-ttu-id="a60c8-109">范围</span><span class="sxs-lookup"><span data-stu-id="a60c8-109">Scope</span></span>|<span data-ttu-id="a60c8-110">未知</span><span class="sxs-lookup"><span data-stu-id="a60c8-110">Unknown</span></span>|
|<span data-ttu-id="a60c8-111">Version</span><span class="sxs-lookup"><span data-stu-id="a60c8-111">Version</span></span>|<span data-ttu-id="a60c8-112">4.8</span><span class="sxs-lookup"><span data-stu-id="a60c8-112">4.8</span></span>|
|<span data-ttu-id="a60c8-113">类型</span><span class="sxs-lookup"><span data-stu-id="a60c8-113">Type</span></span>|<span data-ttu-id="a60c8-114">运行时</span><span class="sxs-lookup"><span data-stu-id="a60c8-114">Runtime</span></span>|
|<span data-ttu-id="a60c8-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="a60c8-115">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|

