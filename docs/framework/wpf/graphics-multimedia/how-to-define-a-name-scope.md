---
title: 如何：定义名称范围
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: 656c1e9af11697cd4a1253bdab673887765976a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674461"
---
# <a name="how-to-define-a-name-scope"></a>如何：定义名称范围
若要使用进行动画处理<xref:System.Windows.Media.Animation.Storyboard>在代码中，必须创建<xref:System.Windows.NameScope>并注册到拥有该名称范围的元素的目标对象名称。 在以下示例中，<xref:System.Windows.NameScope>为创建`myMainPanel`。 两个按钮`button1`和`button2`，添加到面板，并注册其名称。 多个动画和<xref:System.Windows.Media.Animation.Storyboard>创建。 情节提要的<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法用于启动动画。  
  
 因为`button1`， `button2`，并`myMainPanel`所有共享相同的名称范围，其中的任意一个可用于<xref:System.Windows.Media.Animation.Storyboard><xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法来启动动画。  
  
## <a name="example"></a>示例  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a>请参阅
- [使用情节提要对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)
- [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
