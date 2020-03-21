---
title: 如何：定位网格的子元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 44268c32732a9409ea30f028adaa8a2631a06c5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186722"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>如何：定位网格的子元素
此示例演示如何使用定义 get<xref:System.Windows.Controls.Grid>和设置方法来定位子元素。  
  
## <a name="example"></a>示例  
 下面的示例定义具有三列和<xref:System.Windows.Controls.Grid>三行`grid1`的父元素 （ ）。 子<xref:System.Windows.Shapes.Rectangle>元素 （`rect1`） 添加到列<xref:System.Windows.Controls.Grid>位置零，行位置零。 <xref:System.Windows.Controls.Button>元素表示可以调用以重新定位<xref:System.Windows.Shapes.Rectangle>元素的方法。 <xref:System.Windows.Controls.Grid> 当用户单击按钮时，将激活相关方法。  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 下面的代码后面示例处理按钮<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件引发的方法。 该示例将这些方法调用写入<xref:System.Windows.Controls.TextBlock>使用相关 get 方法将新属性值输出为字符串的元素。  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 这是完成的结果！

 ![屏幕截图描绘了包含两列的 WPF 用户界面，右侧有一个 3 x 3 网格，左侧有按钮在网格的列和行之间移动彩色矩形](././media/grid-methods-sample.png)
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Grid>
- [面板概述](panels-overview.md)
