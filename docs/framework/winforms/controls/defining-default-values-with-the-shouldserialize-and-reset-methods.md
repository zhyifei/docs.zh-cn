---
title: 使用 ShouldSerialize 和 Reset 方法定义默认值
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a28cd84c88cd7434eaca3fdaa7b4406006c44dad
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>使用 ShouldSerialize 和 Reset 方法定义默认值
`ShouldSerialize` 和`Reset`是为属性，可以提供的可选方法，如果相应属性不具有简单的默认值。 如果该属性具有简单的默认值，则应对应用<xref:System.ComponentModel.DefaultValueAttribute>并改为提供给特性类构造函数的默认值。 这些机制任一启用了设计器中的以下功能：  
  
-   如果它进行修改得到了其默认值，该属性提供属性浏览器中的视觉指示。  
  
-   用户可以在属性上右键单击并选择**重置**将该属性还原为其默认值。  
  
-   该设计器生成更高效的代码。  
  
    > [!NOTE]
    >  可以应用<xref:System.ComponentModel.DefaultValueAttribute>或提供`Reset` *PropertyName*和`ShouldSerialize` *PropertyName*方法。 不要使用两者。  
  
 `Reset` *PropertyName*方法为其默认值，设置一个属性，如下面的代码段中所示。  
  
```vb  
Public Sub ResetMyFont()  
   MyFont = Nothing  
End Sub  
```  
  
```csharp  
public void ResetMyFont() {  
   MyFont = null;  
}  
```  
  
> [!NOTE]
>  如果属性不具有`Reset`方法，未标记为<xref:System.ComponentModel.DefaultValueAttribute>，并且没有默认值在其声明中，提供`Reset`选项在快捷菜单的情况下禁用该属性对**属性**的 Visual Studio 中的 Windows 窗体设计器窗口。  
  
 例如，Visual Studio 设计器都使用`ShouldSerialize` *PropertyName*更改方法可检查属性是否已从其默认值以及到窗体仅当属性编写代码，从而允许更高效的代码生成。 例如：  
  
```vb  
'Returns true if the font has changed; otherwise, returns false.  
' The designer writes code to the form only if true is returned.  
Public Function ShouldSerializeMyFont() As Boolean  
   Return Not (thefont Is Nothing)  
End Function  
```  
  
```csharp  
// Returns true if the font has changed; otherwise, returns false.  
// The designer writes code to the form only if true is returned.  
public bool ShouldSerializeMyFont() {  
   return thefont != null;  
}  
```  
  
 以下是一个完整的代码示例。  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class MyControl  
   Inherits Control  
  
   ' Declare an instance of the Font class  
   ' and set its default value to Nothing.  
   Private thefont As Font = Nothing  
  
   ' The MyFont property.   
   Public Property MyFont() As Font  
      ' Note that the Font property never  
      ' returns null.  
      Get  
         If Not (thefont Is Nothing) Then  
            Return thefont  
         End If  
         If Not (Parent Is Nothing) Then  
            Return Parent.Font  
         End If  
         Return Control.DefaultFont  
      End Get  
      Set  
         thefont = value  
      End Set  
   End Property  
  
   Public Function ShouldSerializeMyFont() As Boolean  
      Return Not (thefont Is Nothing)  
   End Function  
  
   Public Sub ResetMyFont()  
      MyFont = Nothing  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class MyControl : Control {  
   // Declare an instance of the Font class  
   // and set its default value to null.  
   private Font thefont = null;  
  
   // The MyFont property.      
   public Font MyFont {  
      // Note that the MyFont property never  
      // returns null.  
      get {  
         if (thefont != null) return thefont;  
         if (Parent != null) return Parent.Font;  
         return Control.DefaultFont;  
      }  
      set {  
         thefont = value;  
      }  
   }  
  
   public bool ShouldSerializeMyFont() {  
      return thefont != null;  
   }  
  
   public void ResetMyFont() {  
      MyFont = null;  
   }  
}  
```  
  
 在此情况下，访问私有变量的值的情况下，即使`MyFont`属性是`null`，属性浏览器不会显示`null`; 相反，它显示<xref:System.Windows.Forms.Control.Font%2A>父级，如果不是属性`null`，默认值或<xref:System.Windows.Forms.Control.Font%2A>中定义值<xref:System.Windows.Forms.Control>。 因此的默认值为`MyFont`不能只需设置，和一个<xref:System.ComponentModel.DefaultValueAttribute>不能应用于此属性。 相反，`ShouldSerialize`和`Reset`方法必须为实现`MyFont`属性。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体控件中的属性](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [定义属性](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 [属性更改事件](../../../../docs/framework/winforms/controls/property-changed-events.md)
