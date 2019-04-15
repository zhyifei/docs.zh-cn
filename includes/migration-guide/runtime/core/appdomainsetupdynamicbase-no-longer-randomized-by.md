---
ms.openlocfilehash: 3f553f95941eaf36cf335e9765a670a05bd157f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234110"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a><span data-ttu-id="a1b67-101">UseRandomizedStringHashAlgorithm 不再由 AppDomainSetup.DynamicBase 进行随机化</span><span class="sxs-lookup"><span data-stu-id="a1b67-101">AppDomainSetup.DynamicBase is no longer randomized by UseRandomizedStringHashAlgorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a1b67-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="a1b67-102">Details</span></span>|<span data-ttu-id="a1b67-103">在 .NET Framework 4.6 之前，如果在应用的配置文件中启用了 UseRandomizedStringHashAlgorithm，那么 <xref:System.AppDomainSetup.DynamicBase> 的值会在应用程序域或者进程之间进行随机化。</span><span class="sxs-lookup"><span data-stu-id="a1b67-103">Prior to the .NET Framework 4.6, the value of <xref:System.AppDomainSetup.DynamicBase> would be randomized between application domains, or between processes, if UseRandomizedStringHashAlgorithm was enabled in the app's config file.</span></span> <span data-ttu-id="a1b67-104">自 .NET Framework 4.6 起，<xref:System.AppDomainSetup.DynamicBase> 将在运行的应用的不同实例之间，以及在不同的应用域之间返回一个稳定的结果。</span><span class="sxs-lookup"><span data-stu-id="a1b67-104">Beginning in the .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> will return a stable result between different instances of an app running, and between different app domains.</span></span> <span data-ttu-id="a1b67-105">不同应用的动态基各不相同；此更改仅删除相同应用的不同实例的随机命名元素。</span><span class="sxs-lookup"><span data-stu-id="a1b67-105">Dynamic bases will still differ for different apps; this change only removes the random naming element for different instances of the same app.</span></span>|
|<span data-ttu-id="a1b67-106">建议</span><span class="sxs-lookup"><span data-stu-id="a1b67-106">Suggestion</span></span>|<span data-ttu-id="a1b67-107">请注意，启用 <code>UseRandomizedStringHashAlgorithm</code> 不会导致随机化 <xref:System.AppDomainSetup.DynamicBase>。</span><span class="sxs-lookup"><span data-stu-id="a1b67-107">Be aware that enabling <code>UseRandomizedStringHashAlgorithm</code> will not result in <xref:System.AppDomainSetup.DynamicBase> being randomized.</span></span> <span data-ttu-id="a1b67-108">如果需要随机基，则必须在应用代码中生成它，而不是通过此 API 生成。</span><span class="sxs-lookup"><span data-stu-id="a1b67-108">If a random base is needed, it must be produced in your app's code rather than via this API.</span></span>|
|<span data-ttu-id="a1b67-109">范围</span><span class="sxs-lookup"><span data-stu-id="a1b67-109">Scope</span></span>|<span data-ttu-id="a1b67-110">边缘</span><span class="sxs-lookup"><span data-stu-id="a1b67-110">Edge</span></span>|
|<span data-ttu-id="a1b67-111">版本</span><span class="sxs-lookup"><span data-stu-id="a1b67-111">Version</span></span>|<span data-ttu-id="a1b67-112">4.6</span><span class="sxs-lookup"><span data-stu-id="a1b67-112">4.6</span></span>|
|<span data-ttu-id="a1b67-113">类型</span><span class="sxs-lookup"><span data-stu-id="a1b67-113">Type</span></span>|<span data-ttu-id="a1b67-114">运行时</span><span class="sxs-lookup"><span data-stu-id="a1b67-114">Runtime</span></span>|
|<span data-ttu-id="a1b67-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="a1b67-115">Affected APIs</span></span>|<ul><li><xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
