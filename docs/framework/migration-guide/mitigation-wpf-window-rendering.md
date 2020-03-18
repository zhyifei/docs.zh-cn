---
title: 缓解：WPF 窗口呈现
ms.date: 03/30/2017
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
ms.openlocfilehash: 42d6abf1ba6ed7c17a5a5604e98b5ee46d0c3ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457766"
---
# <a name="mitigation-wpf-window-rendering"></a><span data-ttu-id="0e446-102">缓解：WPF 窗口呈现</span><span class="sxs-lookup"><span data-stu-id="0e446-102">Mitigation: WPF Window Rendering</span></span>

<span data-ttu-id="0e446-103">在 Windows 8 及更高版本上运行的 .NET Framework 4.6 中，当一个窗口超出多监视器方案中的单个显示屏时，会不经剪辑就呈现整个窗口。</span><span class="sxs-lookup"><span data-stu-id="0e446-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span>

## <a name="impact"></a><span data-ttu-id="0e446-104">影响</span><span class="sxs-lookup"><span data-stu-id="0e446-104">Impact</span></span>

<span data-ttu-id="0e446-105">通常，跨多个监视器不经剪辑呈现整个窗口是预期行为。</span><span class="sxs-lookup"><span data-stu-id="0e446-105">In general, rendering an entire window across multiple monitors without clipping is the expected behavior.</span></span> <span data-ttu-id="0e446-106">但是，在 Windows 7 和更早版本上，WPF 窗口在超出单个显示屏时将被剪辑，因为在第二个监视器上呈现窗口的一部分具有显著的性能影响。</span><span class="sxs-lookup"><span data-stu-id="0e446-106">However, on Windows 7 and earlier versions, WPF windows are clipped when they extend beyond a single display because rendering a portion of the window on the second monitor has a significant performance impact.</span></span>

<span data-ttu-id="0e446-107">在 Windows 8 和更高版本上跨监视器呈现 WPF 窗口的具体影响无法精确计量，因为它取决于大量因素。</span><span class="sxs-lookup"><span data-stu-id="0e446-107">The precise impact of rendering WPF windows across monitors on Windows 8 and above is not precisely quantifiable since it depends on a large number of factors.</span></span> <span data-ttu-id="0e446-108">在某些情况下，它仍可能会对性能产生不良影响，特别是对于运行图形密集型应用程序和具有跨监视器窗口的用户。</span><span class="sxs-lookup"><span data-stu-id="0e446-108">In some cases, it may still produce an undesirable impact on performance, particularly for users who run graphics-intensive applications and have windows straddling monitors.</span></span> <span data-ttu-id="0e446-109">在其他情况下，你可能只是希望各 .NET Framework 版本有一致的行为。</span><span class="sxs-lookup"><span data-stu-id="0e446-109">In other cases, you may simply want a consistent behavior across .NET Framework versions.</span></span>

## <a name="mitigation"></a><span data-ttu-id="0e446-110">缓解操作</span><span class="sxs-lookup"><span data-stu-id="0e446-110">Mitigation</span></span>

<span data-ttu-id="0e446-111">当窗口超出单个显示屏时，你可以禁用此更改并恢复到以前的剪辑 WPF 窗口的行为。</span><span class="sxs-lookup"><span data-stu-id="0e446-111">You can disable this change and revert to the previous behavior of clipping a WPF window when it extends beyond a single display.</span></span> <span data-ttu-id="0e446-112">有两种方法可以实现此目的：</span><span class="sxs-lookup"><span data-stu-id="0e446-112">There are two ways to do this:</span></span>

- <span data-ttu-id="0e446-113">通过将 `<EnableMultiMonitorDisplayClipping>` 元素添加到应用程序配置文件的 `<appSettings>` 部分，你可以对在 Windows 8 或更高版本上运行的应用禁用或启用此行为。</span><span class="sxs-lookup"><span data-stu-id="0e446-113">By adding the `<EnableMultiMonitorDisplayClipping>` element to the `<appSettings>` section of your application configuration file, you can disable or enable this behavior on apps running on Windows 8 or later.</span></span> <span data-ttu-id="0e446-114">例如，下面的配置部分禁用不经剪辑的呈现：</span><span class="sxs-lookup"><span data-stu-id="0e446-114">For example, the following configuration section disables rendering without clipping:</span></span>

  ```xml
  <appSettings>
      <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    </appSettings>
  ```

  <span data-ttu-id="0e446-115">`<EnableMultiMonitorDisplayClipping>` 配置设置可以有两个值之一：</span><span class="sxs-lookup"><span data-stu-id="0e446-115">The `<EnableMultiMonitorDisplayClipping>` configuration setting can have either of two values:</span></span>

  - <span data-ttu-id="0e446-116">`true`，启用在呈现期间监视边界的窗口剪辑。</span><span class="sxs-lookup"><span data-stu-id="0e446-116">`true`, to enable clipping of windows to monitor bounds during rendering.</span></span>

  - <span data-ttu-id="0e446-117">`false`，禁用在呈现期间监视边界的窗口剪辑。</span><span class="sxs-lookup"><span data-stu-id="0e446-117">`false`, to disable clipping of windows to monitor bounds during rendering.</span></span>

- <span data-ttu-id="0e446-118">通过在应用启动时将 <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0e446-118">By setting the <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> property to `true` at app startup.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e446-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e446-119">See also</span></span>

- [<span data-ttu-id="0e446-120">应用程序兼容性</span><span class="sxs-lookup"><span data-stu-id="0e446-120">Application compatibility</span></span>](application-compatibility.md)
