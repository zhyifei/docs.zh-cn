---
title: 缓解：基于指针的触控和触笔支持
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: 023c38f66611bd0022699d3f62d90c3923585012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "77094470"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="16d60-102">缓解：基于指针的触控和触笔支持</span><span class="sxs-lookup"><span data-stu-id="16d60-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="16d60-103">对于面向 .NET Framework 4.7 且在 Windows 10 创意者更新及更高版本的 Windows 上运行的 WPF 应用程序，可以启用基于 `WM_POINTER` 的可选 WPF 触控/触笔堆栈。</span><span class="sxs-lookup"><span data-stu-id="16d60-103">WPF applications that target the .NET Framework 4.7 and are running on Windows starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="16d60-104">影响</span><span class="sxs-lookup"><span data-stu-id="16d60-104">Impact</span></span>

<span data-ttu-id="16d60-105">未显式启用基于指针的触控/触笔支持的开发者应该不会看到 WPF 触控/触笔行为有任何变化。</span><span class="sxs-lookup"><span data-stu-id="16d60-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="16d60-106">下面介绍了可选的基于 `WM_POINTER` 的触控/触笔堆栈当前存在的已知问题：</span><span class="sxs-lookup"><span data-stu-id="16d60-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="16d60-107">不支持实时墨迹书写。</span><span class="sxs-lookup"><span data-stu-id="16d60-107">No support for real-time inking.</span></span>

   <span data-ttu-id="16d60-108">尽管墨迹书写和触笔插件仍可运行，但它们是在 UI 线程上进行处理，这可能会导致性能变得糟糕。</span><span class="sxs-lookup"><span data-stu-id="16d60-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="16d60-109">从触控/触笔事件提升到鼠标事件方面的更改导致行为发生变化。</span><span class="sxs-lookup"><span data-stu-id="16d60-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="16d60-110">控制行为可能不同。</span><span class="sxs-lookup"><span data-stu-id="16d60-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="16d60-111">拖/放行为无法正确显示触控输入反馈。</span><span class="sxs-lookup"><span data-stu-id="16d60-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="16d60-112">（这不会影响触笔输入。）</span><span class="sxs-lookup"><span data-stu-id="16d60-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="16d60-113">无法再通过触控/触笔事件启动拖/放行为。</span><span class="sxs-lookup"><span data-stu-id="16d60-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="16d60-114">这可能会导致应用程序无响应，直到检测到鼠标输入。</span><span class="sxs-lookup"><span data-stu-id="16d60-114">This can potentially cause the application to become unresponsive until mouse input is detected.</span></span> <span data-ttu-id="16d60-115">相反，开发者应通过鼠标事件启动拖放行为。</span><span class="sxs-lookup"><span data-stu-id="16d60-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a><span data-ttu-id="16d60-116">选择启用基于 WM_POINTER 的触控/触笔支持</span><span class="sxs-lookup"><span data-stu-id="16d60-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="16d60-117">要启用此堆栈的开发者可以在应用程序的 app.config 文件中添加下面的代码。 </span><span class="sxs-lookup"><span data-stu-id="16d60-117">Developers who wish to enable this stack can add the following to their application's *app.config* file.</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="16d60-118">删除此条目或将其值设置为 `false` 可以禁用此可选堆栈。</span><span class="sxs-lookup"><span data-stu-id="16d60-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="16d60-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16d60-119">See also</span></span>

- [<span data-ttu-id="16d60-120">应用程序兼容性</span><span class="sxs-lookup"><span data-stu-id="16d60-120">Application compatibility</span></span>](application-compatibility.md)
