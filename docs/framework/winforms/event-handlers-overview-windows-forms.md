---
title: "事件处理程序概述（Windows 窗体）"
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
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44d79fb9d6ca2712c470354999b4795408044166
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="event-handlers-overview-windows-forms"></a>事件处理程序概述（Windows 窗体）
事件处理程序是与该事件绑定的方法。 当引发事件时，将执行在事件处理程序内的代码。 每个事件处理程序提供了两个参数，可用于正确处理该事件。 下面的示例演示的事件处理程序<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件。  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 第一个参数，`sender`，提供对引发事件的对象的引用。 第二个参数， `e`，在上面的示例中，将对象传递特定于正在处理的事件。 通过引用对象的属性 （和有时，其方法），你可以获取的鼠标事件或拖放事件中传输的数据鼠标位置等信息。  
  
 通常，每个事件生成的事件处理程序替换为第二个参数是不同的事件对象类型。 某些事件处理程序，例如，那些用于<xref:System.Windows.Forms.Control.MouseDown>和<xref:System.Windows.Forms.Control.MouseUp>事件，都具有其第二个参数的相同对象类型。 对于这些类型的事件，你可以使用相同的事件处理程序来处理这两个事件。  
  
 你可以使用相同的事件处理程序来处理不同的控件的同一事件。 例如，如果你有一组<xref:System.Windows.Forms.RadioButton>窗体上的控件，你可以创建一个事件处理程序<xref:System.Windows.Forms.Control.Click>事件并对每个控制<xref:System.Windows.Forms.Control.Click>事件绑定到单个事件处理程序。 有关详细信息，请参阅[如何： 连接到 Windows 窗体中的单个事件处理程序的多个事件](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)。  
  
## <a name="see-also"></a>请参阅  
 [在 Windows 窗体中创建事件处理程序](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [事件概述](../../../docs/framework/winforms/events-overview-windows-forms.md)
