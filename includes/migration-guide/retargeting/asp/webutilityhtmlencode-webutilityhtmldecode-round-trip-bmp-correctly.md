---
ms.openlocfilehash: ca662b57fae9b1d0d41290f3052f71bca66e9bf3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774308"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a><span data-ttu-id="4b746-101">WebUtility.HtmlEncode 和 WebUtility.HtmlDecode 正确往返 BMP</span><span class="sxs-lookup"><span data-stu-id="4b746-101">WebUtility.HtmlEncode and WebUtility.HtmlDecode round-trip BMP correctly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4b746-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="4b746-102">Details</span></span>|<span data-ttu-id="4b746-103">对于面向 .NET Framework 4.5 的应用程序，当基本多语言平面 (BMP) 外的字符传递给 <xref:System.Net.WebUtility.HtmlDecode(System.String)> 方法时，这些字符可正确往返。</span><span class="sxs-lookup"><span data-stu-id="4b746-103">For applications that target the .NET Framework 4.5, characters that are outside the Basic Multilingual Plane (BMP) round-trip correctly when they are passed to the <xref:System.Net.WebUtility.HtmlDecode(System.String)> methods.</span></span>|
|<span data-ttu-id="4b746-104">建议</span><span class="sxs-lookup"><span data-stu-id="4b746-104">Suggestion</span></span>|<span data-ttu-id="4b746-105">此更改不应影响当前应用程序，但要还原原始行为，请将 <code>&lt;httpRuntime&gt;</code> 元素的 <code>targetFramework</code> 属性设置为除 &quot;4.5&quot; 以外的字符串。</span><span class="sxs-lookup"><span data-stu-id="4b746-105">This change should have no effect on current applications, but to restore the original behavior, set the <code>targetFramework</code> attribute of the <code>&lt;httpRuntime&gt;</code> element to a string other than &quot;4.5&quot;.</span></span> <span data-ttu-id="4b746-106">还可以设置 <code>unicodeEncodingConformance</code> 配置元素的 <code>unicodeDecodingConformance</code> 和 <code>&lt;webUtility&gt;</code> 特性以单独控制 .NET Framework 的目标版本的行为。</span><span class="sxs-lookup"><span data-stu-id="4b746-106">You can also set the <code>unicodeEncodingConformance</code> and <code>unicodeDecodingConformance</code> attributes of the <code>&lt;webUtility&gt;</code> configuration element to control this behavior independently of the targeted version of the .NET Framework.</span></span>|
|<span data-ttu-id="4b746-107">范围</span><span class="sxs-lookup"><span data-stu-id="4b746-107">Scope</span></span>|<span data-ttu-id="4b746-108">边缘</span><span class="sxs-lookup"><span data-stu-id="4b746-108">Edge</span></span>|
|<span data-ttu-id="4b746-109">版本</span><span class="sxs-lookup"><span data-stu-id="4b746-109">Version</span></span>|<span data-ttu-id="4b746-110">4.5</span><span class="sxs-lookup"><span data-stu-id="4b746-110">4.5</span></span>|
|<span data-ttu-id="4b746-111">类型</span><span class="sxs-lookup"><span data-stu-id="4b746-111">Type</span></span>|<span data-ttu-id="4b746-112">重定目标</span><span class="sxs-lookup"><span data-stu-id="4b746-112">Retargeting</span></span>|
|<span data-ttu-id="4b746-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="4b746-113">Affected APIs</span></span>|<ul><li><xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li></ul>|
