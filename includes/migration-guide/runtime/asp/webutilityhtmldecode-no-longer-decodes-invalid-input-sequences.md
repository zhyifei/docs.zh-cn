---
ms.openlocfilehash: dfc1a0d05142861ff1c1b7391126d86e09fa71c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235165"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a><span data-ttu-id="6dc3a-101">WebUtility.HtmlDecode 不再对无效的输入序列进行解码</span><span class="sxs-lookup"><span data-stu-id="6dc3a-101">WebUtility.HtmlDecode no longer decodes invalid input sequences</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6dc3a-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="6dc3a-102">Details</span></span>|<span data-ttu-id="6dc3a-103">默认情况下，解码方法不再将无效的输入序列解码为无效的 UTF-16 字符串。</span><span class="sxs-lookup"><span data-stu-id="6dc3a-103">By default, decoding methods no longer decode an invalid input sequence into an invalid UTF-16 string.</span></span> <span data-ttu-id="6dc3a-104">相反，它们将返回原始的输入。</span><span class="sxs-lookup"><span data-stu-id="6dc3a-104">Instead, they return the original input.</span></span>|
|<span data-ttu-id="6dc3a-105">建议</span><span class="sxs-lookup"><span data-stu-id="6dc3a-105">Suggestion</span></span>|<span data-ttu-id="6dc3a-106">仅当你存储二进制数据而不是字符串中的 UTF-16 数据时，解码器输出中的更改才会起作用。</span><span class="sxs-lookup"><span data-stu-id="6dc3a-106">The change in decoder output should matter only if you store binary data instead of UTF-16 data in strings.</span></span> <span data-ttu-id="6dc3a-107">要显式控制此行为，请将 [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) 元素的 <code>aspnet:AllowRelaxedUnicodeDecoding</code> 特性设置为 <code>true</code> 以启用旧行为，或设置为 <code>false</code> 以启用当前行为。</span><span class="sxs-lookup"><span data-stu-id="6dc3a-107">To explicitly control this behavior, set the <code>aspnet:AllowRelaxedUnicodeDecoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) element to <code>true</code> to enable legacy behavior or to <code>false</code> to enable the current behavior.</span></span>|
|<span data-ttu-id="6dc3a-108">范围</span><span class="sxs-lookup"><span data-stu-id="6dc3a-108">Scope</span></span>|<span data-ttu-id="6dc3a-109">次要</span><span class="sxs-lookup"><span data-stu-id="6dc3a-109">Minor</span></span>|
|<span data-ttu-id="6dc3a-110">版本</span><span class="sxs-lookup"><span data-stu-id="6dc3a-110">Version</span></span>|<span data-ttu-id="6dc3a-111">4.5</span><span class="sxs-lookup"><span data-stu-id="6dc3a-111">4.5</span></span>|
|<span data-ttu-id="6dc3a-112">类型</span><span class="sxs-lookup"><span data-stu-id="6dc3a-112">Type</span></span>|<span data-ttu-id="6dc3a-113">运行时</span><span class="sxs-lookup"><span data-stu-id="6dc3a-113">Runtime</span></span>|
|<span data-ttu-id="6dc3a-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="6dc3a-114">Affected APIs</span></span>|<ul><li><xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType></li></ul>|
