---
title: "缓解：基于指针的触控和触笔支持"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
caps.latest.revision: "2"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 053ff4c5fba7b4f2b5a4c29a35c954e888cb095a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="5a026-102">缓解：基于指针的触控和触笔支持</span><span class="sxs-lookup"><span data-stu-id="5a026-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="5a026-103">对于定位 .NET Framework 4.7 且在 Windows 10 创意者更新及更高版本的 Windows 系统上运行的 WPF 应用程序，可以启用可选的基于 `WM_POINTER` 的 WPF 触控/触笔堆栈。</span><span class="sxs-lookup"><span data-stu-id="5a026-103">WPF applications that target the .NET Framework 4.7 and are running on Windows Systems starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="5a026-104">影响</span><span class="sxs-lookup"><span data-stu-id="5a026-104">Impact</span></span>

<span data-ttu-id="5a026-105">未显式启用基于指针的触控/触笔支持的开发者应该不会看到 WPF 触控/触笔行为有任何变化。</span><span class="sxs-lookup"><span data-stu-id="5a026-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="5a026-106">下面介绍了可选的基于 `WM_POINTER` 的触控/触笔堆栈当前存在的已知问题：</span><span class="sxs-lookup"><span data-stu-id="5a026-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="5a026-107">不支持实时墨迹书写。</span><span class="sxs-lookup"><span data-stu-id="5a026-107">No support for real-time inking.</span></span>

   <span data-ttu-id="5a026-108">尽管墨迹书写和触笔插件仍可运行，但它们是在 UI 线程上进行处理，这可能会导致性能变得糟糕。</span><span class="sxs-lookup"><span data-stu-id="5a026-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="5a026-109">从触控/触笔事件提升到鼠标事件方面的更改导致行为发生变化。</span><span class="sxs-lookup"><span data-stu-id="5a026-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="5a026-110">控制行为可能不同。</span><span class="sxs-lookup"><span data-stu-id="5a026-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="5a026-111">拖/放行为无法正确显示触控输入反馈。</span><span class="sxs-lookup"><span data-stu-id="5a026-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="5a026-112">（这不会影响触笔输入。）</span><span class="sxs-lookup"><span data-stu-id="5a026-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="5a026-113">无法再通过触控/触笔事件启动拖/放行为。</span><span class="sxs-lookup"><span data-stu-id="5a026-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="5a026-114">这可能会在检测到鼠标输入前导致应用程序挂起。</span><span class="sxs-lookup"><span data-stu-id="5a026-114">This can potentially hang the application until mouse input is detected.</span></span> <span data-ttu-id="5a026-115">相反，开发者应通过鼠标事件启动拖放行为。</span><span class="sxs-lookup"><span data-stu-id="5a026-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wmpointer-based-touchstylus-support"></a><span data-ttu-id="5a026-116">选择启用基于 WM_POINTER 的触控/触笔支持</span><span class="sxs-lookup"><span data-stu-id="5a026-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="5a026-117">要启用此堆栈的开发者可以在应用程序的 app.config 文件中添加下面的代码：</span><span class="sxs-lookup"><span data-stu-id="5a026-117">Developers who wish to enable this stack can add the following to their application's app.config file:</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="5a026-118">删除此条目或将其值设置为 `false` 可以禁用此可选堆栈。</span><span class="sxs-lookup"><span data-stu-id="5a026-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a026-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a026-119">See also</span></span>

[<span data-ttu-id="5a026-120">.NET Framework 4.7 中的重定目标更改</span><span class="sxs-lookup"><span data-stu-id="5a026-120">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
