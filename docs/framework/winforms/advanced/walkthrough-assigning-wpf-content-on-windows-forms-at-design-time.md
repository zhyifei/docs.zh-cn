---
title: 演练：设计时在 Windows 窗体上分配 WPF 内容
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: abdeb2e77486d4f94f3d0543d94186168baae31c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528650"
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a>演练：设计时在 Windows 窗体上分配 WPF 内容
本演练展示了如何选择要在窗体上显示的 Windows Presentation Foundation (WPF) 控件类型。 可选择项目中包含的任何 WPF 控件类型。  
  
 在本演练中，你将要执行以下任务：  
  
-   创建项目。  
  
-   创建 WPF 控件类型。  
  
-   选择 WPF 控件。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
## <a name="prerequisites"></a>系统必备  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]。  
  
## <a name="creating-the-project"></a>创建项目  
 第一步是创建 Windows 窗体项目。  
  
> [!NOTE]
>  承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。  
  
#### <a name="to-create-the-project"></a>要创建项目  
  
-   创建新的 Windows 窗体应用程序项目中 Visual Basic 或 Visual C# 名为`SelectingWpfContent`。  
  
## <a name="creating-the-wpf-control-types"></a>创建 WPF 控件类型  
 将 WPF 控件类型添加到项目后，可将其托管到不同的 <xref:System.Windows.Forms.Integration.ElementHost> 控件。  
  
#### <a name="to-create-wpf-control-types"></a>创建 WPF 控件类型  
  
1.  将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。 使用控件类型的默认名称，`UserControl1.xaml`。 有关详细信息，请参阅[演练： 创建新 WPF 内容在设计时的 Windows 窗体上](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。  
  
2.  在设计视图中，请确保已选中 `UserControl1`。 有关详细信息，请参阅[如何： 选择和设计图面上移动元素](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)。  
  
3.  在**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性设置为`200`。  
  
4.  添加<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>控制转移到<xref:System.Windows.Controls.UserControl>和设置的值<xref:System.Windows.Controls.TextBox.Text%2A>属性**承载的内容**。  
  
5.  将第二个 WPF <xref:System.Windows.Controls.UserControl> 添加到项目。 使用控件类型的默认名称，`UserControl2.xaml`。  
  
6.  在**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性设置为`200`。  
  
7.  添加<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>控制转移到<xref:System.Windows.Controls.UserControl>和设置的值<xref:System.Windows.Controls.TextBox.Text%2A>属性**承载的内容 2**。  
  
 **请注意**一般情况下，你应承载更复杂的 WPF 内容。 此处，<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件仅为了便于说明。  
  
1.  生成项目。  
  
## <a name="selecting-wpf-controls"></a>选择 WPF 控件  
 可将不同的 WPF 内容分配到 <xref:System.Windows.Forms.Integration.ElementHost> 控件，该控件现已承载内容。  
  
#### <a name="to-select-wpf-controls"></a>选择 WPF 控件  
  
1.  在 Windows 窗体设计器中打开 `Form1`。  
  
2.  在**工具箱**，双击`UserControl1`若要创建的实例`UserControl1`窗体上。  
  
     `UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。  
  
3.  在智能标记面板中`elementHost1`，打开**选择承载的内容**下拉列表。  
  
4.  选择**UserControl2**从下拉列表框。  
  
     `elementHost1` 控件现承载 `UserControl2` 类型的实例。  
  
5.  在**属性**窗口中，确认<xref:System.Windows.Forms.Integration.ElementHost.Child%2A>属性设置为**UserControl2**。  
  
6.  从**工具箱**中**WPF 互操作性**组中，将<xref:System.Windows.Forms.Integration.ElementHost>拖到窗体控件。  
  
     新控件的默认名称是 `elementHost2`。  
  
7.  在智能标记面板中`elementHost2`，打开**选择承载的内容**下拉列表。  
  
8.  选择**UserControl1**从下拉列表。  
  
9. `elementHost2` 控件现承载 `UserControl1` 类型的实例。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [迁移和互操作性](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [使用 WPF 控件](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF 设计器](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
