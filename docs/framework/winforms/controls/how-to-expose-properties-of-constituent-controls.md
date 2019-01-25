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
ms.openlocfilehash: f3ad37032ee2bb85f37a0eb754277cc9bc040a38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532157"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="188d3-102">如何：公开构成控件的属性</span><span class="sxs-lookup"><span data-stu-id="188d3-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="188d3-103">构成复合控件的控件称为*构成控件*。</span><span class="sxs-lookup"><span data-stu-id="188d3-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="188d3-104">这些控件通常被声明为私有的并因此不能由开发人员访问。</span><span class="sxs-lookup"><span data-stu-id="188d3-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="188d3-105">如果你想要使这些控件的属性可供将来的用户，必须向用户公开它们。</span><span class="sxs-lookup"><span data-stu-id="188d3-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="188d3-106">通过在用户控件中，创建属性并使用公开构成控件的属性`get`和`set`该属性的访问器以构成控件的私有属性更改生效。</span><span class="sxs-lookup"><span data-stu-id="188d3-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>  
  
 <span data-ttu-id="188d3-107">有一个用户控件，请考虑使用名为的构成按钮`MyButton`。</span><span class="sxs-lookup"><span data-stu-id="188d3-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="188d3-108">在此示例中，当用户请求`ConstituentButtonBackColor`属性中，存储中的值<xref:System.Windows.Forms.Control.BackColor%2A>属性的`MyButton`传送。</span><span class="sxs-lookup"><span data-stu-id="188d3-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="188d3-109">当用户将分配给此属性的值时，该值将自动传递给<xref:System.Windows.Forms.Control.BackColor%2A>的属性`MyButton`和`set`将会执行代码，更改颜色`MyButton`。</span><span class="sxs-lookup"><span data-stu-id="188d3-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>  
  
 <span data-ttu-id="188d3-110">下面的示例演示如何公开<xref:System.Windows.Forms.Control.BackColor%2A>构成按钮的属性：</span><span class="sxs-lookup"><span data-stu-id="188d3-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>  
  
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
  
### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="188d3-111">若要公开构成控件的属性</span><span class="sxs-lookup"><span data-stu-id="188d3-111">To expose a property of a constituent control</span></span>  
  
1.  <span data-ttu-id="188d3-112">创建你的用户控件的公共属性。</span><span class="sxs-lookup"><span data-stu-id="188d3-112">Create a public property for your user control.</span></span>  
  
2.  <span data-ttu-id="188d3-113">在`get`一部分的属性，编写代码，以检索你想要公开的属性的值。</span><span class="sxs-lookup"><span data-stu-id="188d3-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>  
  
3.  <span data-ttu-id="188d3-114">在`set`一部分的属性，编写代码，将属性的值传递给构成控件的公开的属性。</span><span class="sxs-lookup"><span data-stu-id="188d3-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188d3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="188d3-115">See also</span></span>
- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="188d3-116">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="188d3-116">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
- [<span data-ttu-id="188d3-117">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="188d3-117">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
