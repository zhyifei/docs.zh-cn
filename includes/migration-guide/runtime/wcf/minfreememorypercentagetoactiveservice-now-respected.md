---
ms.openlocfilehash: fa472b3a142f55f0cbdd83eabbbb00bddd9786d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235183"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="be874-101">MinFreeMemoryPercentageToActiveService 现在受到遵从</span><span class="sxs-lookup"><span data-stu-id="be874-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

|   |   |
|---|---|
|<span data-ttu-id="be874-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="be874-102">Details</span></span>|<span data-ttu-id="be874-103">此设置可确立激活 WCF 服务之前必须在服务器上可用的最小内存。</span><span class="sxs-lookup"><span data-stu-id="be874-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="be874-104">它旨在阻止 <xref:System.OutOfMemoryException?displayProperty=name> 异常。</span><span class="sxs-lookup"><span data-stu-id="be874-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=name> exceptions.</span></span> <span data-ttu-id="be874-105">在 .NET Framework 4.5 中，此设置没有效果。</span><span class="sxs-lookup"><span data-stu-id="be874-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="be874-106">在 .NET Framework 4.5.1 中，观察到该设置。</span><span class="sxs-lookup"><span data-stu-id="be874-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>|
|<span data-ttu-id="be874-107">建议</span><span class="sxs-lookup"><span data-stu-id="be874-107">Suggestion</span></span>|<span data-ttu-id="be874-108">如果 Web 服务器上的可用内存少于由配置设置定义的百分比，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="be874-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="be874-109">某些成功启动并且在受约束的内存环境中运行的 WCF 服务现在可能失败。</span><span class="sxs-lookup"><span data-stu-id="be874-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>|
|<span data-ttu-id="be874-110">范围</span><span class="sxs-lookup"><span data-stu-id="be874-110">Scope</span></span>|<span data-ttu-id="be874-111">次要</span><span class="sxs-lookup"><span data-stu-id="be874-111">Minor</span></span>|
|<span data-ttu-id="be874-112">版本</span><span class="sxs-lookup"><span data-stu-id="be874-112">Version</span></span>|<span data-ttu-id="be874-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="be874-113">4.5.1</span></span>|
|<span data-ttu-id="be874-114">类型</span><span class="sxs-lookup"><span data-stu-id="be874-114">Type</span></span>|<span data-ttu-id="be874-115">运行时</span><span class="sxs-lookup"><span data-stu-id="be874-115">Runtime</span></span>|
