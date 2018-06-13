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
ms.locfileid: "33532628"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="feaf5-102">如何：公开构成控件的属性</span><span class="sxs-lookup"><span data-stu-id="feaf5-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="feaf5-103">构成复合控件的控件称为*构成控件*。</span><span class="sxs-lookup"><span data-stu-id="feaf5-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="feaf5-104">这些控件通常被声明为私有的并因此不能由开发人员访问。</span><span class="sxs-lookup"><span data-stu-id="feaf5-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="feaf5-105">如果你想要使这些控件的属性适用于未来的用户，必须将它们公开给用户。</span><span class="sxs-lookup"><span data-stu-id="feaf5-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="feaf5-106">通过在用户控件中，创建的属性并使用公开构成控件的属性`get`和`set`访问器的该属性以影响构成控件的私有属性中更改。</span><span class="sxs-lookup"><span data-stu-id="feaf5-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>  
  
 <span data-ttu-id="feaf5-107">假设用户控件，请考虑与名为构成按钮`MyButton`。</span><span class="sxs-lookup"><span data-stu-id="feaf5-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="feaf5-108">在此示例中，当用户请求`ConstituentButtonBackColor`属性、 中存储的值<xref:System.Windows.Forms.Control.BackColor%2A>属性`MyButton`传递。</span><span class="sxs-lookup"><span data-stu-id="feaf5-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="feaf5-109">当用户将分配给此属性的一个值时，该值将自动传递给<xref:System.Windows.Forms.Control.BackColor%2A>属性`MyButton`和`set`的代码将执行更改的颜色`MyButton`。</span><span class="sxs-lookup"><span data-stu-id="feaf5-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>  
  
 <span data-ttu-id="feaf5-110">下面的示例演示如何公开<xref:System.Windows.Forms.Control.BackColor%2A>构成按钮属性：</span><span class="sxs-lookup"><span data-stu-id="feaf5-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>  
  
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
  
### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="feaf5-111">若要公开构成控件的属性</span><span class="sxs-lookup"><span data-stu-id="feaf5-111">To expose a property of a constituent control</span></span>  
  
1.  <span data-ttu-id="feaf5-112">创建你的用户控件的公共属性。</span><span class="sxs-lookup"><span data-stu-id="feaf5-112">Create a public property for your user control.</span></span>  
  
2.  <span data-ttu-id="feaf5-113">在`get`一部分的属性，编写代码，以检索要公开的属性值。</span><span class="sxs-lookup"><span data-stu-id="feaf5-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>  
  
3.  <span data-ttu-id="feaf5-114">在`set`一部分的属性，将属性的值传递给构成控件的公开的属性编写代码。</span><span class="sxs-lookup"><span data-stu-id="feaf5-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feaf5-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="feaf5-115">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 [<span data-ttu-id="feaf5-116">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="feaf5-116">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [<span data-ttu-id="feaf5-117">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="feaf5-117">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
