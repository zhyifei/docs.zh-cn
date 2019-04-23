---
ms.openlocfilehash: 318609c15d2e0b9a7ee59b38463735b33ef87974
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803320"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="5d45c-101">WCF PipeConnection.GetHashAlgorithm 现在使用 SHA256</span><span class="sxs-lookup"><span data-stu-id="5d45c-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5d45c-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="5d45c-102">Details</span></span>|<span data-ttu-id="5d45c-103">从 .NET Framework 4.7.1 开始，Windows Communication Foundation 使用 SHA256 哈希为命名管道生成随机名称。</span><span class="sxs-lookup"><span data-stu-id="5d45c-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="5d45c-104">在 .NET Framework 4.7 和更早版本中，它使用 SHA1 哈希。</span><span class="sxs-lookup"><span data-stu-id="5d45c-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="5d45c-105">建议</span><span class="sxs-lookup"><span data-stu-id="5d45c-105">Suggestion</span></span>|<span data-ttu-id="5d45c-106">如果在 .NET Framework 4.7.1 或更高版本中遇到此更改的兼容性问题，则可以通过将以下行添加到 app.config 文件的 <code>&lt;runtime&gt;</code> 部分选择弃用此更改：</span><span class="sxs-lookup"><span data-stu-id="5d45c-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="5d45c-107">范围</span><span class="sxs-lookup"><span data-stu-id="5d45c-107">Scope</span></span>|<span data-ttu-id="5d45c-108">次要</span><span class="sxs-lookup"><span data-stu-id="5d45c-108">Minor</span></span>|
|<span data-ttu-id="5d45c-109">版本</span><span class="sxs-lookup"><span data-stu-id="5d45c-109">Version</span></span>|<span data-ttu-id="5d45c-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="5d45c-110">4.7.1</span></span>|
|<span data-ttu-id="5d45c-111">类型</span><span class="sxs-lookup"><span data-stu-id="5d45c-111">Type</span></span>|<span data-ttu-id="5d45c-112">运行时</span><span class="sxs-lookup"><span data-stu-id="5d45c-112">Runtime</span></span>|
