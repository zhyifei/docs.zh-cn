---
title: 如何：测试 UserControl 的运行时行为
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 40ec136a86b52dcb007d15d5a2917212745961f2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392898"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>如何：测试 UserControl 的运行时行为
开发时<xref:System.Windows.Forms.UserControl>，您需要测试其运行时行为。 可以创建一个单独的基于 Windows 的应用程序项目，并将你窗体控件的测试，但此过程是不方便。 更快、 更轻松的方法是使用**UserControl 测试容器**Visual Studio 提供的。 此测试容器开始直接从 Windows 控件库项目。  
  
> [!IMPORTANT]
>  若要加载的测试容器在<xref:System.Windows.Forms.UserControl>，控件必须具有至少一个公共构造函数。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
> [!NOTE]
>  不能使用进行测试的 Visual c + + 控件**UserControl 测试容器**。  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a>若要测试 UserControl 的运行时行为  
  
1.  创建一个名为的 Windows 控件库项目**TestContainerExample**。 有关详细信息，请参阅[Windows 控件库模板](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4)。  
  
2.  在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.Label>控件从**工具箱**到控件的设计图面。  
  
3.  按 F5 以生成项目并运行**UserControl 测试容器**。 测试容器会显示与你<xref:System.Windows.Forms.UserControl>中**预览**窗格。  
  
4.  选择<xref:System.Windows.Forms.Control.BackColor%2A>属性中显示<xref:System.Windows.Forms.PropertyGrid>右侧的控件**预览**窗格。 其值更改为`ControlDark`。 观察控件更改为较深的颜色。 请尝试更改其他属性值，并观察在控件上的效果。  
  
5.  单击**停靠填充用户控件**下面的复选框**预览**窗格。 观察到该控件调整大小以填充窗格。 调整测试容器的大小，并观察调整控件大小与窗格。  
  
6.  关闭测试容器。  
  
7.  另一个用户控件添加到**TestContainerExample**项目。 有关详细信息，请参阅[NIB： 如何： 添加现有项添加至项目](https://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)。  
  
8.  在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到控件的设计图面。  
  
9. 按 F5 以生成项目并运行测试容器。  
  
10. 单击**选择用户控件**<xref:System.Windows.Forms.ComboBox>两个用户控件之间进行切换。  
  
## <a name="testing-user-controls-from-another-project"></a>从另一个项目的测试用户控件  
 在当前项目的测试容器中，可以测试其他项目中的用户控件。  
  
#### <a name="to-test-user-controls-from-another-project"></a>若要测试从另一个项目的用户控件  
  
1.  创建一个名为的 Windows 控件库项目**TestContainerExample2**。 有关详细信息，请参阅[Windows 控件库模板](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4)。  
  
2.  在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.RadioButton>控件从**工具箱**到控件的设计图面。  
  
3.  按 F5 以生成项目并运行测试容器。 测试容器会显示与你<xref:System.Windows.Forms.UserControl>中**预览**窗格。  
  
4.  单击**负载**按钮。  
  
5.  在中**开放**对话框框中，导航到**TestContainerExample**.dll 上, 一个过程中生成。 选择**TestContainerExample**.dll，然后单击**打开**按钮以加载用户控件  
  
6.  使用**选择用户控件**<xref:System.Windows.Forms.ComboBox>若要从两个用户控件之间切换**TestContainerExample**项目。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.UserControl>  
 [如何：创作复合控件](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [演练：使用 Visual Basic 创作复合控件](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [演练：使用 Visual C# 创作复合控件](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [用户控件设计器](https://msdn.microsoft.com/library/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
