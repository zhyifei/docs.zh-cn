---
ms.openlocfilehash: 6dc3669433804a4524c18d5a932f9879343ab508
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803299"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="12354-101">默认情况下，禁用 OData URL 中的 Replace 方法</span><span class="sxs-lookup"><span data-stu-id="12354-101">The Replace method in OData URLs is disabled by default</span></span>

|   |   |
|---|---|
|<span data-ttu-id="12354-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="12354-102">Details</span></span>|<span data-ttu-id="12354-103">从 .NET Framework 4.5 开始，默认会禁用 OData URL 中的 Replace 方法。</span><span class="sxs-lookup"><span data-stu-id="12354-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="12354-104">在禁用 OData Replace 时（现在是默认设置），任何包含 replace 函数的用户请求（这并不常见）都将失败。</span><span class="sxs-lookup"><span data-stu-id="12354-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>|
|<span data-ttu-id="12354-105">建议</span><span class="sxs-lookup"><span data-stu-id="12354-105">Suggestion</span></span>|<span data-ttu-id="12354-106">如果需要 replace 方法（这并不常见），可通过配置设置 (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>) 重新启用。</span><span class="sxs-lookup"><span data-stu-id="12354-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span></span> <span data-ttu-id="12354-107">但是，启用的 replace 方法可能会带来安全漏洞，应仅在仔细检查后使用。</span><span class="sxs-lookup"><span data-stu-id="12354-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>|
|<span data-ttu-id="12354-108">范围</span><span class="sxs-lookup"><span data-stu-id="12354-108">Scope</span></span>|<span data-ttu-id="12354-109">边缘</span><span class="sxs-lookup"><span data-stu-id="12354-109">Edge</span></span>|
|<span data-ttu-id="12354-110">版本</span><span class="sxs-lookup"><span data-stu-id="12354-110">Version</span></span>|<span data-ttu-id="12354-111">4.5</span><span class="sxs-lookup"><span data-stu-id="12354-111">4.5</span></span>|
|<span data-ttu-id="12354-112">类型</span><span class="sxs-lookup"><span data-stu-id="12354-112">Type</span></span>|<span data-ttu-id="12354-113">运行时</span><span class="sxs-lookup"><span data-stu-id="12354-113">Runtime</span></span>|
|<span data-ttu-id="12354-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="12354-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
