---
title: "演练：设计时更改承载的 WPF 元素的属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46b80ee0c74da7371ac8f7a16d3430b5b753059d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a>演练：设计时更改承载的 WPF 元素的属性
本演练展示了如何更改 Windows 窗体上承载的 Windows Presentation Foundation (WPF) 控件的属性值。  
  
 在本演练中，你将要执行以下任务：  
  
-   创建项目。  
  
-   创建 WPF 控件。  
  
-   在 Windows 窗体上承载 WPF 控件。  
  
-   使用 Visual Studio 的 WPF 设计器来更改属性值。  
  
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
  
-   创建新的 Windows 窗体应用程序项目中 Visual Basic 或 Visual C# 名为`WpfHost`。  
  
## <a name="creating-the-wpf-control"></a>创建 WPF 控件  
 将 WPF 控件添加到项目后，就可以在窗体上对其进行排列。  
  
#### <a name="to-create-wpf-controls"></a>创建 WPF 控件  
  
1.  将新的 WPF <xref:System.Windows.Controls.UserControl> 添加到项目。 使用控件类型的默认名称，`UserControl1.xaml`。 有关详细信息，请参阅[演练： 创建新 WPF 内容在设计时的 Windows 窗体上](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。  
  
2.  在**属性**窗口中，设置的值<xref:System.Windows.Controls.Control.Background%2A>属性`Blue`。  
  
3.  生成项目。  
  
## <a name="changing-property-values-on-the-wpf-control"></a>在 WPF 控件上更改属性值  
 通过使用 WPF 设计器，<xref:System.Windows.Forms.Integration.ElementHost> 智能标记使更改承载的 WPF 内容的属性变得轻松。  
  
#### <a name="to-host-a-wpf-control"></a>承载 WPF 控件  
  
1.  在 Windows 窗体设计器中打开 `Form1`。  
  
2.  在**工具箱**中**WPF 用户控件**选项卡上，双击`UserControl1`若要创建的实例`UserControl1`窗体上。  
  
     `UserControl1` 的实例承载在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。  
  
3.  在**ElementHost 任务**智能标记面板中，选择**编辑所承载的内容**。  
  
     UserControl1.xaml 在 WPF 设计器中随即打开。  
  
4.  在**属性**窗口中，设置的值<xref:System.Windows.Controls.Control.Background%2A>属性`Red`。  
  
5.  重新生成项目。  
  
6.  在 Windows 窗体设计器中打开 `Form1`。  
  
     `UserControl1` 的实例具有红色背景。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [如何：设计时将控件与窗体边缘对齐](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [演练：使用对齐线在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [迁移和互操作性](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [使用 WPF 控件](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF 设计器](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
