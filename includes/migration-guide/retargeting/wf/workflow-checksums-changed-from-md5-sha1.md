---
ms.openlocfilehash: f007a2b81820a1d25a2d101b35f3a49e7794fec1
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760175"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a><span data-ttu-id="5bbea-101">工作流校验和已从 MD5 更改为 SHA1</span><span class="sxs-lookup"><span data-stu-id="5bbea-101">Workflow checksums changed from MD5 to SHA1</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5bbea-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="5bbea-102">Details</span></span>|<span data-ttu-id="5bbea-103">为支持使用 Visual Studio 进行调试，工作流运行时使用哈希算法为工作流实例生成校验和。</span><span class="sxs-lookup"><span data-stu-id="5bbea-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow instance using a hashing algorithm.</span></span> <span data-ttu-id="5bbea-104">在 .NET Framework 4.6.2 和早期版本中，工作流校验和哈希使用 MD5 算法，这会在启用 FIPS 的系统上导致问题。</span><span class="sxs-lookup"><span data-stu-id="5bbea-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="5bbea-105">从 .NET Framework 4.7 开始，算法为 SHA1。</span><span class="sxs-lookup"><span data-stu-id="5bbea-105">Starting with the .NET Framework 4.7, the algorithm is SHA1.</span></span> <span data-ttu-id="5bbea-106">如果代码保留了这些校验和，它们将是不兼容的。</span><span class="sxs-lookup"><span data-stu-id="5bbea-106">If your code has persisted these checksums, they will be incompatible.</span></span>|
|<span data-ttu-id="5bbea-107">建议</span><span class="sxs-lookup"><span data-stu-id="5bbea-107">Suggestion</span></span>|<span data-ttu-id="5bbea-108">如果代码由于校验和失败而无法加载工作流实例，请尝试将 <code>AppContext</code> 开关 &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; 设置为 true。在代码中：</span><span class="sxs-lookup"><span data-stu-id="5bbea-108">If your code is unable to load workflow instances due to a checksum failure, try setting the <code>AppContext</code> switch &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; to true.In code:</span></span><pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseMD5ForWFDebugger&quot;, true);&#13;&#10;</code></pre><span data-ttu-id="5bbea-109">或在配置中：</span><span class="sxs-lookup"><span data-stu-id="5bbea-109">Or in configuration:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseMD5ForWFDebugger=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="5bbea-110">范围</span><span class="sxs-lookup"><span data-stu-id="5bbea-110">Scope</span></span>|<span data-ttu-id="5bbea-111">次要</span><span class="sxs-lookup"><span data-stu-id="5bbea-111">Minor</span></span>|
|<span data-ttu-id="5bbea-112">版本</span><span class="sxs-lookup"><span data-stu-id="5bbea-112">Version</span></span>|<span data-ttu-id="5bbea-113">4.7</span><span class="sxs-lookup"><span data-stu-id="5bbea-113">4.7</span></span>|
|<span data-ttu-id="5bbea-114">类型</span><span class="sxs-lookup"><span data-stu-id="5bbea-114">Type</span></span>|<span data-ttu-id="5bbea-115">重定目标</span><span class="sxs-lookup"><span data-stu-id="5bbea-115">Retargeting</span></span>|

