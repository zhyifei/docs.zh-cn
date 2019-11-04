---
title: Freezable 对象概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
ms.openlocfilehash: 755240859829042e9790b9c89e47bb7a2013ceef
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460450"
---
# <a name="freezable-objects-overview"></a>Freezable 对象概述

本主题介绍如何有效地使用和创建 <xref:System.Windows.Freezable> 对象，这些对象提供有助于提高应用程序性能的特殊功能。 被冻结对象的示例包括画笔、笔、转换、几何图形和动画。

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a>什么是可冻结的？

<xref:System.Windows.Freezable> 是一种特殊类型的对象，该对象具有两种状态：未冻结和已冻结。 解冻后，<xref:System.Windows.Freezable> 的行为与任何其他对象的行为类似。 冻结后，不能再修改 <xref:System.Windows.Freezable>。

<xref:System.Windows.Freezable> 提供 <xref:System.Windows.Freezable.Changed> 事件来通知观察者对对象的任何修改。 冻结 <xref:System.Windows.Freezable> 可以提高其性能，因为它不再需要在更改通知上消耗资源。 还可以在线程之间共享冻结的 <xref:System.Windows.Freezable>，而未冻结的 <xref:System.Windows.Freezable> 不能。

尽管 <xref:System.Windows.Freezable> 类有许多应用程序，但 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的大多数 <xref:System.Windows.Freezable> 对象都与图形子系统相关。

使用 <xref:System.Windows.Freezable> 类可以更轻松地使用特定图形系统对象，并且可以帮助提高应用程序性能。 继承自 <xref:System.Windows.Freezable> 的类型的示例包括 <xref:System.Windows.Media.Brush>、<xref:System.Windows.Media.Transform>和 <xref:System.Windows.Media.Geometry> 类。 由于它们包含非托管资源，因此，系统必须监视这些对象进行修改，然后在对原始对象进行更改时更新其相应的非托管资源。 即使您不实际修改图形系统对象，系统仍必须将它的一些资源用于监视对象，以防您这样做更改。

例如，假设您创建一个 <xref:System.Windows.Media.SolidColorBrush> 画笔，并使用它来绘制按钮的背景。

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

呈现按钮时，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 图形子系统将使用您提供的信息来绘制一组像素来创建按钮的外观。 虽然您使用纯色画笔来说明如何绘制按钮，但您的纯色画笔实际上不会执行绘制操作。 图形系统会为按钮和画笔生成快速、低级别的对象，并且这些对象确实出现在屏幕上。

如果要修改画笔，则必须重新生成这些低级别对象。 可冻结的类可让画笔查找其相应的已生成低级别对象并在更改时更新这些对象。 启用此功能后，画笔会被视为 "解冻"。

可冻结的 <xref:System.Windows.Freezable.Freeze%2A> 方法使您能够禁用此自我更新功能。 您可以使用此方法使画笔变为 "冻结" 或不可修改。

> [!NOTE]
> 并非每个可冻结的对象都可以冻结。 若要避免引发 <xref:System.InvalidOperationException>，请检查可冻结对象的 <xref:System.Windows.Freezable.CanFreeze%2A> 属性的值，以确定是否可以冻结该对象，然后再尝试将其冻结。

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

当你不再需要修改可冻结的时，冻结它可提供性能优势。 如果在此示例中冻结了画笔，则图形系统将不再需要监视其更改。 图形系统还可以进行其他优化，因为它知道画笔不会改变。

> [!NOTE]
> 为方便起见，可冻结对象保持解冻，除非你显式冻结它们。

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a>使用可冻结对象

使用未冻结的可冻结对象与使用任何其他类型的对象类似。 在下面的示例中，将 <xref:System.Windows.Media.SolidColorBrush> 的颜色在用于绘制按钮背景后从黄色更改为红色。 图形系统在幕后工作，在下次刷新屏幕时，自动将按钮从黄色更改为红色。

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a>冻结冻结

若要使 <xref:System.Windows.Freezable> 成为不可修改的，请调用其 <xref:System.Windows.Freezable.Freeze%2A> 方法。 冻结包含可冻结对象的对象时，这些对象也会被冻结。 例如，如果您冻结 <xref:System.Windows.Media.PathGeometry>，则它包含的图形和段也将冻结。

如果满足以下任一条件，则**无法**冻结可冻结的：

- 它具有动画或数据绑定属性。

- 它包含动态资源设置的属性。 （有关动态资源的详细信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。）

- 它包含不能冻结 <xref:System.Windows.Freezable> 子对象。

如果这些条件为 false，并且你不打算修改 <xref:System.Windows.Freezable>，则应将其冻结，以获取之前所述的性能优势。

调用可冻结的 <xref:System.Windows.Freezable.Freeze%2A> 方法后，将无法再修改它。 尝试修改冻结对象将导致引发 <xref:System.InvalidOperationException>。 下面的代码引发异常，因为我们尝试在冻结画笔之后修改画笔。

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

若要避免引发此异常，可以使用 <xref:System.Windows.Freezable.IsFrozen%2A> 方法来确定 <xref:System.Windows.Freezable> 是否被冻结。

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

在上面的代码示例中，使用 <xref:System.Windows.Freezable.Clone%2A> 方法为冻结对象创建了一个可修改的副本。 下一部分更详细地讨论了克隆。

> [!NOTE]
> 由于无法对冻结的可冻结对象进行动画处理，因此当你尝试使用 <xref:System.Windows.Media.Animation.Storyboard>对它们进行动画处理时，动画系统将自动创建冻结 <xref:System.Windows.Freezable> 对象的可修改复本。 若要消除克隆导致的性能开销，请在要对对象进行动画处理时使对象保持解冻。 有关利用情节提要进行动画处理的详细信息，请参阅[情节提要概述](../graphics-multimedia/storyboards-overview.md)。

### <a name="freezing-from-markup"></a>从标记冻结

若要冻结在标记中声明的 <xref:System.Windows.Freezable> 对象，请使用 `PresentationOptions:Freeze` 特性。 在下面的示例中，将 <xref:System.Windows.Media.SolidColorBrush> 声明为页资源并冻结。 然后，将使用它来设置按钮的背景。

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

若要使用 `Freeze` 属性，必须映射到 "演示选项命名空间： `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`"。 建议使用 `PresentationOptions` 前缀来映射此命名空间：

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

由于并非所有 XAML 读取器都能识别此特性，因此建议使用[mc：可忽略属性](mc-ignorable-attribute.md)将 `Presentation:Freeze` 特性标记为可忽略：

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

有关详细信息，请参阅[mc：忽略属性](mc-ignorable-attribute.md)页。

### <a name="unfreezing-a-freezable"></a>"解冻"

一旦冻结，就永远不能修改或解冻 <xref:System.Windows.Freezable>;但是，可以使用 <xref:System.Windows.Freezable.Clone%2A> 或 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 方法创建未冻结的克隆。

在下面的示例中，按钮的背景是使用画笔设置的，然后该画笔会被冻结。 使用 <xref:System.Windows.Freezable.Clone%2A> 方法创建画笔的未冻结副本。 将修改克隆，并使用它将按钮的背景从黄色更改为红色。

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> 不管使用哪种克隆方法，动画都不会复制到新的 <xref:System.Windows.Freezable>。

<xref:System.Windows.Freezable.Clone%2A> 和 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 方法将生成具有该冻结的深层副本。 如果可冻结的包含其他冻结的可冻结对象，则它们也会被克隆，并可进行修改。 例如，如果克隆一个冻结的 <xref:System.Windows.Media.PathGeometry> 以使其可修改，则还会复制其包含的图形和线段，并使其成为可修改的。

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a>创建自己的有冻结类

派生自 <xref:System.Windows.Freezable> 的类获得以下功能。

- 特殊状态：只读（冻结）和可写状态。

- 线程安全：可在线程之间共享冻结 <xref:System.Windows.Freezable>。

- 详细更改通知：与其他 <xref:System.Windows.DependencyObject>不同，可冻结对象会在子属性值更改时提供更改通知。

- 轻松克隆：可冻结的类已经实现了几种生成深层克隆的方法。

<xref:System.Windows.Freezable> 是一种 <xref:System.Windows.DependencyObject>类型，因此使用了依赖属性系统。 类属性不一定是依赖属性，但使用依赖属性将减少您必须编写的代码量，因为 <xref:System.Windows.Freezable> 类设计为具有依赖属性。 有关依赖属性系统的详细信息，请参阅[依赖属性概述](dependency-properties-overview.md)。

每个 <xref:System.Windows.Freezable> 子类必须重写 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 方法。 如果你的类对所有数据使用依赖属性，则你已完成。

如果类包含非依赖属性数据成员，还必须重写以下方法：

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

还必须遵守以下规则，以便访问和写入不是依赖属性的数据成员：

- 在读取非依赖属性数据成员的任何 API 的开头，调用 <xref:System.Windows.Freezable.ReadPreamble%2A> 方法。

- 在写入非依赖属性数据成员的任何 API 的开头，调用 <xref:System.Windows.Freezable.WritePreamble%2A> 方法。 （在 API 中调用 <xref:System.Windows.Freezable.WritePreamble%2A> 后，如果还读取非依赖属性数据成员，则无需额外调用 <xref:System.Windows.Freezable.ReadPreamble%2A>。）

- 在退出写入非依赖属性数据成员的方法之前调用 <xref:System.Windows.Freezable.WritePostscript%2A> 方法。

如果类包含 <xref:System.Windows.DependencyObject> 对象的非依赖属性数据成员，则每次更改其值时，还必须调用 <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> 方法，即使要将成员设置为 `null`也是如此。

> [!NOTE]
> 使用对基实现的调用来开始每个 <xref:System.Windows.Freezable> 方法，这一点非常重要。

有关自定义 <xref:System.Windows.Freezable> 类的示例，请参阅[自定义动画示例](https://go.microsoft.com/fwlink/?LinkID=159981)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Freezable>
- [自定义动画示例](https://go.microsoft.com/fwlink/?LinkID=159981)
- [依赖项属性概述](dependency-properties-overview.md)
- [自定义依赖属性](custom-dependency-properties.md)
