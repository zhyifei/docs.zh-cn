---
ms.openlocfilehash: 71f61f23a8b17459610d253766a99e594f09428e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857216"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="725dd-101">WCF PipeConnection.GetHashAlgorithm 现在使用 SHA256</span><span class="sxs-lookup"><span data-stu-id="725dd-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="725dd-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="725dd-102">Details</span></span>|<span data-ttu-id="725dd-103">从 .NET Framework 4.7.1 开始，Windows Communication Foundation 使用 SHA256 哈希为命名管道生成随机名称。</span><span class="sxs-lookup"><span data-stu-id="725dd-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="725dd-104">在 .NET Framework 4.7 和更早版本中，它使用 SHA1 哈希。</span><span class="sxs-lookup"><span data-stu-id="725dd-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="725dd-105">建议</span><span class="sxs-lookup"><span data-stu-id="725dd-105">Suggestion</span></span>|<span data-ttu-id="725dd-106">如果在 .NET Framework 4.7.1 或更高版本中遇到此更改的兼容性问题，则可以通过将以下行添加到 app.config 文件的 <code>&lt;runtime&gt;</code> 部分选择弃用此更改：</span><span class="sxs-lookup"><span data-stu-id="725dd-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="725dd-107">范围</span><span class="sxs-lookup"><span data-stu-id="725dd-107">Scope</span></span>|<span data-ttu-id="725dd-108">次要</span><span class="sxs-lookup"><span data-stu-id="725dd-108">Minor</span></span>|
|<span data-ttu-id="725dd-109">版本</span><span class="sxs-lookup"><span data-stu-id="725dd-109">Version</span></span>|<span data-ttu-id="725dd-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="725dd-110">4.7.1</span></span>|
|<span data-ttu-id="725dd-111">类型</span><span class="sxs-lookup"><span data-stu-id="725dd-111">Type</span></span>|<span data-ttu-id="725dd-112">运行时</span><span class="sxs-lookup"><span data-stu-id="725dd-112">Runtime</span></span>|

