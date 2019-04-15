---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235149"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="189f3-101">不应在自定义功能文件中使用 IPad，因为它现在是浏览器功能</span><span class="sxs-lookup"><span data-stu-id="189f3-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

|   |   |
|---|---|
|<span data-ttu-id="189f3-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="189f3-102">Details</span></span>|<span data-ttu-id="189f3-103">自 .NET Framework 4.5 起，iPad 是默认 ASP.NET 浏览器功能文件中的标识符，所以它不应在自定义功能文件中使用</span><span class="sxs-lookup"><span data-stu-id="189f3-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>|
|<span data-ttu-id="189f3-104">建议</span><span class="sxs-lookup"><span data-stu-id="189f3-104">Suggestion</span></span>|<span data-ttu-id="189f3-105">如果需要特定于 iPad 的功能，则需要修改 iPad 行为，具体方法为 设置预定义网关 refID &quot;IPad&quot; 上的功能，而不是通过用户代理匹配生成新的 &quot;IPad&quot; ID。</span><span class="sxs-lookup"><span data-stu-id="189f3-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>|
|<span data-ttu-id="189f3-106">范围</span><span class="sxs-lookup"><span data-stu-id="189f3-106">Scope</span></span>|<span data-ttu-id="189f3-107">边缘</span><span class="sxs-lookup"><span data-stu-id="189f3-107">Edge</span></span>|
|<span data-ttu-id="189f3-108">版本</span><span class="sxs-lookup"><span data-stu-id="189f3-108">Version</span></span>|<span data-ttu-id="189f3-109">4.5</span><span class="sxs-lookup"><span data-stu-id="189f3-109">4.5</span></span>|
|<span data-ttu-id="189f3-110">类型</span><span class="sxs-lookup"><span data-stu-id="189f3-110">Type</span></span>|<span data-ttu-id="189f3-111">运行时</span><span class="sxs-lookup"><span data-stu-id="189f3-111">Runtime</span></span>|
