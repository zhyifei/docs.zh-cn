---
title: "如何：在不更改时间线速度的情况下更改时钟速度"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 98cfa63eac4bc697c5412616de71395624408c63
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>如何：在不更改时间线速度的情况下更改时钟速度
A<xref:System.Windows.Media.Animation.ClockController>对象的<xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>属性使您能够更改的速度<xref:System.Windows.Media.Animation.Clock>而无需更改<xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>的时钟的<xref:System.Windows.Media.Animation.Timeline>。 在下面的示例中，<xref:System.Windows.Media.Animation.ClockController>用于以交互方式修改<xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>的时钟。 <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated>事件和时钟的<xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A>属性用于显示时钟的当前全局速度每次其交互式<xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>更改。  
  
## <a name="example"></a>示例  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
