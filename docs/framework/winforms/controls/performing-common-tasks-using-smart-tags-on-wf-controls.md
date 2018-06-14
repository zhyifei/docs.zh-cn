---
title: 演练：使用 Windows 窗体控件上的智能标记执行常规任务
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: a558f6d274f260fc91fd140e9dae2c740b1ae00d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537939"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>演练：使用 Windows 窗体控件上的智能标记执行常规任务
为 Windows 窗体应用程序中构造窗体和控件，如有需要反复执行的许多任务。 以下是一些常执行的任务，则会遇到：  
  
-   添加或删除选项卡上<xref:System.Windows.Forms.TabControl>。  
  
-   将控件停靠到其父级。  
  
-   更改的方向<xref:System.Windows.Forms.SplitContainer>控件。  
  
 为了加快开发速度，许多控件提供了智能标记，它们是可用于在设计时执行常见任务，比如这些中的单个笔势的上下文相关菜单。 这些任务称作*智能标记谓词*。  
  
 智能标记的设计器中的整个生存期保持附加到控件实例并且始终可用。  
  
 本演练涉及以下任务：  
  
-   创建 Windows 窗体项目  
  
-   使用智能标记  
  
-   启用和禁用智能标记  
  
 完成上述操作后，你将会了解这些重要布局功能所发挥的作用。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
## <a name="creating-the-project"></a>创建项目  
 第一步是创建项目并设置窗体。  
  
#### <a name="to-create-the-project"></a>要创建项目  
  
1.  创建一个名为"SmartTagsExample"的基于 Windows 的应用程序项目。 有关详细信息，请参阅[如何：创建一个 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)。  
  
2.  选择的窗体中**Windows 窗体设计器**。  
  
## <a name="using-smart-tags"></a>使用智能标记  
 在设计时为他们提供的控件上都可以使用智能标记。  
  
#### <a name="to-use-smart-tags"></a>若要使用智能标记  
  
1.  拖动<xref:System.Windows.Forms.TabControl>从**工具箱**拖动到窗体。 请注意的智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 旁边的显示<xref:System.Windows.Forms.TabControl>。  
  
2.  单击智能标记标志符号。 在出现旁边标志符号的快捷菜单，选择**添加选项卡**项。 观察新的选项卡页添加到<xref:System.Windows.Forms.TabControl>。  
  
3.  拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。  
  
4.  单击智能标记标志符号。 在出现旁边标志符号的快捷菜单，选择**添加列**项。 观察新列添加到<xref:System.Windows.Forms.TableLayoutPanel>控件。  
  
5.  拖动<xref:System.Windows.Forms.SplitContainer>控件从**工具箱**拖动到窗体。  
  
6.  单击智能标记标志符号。 在出现旁边标志符号的快捷菜单，选择**水平拆分器方向**项。 注意，<xref:System.Windows.Forms.SplitContainer>控件的拆分栏现在处于水平放置。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [演练： 将智能标记添加到 Windows 窗体组件](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
