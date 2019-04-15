---
ms.openlocfilehash: 958a89015420ce5632d596688963d576c40b4cb6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235164"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="59f1c-101">与 Asp.Net StateServer 共享会话状态需要 Web 场中的所有服务器使用相同版本的 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="59f1c-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="59f1c-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="59f1c-102">Details</span></span>|<span data-ttu-id="59f1c-103">启用 <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name> 会话状态时，给定 Web 场中的所有服务器必须使用相同版本的 .NET Framework 以便正确共享状态。</span><span class="sxs-lookup"><span data-stu-id="59f1c-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>|
|<span data-ttu-id="59f1c-104">建议</span><span class="sxs-lookup"><span data-stu-id="59f1c-104">Suggestion</span></span>|<span data-ttu-id="59f1c-105">请务必在同时共享状态的 Web 服务器上升级 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="59f1c-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>|
|<span data-ttu-id="59f1c-106">范围</span><span class="sxs-lookup"><span data-stu-id="59f1c-106">Scope</span></span>|<span data-ttu-id="59f1c-107">边缘</span><span class="sxs-lookup"><span data-stu-id="59f1c-107">Edge</span></span>|
|<span data-ttu-id="59f1c-108">版本</span><span class="sxs-lookup"><span data-stu-id="59f1c-108">Version</span></span>|<span data-ttu-id="59f1c-109">4.5</span><span class="sxs-lookup"><span data-stu-id="59f1c-109">4.5</span></span>|
|<span data-ttu-id="59f1c-110">类型</span><span class="sxs-lookup"><span data-stu-id="59f1c-110">Type</span></span>|<span data-ttu-id="59f1c-111">运行时</span><span class="sxs-lookup"><span data-stu-id="59f1c-111">Runtime</span></span>|
|<span data-ttu-id="59f1c-112">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="59f1c-112">Affected APIs</span></span>|<ul><li><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
