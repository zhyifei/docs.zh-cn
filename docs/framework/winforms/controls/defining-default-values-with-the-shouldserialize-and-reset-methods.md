---
title: 使用 ShouldSerialize 和 Reset 方法定义默认值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: 609fe4896a2b01b8a69ff8a3d0854c85ddbd6a26
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969094"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="67af2-102">使用 ShouldSerialize 和 Reset 方法定义默认值</span><span class="sxs-lookup"><span data-stu-id="67af2-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="67af2-103">`ShouldSerialize`和`Reset`是可为属性提供的可选方法 (如果该属性不具有简单的默认值)。</span><span class="sxs-lookup"><span data-stu-id="67af2-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="67af2-104">如果属性具有简单的默认值, 则应应用<xref:System.ComponentModel.DefaultValueAttribute> , 并改为向特性类构造函数提供默认值。</span><span class="sxs-lookup"><span data-stu-id="67af2-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="67af2-105">其中任何一个机制都会在设计器中启用以下功能:</span><span class="sxs-lookup"><span data-stu-id="67af2-105">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="67af2-106">如果属性已从其默认值中修改, 则属性在属性浏览器中提供可视指示。</span><span class="sxs-lookup"><span data-stu-id="67af2-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="67af2-107">用户可以右键单击属性, 然后选择 "**重置**" 将属性还原为其默认值。</span><span class="sxs-lookup"><span data-stu-id="67af2-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="67af2-108">设计器生成更高效的代码。</span><span class="sxs-lookup"><span data-stu-id="67af2-108">The designer generates more efficient code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="67af2-109"><xref:System.ComponentModel.DefaultValueAttribute>应用或`Reset`提供*propertyname* 和`ShouldSerialize` *propertyname*方法。</span><span class="sxs-lookup"><span data-stu-id="67af2-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="67af2-110">请勿同时使用这两种方法。</span><span class="sxs-lookup"><span data-stu-id="67af2-110">Do not use both.</span></span>

 <span data-ttu-id="67af2-111">PropertyName 方法将属性设置为其默认值, 如下面的代码段所示。 `Reset`</span><span class="sxs-lookup"><span data-stu-id="67af2-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

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
> <span data-ttu-id="67af2-112">如果属性`Reset`没有方法, 则不会标记<xref:System.ComponentModel.DefaultValueAttribute>为, 且在其声明中未提供默认值, 则会在的 "**属性**" 窗口的快捷菜单中禁用该属性的`Reset`选项。Visual Studio 中的 Windows 窗体设计器。</span><span class="sxs-lookup"><span data-stu-id="67af2-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="67af2-113">Visual Studio 等设计器使用`ShouldSerialize` *PropertyName*方法来检查属性是否已从其默认值更改并仅在属性发生更改时将代码写入窗体中, 从而允许更高效地生成代码。</span><span class="sxs-lookup"><span data-stu-id="67af2-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="67af2-114">例如：</span><span class="sxs-lookup"><span data-stu-id="67af2-114">For example:</span></span>

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

 <span data-ttu-id="67af2-115">下面是完整的代码示例。</span><span class="sxs-lookup"><span data-stu-id="67af2-115">A complete code example follows.</span></span>

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

 <span data-ttu-id="67af2-116">在这种`MyFont`情况下, 即使属性访问的私有变量的值为`null`, 也不会显示`null`属性浏览器; 相反, 它会显示<xref:System.Windows.Forms.Control.Font%2A>父级的属性 (如果没有`null`)。或在中<xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control>定义的默认值。</span><span class="sxs-lookup"><span data-stu-id="67af2-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="67af2-117">因此, 的默认值`MyFont`不能简单地设置, <xref:System.ComponentModel.DefaultValueAttribute>并且不能应用于此属性。</span><span class="sxs-lookup"><span data-stu-id="67af2-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="67af2-118">相反, `ShouldSerialize` `Reset` 必须为属性实现和方法。`MyFont`</span><span class="sxs-lookup"><span data-stu-id="67af2-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="67af2-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="67af2-119">See also</span></span>

- [<span data-ttu-id="67af2-120">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="67af2-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="67af2-121">定义属性</span><span class="sxs-lookup"><span data-stu-id="67af2-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="67af2-122">属性更改事件</span><span class="sxs-lookup"><span data-stu-id="67af2-122">Property-Changed Events</span></span>](property-changed-events.md)
