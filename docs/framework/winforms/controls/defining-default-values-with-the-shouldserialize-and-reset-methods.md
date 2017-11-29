---
title: "使用 ShouldSerialize 和 Reset 方法定义默认值"
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
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d082b0e3db1e1c115d28446cf515cf6acf60a7d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="c2a79-102">使用 ShouldSerialize 和 Reset 方法定义默认值</span><span class="sxs-lookup"><span data-stu-id="c2a79-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="c2a79-103">`ShouldSerialize`和`Reset`是为属性，可以提供的可选方法，如果相应属性不具有简单的默认值。</span><span class="sxs-lookup"><span data-stu-id="c2a79-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="c2a79-104">如果该属性具有简单的默认值，则应对应用<xref:System.ComponentModel.DefaultValueAttribute>并改为提供给特性类构造函数的默认值。</span><span class="sxs-lookup"><span data-stu-id="c2a79-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="c2a79-105">这些机制任一启用了设计器中的以下功能：</span><span class="sxs-lookup"><span data-stu-id="c2a79-105">Either of these mechanisms enables the following features in the designer:</span></span>  
  
-   <span data-ttu-id="c2a79-106">如果它进行修改得到了其默认值，该属性提供属性浏览器中的视觉指示。</span><span class="sxs-lookup"><span data-stu-id="c2a79-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>  
  
-   <span data-ttu-id="c2a79-107">用户可以在属性上右键单击并选择**重置**将该属性还原为其默认值。</span><span class="sxs-lookup"><span data-stu-id="c2a79-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>  
  
-   <span data-ttu-id="c2a79-108">该设计器生成更高效的代码。</span><span class="sxs-lookup"><span data-stu-id="c2a79-108">The designer generates more efficient code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c2a79-109">可以应用<xref:System.ComponentModel.DefaultValueAttribute>或提供`Reset` *PropertyName*和`ShouldSerialize` *PropertyName*方法。</span><span class="sxs-lookup"><span data-stu-id="c2a79-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="c2a79-110">不要使用两者。</span><span class="sxs-lookup"><span data-stu-id="c2a79-110">Do not use both.</span></span>  
  
 <span data-ttu-id="c2a79-111">`Reset` *PropertyName*方法为其默认值，设置一个属性，如下面的代码段中所示。</span><span class="sxs-lookup"><span data-stu-id="c2a79-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>  
  
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
>  <span data-ttu-id="c2a79-112">如果属性不具有`Reset`方法，未标记为<xref:System.ComponentModel.DefaultValueAttribute>，并且没有默认值在其声明中，提供`Reset`选项在快捷菜单的情况下禁用该属性对**属性**窗口中的 Windows 窗体设计器[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c2a79-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="c2a79-113">设计器，如[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]使用`ShouldSerialize` *PropertyName*更改，从而允许更高效的方法来检查属性是否已从其默认值和写入到窗体仅当属性的代码代码生成。</span><span class="sxs-lookup"><span data-stu-id="c2a79-113">Designers such as [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="c2a79-114">例如: </span><span class="sxs-lookup"><span data-stu-id="c2a79-114">For example:</span></span>  
  
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
  
 <span data-ttu-id="c2a79-115">以下是一个完整的代码示例。</span><span class="sxs-lookup"><span data-stu-id="c2a79-115">A complete code example follows.</span></span>  
  
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
  
 <span data-ttu-id="c2a79-116">在此情况下，访问私有变量的值的情况下，即使`MyFont`属性是`null`，属性浏览器不会显示`null`; 相反，它显示<xref:System.Windows.Forms.Control.Font%2A>父级，如果不是属性`null`，默认值或<xref:System.Windows.Forms.Control.Font%2A>中定义值<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="c2a79-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="c2a79-117">因此的默认值为`MyFont`不能只需设置，和一个<xref:System.ComponentModel.DefaultValueAttribute>不能应用于此属性。</span><span class="sxs-lookup"><span data-stu-id="c2a79-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="c2a79-118">相反，`ShouldSerialize`和`Reset`方法必须为实现`MyFont`属性。</span><span class="sxs-lookup"><span data-stu-id="c2a79-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a79-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2a79-119">See Also</span></span>  
 [<span data-ttu-id="c2a79-120">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="c2a79-120">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [<span data-ttu-id="c2a79-121">定义属性</span><span class="sxs-lookup"><span data-stu-id="c2a79-121">Defining a Property</span></span>](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 [<span data-ttu-id="c2a79-122">属性更改事件</span><span class="sxs-lookup"><span data-stu-id="c2a79-122">Property-Changed Events</span></span>](../../../../docs/framework/winforms/controls/property-changed-events.md)
