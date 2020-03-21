---
title: 如何：在演示图板启动之后使用事件触发器来控制演示图板
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186706"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>如何：在演示图板启动之后使用事件触发器来控制演示图板

此示例演示如何在 启动后控制<xref:System.Windows.Media.Animation.Storyboard>。 要使用<xref:System.Windows.Media.Animation.Storyboard>[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]开始 ，<xref:System.Windows.Media.Animation.BeginStoryboard>使用 ， 将动画分发到它们为对象和属性设置动画，然后启动情节提要。 如果通过指定<xref:System.Windows.Media.Animation.BeginStoryboard>名称<xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>的属性来命名，则可以将其制作为可控制的情节提要。 然后，您可以在情节提要启动后以交互方式控制它。

将以下情节提要操作与<xref:System.Windows.EventTrigger>对象一起使用来控制情节提要。

- <xref:System.Windows.Media.Animation.PauseStoryboard>：暂停情节提要。

- <xref:System.Windows.Media.Animation.ResumeStoryboard>：恢复暂停的情节提要。

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>：更改情节提要速度。

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>：将情节提要提前到填充期结束时（如果有）。

- <xref:System.Windows.Media.Animation.StopStoryboard>：停止情节提要。

- <xref:System.Windows.Media.Animation.RemoveStoryboard>：删除情节提要，释放资源。

## <a name="example"></a>示例

下面的示例使用可控的情节提要操作来交互控制情节提要。

> [!NOTE]
> 要查看使用代码控制情节提要的示例，请参阅[在情节提要开始使用其交互方法后对其进行控制](how-to-control-a-storyboard-after-it-starts.md)。

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

有关其他示例，请参阅[动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [在情节提要启动后使用其交互式方法对其进行控制](how-to-control-a-storyboard-after-it-starts.md)
- [动画概述](animation-overview.md)
- [演示图板概述](storyboards-overview.md)
