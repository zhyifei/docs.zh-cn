---
ms.openlocfilehash: a70aca33d0830f3b23ff985f17c469cb7c4ff35c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234613"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a><span data-ttu-id="4afd7-101">不支持对具有非公共资源库的属性的双向数据绑定</span><span class="sxs-lookup"><span data-stu-id="4afd7-101">Two-way data-binding to a property with a non-public setter is not supported</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4afd7-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="4afd7-102">Details</span></span>|<span data-ttu-id="4afd7-103">尝试将数据绑定到没有公共资源库的方案从未受支持。</span><span class="sxs-lookup"><span data-stu-id="4afd7-103">Attempting to data bind to a property without a public setter has never been a supported scenario.</span></span> <span data-ttu-id="4afd7-104">从 .NET Framework 4.5.1 开始，此方案将引发 <xref:System.InvalidOperationException?displayProperty=name>。</span><span class="sxs-lookup"><span data-stu-id="4afd7-104">Beginning in the .NET Framework 4.5.1, this scenario will throw an <xref:System.InvalidOperationException?displayProperty=name>.</span></span> <span data-ttu-id="4afd7-105">请注意，仅专门面向 .NET Framework 4.5.1 的应用会引发此新异常。</span><span class="sxs-lookup"><span data-stu-id="4afd7-105">Note that this new exception will only be thrown for apps that specifically target the .NET Framework 4.5.1.</span></span> <span data-ttu-id="4afd7-106">如果应用面向 .NET Framework 4.5，将允许该调用。</span><span class="sxs-lookup"><span data-stu-id="4afd7-106">If an app targets the .NET Framework 4.5, the call will be allowed.</span></span> <span data-ttu-id="4afd7-107">如果应用不面向特定 .NET Framework 版本，绑定将视为单向绑定。</span><span class="sxs-lookup"><span data-stu-id="4afd7-107">If the app does not target a particular .NET Framework version, the binding will be treated as one-way.</span></span>|
|<span data-ttu-id="4afd7-108">建议</span><span class="sxs-lookup"><span data-stu-id="4afd7-108">Suggestion</span></span>|<span data-ttu-id="4afd7-109">应更新应用以使用单向绑定，或公开公布属性的资源库。</span><span class="sxs-lookup"><span data-stu-id="4afd7-109">The app should be updated to either use one-way binding, or expose the property's setter publicly.</span></span> <span data-ttu-id="4afd7-110">或者，面向 .NET Framework 4.5 将使应用展示旧行为。</span><span class="sxs-lookup"><span data-stu-id="4afd7-110">Alternatively, targeting the .NET Framework 4.5 will cause the app to exhibit the old behavior.</span></span>|
|<span data-ttu-id="4afd7-111">范围</span><span class="sxs-lookup"><span data-stu-id="4afd7-111">Scope</span></span>|<span data-ttu-id="4afd7-112">次要</span><span class="sxs-lookup"><span data-stu-id="4afd7-112">Minor</span></span>|
|<span data-ttu-id="4afd7-113">版本</span><span class="sxs-lookup"><span data-stu-id="4afd7-113">Version</span></span>|<span data-ttu-id="4afd7-114">4.5.1</span><span class="sxs-lookup"><span data-stu-id="4afd7-114">4.5.1</span></span>|
|<span data-ttu-id="4afd7-115">类型</span><span class="sxs-lookup"><span data-stu-id="4afd7-115">Type</span></span>|<span data-ttu-id="4afd7-116">重定目标</span><span class="sxs-lookup"><span data-stu-id="4afd7-116">Retargeting</span></span>|
|<span data-ttu-id="4afd7-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="4afd7-117">Affected APIs</span></span>|<ul><li><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType></li></ul>|
