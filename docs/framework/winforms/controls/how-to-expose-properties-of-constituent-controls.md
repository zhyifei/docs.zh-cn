---
title: 如何：公开构成控件的属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: 8f7b5c44a5cb20b5da10df5fd630b371cc959fa8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>如何：公开构成控件的属性
构成复合控件的控件称为*构成控件*。 这些控件通常被声明为私有的并因此不能由开发人员访问。 如果你想要使这些控件的属性适用于未来的用户，必须将它们公开给用户。 通过在用户控件中，创建的属性并使用公开构成控件的属性`get`和`set`访问器的该属性以影响构成控件的私有属性中更改。  
  
 假设用户控件，请考虑与名为构成按钮`MyButton`。 在此示例中，当用户请求`ConstituentButtonBackColor`属性、 中存储的值<xref:System.Windows.Forms.Control.BackColor%2A>属性`MyButton`传递。 当用户将分配给此属性的一个值时，该值将自动传递给<xref:System.Windows.Forms.Control.BackColor%2A>属性`MyButton`和`set`的代码将执行更改的颜色`MyButton`。  
  
 下面的示例演示如何公开<xref:System.Windows.Forms.Control.BackColor%2A>构成按钮属性：  
  
```vb  
Public Property ButtonColor() as System.Drawing.Color  
   Get  
      Return MyButton.BackColor  
   End Get  
   Set(Value as System.Drawing.Color)  
      MyButton.BackColor = Value  
   End Set  
End Property  
```  
  
```csharp  
public Color ButtonColor  
{  
   get  
   {  
      return(myButton.BackColor);  
   }  
   set  
   {  
      myButton.BackColor = value;  
   }  
}  
```  
  
### <a name="to-expose-a-property-of-a-constituent-control"></a>若要公开构成控件的属性  
  
1.  创建你的用户控件的公共属性。  
  
2.  在`get`一部分的属性，编写代码，以检索要公开的属性值。  
  
3.  在`set`一部分的属性，将属性的值传递给构成控件的公开的属性编写代码。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.UserControl>  
 [Windows 窗体控件中的属性](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [各种自定义控件](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
