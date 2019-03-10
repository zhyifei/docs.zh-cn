---
title: 在 Windows 窗体控件中定义事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [Windows Forms], defining within Windows Forms custom controls
- custom controls [Windows Forms], events using code
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
ms.openlocfilehash: 4235c8b3c513509023388112071e78cfd079ec6f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705371"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="53018-102">在 Windows 窗体控件中定义事件</span><span class="sxs-lookup"><span data-stu-id="53018-102">Defining an Event in Windows Forms Controls</span></span>
<span data-ttu-id="53018-103">有关定义自定义事件的详细信息，请参阅[事件](../../../standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="53018-103">For details about defining custom events, see [Events](../../../standard/events/index.md).</span></span> <span data-ttu-id="53018-104">如果你定义的事件没有任何关联的数据，则使用事件数据的基类型 <xref:System.EventArgs>，并使用 <xref:System.EventHandler> 作为事件委托。</span><span class="sxs-lookup"><span data-stu-id="53018-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="53018-105">所有这些剩下工作就是定义一个事件成员和受保护`On` *EventName*引发事件的方法。</span><span class="sxs-lookup"><span data-stu-id="53018-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="53018-106">以下代码段显示了 `FlashTrackBar` 自定义控件如何定义自定义事件 `ValueChanged`。</span><span class="sxs-lookup"><span data-stu-id="53018-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="53018-107">有关的完整代码`FlashTrackBar`示例，请参阅[如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="53018-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class FlashTrackBar  
   Inherits Control  
  
   ' The event does not have any data, so EventHandler is adequate   
   ' as the event delegate.          
   ' Define the event member using the event keyword.  
   ' In this case, for efficiency, the event is defined   
   ' using the event property construct.  
   Public Event ValueChanged As EventHandler  
   ' The protected method that raises the ValueChanged   
   ' event when the value has actually   
   ' changed. Derived controls can override this method.    
   Protected Overridable Sub OnValueChanged(e As EventArgs)  
      RaiseEvent ValueChanged(Me, e)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class FlashTrackBar : Control {  
   // The event does not have any data, so EventHandler is adequate   
   // as the event delegate.  
   private EventHandler onValueChanged;  
   // Define the event member using the event keyword.  
   // In this case, for efficiency, the event is defined   
   // using the event property construct.  
   public event EventHandler ValueChanged {  
            add {  
                onValueChanged += value;  
            }  
            remove {  
                onValueChanged -= value;  
            }  
        }  
   // The protected method that raises the ValueChanged  
   // event when the value has actually   
   // changed. Derived controls can override this method.    
   protected virtual void OnValueChanged(EventArgs e) 
   {  
       ValueChanged?.Invoke(this, e);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="53018-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="53018-108">See also</span></span>

- [<span data-ttu-id="53018-109">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="53018-109">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="53018-110">事件</span><span class="sxs-lookup"><span data-stu-id="53018-110">Events</span></span>](../../../standard/events/index.md)
