---
title: "Windows 窗体中鼠标输入的工作原理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 388fd8d3e7f23dc55d46c5a097be99e9f1c34ab0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Windows 窗体中鼠标输入的工作原理
接收和处理鼠标输入是每个 Windows 应用程序的一个重要部分。 你可以处理鼠标事件以在你的应用程序，执行操作，或使用鼠标位置信息来执行的命中测试或其他操作。 此外，你可以更改你的应用程序中的控件处理鼠标输入的方式。 本主题介绍这些详细信息，以及如何获取和更改鼠标的系统设置中的鼠标事件。 事件和在其中鼠标单击事件的顺序引发有关使用鼠标提供的数据的详细信息，请参阅[Windows 窗体中的鼠标事件](../../../docs/framework/winforms/mouse-events-in-windows-forms.md)。  
  
## <a name="mouse-location-and-hit-testing"></a>鼠标位置和命中测试  
 当用户移动鼠标时，操作系统将鼠标指针移。 鼠标指针包含的单一像素，调用作用点，也不能操作系统跟踪会识别为指针的位置。 当用户移动鼠标或按下鼠标按钮，<xref:System.Windows.Forms.Control>包含<xref:System.Windows.Forms.Cursor.HotSpot%2A>引发适当的鼠标事件。 你可以获取与当前的鼠标位置<xref:System.Windows.Forms.MouseEventArgs.Location%2A>属性<xref:System.Windows.Forms.MouseEventArgs>处理鼠标事件时，或通过使用<xref:System.Windows.Forms.Cursor.Position%2A>属性<xref:System.Windows.Forms.Cursor>类。 你可以随后使用鼠标位置信息来执行命中测试，然后执行基于的鼠标位置的操作。 命中测试功能内置的与 Windows 窗体中的多个控件如<xref:System.Windows.Forms.ListView>， <xref:System.Windows.Forms.TreeView>，<xref:System.Windows.Forms.MonthCalendar>和<xref:System.Windows.Forms.DataGridView>控件。 使用与适当的鼠标事件<xref:System.Windows.Forms.Control.MouseHover>例如如，命中测试是用于确定当你的应用程序应执行特定的操作非常有用。  
  
## <a name="mouse-events"></a>鼠标事件  
 响应的鼠标输入的主要方法是处理鼠标事件。 下表显示鼠标事件，并介绍引发时。  
  
|鼠标事件|描述|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|释放鼠标按钮时，通常之前时发生此事件<xref:System.Windows.Forms.Control.MouseUp>事件。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。 处理此事件时你只需以确定何时发生单击。|  
|<xref:System.Windows.Forms.Control.MouseClick>|当用户单击控件使用鼠标，将发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。 处理需要进行一次单击发生时获取鼠标有关的信息时此事件。|  
|<xref:System.Windows.Forms.Control.DoubleClick>|双击该控件时，将发生此事件。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。 处理此事件时你只需以确定何时发生一次双击。|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|当用户双击鼠标控件，将发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。 处理需要进行一次双击发生时获取鼠标有关的信息时此事件。|  
|<xref:System.Windows.Forms.Control.MouseDown>|当鼠标指针位于控件和用户按下鼠标按钮时，将发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseEnter>|当鼠标指针进入控件，具体取决于控件的类型的边框或客户端区域，则会发生此事件。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseHover>|当鼠标指针停止，并停留在该控件时，将发生此事件。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseLeave>|在鼠标指针离开控件，具体取决于控件的类型的边框或客户端区域时发生此事件。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseMove>|当鼠标指针移动到控件上时，将发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseUp>|当鼠标指针位于控件和用户释放鼠标按钮时，将发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseWheel>|在控件有焦点，用户旋转鼠标滚轮时，将发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。 你可以使用<xref:System.Windows.Forms.MouseEventArgs.Delta%2A>属性<xref:System.Windows.Forms.MouseEventArgs>来确定已经滚动鼠标的距离。|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>更改鼠标输入并检测系统设置  
 你可以检测和更改控件处理通过从该控件派生，并使用鼠标输入的方式<xref:System.Windows.Forms.Control.GetStyle%2A>和<xref:System.Windows.Forms.Control.SetStyle%2A>方法。 <xref:System.Windows.Forms.Control.SetStyle%2A>方法采用的按位组合<xref:System.Windows.Forms.ControlStyles>值来确定控件是否会将标准单击或双击行为，或如果该控件将处理其自己的鼠标处理。 此外，<xref:System.Windows.Forms.SystemInformation>类包括的属性，描述鼠标的功能，并指定与操作系统鼠标交互的方式。 下表总结了这些属性。  
  
|属性|描述|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|获取维度，以像素为单位，在其中用户必须单击两次，操作系统才两个区域的单击一次双击。|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|获取最大的第一次单击与操作系统将鼠标操作视为双击第二次单击之间可以经过的毫秒数。|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|获取鼠标上的按钮数。|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|获取一个值，该值指示是否已交换鼠标左右按钮的功能。|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|获取特定矩形的尺寸（以像素为单位），鼠标指针必须在该矩形范围内停留达到鼠标悬停时间后，才会生成鼠标悬停消息。|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|获取一个以毫秒为单位的时间，鼠标指针必须在悬停矩形中停留该时间后，才会生成鼠标悬停消息。|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|获取一个值，该值指示鼠标是否已安装。|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|获取一个值，该值指示当前鼠标的速度，从 1 到 20。|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|获取一个值，该值指示是否安装了带有鼠标轮的鼠标。|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|获取单次鼠标轮旋转增量的增量值的量。|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|获取滚动鼠标轮时所滚动过的行数。|  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体应用程序中的鼠标输入](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 [Windows 窗体中的鼠标捕获](../../../docs/framework/winforms/mouse-capture-in-windows-forms.md)  
 [Windows 窗体中的鼠标指针](../../../docs/framework/winforms/mouse-pointers-in-windows-forms.md)
