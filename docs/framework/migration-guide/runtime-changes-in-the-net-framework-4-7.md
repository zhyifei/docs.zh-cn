---
title: ".NET Framework 4.7 中的运行时更改 | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes,.NET Framework
- runtime changes,.NET Framework 4.7
- application compatibility
ms.assetid: 268eb334-7906-4e0b-a1e3-c74b745de2a5
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 321ec8f8293afad0f3da7fb6f907f45d404394cc
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-47"></a>.NET Framework 4.7 中的运行时更改

在极少数情况下，运行时更改可能影响面向以前版本的 .NET Framework 但更高版本的 .NET Framework 运行时上运行的现有应用。 他们还包括运行于不同 .NET Framework 运行时环境上的应用程序间的行为差异。 NET Framework 4.6.2 在以下几个领域进行了更改：

- [Windows Presentation Foundation (WPF)](#WPF)

下表中的“范围”列指定每个更改的基数：

- 主要。 显著的更改，可影响大量应用或需要修改大量代码。 请注意，没有重定目标更改归入此类别。

- 次要。 影响少量应用或需要修改少量代码的更改。

- 边缘。 仅在少数非常特定的情况下影响应用的更改。

- 透明。 对应用的开发人员或用户没有明显影响的更改。 不需要由于此更改而修改应用。

## <a name="a-namewpf--windows-presentation-foundation-wpf"></a><a name="WPF" />Windows Presentation Foundation (WPF)

assetId:///M:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView(System.Int32)?qualifyHint=False&autoUpgrade=True

| 功能 | 更改 | 影响 | 范围 |
|---|---|---|---|
| <xref:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView%2A> 方法 | 在 .NET Framework 4.6.2 中，当启用列虚拟化但尚未确定列宽时，<xref:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView%2A> 方法以异步方式执行。 如果在异步操作完成之前删除列，可能会导致 <xref:System.ArgumentOutOfRangeException> 抛出。<br/></br>自 .NET Framework 4.7 起，此应用场景再也不会导致异常抛出。 | 此更改提高了方法的可靠性。 | 边缘 | 
|<xref:System.Windows.Controls.Ribbon.RibbonGroup> 背景 | 在 .NET Framework 4.6.2 及更低版本中，本地化版本上的 <xref:System.Windows.Controls.Ribbon.RibbonGroup> 背景是使用透明画笔绘制，导致 UI 体验变得糟糕。 在 .NET Framework 4.7 中，WPF 更新了 <xref:System.Windows.Controls.Ribbon.RibbonGroup> 控件的本地化资源，这将确保选择正确的画笔。 | 若要充分利用新行为，请升级到 .NET Framework 4.7。 | 边缘 |
| WPF 拼写检查器 | 自 .NET Framework 4.6.1 起，WPF 应用程序中的拼写检查器在应用程序关闭期间偶尔会抛出 <xref:System.ObjectDisposedException>。 <br/><br/>在 .NET Framework 4.7 中，运行时对此异常进行了妥善处理，因此可确保再也不会对应用程序造成负面影响。 应注意，在调试器控制下运行的应用程序中会继续观察到偶尔抛出的最可能异常。  | 若要充分利用新行为，请升级到 .NET Framework 4.7。   | 边缘 |

## <a name="see-also"></a>请参阅

[.NET Framework 4.7 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-7.md)


