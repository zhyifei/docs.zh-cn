---
title: "如何：使用设计器将 Windows 窗体控件与 BindingSource 组件进行绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18e89d0a236d3b370c521b73dfb640a09137a5dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>如何：使用设计器将 Windows 窗体控件与 BindingSource 组件进行绑定
在已向窗体添加控件并确定你的应用程序用户界面后，你可以将控件绑定到数据源，以便在运行时，用户可以更改和保存到应用程序相关的数据。  
  
 Windows 窗体中的绑定的控件或系列的控件使用非常轻松地实现<xref:System.Windows.Forms.BindingSource>控件用作窗体上的控件和数据源之间的桥梁。  
  
 在窗体上的一个或多个控件可以绑定到数据;在下面的过程中，<xref:System.Windows.Forms.TextBox>控件绑定到数据源。  
  
 若要完成该过程，假定你将绑定到从数据库获得数据源。 从其他存储的数据创建数据源的详细信息，请参阅[添加新数据源](/visualstudio/data-tools/add-new-data-sources)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-bind-a-control-at-design-time"></a>若要将控件绑定在设计时  
  
1.  拖动<xref:System.Windows.Forms.TextBox>到窗体控件。  
  
2.  在**属性**窗口：  
  
    1.  展开**(DataBindings)**节点。  
  
    2.  单击箭头旁边<xref:System.Windows.Forms.TextBox.Text%2A>属性。  
  
         **数据源**UI 类型编辑器随即打开。  
  
         如果数据源具有以前已为配置项目或窗体中，它将会出现。  
  
3.  单击“添加项目数据源”以连接到数据并创建一个数据源。  
  
4.  在“数据源配置向导”欢迎页上，单击“下一步”。  
  
5.  上**选择数据源类型**页上，选择**数据库**。  
  
6.  上**选择你的数据连接**页上，从可用连接列表中选择一个数据连接。 如果所需的数据连接不可用，请选择**新连接**以创建新的数据连接。  
  
7.  选择**是，将连接保存**将连接字符串保存在应用程序配置文件。  
  
8.  选择要放置到应用程序中的数据库对象。 在这种情况下，选择你想要的表中的一个字段<xref:System.Windows.Forms.TextBox>以显示。  
  
9. 如果愿意，可以替换默认的数据集名称。  
  
10. 单击 **“完成”**。  
  
11. 在**属性**窗口中，单击箭头旁边<xref:System.Windows.Forms.TextBox.Text%2A>再次属性。 在**数据源**UI 类型编辑器中，选择要绑定的字段名称<xref:System.Windows.Forms.TextBox>到。  
  
     **数据源**UI 类型编辑器对话框将关闭，数据集，<xref:System.Windows.Forms.BindingSource>和表适配器特定于数据连接将添加到你的窗体。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [添加新数据源](/visualstudio/data-tools/add-new-data-sources)  
 [数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)
