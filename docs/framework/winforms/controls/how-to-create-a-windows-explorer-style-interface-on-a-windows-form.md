---
title: "如何：在 Windows 窗体上创建 Windows 资源管理器样式的界面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26a91052586843f87c04adf1a31025991d9973db
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>如何：在 Windows 窗体上创建 Windows 资源管理器样式的界面
Windows 资源管理器因其比较熟悉的应用程序的常见用户界面选择。  
  
 Windows 资源管理器是，从根本上来说，<xref:System.Windows.Forms.TreeView>控件和<xref:System.Windows.Forms.ListView>在不同面板上的控件。 可调整大小面板进行的拆分。 此类控件排列是对于显示和浏览信息非常有效。  
  
 以下步骤显示如何排列 Windows 资源管理器类似的窗体中的控件。 它们不显示如何添加的 Windows 资源管理器应用程序的文件浏览功能。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a>若要创建 Windows 资源管理器样式 Windows 窗体  
  
1.  创建新的 Windows 应用程序项目。 有关详细信息，请参阅[如何：创建一个 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)。  
  
2.  从**工具箱**:  
  
    1.  拖动<xref:System.Windows.Forms.SplitContainer>拖动到窗体控件。  
  
    2.  拖动<xref:System.Windows.Forms.TreeView>控制**SplitterPanel1** (的面板<xref:System.Windows.Forms.SplitContainer>控件标记**Panel1**)。  
  
    3.  拖动<xref:System.Windows.Forms.ListView>控制**SplitterPanel2** (的面板<xref:System.Windows.Forms.SplitContainer>控件标记**面板 2**)。  
  
3.  通过按住 CTRL 键并单击它们反过来选择所有三个控件。 当选择<xref:System.Windows.Forms.SplitContainer>控件中，单击拆分栏中，而不是面板。  
  
    > [!NOTE]
    >  不要使用**选择所有**命令**编辑**菜单。 如果这样做，在下一步所需的属性不会出现在**属性**窗口。  
  
4.  在**属性**窗口中，设置<xref:System.Windows.Forms.SplitContainer.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Fill>。  
  
5.  按 F5 运行该应用程序。  
  
     窗体显示两个部分构成用户界面，类似于 Windows 资源管理器。  
  
    > [!NOTE]
    >  当拆分器拖动时，面板将调整大小。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.SplitContainer>  
 [如何：使用 Windows 窗体创建多窗格用户界面](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [如何：定义拆分窗口中的重设大小和定位行为](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [如何：水平拆分窗口](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [SplitContainer 控件](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
