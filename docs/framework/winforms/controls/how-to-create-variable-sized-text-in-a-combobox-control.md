---
title: 如何：在 ComboBox 控件中创建大小可变的文本
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
ms.openlocfilehash: 7c0dc40f6cac0af1f88e72089865caa3a17fcf2a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914749"
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a><span data-ttu-id="ee27d-102">如何：在 ComboBox 控件中创建大小可变的文本</span><span class="sxs-lookup"><span data-stu-id="ee27d-102">How to: Create Variable Sized Text in a ComboBox Control</span></span>
<span data-ttu-id="ee27d-103">此示例演示如何自定义<xref:System.Windows.Forms.ComboBox>控件中的文本绘制。</span><span class="sxs-lookup"><span data-stu-id="ee27d-103">This example demonstrates custom drawing of text in a <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="ee27d-104">当某个项满足某个条件时, 它将以较大的字体绘制, 并处于红色状态。</span><span class="sxs-lookup"><span data-stu-id="ee27d-104">When an item meets a certain criteria, it is drawn in a larger font and turned red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee27d-105">示例</span><span class="sxs-lookup"><span data-stu-id="ee27d-105">Example</span></span>  
  
```vb  
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
    Dim siText As SizeF  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _  
lFont)  
    Else  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)  
    End If  
  
    e.ItemHeight = siText.Height  
    e.ItemWidth = siText.Width  
End Sub  
  
Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem  
    Dim g As Graphics = e.Graphics  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _  
e.Bounds.X, e.Bounds.Y)  
    Else  
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)  
    End If  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ee27d-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="ee27d-106">Compiling the Code</span></span>  
 <span data-ttu-id="ee27d-107">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="ee27d-107">This example requires:</span></span>  
  
- <span data-ttu-id="ee27d-108">Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="ee27d-108">A Windows form.</span></span>  
  
- <span data-ttu-id="ee27d-109">一个<xref:System.Windows.Forms.ComboBox>名为`ListBox1`的控件<xref:System.Windows.Forms.ComboBox.Items%2A> , 其属性中包含三项。</span><span class="sxs-lookup"><span data-stu-id="ee27d-109">A <xref:System.Windows.Forms.ComboBox> control named `ListBox1` with three items in the <xref:System.Windows.Forms.ComboBox.Items%2A> property.</span></span> <span data-ttu-id="ee27d-110">在此示例中, 三个项的`"One", Two", and Three"`名称为。</span><span class="sxs-lookup"><span data-stu-id="ee27d-110">In this example, the three items are named `"One", Two", and Three"`.</span></span> <span data-ttu-id="ee27d-111"><xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>的<xref:System.Windows.Forms.ComboBox.DrawMode%2A> 属性`ComboBox1`必须设置为。</span><span class="sxs-lookup"><span data-stu-id="ee27d-111">The <xref:System.Windows.Forms.ComboBox.DrawMode%2A> property of `ComboBox1` must be set to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ee27d-112">此方法也适用于<xref:System.Windows.Forms.ListBox>控件, 可以将<xref:System.Windows.Forms.ListBox>替换为<xref:System.Windows.Forms.ComboBox>。</span><span class="sxs-lookup"><span data-stu-id="ee27d-112">This technique is also applicable to the <xref:System.Windows.Forms.ListBox> control — you can substitute a <xref:System.Windows.Forms.ListBox> for the <xref:System.Windows.Forms.ComboBox>.</span></span>  
  
- <span data-ttu-id="ee27d-113">对 <xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Drawing?displayProperty=nameWithType> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="ee27d-113">References to the <xref:System.Windows.Forms?displayProperty=nameWithType> and <xref:System.Drawing?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee27d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee27d-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox.DrawItem>
- <xref:System.Windows.Forms.DrawItemEventArgs>
- <xref:System.Windows.Forms.ComboBox.MeasureItem>
- [<span data-ttu-id="ee27d-115">具有内置所有者描述支持的控件</span><span class="sxs-lookup"><span data-stu-id="ee27d-115">Controls with Built-In Owner-Drawing Support</span></span>](controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="ee27d-116">ListBox 控件</span><span class="sxs-lookup"><span data-stu-id="ee27d-116">ListBox Control</span></span>](listbox-control-windows-forms.md)
- [<span data-ttu-id="ee27d-117">ComboBox 控件</span><span class="sxs-lookup"><span data-stu-id="ee27d-117">ComboBox Control</span></span>](combobox-control-windows-forms.md)
