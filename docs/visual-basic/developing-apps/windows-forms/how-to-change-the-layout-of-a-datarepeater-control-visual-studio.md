---
title: 如何：更改 DataRepeater 控件的布局 (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: fa780ee40171143c17b5bdbda4a97179ed5f2151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590837"
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a>如何：更改 DataRepeater 控件的布局 (Visual Studio)
<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件可以显示在 （项目垂直滚动） 的垂直或水平 （项目水平滚动） 方向。 你可以在设计时或在运行时将方向更改通过更改<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性。 如果你更改<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性在运行时，你可能还想要调整大小<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>和重新定位其子控件。  
  
> [!NOTE]
>  如果在重新定位控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>在运行时，你将需要调用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>和<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>方法的开头和结尾的代码块，重新定位控件。  
  
### <a name="to-change-the-layout-at-design-time"></a>若要在设计时更改布局  
  
1.  在 Windows 窗体设计器中，选择<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
    > [!NOTE]
    >  您必须选择控件外边框的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>通过单击该控件，不在上面的下半部分区域的控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>区域。  
  
2.  在属性窗口中，设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性为<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical>或<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>。  
  
### <a name="to-change-the-layout-at-run-time"></a>若要在运行时更改布局  
  
1.  将以下代码添加到按钮或菜单`Click`事件处理程序：  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  在大多数情况下，你将想要添加类似于在示例部分中显示要调整大小的代码<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>和重新排列控件以适应新的方向。  
  
## <a name="example"></a>示例  
 下面的示例演示如何响应<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged>事件处理程序中的事件。 此示例要求你拥有<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件名为`DataRepeater1`在窗体和，其<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>包含两个<xref:System.Windows.Forms.TextBox>控件名为`TextBox1`和`TextBox2`。  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>  
 [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
