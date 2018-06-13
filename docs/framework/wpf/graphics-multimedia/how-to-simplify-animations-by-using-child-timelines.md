---
title: 如何：使用子时间线简化动画
ms.date: 03/30/2017
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
ms.openlocfilehash: 57ea558b167f647ec7597ba95382abb0e48f699f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561668"
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>如何：使用子时间线简化动画
此示例演示如何通过使用子简化动画<xref:System.Windows.Media.Animation.ParallelTimeline>对象。 A<xref:System.Windows.Media.Animation.Storyboard>是一种<xref:System.Windows.Media.Animation.Timeline>提供为它包含的时间线的目标信息。 使用<xref:System.Windows.Media.Animation.Storyboard>提供时间线目标信息，包括对象和属性的信息。  
  
 若要开始动画，使用一个或多<xref:System.Windows.Media.Animation.ParallelTimeline>对象作为嵌套的子元素的<xref:System.Windows.Media.Animation.Storyboard>。 这些<xref:System.Windows.Media.Animation.ParallelTimeline>对象可以包含其他动画，因此，可以更好地封装复杂的动画中的计时序列。 例如，如果进行动画处理<xref:System.Windows.Controls.TextBlock>和中相同的多个形状<xref:System.Windows.Media.Animation.Storyboard>，你可以分隔为动画<xref:System.Windows.Controls.TextBlock>和形状，将放入一个单独的每个<xref:System.Windows.Media.Animation.ParallelTimeline>。 因为每个<xref:System.Windows.Media.Animation.ParallelTimeline>都具有其自己<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>和的所有子元素<xref:System.Windows.Media.Animation.ParallelTimeline>开始相对于此<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>，更好地封装计时。  
  
 下面的示例进行动画处理的文本的两个片段 (<xref:System.Windows.Controls.TextBlock>对象) 从在同一<xref:System.Windows.Media.Animation.Storyboard>。 A<xref:System.Windows.Media.Animation.ParallelTimeline>封装之一的动画<xref:System.Windows.Controls.TextBlock>对象。  
  
 **性能注意：** 虽然可以嵌套<xref:System.Windows.Media.Animation.Storyboard>时间线内彼此之上，<xref:System.Windows.Media.Animation.ParallelTimeline>是更适合嵌套因为它们需要较少的开销。 (<xref:System.Windows.Media.Animation.Storyboard>类继承自<xref:System.Windows.Media.Animation.ParallelTimeline>类。)  
  
## <a name="example"></a>示例  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>请参阅  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [指定演示图板动画之间的 HandoffBehavior](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
