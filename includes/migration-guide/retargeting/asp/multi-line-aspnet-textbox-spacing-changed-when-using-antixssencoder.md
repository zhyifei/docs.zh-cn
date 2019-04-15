---
ms.openlocfilehash: e2bca42daebd25667ab2f312d5e59089b986503c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234607"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="28419-101">使用 AntiXSSEncoder 时，多行 ASP.Net 文本框间距已更改</span><span class="sxs-lookup"><span data-stu-id="28419-101">Multi-line ASP.Net TextBox spacing changed when using AntiXSSEncoder</span></span>

|   |   |
|---|---|
|<span data-ttu-id="28419-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="28419-102">Details</span></span>|<span data-ttu-id="28419-103">在 .NET Framework 4.0 中，如果使用 <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>，则多余行将插入回发的多行文本框中的各行之间。</span><span class="sxs-lookup"><span data-stu-id="28419-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>.</span></span> <span data-ttu-id="28419-104">在 .NET Framework 4.5 中，不包括这些多余的换行符，仅在 Web 应用面向 .NET Framework 4.5 时才可包含</span><span class="sxs-lookup"><span data-stu-id="28419-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>|
|<span data-ttu-id="28419-105">建议</span><span class="sxs-lookup"><span data-stu-id="28419-105">Suggestion</span></span>|<span data-ttu-id="28419-106">请注意，重定向到 .NET Framework 4.5 的 4.0 Web 应用可能改进了多行文本框，从而不再插入多余的换行符。</span><span class="sxs-lookup"><span data-stu-id="28419-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="28419-107">如果不需要这样做，当应用在 .NET Framework 4.5 上运行时，通过面向 .NET Framework 4.0 可使用旧行为。</span><span class="sxs-lookup"><span data-stu-id="28419-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>|
|<span data-ttu-id="28419-108">范围</span><span class="sxs-lookup"><span data-stu-id="28419-108">Scope</span></span>|<span data-ttu-id="28419-109">次要</span><span class="sxs-lookup"><span data-stu-id="28419-109">Minor</span></span>|
|<span data-ttu-id="28419-110">版本</span><span class="sxs-lookup"><span data-stu-id="28419-110">Version</span></span>|<span data-ttu-id="28419-111">4.5</span><span class="sxs-lookup"><span data-stu-id="28419-111">4.5</span></span>|
|<span data-ttu-id="28419-112">类型</span><span class="sxs-lookup"><span data-stu-id="28419-112">Type</span></span>|<span data-ttu-id="28419-113">重定目标</span><span class="sxs-lookup"><span data-stu-id="28419-113">Retargeting</span></span>|
