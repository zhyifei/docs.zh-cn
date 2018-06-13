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
ms.openlocfilehash: d3b9f6f7af22b2a846f4ee34e8d4d00bb032fd69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548465"
---
# <a name="freezable-objects-overview"></a>Freezable 对象概述
本主题介绍如何有效地使用和创建<xref:System.Windows.Freezable>对象，提供可以帮助提高应用程序性能的特殊功能。 可冻结的对象的示例包括画笔、 笔、 转换、 几何图形和动画。  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a>可冻结是什么？  
 A<xref:System.Windows.Freezable>是有两种状态的对象的特殊类型： 解冻和冻结。 当未冻结，<xref:System.Windows.Freezable>似乎的行为类似于任何其他对象。 冻结后，<xref:System.Windows.Freezable>无法再进行修改。  
  
 A<xref:System.Windows.Freezable>提供<xref:System.Windows.Freezable.Changed>事件以通知观察器对对象进行任何修改。 冻结<xref:System.Windows.Freezable>可以提高其性能，因为它不再需要更改通知而消耗资源。 冻结<xref:System.Windows.Freezable>还可以跨线程，而解冻共享<xref:System.Windows.Freezable>不能。  
  
 尽管<xref:System.Windows.Freezable>类具有很多应用程序，最<xref:System.Windows.Freezable>中的对象[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]与图形子系统相关。  
  
 <xref:System.Windows.Freezable>类可以容易地使用某些图形系统对象，还有助于提高应用程序性能。 继承自的类型的示例<xref:System.Windows.Freezable>包括<xref:System.Windows.Media.Brush>， <xref:System.Windows.Media.Transform>，和<xref:System.Windows.Media.Geometry>类。 因为它们包含非托管的资源，系统必须监视这些对象的修改，并对原始对象的更改时，然后更新其相应的非托管的资源。 即使你无需实际修改图形系统对象，系统也必须花费一些监视该对象，其资源的情况下对其进行更改。  
  
 例如，假设你创建<xref:System.Windows.Media.SolidColorBrush>画笔并使用它来绘制背景的按钮。  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 当呈现按钮时，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]图形子系统使用您提供要绘制的一组像素创建一个按钮的外观的信息。 尽管纯色画笔用于描述应如何绘制按钮，纯色画笔实际上不进行绘制。 图形系统生成的按钮和画笔的快速、 低级别对象，并且它实际出现在屏幕的那些对象。  
  
 如果你打算修改画笔，这些低级别的对象将不得不重新生成。 可冻结类是什么使画笔能够以查找其相应的生成的、 低级别对象，并且要将它更改时对它们进行更新。 启用此功能后，画笔便被认为是"解冻"。  
  
 可冻结的<xref:System.Windows.Freezable.Freeze%2A>方法使您能够禁用此自我更新功能。 此方法可用于使画笔变为"冻结"或不可修改。  
  
> [!NOTE]
>  可以冻结并非每个可冻结对象。 若要避免引发<xref:System.InvalidOperationException>，检查可冻结对象的值<xref:System.Windows.Freezable.CanFreeze%2A>属性来确定是否它可以冻结然后再尝试冻结它。  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 当不再需要修改可冻结时，冻结它提供性能优势。 如果你是冻结的画笔在此示例中，图形系统将不再需要监视的更改。 图形系统还可以进行其他优化，因为它知道画笔不会更改。  
  
> [!NOTE]
>  为方便起见，可冻结对象仍未冻结，除非显式冻结。  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a>使用可冻结对象  
 使用解冻冻结就像使用任何其他类型的对象。 在下面的示例中的颜色<xref:System.Windows.Media.SolidColorBrush>从黄色更改为红色后它用于绘制背景的按钮。 图形系统自动更改按钮从黄色为红色下次刷新屏幕时在后台运行。  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a>冻结可冻结  
 若要使<xref:System.Windows.Freezable>调用不可修改，其<xref:System.Windows.Freezable.Freeze%2A>方法。 如果已冻结包含可冻结的对象的对象，这些对象也都将冻结。 例如，如果冻结<xref:System.Windows.Media.PathGeometry>，图形和它包含的线段会被冻结。  
  
 可冻结**无法**被冻结如果下列任一条件：  
  
-   它具有经过动画处理或数据绑定属性。  
  
-   它具有由动态资源设置的属性。 (请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)动态资源有关的详细信息。)  
  
-   它包含<xref:System.Windows.Freezable>无法冻结的子对象。  
  
 如果这些条件都为 false，并且你不打算修改<xref:System.Windows.Freezable>，则应冻结其获得前面所述的性能优势。  
  
 一旦调用可冻结的<xref:System.Windows.Freezable.Freeze%2A>方法，它无法再进行修改。 尝试修改冻结对象原因<xref:System.InvalidOperationException>引发。 下面的代码引发异常，因为我们尝试来修改画笔后已冻结。  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 若要避免发生此异常，可以使用<xref:System.Windows.Freezable.IsFrozen%2A>方法来确定是否<xref:System.Windows.Freezable>被冻结。  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 在前面的代码示例中，可修改副本已冻结的对象使用的<xref:System.Windows.Freezable.Clone%2A>方法。 下一部分讨论克隆中更多详细信息。  
  
 **请注意**因为冻结可冻结无法进行动画处理，动画系统会自动创建的可修改克隆冻结<xref:System.Windows.Freezable>对象时尝试对它进行动画处理，使其与<xref:System.Windows.Media.Animation.Storyboard>。 若要消除开销引起的克隆的性能，保留解冻如果你想要对它进行动画处理的对象。 有关如何使用情节提要具有动画效果的详细信息，请参阅[情节提要概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)。  
  
### <a name="freezing-from-markup"></a>从标记冻结  
 若要冻结<xref:System.Windows.Freezable>对象声明在标记中，你使用`PresentationOptions:Freeze`属性。 在下面的示例中，<xref:System.Windows.Media.SolidColorBrush>声明为页资源并在冻结。 然后，它用于设置按钮的背景。  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 若要使用`Freeze`属性，则你必须映射到演示文稿选项命名空间： `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`。 `PresentationOptions` 是用于映射此命名空间的建议的前缀：  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 因为并非所有的 XAML 读取器识别此特性，建议你使用[mc： 可忽略属性](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)标记`Presentation:Freeze`属性为可忽略：  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 有关详细信息，请参阅[mc： 可忽略属性](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)页。  
  
### <a name="unfreezing-a-freezable"></a>"解冻"可冻结  
 一次冻结，<xref:System.Windows.Freezable>永远不会修改或解冻; 但是，你可以创建未使用的冻结的克隆<xref:System.Windows.Freezable.Clone%2A>或<xref:System.Windows.Freezable.CloneCurrentValue%2A>方法。  
  
 在下面的示例中，使用一个画笔设置按钮的背景，然后冻结该画笔。 冻结副本的画笔使用<xref:System.Windows.Freezable.Clone%2A>方法。 克隆为修改并用于将从黄色的按钮的背景更改为红色。  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  无论使用哪种克隆方法，动画不会被复制到新<xref:System.Windows.Freezable>。  
  
 <xref:System.Windows.Freezable.Clone%2A>和<xref:System.Windows.Freezable.CloneCurrentValue%2A>方法将产生可冻结的深层副本。 如果可冻结包含其他冻结可冻结的对象，它们是克隆，并且进行可修改的。 例如，如果克隆某个冻结<xref:System.Windows.Media.PathGeometry>使可供修改，图形和它包含的线段都还复制并保持可修改。  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a>创建你自己可冻结类  
 派生自的类<xref:System.Windows.Freezable>可以获得以下功能。  
  
-   特殊的状态： 的只读 （冻结） 和可写状态。  
  
-   线程安全： 冻结<xref:System.Windows.Freezable>可以跨线程共享。  
  
-   详细的更改通知： 与其他不同<xref:System.Windows.DependencyObject>s，对子属性值更改时可冻结对象提供更改通知。  
  
-   轻松克隆： 可冻结类已实现生成深层克隆的几种方法。  
  
 A<xref:System.Windows.Freezable>是一种<xref:System.Windows.DependencyObject>，因此将使用依赖项属性系统。 您的类属性无需是依赖项属性，但使用依赖项属性将减少你必须编写的代码，因为量<xref:System.Windows.Freezable>类旨在与记住的依赖项属性。 依赖项属性系统有关的详细信息，请参阅[依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。  
  
 每个<xref:System.Windows.Freezable>子类必须重写<xref:System.Windows.Freezable.CreateInstanceCore%2A>方法。 如果你的类使用依赖项属性的所有数据，你已完成。  
  
 如果你的类包含非依赖项属性数据成员，还必须重写以下方法：  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 你必须遵守以下规则用于访问和写入不是依赖项属性的数据成员：  
  
-   任何开头[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]读取非依赖项属性数据成员，请调用<xref:System.Windows.Freezable.ReadPreamble%2A>方法。  
  
-   在开始写入非依赖项属性数据成员的任何 API 时，调用<xref:System.Windows.Freezable.WritePreamble%2A>方法。 (已调用后<xref:System.Windows.Freezable.WritePreamble%2A>中[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]，不需要进行其他调用<xref:System.Windows.Freezable.ReadPreamble%2A>如果你也阅读非依赖项属性数据成员。)  
  
-   调用<xref:System.Windows.Freezable.WritePostscript%2A>之前退出写入非依赖项属性数据成员的方法的方法。  
  
 如果你的类包含非依赖项属性数据成员<xref:System.Windows.DependencyObject>对象，你还必须调用<xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A>方法每次更改的它们的值，即使你要将成员设置为`null`。  
  
> [!NOTE]
>  务必在开始每<xref:System.Windows.Freezable>您通过调用基实现重写的方法。  
  
 有关自定义的示例<xref:System.Windows.Freezable>类，请参阅[自定义动画示例](http://go.microsoft.com/fwlink/?LinkID=159981)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Freezable>  
 [自定义动画示例](http://go.microsoft.com/fwlink/?LinkID=159981)  
 [依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [自定义依赖属性](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
