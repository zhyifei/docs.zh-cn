## <a name="introduction"></a><span data-ttu-id="79d54-101">介绍</span><span class="sxs-lookup"><span data-stu-id="79d54-101">Introduction</span></span>
<span data-ttu-id="79d54-102">重定目标更改影响重新编译为定位不同 .NET Framework 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="79d54-102">Retargeting changes affect apps that are recompiled to target a different .NET Framework.</span></span> <span data-ttu-id="79d54-103">它们包括：</span><span class="sxs-lookup"><span data-stu-id="79d54-103">They include:</span></span>

* <span data-ttu-id="79d54-104">设计时环境的更改。</span><span class="sxs-lookup"><span data-stu-id="79d54-104">Changes in the design-time environment.</span></span> <span data-ttu-id="79d54-105">例如，生成工具可能在之前没有发出警告时发出警告。</span><span class="sxs-lookup"><span data-stu-id="79d54-105">For example, build tools may emit warnings when previously they did not.</span></span>

* <span data-ttu-id="79d54-106">运行时环境的更改。</span><span class="sxs-lookup"><span data-stu-id="79d54-106">Changes in the runtime environment.</span></span> <span data-ttu-id="79d54-107">它们仅影响专门面向重定目标的 .NET Framework 的应用。</span><span class="sxs-lookup"><span data-stu-id="79d54-107">These affect only apps that specifically target the retargeted .NET Framework.</span></span> <span data-ttu-id="79d54-108">面向之前版本 .NET Framework 的应用的行为与在这些版本下运行时相同。</span><span class="sxs-lookup"><span data-stu-id="79d54-108">Apps that target previous versions of the .NET Framework behave as they did when running under those versions.</span></span>

<span data-ttu-id="79d54-109">在介绍重定目标更改的主题中，我们已根据其预期影响为单独的项进行了分类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="79d54-109">In the topics that describe retargeting changes, we have classified individual items by their expected impact, as follows:</span></span>

<span data-ttu-id="79d54-110">**主要** 这是显著的更改，可影响大量应用或需要修改大量代码。</span><span class="sxs-lookup"><span data-stu-id="79d54-110">**Major** This is a significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="79d54-111">**次要** 此更改影响少量应用或需要修改少量代码。</span><span class="sxs-lookup"><span data-stu-id="79d54-111">**Minor** This is a change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="79d54-112">**边缘事例** 此类更改仅在少数非常特定的情况下影响应用。</span><span class="sxs-lookup"><span data-stu-id="79d54-112">**Edge case** This is a change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="79d54-113">**透明** 此类更改对应用的开发人员或用户没有明显影响。</span><span class="sxs-lookup"><span data-stu-id="79d54-113">**Transparent** This is a change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="79d54-114">不需要由于此更改而修改应用。</span><span class="sxs-lookup"><span data-stu-id="79d54-114">The app should not require modification because of this change.</span></span>
