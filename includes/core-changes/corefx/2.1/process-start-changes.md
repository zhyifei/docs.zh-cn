---
ms.openlocfilehash: 58cb3580c8701773452ae8338f036a94bbee80c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449384"
---
### <a name="change-in-default-value-of-useshellexecute"></a><span data-ttu-id="41c9f-101">UseShellExecute 默认值更改</span><span class="sxs-lookup"><span data-stu-id="41c9f-101">Change in default value of UseShellExecute</span></span>

<span data-ttu-id="41c9f-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> 在 .NET Core 上的默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="41c9f-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> has a default value of `false` on .NET Core.</span></span> <span data-ttu-id="41c9f-103">在 .NET Framework 上，其默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="41c9f-103">On .NET Framework, its default value is `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="41c9f-104">更改描述</span><span class="sxs-lookup"><span data-stu-id="41c9f-104">Change description</span></span>

<span data-ttu-id="41c9f-105">可以通过 <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> 直接启动应用程序，例如，使用 `Process.Start("mspaint.exe")` 代码启动画图。</span><span class="sxs-lookup"><span data-stu-id="41c9f-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> lets you launch an application directly, for example, with code such as `Process.Start("mspaint.exe")` that launches Paint.</span></span> <span data-ttu-id="41c9f-106">如果 <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> 设置为 `true`，它还允许间接启动关联的应用程序。</span><span class="sxs-lookup"><span data-stu-id="41c9f-106">It also lets you indirectly launch an associated application if <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is set to `true`.</span></span> <span data-ttu-id="41c9f-107">在 .NET Framework 上，<xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> 的默认值 `true`，这意味着，如果已将 .txt`Process.Start("mytextfile.txt")`*文件与该编辑器相关联，则* 会启动记事本。</span><span class="sxs-lookup"><span data-stu-id="41c9f-107">On .NET Framework, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `true`, meaning that code such as `Process.Start("mytextfile.txt")` would launch Notepad, if you've associated *.txt* files with that editor.</span></span> <span data-ttu-id="41c9f-108">若要防止在 .NET Framework 上间接启动应用，必须将 <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> 显式设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="41c9f-108">To prevent indirectly launching an app on .NET Framework, you must explicitly set <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="41c9f-109">在 .NET Core 中，<xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> 的默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="41c9f-109">On .NET Core, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `false`.</span></span> <span data-ttu-id="41c9f-110">这意味着，默认情况下，在调用 `Process.Start` 时不会启动关联的应用程序。</span><span class="sxs-lookup"><span data-stu-id="41c9f-110">This means that, by default, associated applications are not launched when you call `Process.Start`.</span></span>

<span data-ttu-id="41c9f-111">出于性能方面的考虑，.NET Core 中引入了此更改。</span><span class="sxs-lookup"><span data-stu-id="41c9f-111">This change was introduced in .NET Core for performance reasons.</span></span> <span data-ttu-id="41c9f-112">通常情况下，<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> 用于直接启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="41c9f-112">Typically, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> is used to launch an application directly.</span></span> <span data-ttu-id="41c9f-113">直接启动应用并不需要使用 Windows shell，也不会产生关联的性能成本。</span><span class="sxs-lookup"><span data-stu-id="41c9f-113">Launching an app directly does not need to involve the Windows shell and incur the associated performance cost.</span></span> <span data-ttu-id="41c9f-114">为了更快地使此情况默认化，.NET Core 将 <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> 的默认值更改为 `false`。</span><span class="sxs-lookup"><span data-stu-id="41c9f-114">To make this default case faster, .NET Core changes the default value of <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="41c9f-115">如果需要，可以选择慢速路径。</span><span class="sxs-lookup"><span data-stu-id="41c9f-115">You can opt in to the slower path if you need it.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="41c9f-116">引入的版本</span><span class="sxs-lookup"><span data-stu-id="41c9f-116">Version introduced</span></span>

<span data-ttu-id="41c9f-117">2.1</span><span class="sxs-lookup"><span data-stu-id="41c9f-117">2.1</span></span>

> [!NOTE]
> <span data-ttu-id="41c9f-118">在早期版本的 .NET Core 中，没有为 Windows 实现 `UseShellExecute`。</span><span class="sxs-lookup"><span data-stu-id="41c9f-118">In earlier versions of .NET Core, `UseShellExecute` was not implemented for Windows.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="41c9f-119">建议操作</span><span class="sxs-lookup"><span data-stu-id="41c9f-119">Recommended action</span></span>

<span data-ttu-id="41c9f-120">如果应用依赖于旧行为，请调用 <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType>，并将 <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> 设置为 `true` 对象上的 <xref:System.Diagnostics.ProcessStartInfo>。</span><span class="sxs-lookup"><span data-stu-id="41c9f-120">If your app relies on the old behavior, call <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> with <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> set to `true` on the <xref:System.Diagnostics.ProcessStartInfo> object.</span></span>

#### <a name="category"></a><span data-ttu-id="41c9f-121">类别</span><span class="sxs-lookup"><span data-stu-id="41c9f-121">Category</span></span>

<span data-ttu-id="41c9f-122">CoreFx</span><span class="sxs-lookup"><span data-stu-id="41c9f-122">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="41c9f-123">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="41c9f-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
