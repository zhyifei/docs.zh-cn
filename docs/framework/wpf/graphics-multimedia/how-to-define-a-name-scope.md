---
title: "如何：定义名称范围"
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
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3007088f849f40e4e9b4f1846c19c98c33e95c17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-name-scope"></a>如何：定义名称范围
使用进行动画处理<xref:System.Windows.Media.Animation.Storyboard>在代码中，你必须创建<xref:System.Windows.NameScope>并将注册拥有该名称范围的元素的目标对象的名称。 在下面的示例中，<xref:System.Windows.NameScope>为创建`myMainPanel`。 两个按钮，`button1`和`button2`，添加到面板中，并注册其名称。 几个动画和<xref:System.Windows.Media.Animation.Storyboard>创建。 情节提要的<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法用于启动动画。  
  
 因为`button1`， `button2`，和`myMainPanel`所有共享相同的名称范围，其中任何一个可与<xref:System.Windows.Media.Animation.Storyboard><xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法来启动动画。  
  
## <a name="example"></a>示例  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a>请参阅  
 [使用情节提要对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
