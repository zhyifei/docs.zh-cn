---
title: 演练：使用自定义组件自动填充工具箱
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: d446ab84cfe135e56483b8b309b696f7f15044fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>演练：使用自定义组件自动填充工具箱
如果你的组件定义的那样当前打开的解决方案中的项目中，它们将会自动出现在**工具箱**，而需要你执行任何操作。 你可以手动填充**工具箱**与通过使用你自定义组件[选择工具箱项对话框 (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)，但**工具箱**采用帐户你的解决方案中的项的生成包含所有以下特征的输出结果：  
  
-   实现<xref:System.ComponentModel.IComponent>;  
  
-   没有<xref:System.ComponentModel.ToolboxItemAttribute>设置为`false`;  
  
-   没有<xref:System.ComponentModel.DesignTimeVisibleAttribute>设置为`false`。  
  
> [!NOTE]
>  **工具箱**不遵循引用链，因此它将不显示并非由你的解决方案中的项目生成的项。  
  
 本演练演示如何自定义组件会自动出现在**工具箱**后生成组件。 本演练涉及以下任务：  
  
-   创建 Windows 窗体项目。  
  
-   创建自定义组件。  
  
-   创建自定义组件的实例。  
  
-   卸载并重新加载自定义组件。  
  
 完成后，你将看到**工具箱**填充了你创建的组件。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
## <a name="creating-the-project"></a>创建项目  
 第一步是创建项目并设置窗体。  
  
#### <a name="to-create-the-project"></a>要创建项目  
  
1.  创建一个名为 `ToolboxExample` 的基于 Windows 的应用程序项目。  
  
     有关详细信息，请参阅[如何：创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)。  
  
2.  向项目添加新的组件。 调用它`DemoComponent`。  
  
     有关详细信息，请参阅[NIB： 如何： 添加新项目项](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)。  
  
3.  生成项目。  
  
4.  从**工具**菜单上，单击**选项**项。 单击**常规**下**Windows 窗体设计器**项，然后确保**AutoToolboxPopulate**选项设置为**True**。  
  
## <a name="creating-an-instance-of-a-custom-component"></a>创建自定义组件的实例  
 下一步是在窗体上创建自定义组件的实例。 因为**工具箱**自动为新的组件的帐户，这是和创建任何其他组件或控件一样简单。  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a>若要创建自定义组件的实例  
  
1.  打开项目的窗体中**窗体设计器**。  
  
2.  在**工具箱**，单击新选项卡调用**ToolboxExample 组件**。  
  
     一旦单击选项卡，你将看到**DemoComponent**。  
  
    > [!NOTE]
    >  出于性能原因，自动填充的区域中的组件**工具箱**不显示自定义位图和<xref:System.Drawing.ToolboxBitmapAttribute>不支持。 以显示一个图标中的自定义组件**工具箱**，使用**选择工具箱项**对话框中，以加载你的组件。  
  
3.  你的组件拖到窗体。  
  
     创建组件的实例并将其添加到**组件栏**。  
  
## <a name="unloading-and-reloading-a-custom-component"></a>卸载并重新加载自定义组件  
 **工具箱**会考虑在每个组件的加载项目，并卸载项目时，它将移除对该项目的组件的引用。  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a>尝试卸载并重新加载组件工具箱上的效果  
  
1.  卸载项目从解决方案。  
  
     有关卸载的项目的详细信息，请参阅[NIB： 如何： 卸载并重新加载项目](http://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b)。 如果系统提示您保存时，选择**是**。  
  
2.  添加新**Windows 应用程序**到解决方案的项目。 打开的窗体中**设计器**。  
  
     **ToolboxExample 组件**以前的项目中的选项卡现消失。  
  
3.  重新加载`ToolboxExample`项目。  
  
     **ToolboxExample 组件**选项卡现在随即再次显示。  
  
## <a name="next-steps"></a>后续步骤  
 本演练演示**工具箱**会考虑项目的组件，但**工具箱**同时也会考虑控件。 通过添加和删除控件项目，从你的解决方案来测试你自己的自定义控件。  
  
## <a name="see-also"></a>请参阅  
 [通常，Windows 窗体设计器中，选项对话框](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [如何：操作工具箱选项卡](http://msdn.microsoft.com/library/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [“选择工具箱项”对话框 (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [将控件置于 Windows 窗体上](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
