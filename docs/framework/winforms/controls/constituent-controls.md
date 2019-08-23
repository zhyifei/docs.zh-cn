---
title: 构成控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 522a1012fc7bdd54860b0538064ee073f7a761f7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918431"
---
# <a name="constituent-controls"></a>构成控件
组成用户控件的控件（也称作“构成控件”）在自定义图形呈现方面的灵活性相对较差。 所有 Windows 窗体控件都通过其自己<xref:System.Windows.Forms.Control.OnPaint%2A>的方法来处理其自身的呈现。 由于此方法受到保护，开发人员无法对其进行访问，因此在绘制控件时无法阻止其执行。 然而，这并不意味着不能添加影响构成控件外观的代码。 附加呈现可通过添加事件处理程序来完成。 例如, 假设您是使用名为<xref:System.Windows.Forms.UserControl> `MyButton`的按钮创作的。 如果希望附加呈现超出了所提供<xref:System.Web.UI.WebControls.Button>的内容, 请将代码添加到用户控件, 如下所示:  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
> 某些 Windows 窗体控件 (如<xref:System.Windows.Forms.TextBox>) 是由 Windows 直接绘制的。 在这些情况下, <xref:System.Windows.Forms.Control.OnPaint%2A>永远不会调用方法, 因此永远不会调用上面的示例。  
  
 上例创建一个每次执行 `MyButton.Paint` 事件时都会执行的方法，用于将附加的图形化表示形式添加到控件中。 请注意，这并不妨碍 `MyButton.OnPaint` 的执行，因此，除了自定义绘制外，仍会执行通常由某个按钮执行的所有绘制操作。 有关 GDI+ 技术和自定义呈现的详细信息，请参阅[用 GDI+ 创建图形图像](../advanced/how-to-create-graphics-objects-for-drawing.md)。 如果希望控件具有唯一的表示形式，则最好创建一个继承的控件，为其编写自定义呈现代码。 有关详细信息，请参阅[用户描述的控件](user-drawn-controls.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [用户绘制的控件](user-drawn-controls.md)
- [如何：为绘图创建图形对象](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [各种自定义控件](varieties-of-custom-controls.md)
