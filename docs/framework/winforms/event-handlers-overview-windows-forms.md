---
title: 이벤트 처리기 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: 10ba458197973ede35849a86fec35003f139b8d2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743495"
---
# <a name="event-handlers-overview-windows-forms"></a>이벤트 처리기 개요(Windows Forms)
事件处理程序是绑定到事件的方法。 引发事件时，将执行事件处理程序中的代码。 每个事件处理程序提供了两个参数，可用于正确处理事件。 下面的示例演示 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Click> 事件的事件处理程序。  
  
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
  
 第一个参数`sender`提供对引发事件的对象的引用。 在上面的示例中，第二个参数 `e`会传递特定于正在处理的事件的对象。 通过引用对象的属性（有时是其方法），您可以获得信息，例如鼠标事件的鼠标位置或拖放事件中传输的数据。  
  
 通常，每个事件都为第二个参数生成一个具有不同事件对象类型的事件处理程序。 某些事件处理程序（例如 <xref:System.Windows.Forms.Control.MouseDown> 和 <xref:System.Windows.Forms.Control.MouseUp> 事件的事件处理程序）的第二个参数具有相同的对象类型。 对于这些类型的事件，可以使用同一事件处理程序来处理这两个事件。  
  
 你还可以使用同一事件处理程序来处理不同控件的同一事件。 例如，如果窗体上有一组 <xref:System.Windows.Forms.RadioButton> 控件，则可以为 <xref:System.Windows.Forms.Control.Click> 事件创建一个事件处理程序，并将每个控件的 <xref:System.Windows.Forms.Control.Click> 事件绑定到单个事件处理程序。 有关详细信息，请参阅[如何：将多个事件连接到 Windows 窗体中的单个事件处理程序](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)。  
  
## <a name="see-also"></a>另请参阅

- [Windows Forms에서 이벤트 처리기 만들기](creating-event-handlers-in-windows-forms.md)
- [이벤트 개요](events-overview-windows-forms.md)
