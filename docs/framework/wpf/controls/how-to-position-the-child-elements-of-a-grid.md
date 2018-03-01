---
title: "如何：定位网格的子元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ca385e1aee10fb10ac3e912999aec3a11d03ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>如何：定位网格的子元素
此示例演示如何使用 get 和 set 定义的方法<xref:System.Windows.Controls.Grid>来定位子元素。  
  
## <a name="example"></a>示例  
 下面的示例定义一个父<xref:System.Windows.Controls.Grid>元素 (`grid1`) 具有三列和三个行。 子<xref:System.Windows.Shapes.Rectangle>元素 (`rect1`) 添加到<xref:System.Windows.Controls.Grid>在列的位置零，行位置零。 <xref:System.Windows.Controls.Button>元素表示方法可以调用以进行重新定位<xref:System.Windows.Shapes.Rectangle>中的元素<xref:System.Windows.Controls.Grid>。 当用户单击按钮时，将激活相关的方法。  
  
 [!code-xaml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 下面的代码隐藏示例处理方法，该按钮<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件引发。 此示例将对这些方法调用<xref:System.Windows.Controls.TextBlock>元素使用与 get 方法以输出字符串的形式将新属性值。  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Grid>  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)
