---
title: "演练：设计时调试自定义 Windows 窗体控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc5f0fab7c380268dfc041d6105595858c2fed93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a>演练：设计时调试自定义 Windows 窗体控件
当你创建自定义控件时，你通常会发现它需调试其设计时行为。 这是如果自定义设计器创作的自定义控件尤其如此。 有关详细信息，请参阅[演练： 创建 Windows 窗体控件，采用利用的 Visual Studio 设计时功能](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)。  
  
 正如你将调试任何其他.NET Framework 类，你可以调试使用 Visual Studio 中，你自定义控件。 区别是，你将调试正在运行自定义控件的代码的 Visual Studio 的单独实例  
  
 本演练涉及以下任务：  
  
-   创建用于承载自定义控件的 Windows 窗体项目  
  
-   创建控件库项目  
  
-   将属性添加到自定义控件  
  
-   将自定义控件添加到宿主窗体  
  
-   设置项目以便进行设计时调试  
  
-   在设计时调试自定义控件  
  
 完成后，你将会了解的调试自定义控件的设计时行为所需的任务。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
## <a name="creating-the-project"></a>创建项目  
 第一步是创建应用程序项目。 此项目将用于生成承载自定义控件的应用程序。  
  
#### <a name="to-create-the-project"></a>创建项目  
  
-   创建一个名为"DebuggingExample"的 Windows 应用程序项目。 有关详细信息，请参阅[如何：创建一个 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)。  
  
## <a name="creating-a-control-library-project"></a>创建控件库项目  
 下一步是创建控件库项目并设置自定义控件。  
  
#### <a name="to-create-the-control-library-project"></a>若要创建控件库项目  
  
1.  添加**Windows 控件库**到解决方案的项目。  
  
2.  添加新**UserControl**到 DebugControlLibrary 项目项。 有关详细信息，请参阅[NIB： 如何： 添加新项目项](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)。 为新的源文件提供一个"DebugControl"的基本名称。  
  
3.  使用**解决方案资源管理器**，通过删除具有的基名称的代码文件中删除项目的默认控件"`UserControl1`"。 有关详细信息，请参阅[NIB： 如何： 删除、 删除和排除项](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)。  
  
4.  生成解决方案。  
  
## <a name="checkpoint"></a>检查点  
 此时，你将能够看到自定义控件中的**工具箱**。  
  
#### <a name="to-check-your-progress"></a>若要检查你的进度  
  
-   查找名为新选项卡**DebugControlLibrary 组件**单击以将其选中。 当它打开后时，你将看到列为控件**DebugControl**与它旁边的默认图标。  
  
## <a name="adding-a-property-to-your-custom-control"></a>将属性添加到自定义控件  
 为了演示自定义控件的代码运行设计时，将添加属性，并实现属性的代码中设置断点。  
  
#### <a name="to-add-a-property-to-your-custom-control"></a>若要将属性添加到自定义控件  
  
1.  打开**DebugControl**中**代码编辑器**。 将以下代码添加到类定义：  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  生成解决方案。  
  
## <a name="adding-your-custom-control-to-the-host-form"></a>将自定义控件添加到宿主窗体  
 若要调试你的自定义控件的设计时行为，将在主机窗体上将自定义控件类的一个实例。  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a>若要将自定义控件添加到宿主窗体  
  
1.  在"DebuggingExample"项目中，打开中的 form1 **Windows 窗体设计器**。  
  
2.  在**工具箱**，打开**DebugControlLibrary 组件**选项卡，将**DebugControl**拖到窗体的实例。  
  
3.  查找`DemoString`中的自定义属性**属性**窗口。 请注意，你可以更改其值，就像任何其他属性。 另请注意，当`DemoString`选择属性后，该属性的描述字符串会显示在底部**属性**窗口。  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>设置项目以便进行设计时调试  
 若要调试自定义控件的设计时行为，你将调试正在运行自定义控件的代码的 Visual Studio 的单独实例。  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>若要设置项目以便进行设计时调试  
  
1.  右键单击**DebugControlLibrary**项目中**解决方案资源管理器**和选择**属性**。  
  
2.  在**DebugControlLibrary**属性表中，选择**调试**选项卡。  
  
     在**启动操作**部分中，选择**启动外部程序**。 你将调试的单独实例的 Visual Studio 中，因此单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以浏览 Visual Studio IDE。 可执行文件的名称是**devenv.exe**，如果你已安装到默认位置，其路径为 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe。  
  
3.  单击“确定”关闭对话框。  
  
4.  右键单击**DebugControlLibrary**项目，然后选择**设为启动项目**为启用此调试配置。  
  
## <a name="debugging-your-custom-control-at-design-time"></a>在设计时调试自定义控件  
 现在你已准备好调试自定义控件，因为它在设计模式下运行。 当你启动调试会话时，将创建 Visual Studio 的新实例，并将使用它以加载"DebuggingExample"解决方案。 当你打开中的 form1**窗体设计器**，自定义控件的实例将创建并将开始运行。  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a>若要在设计时调试自定义控件  
  
1.  打开**DebugControl**中的源文件**代码编辑器**并将断点放置在`Set`的访问器`DemoString`属性。  
  
2.  按 F5 启动调试会话。 请注意，创建 Visual Studio 的新实例。 你可区分两种方式的实例：  
  
    -   调试实例都有单词**运行**其标题栏中  
  
    -   调试实例具有**启动**按钮上其**调试**禁用工具栏  
  
     调试实例中设置断点。  
  
3.  在 Visual Studio 的新实例中，打开的"DebuggingExample"解决方案。 你可以轻松地找到解决方案，通过选择**最近项目**从**文件**菜单。 将列出"DebuggingExample.sln"解决方案文件，如最近使用的文件。  
  
4.  打开中的 form1**窗体设计器**和选择**DebugControl**控件。  
  
5.  更改的值`DemoString`属性。 请注意，在提交更改时，Visual Studio 的调试实例获取焦点并且执行在断点处停止。 你可以单步执行属性访问器就像你将任何其他代码。  
  
6.  在完成时与你的调试会话，可以退出解除 Visual Studio 的托管的实例，或单击**停止调试**调试实例中的按钮。  
  
## <a name="next-steps"></a>后续步骤  
 现在，你可以在设计时调试自定义控件，有许多可能的展开与 Visual Studio IDE 的控件的交互。  
  
-   你可以使用<xref:System.ComponentModel.Component.DesignMode%2A>属性<xref:System.ComponentModel.Component>将仅执行在设计时编写代码的类。 有关详细信息，请参阅<xref:System.ComponentModel.Component.DesignMode%2A>。  
  
-   有几个属性可应用于控件的属性，以处理与设计器的自定义控件的交互。 你可以找到这些属性中的<xref:System.ComponentModel?displayProperty=nameWithType>命名空间。  
  
-   对于自定义控件，可以编写自定义设计器。 这使你可以使用由 Visual Studio 公开的可扩展设计器基础结构的设计体验的完全控制。 有关详细信息，请参阅[演练： 创建 Windows 窗体控件，采用利用的 Visual Studio 设计时功能](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)。  
  
## <a name="see-also"></a>另请参阅  
 [演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [如何： 访问设计时服务](http://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [如何： 访问 Windows 窗体中的设计时支持](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
