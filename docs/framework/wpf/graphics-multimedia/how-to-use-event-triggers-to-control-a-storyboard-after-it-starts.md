---
title: 如何：在情节提要启动之后使用事件触发器来控制情节提要
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 32591edd065a8122b84ff14102f672ccf6001d67
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855852"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>如何：在情节提要启动之后使用事件触发器来控制情节提要

此示例演示如何<xref:System.Windows.Media.Animation.Storyboard>在启动后对其进行控制。 若要使用<xref:System.Windows.Media.Animation.Storyboard> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]启动，请使用<xref:System.Windows.Media.Animation.BeginStoryboard>，它将动画分散到它们动画处理的对象和属性，然后启动情节提要。 如果通过指定名称的<xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>属性来指定名称，则会使其成为可控制的<xref:System.Windows.Media.Animation.BeginStoryboard>情节提要。 然后，你可以在情节提要启动后以交互方式控制情节提要。

结合使用以下情节提要操作和<xref:System.Windows.EventTrigger>对象控制情节提要。

- <xref:System.Windows.Media.Animation.PauseStoryboard>：暂停情节提要。

- <xref:System.Windows.Media.Animation.ResumeStoryboard>：恢复暂停的情节提要。

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>：更改情节提要的速度。

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>：将情节提要前进到其填充期的末尾（如果有一个）。

- <xref:System.Windows.Media.Animation.StopStoryboard>：停止情节提要。

- <xref:System.Windows.Media.Animation.RemoveStoryboard>：删除情节提要，释放资源。

## <a name="example"></a>示例

下面的示例使用可控制的情节提要操作以交互方式控制情节提要。

> [!NOTE]
> 若要查看使用代码控制情节提要的示例，请参阅[使用其交互式方法控制情节提要](how-to-control-a-storyboard-after-it-starts.md)。

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

有关其他示例，请参阅[动画示例库](https://go.microsoft.com/fwlink/?LinkID=159969)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [在情节提要启动后使用其交互式方法对其进行控制](how-to-control-a-storyboard-after-it-starts.md)
- [动画概述](animation-overview.md)
- [演示图板概述](storyboards-overview.md)
