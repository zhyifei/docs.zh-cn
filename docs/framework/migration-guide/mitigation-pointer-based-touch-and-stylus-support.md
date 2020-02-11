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
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094470"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a>缓解：基于指针的触控和触笔支持

对于面向 .NET Framework 4.7 且在 Windows 10 创意者更新及更高版本的 Windows 上运行的 WPF 应用程序，可以启用基于 `WM_POINTER` 的可选 WPF 触控/触笔堆栈。

## <a name="impact"></a>影响

未显式启用基于指针的触控/触笔支持的开发者应该不会看到 WPF 触控/触笔行为有任何变化。

下面介绍了可选的基于 `WM_POINTER` 的触控/触笔堆栈当前存在的已知问题：

- 不支持实时墨迹书写。

   尽管墨迹书写和触笔插件仍可运行，但它们是在 UI 线程上进行处理，这可能会导致性能变得糟糕。

- 从触控/触笔事件提升到鼠标事件方面的更改导致行为发生变化。

  - 控制行为可能不同。

  - 拖/放行为无法正确显示触控输入反馈。 （这不会影响触笔输入。）

  - 无法再通过触控/触笔事件启动拖/放行为。

      这可能会导致应用程序无响应，直到检测到鼠标输入。 相反，开发者应通过鼠标事件启动拖放行为。

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a>选择启用基于 WM_POINTER 的触控/触笔支持

要启用此堆栈的开发者可以在应用程序的 app.config 文件中添加下面的代码。 

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

删除此条目或将其值设置为 `false` 可以禁用此可选堆栈。

## <a name="see-also"></a>请参阅

- [应用程序兼容性](application-compatibility.md)
