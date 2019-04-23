---
ms.openlocfilehash: a573a78109036b87201b53f72aa8dba6755e7a21
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803316"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>从自定义 INCC 集合删除项时选择器出现故障

|   |   |
|---|---|
|详细信息|<code>T:System.InvalidOperationException</code> 会在以下方案中发生：<ul><li><code>T:System.Windows.Controls.Primitives.Selector</code> 的 ItemsSource 是 <code>T:System.Collections.Specialized.INotifyCollectionChanged</code> 自定义实现的集合。</li><li>从集合中删除所选的项。</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> 中 <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1（表示未知位置）。</li></ul>异常的调用堆栈开始于 System.Windows.Threading.Dispatcher.VerifyAccess()、System.Windows.DependencyObject.GetValue(DependencyProperty dp)、System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element)。如果应用程序的 Dispatcher 线程不止一个，则 .NET Framework 4.5 中可能发生此异常。 在 .NET Framework 4.7 中，也可能在具有单个 Dispatcher 线程的应用程序中发生该异常。 此问题已在 .NET Framework 4.7.1 中解决。|
|建议|升级到 .NET Framework 4.7.1。|
|范围|次要|
|版本|4.7|
|类型|运行时|
