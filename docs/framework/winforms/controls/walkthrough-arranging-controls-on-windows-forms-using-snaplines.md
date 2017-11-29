---
title: "演练：使用对齐线在 Windows 窗体上排列控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be514f435b787c770eca114d42bee5c1424a40c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a>演练：使用对齐线在 Windows 窗体上排列控件
在窗体上精确地放置控件对于许多应用程序而言是高优先级。 Windows 窗体设计器为你提供许多布局工具实现此目的。 最重要之一是<xref:System.Windows.Forms.Design.Behavior.SnapLine>功能。  
  
 对齐线显示确切位置与其他控件的控件对齐。 它们还显示你的控件，为指定的 Windows 用户界面指南之间的边距的建议的距离。 有关详细信息，请参阅[用户界面设计和开发](http://go.microsoft.com/FWLink/?LinkId=83878)。  
  
 对齐线可以方便轻松地对齐您控件，获得简洁、 专业外观和行为 （外观和感觉）。  
  
 本演练涉及以下任务：  
  
-   创建 Windows 窗体项目  
  
-   间距和对齐控件使用对齐线  
  
-   到窗体和容器的边缘对齐  
  
-   对齐到分组后的控件  
  
-   使用对齐线通过勾画放置控件  
  
-   从工具箱中拖动控件时使用对齐线  
  
-   使用对齐线的大小调整控件  
  
-   对齐标签与控件的文本  
  
-   使用键盘导航线对齐  
  
-   对齐线和布局面板  
  
-   禁用对齐线  
  
 完成后，将会对齐线功能所发挥的布局作用的了解。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
## <a name="creating-the-project"></a>创建项目  
 第一步是创建项目并设置窗体。  
  
#### <a name="to-create-the-project"></a>创建项目  
  
1.  创建一个名为"SnaplineExample"的基于 Windows 的应用程序项目。 有关详细信息，请参阅[如何：创建一个 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)。  
  
2.  在窗体设计器中选择窗体。  
  
## <a name="spacing-and-aligning-controls-using-snaplines"></a>间距和对齐控件使用对齐线  
 对齐线使您可以在你的窗体上对齐控件准确且直观的方式。 它们显示在与另一个控件或组控件将保持一致的位置附近移动选定的控件时。 你的选择将"对齐"到建议的位置根据越过其他控件。  
  
#### <a name="to-arrange-controls-using-snaplines"></a>使用对齐线排列控件  
  
1.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。  
  
2.  移动<xref:System.Windows.Forms.Button>在窗体右下角的控件。 请注意显示为对齐线<xref:System.Windows.Forms.Button>控件接近下边缘和右边框的窗体。 这些对齐线显示控件的边框和窗体的建议的距离。  
  
3.  移动<xref:System.Windows.Forms.Button>控件周围的边框的窗体并注意对齐线的显示位置。 完成后，移动<xref:System.Windows.Forms.Button>附近窗体的中心。  
  
4.  将另一个<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。  
  
5.  移动第二个<xref:System.Windows.Forms.Button>控件，直到它是几乎与第一个级别。 请注意出现在两个按钮的文本基线对齐线，并记下你移动的控件对齐到的位置，则完全与另一个控件的级别。  
  
6.  移动第二个<xref:System.Windows.Forms.Button>控制直到它位于第一个的正上方。 请注意出现沿左边缘和右边缘的两个按钮，并记下该控件与准确对齐与另一个控件的位置的移动对齐的对齐线。  
  
7.  选择其中一个<xref:System.Windows.Forms.Button>控制并将其移近另一个，直到它们几乎接触。 请注意它们之间的对齐线。 此距离是控件的边框之间的建议的距离。 另请注意你移动的控件对齐到此位置。  
  
8.  将两个<xref:System.Windows.Forms.Panel>控件从**工具箱**拖动到窗体。  
  
9. 将其中一个移动<xref:System.Windows.Forms.Panel>控件，直到它是几乎与第一个级别。 请注意显示两个控件的边缘和下边缘沿并记下你移动的控件对齐到的位置，则完全级别与另一个控件的对齐线。  
  
## <a name="aligning-to-form-and-container-margins"></a>到窗体和容器的边缘对齐  
 对齐线有助于以一致的方式对齐将控件与窗体和容器的边距。  
  
#### <a name="to-align-controls-to-form-and-container-margins"></a>对齐控件添加到窗体和容器的边距  
  
1.  选择其中一个<xref:System.Windows.Forms.Button>控制并将其移接近右边框的窗体中，直到显示对齐线。 从右边框对齐线的距离是控件的总和<xref:System.Windows.Forms.Control.Margin%2A>属性和窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性值。  
  
> [!NOTE]
>  如果窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性设置为 0,0,0,0、 Windows 窗体设计器使该窗体指定隐藏<xref:System.Windows.Forms.Control.Padding%2A>9,9,9,9 的值。 若要重写此行为，分配 0,0,0,0 以外的值。  
  
1.  更改的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Margin%2A>属性通过展开<xref:System.Windows.Forms.Control.Margin%2A>中的条目**属性**窗口和设置<xref:System.Windows.Forms.Padding.All%2A>属性设为 0。 有关详细信息，请参阅[演练： 设计出 Windows 窗体控件与 Padding、 Margins 和 AutoSize 属性](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)。  
  
2.  移动<xref:System.Windows.Forms.Button>接近右边框直到显示对齐线在窗体控件。 此距离现在由窗体的值指定<xref:System.Windows.Forms.Control.Padding%2A>属性。  
  
3.  拖动<xref:System.Windows.Forms.GroupBox>控件从**工具箱**拖动到窗体。  
  
4.  更改的值<xref:System.Windows.Forms.GroupBox>控件的<xref:System.Windows.Forms.Control.Padding%2A>属性通过展开<xref:System.Windows.Forms.Control.Padding%2A>中的条目**属性**窗口和设置<xref:System.Windows.Forms.Padding.All%2A>属性设置为 10。  
  
5.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到<xref:System.Windows.Forms.GroupBox>控件。  
  
6.  移动<xref:System.Windows.Forms.Button>接近的右边框的控件<xref:System.Windows.Forms.GroupBox>控制直到显示对齐线。 移动<xref:System.Windows.Forms.Button>控件中<xref:System.Windows.Forms.GroupBox>控制和注意对齐线的显示位置。  
  
## <a name="aligning-to-grouped-controls"></a>对齐到分组后的控件  
 你可以使用对齐线对齐分组后的控件以及为控件中<xref:System.Windows.Forms.GroupBox>控件。  
  
#### <a name="to-align-to-grouped-controls"></a>对齐到一组控件  
  
1.  选择两个窗体上的控件。 移动所选内容，并记下你的选择和其他控件之间显示的对齐线。  
  
2.  拖动<xref:System.Windows.Forms.GroupBox>控件从**工具箱**拖动到窗体。  
  
3.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到<xref:System.Windows.Forms.GroupBox>控件。  
  
4.  选择其中一个<xref:System.Windows.Forms.Button>控制并移动文件<xref:System.Windows.Forms.GroupBox>控件。 请注意显示的两端的对齐线<xref:System.Windows.Forms.GroupBox>控件。 另请注意显示的两端的对齐线<xref:System.Windows.Forms.Button>所包含的控件<xref:System.Windows.Forms.GroupBox>控件。 控件的子级的容器控件还支持对齐线。  
  
## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a>使用对齐线通过勾画放置控件  
 对齐线有助于控件对齐时你首先将其放在窗体上。  
  
#### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a>若要使用对齐线控件置于通过勾画  
  
1.  在“工具箱” 中，单击 <xref:System.Windows.Forms.Button> 控件图标。 请勿将其拖到窗体上。  
  
2.  将鼠标指针移窗体的设计图面。 请注意，指针会更改为十字形，同时会附上 <xref:System.Windows.Forms.Button> 控件图标。 另请注意显示来建议对齐的位置的对齐线<xref:System.Windows.Forms.Button>控件。  
  
3.  单击并按住鼠标按钮。  
  
4.  拖动鼠标指针在窗体。 请注意，绘制概述，指示的位置和控件的大小。  
  
5.  拖动指针，直到它与另一个控件在窗体上对齐。 请注意，显示对齐线，以指示对齐方式。  
  
6.  释放鼠标按钮。 位置和大小轮廓线指示在创建滑块控件。  
  
## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a>从工具箱中拖动控件时使用对齐线  
 对齐线有助于控件对齐将它们从**工具箱**拖动到窗体。  
  
#### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a>若要从工具箱中拖动控件时使用对齐线  
  
1.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体，但不是释放鼠标按钮。  
  
2.  将鼠标指针移窗体的设计图面。 请注意，指针更改以指示的位置新<xref:System.Windows.Forms.Button>，都会创建控件。  
  
3.  拖动鼠标指针在窗体。 请注意显示来建议对齐的位置的对齐线<xref:System.Windows.Forms.Button>控件。 查找与其他控件对齐的位置。  
  
4.  释放鼠标按钮。 在指示对齐线的位置创建该控件。  
  
## <a name="resizing-controls-using-snaplines"></a>使用对齐线的大小调整控件  
 对齐线有助于对齐控件，如调整其大小。  
  
#### <a name="to-resize-a-control-using-snaplines"></a>若要调整大小使用对齐线的控件  
  
1.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。  
  
2.  调整大小<xref:System.Windows.Forms.Button>抓住角大小调整控点和拖动某个控件。 有关详细信息，请参阅[如何： 调整 Windows 窗体上的控件](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)。  
  
3.  拖动直到其中一个尺寸控点<xref:System.Windows.Forms.Button>与另一个控件对齐控件的边框。 请注意，显示对齐线。 另请注意尺寸控点对齐到指示对齐线的位置。  
  
4.  调整大小<xref:System.Windows.Forms.Button>在不同的方向中控制和对齐不同的控件的大小调整句柄。 请注意对齐线中不同的方向，以指示对齐方式的显示方式。  
  
## <a name="aligning-a-label-to-a-controls-text"></a>对齐标签与控件的文本  
 某些控件提供对齐到显示的文本的其他控件对齐的线。  
  
#### <a name="to-align-a-label-to-a-controls-text"></a>若要对齐标签与控件的文本  
  
1.  拖动<xref:System.Windows.Forms.TextBox>控件从**工具箱**拖动到窗体。 当删除<xref:System.Windows.Forms.TextBox>拖到窗体控件，请单击智能标记标志符号，选择**将文本设置为 textBox1**选项。 有关详细信息，请参阅[演练： 执行常见任务使用智能标记 Windows 窗体控件上](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)。  
  
2.  拖动<xref:System.Windows.Forms.Label>控件从**工具箱**拖动到窗体。  
  
3.  将 <xref:System.Windows.Forms.Label> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性值更改为 `true`。 请注意，将该控件的边框调整以适合显示文本。  
  
4.  移动<xref:System.Windows.Forms.Label>控件左侧<xref:System.Windows.Forms.TextBox>控件，以便它与下边缘对齐<xref:System.Windows.Forms.TextBox>控件。 请注意将沿两个控件的下边缘显示对齐线。  
  
5.  移动<xref:System.Windows.Forms.Label>控件略微向上，直到<xref:System.Windows.Forms.Label>文本和<xref:System.Windows.Forms.TextBox>对齐文本。 请注意样式有所不同对齐线显示，该值指示当对齐两个控件的文本字段。  
  
## <a name="using-snaplines-with-keyboard-navigation"></a>使用键盘导航线对齐  
 对齐线有助于控件对齐时排列它们使用键盘上的箭头键。  
  
#### <a name="to-use-snaplines-with-keyboard-navigation"></a>若要使用键盘导航线对齐  
  
1.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。 将其放在窗体的左上角。  
  
2.  按 CTRL + 向下箭头。 请注意，控件向窗体下移动到第一个可用的水平对齐位置。  
  
3.  按 CTRL + 向下箭头，直到控件到达窗体的底部。 注意，它占用下移窗体的位置。  
  
4.  按 CTRL + 向右键。 请注意，该控件在窗体移动到第一个可用的垂直对齐位置。  
  
5.  按 CTRL + 向右键，直到控件到达窗体的左侧。 注意，它占用当它移到窗体的位置。  
  
6.  将在窗体控件移动使用箭头键的组合。 请注意控件所占据的位置和伴随它们出现的对齐线。  
  
7.  按下 SHIFT + 任意箭头键调整大小<xref:System.Windows.Forms.Button>按一个像素的增量的控件。  
  
8.  按 CTRL + SHIFT + 任意箭头键调整大小<xref:System.Windows.Forms.Button>控件中对齐线的增量。  
  
## <a name="snaplines-and-layout-panels"></a>对齐线和布局面板  
 对齐线被禁用在布局面板内。  
  
#### <a name="to-selectively-disable-snaplines"></a>若要有选择性地禁用对齐线  
  
1.  拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。  
  
2.  在“工具箱” <xref:System.Windows.Forms.Button>**中，双击**控件图标。 请注意，在将出现一个新的按钮控件<xref:System.Windows.Forms.TableLayoutPanel>控件的第一个单元格。  
  
3.  双击<xref:System.Windows.Forms.Button>中的控件图标**工具箱**两次。 这将使在一个空单元格<xref:System.Windows.Forms.TableLayoutPanel>控件。  
  
4.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到的空单元格中<xref:System.Windows.Forms.TableLayoutPanel>控件。 请注意，没有对齐线显示。  
  
5.  拖动<xref:System.Windows.Forms.Button>外控制<xref:System.Windows.Forms.TableLayoutPanel>控制并移动文件<xref:System.Windows.Forms.TableLayoutPanel>控件。 请注意，对齐线会再次出现。  
  
## <a name="disabling-snaplines"></a>禁用对齐线  
 默认情况下，对齐线被开启。 您可以有选择地，禁用对齐线，或者你可以在设计环境中禁用它们。  
  
#### <a name="to-selectively-disable-snaplines"></a>若要有选择性地禁用对齐线  
  
-   按 ALT 键和而移动在窗体控件。  
  
     请注意，没有对齐线显示该控件不会按任何可能的对齐位置。  
  
#### <a name="to-disable-snaplines-in-the-design-environment"></a>若要禁用设计环境中的对齐线  
  
1.  从**工具**菜单上，打开**选项**对话框。 打开 Windows 窗体设计器对话框。 有关详细信息，请参阅[常规、 Windows 窗体设计器、 选项对话框](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834)。  
  
2.  选择**常规**节点。 在**布局模式**部分中，更改从选择**对齐线**到**网格线对齐**。  
  
3.  单击确定以应用设置。  
  
4.  选择你的窗体上的控件并将其移动的其他控件周围。 请注意，不会显示对齐线。  
  
## <a name="next-steps"></a>后续步骤  
 对齐线提供一种直观的方法来对齐窗体上的控件。 有关进一步探索的建议包括：  
  
-   请尝试嵌套<xref:System.Windows.Forms.GroupBox>中另一个控件<xref:System.Windows.Forms.GroupBox>控件。 位置<xref:System.Windows.Forms.Button>内子控件<xref:System.Windows.Forms.GroupBox>控制和另一个父项中<xref:System.Windows.Forms.GroupBox>控件。 移动<xref:System.Windows.Forms.Button>控件以查看如何对齐线跨容器边界。  
  
-   创建一列<xref:System.Windows.Forms.TextBox>控件与相应的列的<xref:System.Windows.Forms.Label>控件。 设置的值<xref:System.Windows.Forms.Label>控件的<xref:System.Windows.Forms.Control.AutoSize%2A>属性`true`。 使用对齐线移动<xref:System.Windows.Forms.Label>控制以便与中的文本对齐其显示的文本<xref:System.Windows.Forms.TextBox>控件。  
  
 有关 Windows 用户界面设计的信息，请参阅图书*Microsoft Windows 用户体验、 用户界面开发人员和设计器的官方指南*Redmond，WA: Microsoft Press，1999年。 (USBN: 0-7356-0566年-1)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>  
 [演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)  
 [在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
