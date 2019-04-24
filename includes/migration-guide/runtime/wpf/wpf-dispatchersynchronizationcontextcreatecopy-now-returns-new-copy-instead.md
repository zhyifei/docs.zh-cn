---
ms.openlocfilehash: ff4d67a1c821fc96130c4efbd88eb5c56766da06
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803354"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>WPF DispatcherSynchronizationContext.CreateCopy 现在返回新副本，而非当前实例

|   |   |
|---|---|
|详细信息|在 .NET Framework 4 中，<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> 返回当前实例的引用，这主要作为一项性能优化。 在 .NET Framework 4.5 中，它返回新实例，这可以首次得出结论：相同的引用指示执行线程位于正确的同步上下文中。  检查这些引用标识的代码可能不受影响，但由于此更改，作为迁移到 .NET Framework 4.5 或更高版本的一部分，应测试调用 <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> 的代码。|
|建议|请注意，<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> 现在将返回新的 <xref:System.Threading.SynchronizationContext?displayProperty=name> 对象。 以前，使用按此方法所生成引用的等效项的代码实际上不会检查它是否在正确的上下文中，但针对 .NET Framework 4.5 或更高版本生成时则会检查。  虽然不太可能产生问题，但执行受影响的代码路径应足以确定这是否会带来任何问题。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType></li></ul>|
