---
title: "如何：在演示图板启动之后使用事件触发器来控制演示图板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d9e096969713cc4b9c42261b238691d51cb49d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>如何：在演示图板启动之后使用事件触发器来控制演示图板
此示例演示如何控制<xref:System.Windows.Media.Animation.Storyboard>启动后对它。 若要启动<xref:System.Windows.Media.Animation.Storyboard>使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，使用<xref:System.Windows.Media.Animation.BeginStoryboard>，这样可以将对象和属性，它们进行动画处理，然后启动情节提要的动画。 如果你向提供<xref:System.Windows.Media.Animation.BeginStoryboard>通过指定的名称及其<xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>属性，你可以让它从此情节提要。 然后，你可以以交互方式控制情节提要在其开始后。  
  
 使用下列情节提要操作连同<xref:System.Windows.EventTrigger>对象以控制情节提要。  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>： 暂停情节提要。  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>： 将恢复暂停的情节提要。  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>： 更改的情节提要速度。  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>： 如果有的话，请转到其填充期间，末尾情节提要。  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>： 停止情节提要。  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>： 删除的情节提要释放资源。  
  
## <a name="example"></a>示例  
 下面的示例使用可控演示图板操作以交互方式控制情节提要。  
  
 **注意：**若要查看的情节提要控制通过使用代码示例，请参阅[控制情节提要后它启动使用其交互式方法](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)。  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 有关其他示例，请参阅[动画示例库](http://go.microsoft.com/fwlink/?LinkID=159969)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [在情节提要启动后使用其交互式方法对其进行控制](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [演示图板概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
