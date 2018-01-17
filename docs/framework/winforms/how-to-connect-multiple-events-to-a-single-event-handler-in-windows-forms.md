---
title: "如何：将多个事件连接到 Windows 窗体中的单个事件处理程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfd955b4153c7a2bc54d8b52ff1801541c3a7559
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>如何：将多个事件连接到 Windows 窗体中的单个事件处理程序
在应用程序设计中，你可能会发现多个事件用于单个事件处理程序或具有多个事件执行相同的过程所需。 例如，它通常是功能强大的时间的保护程序具有引发同一事件，因为它们公开相同的功能时，将执行你的窗体上的按钮的菜单命令。 你可以执行此操作通过使用 C# 中的属性窗口的事件视图或使用`Handles`关键字和**类名**和**方法名称**下拉列表框在 Visual Basic 代码编辑器中。  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>若要将多个事件连接到在 Visual Basic 中的单个事件处理程序  
  
1.  右键单击该表单，然后选择**查看代码**。  
  
2.  从**类名**下拉列表框中，选择一个你想要处理的事件处理程序的控件。  
  
3.  从**方法名称**下拉列表框中，选择一个你想要处理的事件处理程序的事件。  
  
4.  代码编辑器将插入相应的事件处理程序并将插入点放在方法内。 在下面的示例中，它是<xref:System.Windows.Forms.Control.Click>事件<xref:System.Windows.Forms.Button>控件。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  追加的其他事件你想要处理到`Handles`子句。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  将相应的代码添加到事件处理程序。  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>若要将多个事件连接到在 C# 中的单个事件处理程序  
  
1.  选择你想要连接的事件处理程序的控件。  
  
2.  在属性窗口中，单击**事件**按钮 (![事件按钮](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow"))。  
  
3.  单击你想要处理的事件的名称。  
  
4.  在事件名称旁边的值部分中，单击下拉列表按钮，以显示与你想要处理的事件的方法签名匹配的现有事件处理程序的列表。  
  
5.  从列表中选择相应的事件处理程序。  
  
     会将代码添加到窗体，以将该事件绑定到现有的事件处理程序。  
  
## <a name="see-also"></a>请参阅  
 [在 Windows 窗体中创建事件处理程序](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [事件处理程序概述](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
