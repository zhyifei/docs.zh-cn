---
title: 演练：将 ElementHost 控件复制并粘贴到单独的 Windows 窗体中
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
ms.openlocfilehash: 55b426fbe95bac269183a649ecd839175a8cbdda
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "44778451"
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a>演练：将 ElementHost 控件复制并粘贴到单独的 Windows 窗体中
本演练显示了如何将 Windows Presentation Foundation (WPF) 控件从一个 Windows 窗体复制到其他 Windows 窗体。  
  
 在本演练中，你将要执行以下任务：  
  
-   创建项目。  
  
-   复制 WPF 控件。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
## <a name="prerequisites"></a>系统必备  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]。  
  
## <a name="creating-the-project"></a>创建项目  
 第一步是创建 Windows 窗体项目。  
  
> [!NOTE]
>  承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。  
  
#### <a name="to-create-the-project"></a>要创建项目  
  
-   创建新的 Windows 窗体应用程序项目在 Visual Basic 或 Visual C# 名为`CopyElementHost`。  
  
## <a name="copying-a-wpf-control"></a>复制 WPF 控件  
 将 WPF 控件添加到项目后，可将它复制到项目中的其他窗体。  
  
#### <a name="to-copy-a-wpf-control"></a>复制 WPF 控件  
  
1.  将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。 使用控件类型的默认名称，`UserControl1.xaml`。 有关详细信息，请参阅[演练： 创建新 WPF 内容在设计时的 Windows 窗体上](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。  
  
2.  生成项目。  
  
3.  在 Windows 窗体设计器中打开 `Form1`。  
  
4.  从**工具箱**，将拖动的一个实例`UserControl1`拖到窗体。  
  
     `UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。  
  
5.  选择`elementHost1` 后，按 CTRL + C 将它复制到剪贴板。  
  
6.  向项目添加新的 Windows 窗体。 使用窗体类型的默认名称：`Form2`。  
  
7.  在 Windows 窗体设计器中打开 `Form2` 的情况下，按 CTRL+V 将 `elementHost1` 的副本粘贴到窗体。  
  
     复制的控件名称也命名为 `elementHost1`，因为它是 `Form2` 类的私有字段。 `Form1` 类中不存在与 `elementHost1` 的名称冲突。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [迁移和互操作性](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [使用 WPF 控件](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [在 Visual Studio 中设计 XAML](/visualstudio/designers/designing-xaml-in-visual-studio)
